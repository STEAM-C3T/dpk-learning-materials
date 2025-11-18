---
marp: true
theme: default
paginate: true
---

<!-- _class: lead -->

# Unit 7.1

## Sustainability Mini‑App

**Module 07: Green STEAM Challenge**

---

## Learning Outcomes

By the end of this unit, you will be able to:

- Build a purpose-driven web application with localStorage
- Implement ethical transparency in UI and data handling
- Create accessible forms and interactive controls
- Design modular JavaScript for state management
- Reflect critically on impact claims and sustainability messaging

---

## Why This Mini‑App?

**Purpose:** Encourage mindful daily sustainability actions

**Core Values:**

- Small & finishable (avoid feature sprawl)
- Honest impact communication (no greenwashing)
- Accessible to all users
- Privacy-respecting (local data only)

**SDG Alignment:** Choose ONE clear link (e.g., SDG 13 Climate Action)

**Success Metric:** Honest impact + Accessible UI + Ethical transparency

---

## User Story & Flow

**User Story Template:**

> "As a [person type] I want [goal] so that [impact]."

**Example:**

> "As a student, I want to track my sustainable actions so that I can build habits and see my progress."

**Core Flow (≤4 steps):**

1. Add an action (quick button or custom input)
2. See totals update instantly
3. Review list / delete mistakes
4. Reflect, export, or reset

---

## Semantic HTML Skeleton

**Key Landmarks:**

```html
<header>
  <h1>Green Tracker</h1>
</header>
<main>
  <section id="metrics"><!-- Totals display --></section>
  <section id="quick-actions"><!-- Quick add buttons --></section>
  <section id="custom-entry"><!-- Custom form --></section>
  <section id="action-log"><!-- List of actions --></section>
</main>
```

**Why Semantic?**

- Improves screen reader navigation
- Enhances maintainability
- Provides clear document structure

---

## Privacy & Ethics Disclaimer

**Include early in the UI (use `<details>` for progressive disclosure):**

```html
<details>
  <summary>About This Tracker</summary>
  <p>
    <strong>Privacy:</strong> All data stays in your browser (localStorage).
    Nothing is sent to a server.
  </p>
  <p>
    <strong>Impact:</strong> Points are approximate motivational indicators, not
    precise CO₂ calculations. Use them to encourage habits, not claim exact
    emissions savings.
  </p>
</details>
```

**Key Principles:**

- Clarify data scope (local only)
- Avoid greenwashing
- State limitations clearly

---

## Data & State Model

**State Structure:**

```javascript
const state = {
  actions: [
    // Array of action objects
    { id: 1234567890, name: "Bike to school", points: 5, ts: "2025-01-15" },
  ],
  totals: {
    points: 5,
    count: 1,
  },
};
```

**Key Points:**

- `id`: Unique identifier (timestamp)
- `points`: Motivational indicator (NOT precise CO₂)
- `ts`: Timestamp (date string)
- `totals`: Aggregated values for display

---

## localStorage Basics

**Save Data:**

```javascript
localStorage.setItem("greenTracker", JSON.stringify(state));
```

**Load Data:**

```javascript
const saved = localStorage.getItem("greenTracker");
if (saved) {
  state = JSON.parse(saved);
}
```

**Clear Data:**

```javascript
localStorage.removeItem("greenTracker");
```

**Important:**

- localStorage stores strings only (use JSON)
- Data persists across sessions
- Single key per app simplifies management

---

## Core Functions: Load & Save

**Load State:**

```javascript
function loadState() {
  const saved = localStorage.getItem("greenTracker");
  if (saved) {
    try {
      state = JSON.parse(saved);
    } catch (e) {
      console.error("Failed to parse saved state:", e);
      state = { actions: [], totals: { points: 0, count: 0 } };
    }
  }
}
```

**Save State:**

```javascript
function saveState() {
  localStorage.setItem("greenTracker", JSON.stringify(state));
}
```

**Tip:** Call `saveState()` after every state mutation

---

## Core Functions: Add Action

```javascript
function addAction(name, points) {
  // Sanitize input
  name = sanitize(name);

  // Validate
  if (!name || name.length < 2) {
    alert("Please enter a valid action name.");
    return;
  }

  // Create action object
  const action = {
    id: Date.now(),
    name: name,
    points: parseInt(points) || 1,
    ts: new Date().toISOString().split("T")[0], // YYYY-MM-DD
  };

  // Add to state
  state.actions.push(action);

  // Update totals
  updateTotals();

  // Persist
  saveState();

  // Re-render
  renderLog();
}
```

---

## Core Functions: Delete Action

```javascript
function deleteAction(id) {
  // Filter out action with matching id
  state.actions = state.actions.filter((action) => action.id !== id);

  // Update totals
  updateTotals();

  // Persist
  saveState();

  // Re-render
  renderLog();
}
```

**Key Insight:** Always call `updateTotals()` after mutation to keep aggregates in sync

---

## Core Functions: Update Totals

```javascript
function updateTotals() {
  state.totals.count = state.actions.length;
  state.totals.points = state.actions.reduce(
    (sum, action) => sum + action.points,
    0
  );

  // Update UI
  document.getElementById("total-points").textContent = state.totals.points;
  document.getElementById("total-count").textContent = state.totals.count;
}
```

**Accessibility Tip:** Use `aria-live="polite"` on totals container so screen readers announce updates

---

## Sanitizing Input

**Prevent XSS Injection:**

```javascript
function sanitize(str) {
  const div = document.createElement("div");
  div.textContent = str;
  return div.innerHTML;
}
```

**What This Does:**

- Converts `<script>alert('XSS')</script>` → `&lt;script&gt;...`
- Ensures user input displays as text, not code

**When to Use:** Before adding user input to DOM or state

---

## Rendering the Action Log

```javascript
function renderLog() {
  const logContainer = document.getElementById("action-log");
  logContainer.innerHTML = ""; // Clear

  if (state.actions.length === 0) {
    logContainer.innerHTML = "<p>No actions yet. Add one above!</p>";
    return;
  }

  state.actions.forEach((action) => {
    const item = document.createElement("div");
    item.className = "action-item";
    item.innerHTML = `
      <span><strong>${action.name}</strong> (+${action.points} pts) — ${action.ts}</span>
      <button onclick="deleteAction(${action.id})">Delete</button>
    `;
    logContainer.appendChild(item);
  });
}
```

---

## Quick Action Buttons

**HTML:**

```html
<section id="quick-actions">
  <h2>Quick Actions</h2>
  <button onclick="addAction('Bike to school', 5)">🚲 Bike to school</button>
  <button onclick="addAction('Reusable bottle', 3)">💧 Reusable bottle</button>
  <button onclick="addAction('No food waste', 4)">🍽️ No food waste</button>
</section>
```

**Benefits:**

- Fast entry for common actions
- Reduces friction
- Encourages consistent tracking

**Design Tip:** Limit to 3–5 most common actions

---

## Custom Entry Form

**HTML:**

```html
<form id="custom-form" onsubmit="handleCustomEntry(event)">
  <label for="action-name">Action:</label>
  <input type="text" id="action-name" required />

  <label for="action-points">Points:</label>
  <input type="number" id="action-points" value="1" min="1" max="20" required />

  <button type="submit">Add</button>
</form>
```

**JavaScript:**

```javascript
function handleCustomEntry(event) {
  event.preventDefault();
  const name = document.getElementById("action-name").value;
  const points = document.getElementById("action-points").value;
  addAction(name, points);
  event.target.reset(); // Clear form
}
```

---

## Accessibility Checklist

✅ **Visible focus ring** on all interactive elements

✅ **Proper heading hierarchy** (h1 > h2 > h3)

✅ **Form labels** explicitly tied to inputs (`<label for="...">`)

✅ **aria-live region** for totals updates

✅ **Keyboard navigation:** Tab through add, delete, reset without traps

**Test Strategy:**

- Navigate with Tab key only
- Use screen reader (VoiceOver, NVDA, JAWS)
- Test accessibility mid-build, not last minute

---

## Testing Strategy

**Manual Test Cases:**

- Add quick action → totals increment ✓
- Add custom action → appears in log ✓
- Delete action → totals decrement ✓
- Refresh page → state persists ✓
- Reset button → state clears; disclaimer still visible ✓

**Edge Cases:**

- Empty name input → blocked by validation ✓
- Large number input → clamped by `max` attribute ✓
- Duplicate actions → allowed (each has unique timestamp ID) ✓

---

## Reset Functionality

```javascript
function resetData() {
  if (!confirm("Delete all actions? This cannot be undone.")) {
    return;
  }

  // Clear state
  state = { actions: [], totals: { points: 0, count: 0 } };

  // Clear localStorage
  localStorage.removeItem("greenTracker");

  // Update UI
  updateTotals();
  renderLog();
}
```

**UX Tip:** Use `confirm()` dialog to prevent accidental data loss

---

## Common Pitfalls & Fixes

**Pitfall:** Overclaim impact  
**Fix:** Use cautious language ("approximate," "encouragement points")

**Pitfall:** Feature overload  
**Fix:** Revisit original scope statement; stick to ≤4 core steps

**Pitfall:** Invisible focus style  
**Fix:** Reinstate default `outline` or add custom focus ring

**Pitfall:** Stale totals after delete  
**Fix:** Always call `updateTotals()` after mutation

**Pitfall:** localStorage quota exceeded  
**Fix:** Limit action count or add cleanup for old entries

---

## Ethical Transparency

**Disclaimers Should:**

- Clarify data scope (local only, no server)
- Avoid greenwashing ("approximate" not "exact")
- State limitations (not a real carbon calculator)

**Example:**

> "Data stays in your browser; points motivate habits, not exact emissions."

**Why This Matters:**

- Builds trust
- Prevents misleading claims
- Respects user intelligence

**Design Principle:** Transparency > Exaggeration

---

## Extension Ideas (Pick ONE After Core Complete)

**1. Category Filters:**

- Add `category` field to actions (transport, food, energy)
- Filter log by category

**2. Weekly Goal Progress Bar:**

- Set target points per week
- Visual progress bar

**3. Trend Chart:**

- Reuse Canvas logic from Module 05
- Show points over time

**4. Import/Export Presets:**

- Save common action sets as JSON
- Share with others

**Important:** Impact narrative must evolve with added features

---

## Quality Indicators

✅ **Scope statement** matches final feature set

✅ **Code modular:** Functions short & named clearly

✅ **Disclaimer** specific & honest

✅ **Accessibility** verified via keyboard + screen reader simulation

✅ **Reflection** includes concrete improvement idea

---

## Mini Rubric Snapshot

| Aspect        | Proficient Signal                         |
| ------------- | ----------------------------------------- |
| Scope         | Single focused goal; limited interactions |
| Persistence   | Stable across refresh; reset works        |
| Accessibility | All checklist items met                   |
| Ethics        | Transparent, non-exaggerated claims       |
| Code          | Readable, minimal duplication             |
| Reflection    | Specific learning + next step             |

---

## Reflection Prompts

**Questions to Consider:**

1. Which design decision most improved usability?
2. How might scoring mislead users? What mitigation did you add?
3. What enhancement would improve inclusivity?
4. If scaling to public users, what changes first?

**Document Your Process:**

- Initial scope statement
- Iterations / changes made
- Final reflection

---

## Launch & Share

**Peer Demo (2 min each):**

1. Show core functionality
2. Explain one design decision
3. Demonstrate accessibility feature

**Peer Feedback Format:**

- **Praise:** One thing that works well
- **Question:** One clarifying question
- **Suggest:** One improvement idea

**Capture improvement idea before final submission**

---

## Debugging Tips

**State not persisting?**

- Check browser console for errors
- Verify localStorage key: `localStorage.getItem("greenTracker")`
- Test in private browsing (localStorage enabled?)

**Totals not updating?**

- Log state after mutation: `console.log(state)`
- Ensure `updateTotals()` called after every change

**Delete button not working?**

- Check that `id` is correctly passed to `deleteAction()`
- Verify `onclick` attribute syntax

---

## Code Organization Best Practices

**Modular Functions:**

- One responsibility per function
- Clear names (`addAction`, not `doStuff`)
- Keep functions short (< 20 lines when possible)

**State Management:**

- Single source of truth (`state` object)
- Mutation → Save → Render pattern
- Avoid global variables except for state

**Comments:**

- Explain "why" not "what"
- Document non-obvious logic
- Include TODOs for future enhancements

---

## Performance Considerations

**Avoid:**

- Recreating entire log on every keystroke
- Storing thousands of actions without cleanup
- Unnecessary re-renders

**Optimize:**

- Debounce input events if needed
- Limit action count (e.g., max 100, then archive old)
- Use event delegation for delete buttons

---

## Privacy & Data Ethics

**Questions to Ask:**

- What data am I collecting?
- Where is it stored? (Answer: Browser only)
- Who can access it? (Answer: Only the user)
- Can user delete it? (Answer: Yes, via reset button)

**Best Practices:**

- Never send data to server without explicit consent
- Provide clear reset/delete option
- Use plain language in privacy notices

---

## Key Takeaway

**Small, honest, accessible tools can drive sustained behavior more effectively than complex, overstated platforms.**

**Core Principles:**

- Simplicity over feature creep
- Transparency over exaggeration
- Accessibility for all
- Privacy by default

---

## Next Steps

**In this unit, you learned:**

- localStorage for state persistence
- Modular JavaScript architecture
- Ethical transparency in sustainability apps
- Accessible form design

**Next Module:**

- **Portfolio & Showcase** — Present your work, reflect on learning journey, plan future projects

**Practice:**

- Extend your mini-app with ONE new feature
- Share with peers and gather feedback
- Reflect on impact claims and refine messaging

---

<!-- _class: lead -->

# Questions?

**Let's build sustainable solutions!**

---

## Resources

**Documentation:**

- [MDN: localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
- [MDN: JSON methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)
- [Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/)

**Sustainability:**

- [UN SDG 13: Climate Action](https://sdgs.un.org/goals/goal13)
- [Principles of Green Software](https://principles.green/)

**Tutorial:** Unit 7.1 Tutorial (detailed step-by-step guide)

---

<!-- End of Unit 7.1 Deck -->
