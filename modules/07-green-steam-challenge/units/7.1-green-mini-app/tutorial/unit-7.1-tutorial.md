# Tutorial: Unit 7.1 — Build a Sustainability Mini‑App

**Module:** 07 — Green STEAM Challenge  
**Unit:** 7.1 — Sustainability Mini‑App  
**Estimated Time:** 2–4 lessons (90–180 minutes)  
**Prerequisites:** HTML structure (Module 1–2), CSS layout (Module 3), JavaScript & DOM (Module 4), Optional: Canvas/Data Viz (Modules 5–6)  
**Focus:** Purpose-driven web application aligned with a specific UN Sustainable Development Goal (SDG) or local sustainability challenge.

---

## 1. Unit Overview

In this unit you will design and implement a _small_, _impactful_ web application that encourages awareness or behavior change related to sustainability (e.g., tracking green actions, comparing energy usage, presenting eco tips). You will:

1. Define a **scope** so small it can realistically be finished (MVP mindset).
2. Map a **clear user flow** (e.g., “Add action → View total points → Reset”).
3. Build a semantic, accessible interface using only HTML/CSS/JS.
4. Persist minimal state using `localStorage` (with transparency about what is stored and how to reset/export).
5. Communicate impact honestly with simple metrics or narrative.

---

## 2. Learning Outcomes

By the end of this unit you will be able to:

- Plan and implement a focused sustainability mini‑app using iterative design.
- Translate a user story into semantic HTML structure and minimal JavaScript logic.
- Persist simple state responsibly with `localStorage` and explain privacy trade‑offs.
- Provide accessible interactions (keyboard, labels, focus styles, clear copy).
- Communicate sustainability impact with simple metrics or explanatory text.
- Reflect on design limitations and ethical considerations.

---

## 3. Choosing a Sustainability Focus

Pick **one narrow use case**. Examples:

- Track daily “green actions” (reuse bottle, bike commute, reduce meat).
- Compare estimated CO₂ impact between two choices (dishwasher vs. hand wash scenario).
- Library of eco tips with bookmarking/favorites.
- Simple water usage tally (shower minutes → approximate liters).

**Checklist for a good scope:**

- [ ] One primary user goal (e.g., “See daily action total”).
- [ ] ≤ 3 core interactions (add, view, reset/export).
- [ ] Data set is tiny (local array, not huge dataset).
- [ ] Achievable UI components (buttons, list, maybe form).

**SDG Mapping Prompt:**
Write one sentence: _“This app supports SDG **\_ by helping users ****\_\_\_\_******.”_

---

## 4. Defining the User Story & Acceptance Criteria

**User Story Template:**
“As a [type of user], I want to [action] so that I can [goal/benefit].”

**Example:** “As a student, I want to log small eco‑friendly actions so I can stay motivated and see my cumulative impact.”

**Acceptance Criteria Example (Green Actions Tracker):**

- User can add predefined actions with a single click.
- App displays total points and count of actions.
- User can add a custom action with name + points.
- State persists on refresh via `localStorage`.
- User can reset data (with confirmation).
- Plain explanation of what is stored and how to delete it.
- Accessible: keyboard focus, aria labels, color contrast.

---

## 5. Wireframing (Low‑Fidelity Planning)

Sketch in text or paper:

```
+--------------------------------------------------+
|  Title: Green Action Tracker                      |
|  Intro paragraph (purpose + SDG mapping)          |
|  [Points Total: 45] [Actions Logged: 7]           |
|                                                  |
|  Quick Actions:                                   |
|  [Reuse Bottle (+5)] [Bike Commute (+8)]          |
|  [Vegetarian Meal (+6)] [LED Lights Off (+3)]     |
|                                                  |
|  Custom Action: [Name____] [Points__] [Add]       |
|                                                  |
|  Logged Actions (list):                           |
|   - Bike Commute (8) [Delete]                     |
|   - ...                                           |
|                                                  |
|  [Export JSON] [Reset Data]                       |
|  Data Explanation (privacy & impact notes)        |
+--------------------------------------------------+
```

---

## 6. HTML Skeleton (Semantic Structure)

Create a base HTML file (e.g., `green-mini-app.html`).

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Green Action Tracker</title>
    <style>
      :root {
        --bg: #f5f7f9;
        --card: #ffffff;
        --accent: #1b7f5f;
        --accent-alt: #0d4b37;
        --danger: #b33030;
        --text: #222;
        --focus: #ffcc33;
      }
      body {
        font-family: system-ui, Arial, sans-serif;
        margin: 0;
        background: var(--bg);
        color: var(--text);
      }
      header,
      main {
        max-width: 840px;
        margin: 0 auto;
        padding: 1.5rem;
      }
      header h1 {
        margin: 0 0 0.5rem;
      }
      .metrics {
        display: flex;
        gap: 1rem;
        flex-wrap: wrap;
        margin: 1rem 0;
      }
      .metric {
        background: var(--card);
        padding: 0.75rem 1rem;
        border-radius: 0.5rem;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.06);
      }
      .actions-panel {
        background: var(--card);
        padding: 1rem;
        border-radius: 0.75rem;
        margin-bottom: 1rem;
      }
      button {
        cursor: pointer;
        font: inherit;
        border-radius: 0.5rem;
        border: none;
        padding: 0.6rem 0.9rem;
        background: var(--accent);
        color: #fff;
      }
      button:hover {
        background: var(--accent-alt);
      }
      button:focus {
        outline: 3px solid var(--focus);
        outline-offset: 2px;
      }
      .quick-actions button {
        margin: 0.25rem 0.25rem 0.25rem 0;
      }
      form.custom-action {
        display: flex;
        gap: 0.5rem;
        flex-wrap: wrap;
        margin-top: 0.75rem;
      }
      form.custom-action input {
        padding: 0.5rem;
        border: 1px solid #ccc;
        border-radius: 0.4rem;
        font: inherit;
      }
      ul#log {
        list-style: none;
        padding: 0;
        margin: 0;
      }
      ul#log li {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0.5rem 0.75rem;
        background: var(--card);
        margin-bottom: 0.5rem;
        border-radius: 0.5rem;
        box-shadow: 0 1px 4px rgba(0, 0, 0, 0.04);
      }
      .danger {
        background: var(--danger);
      }
      .danger:hover {
        background: #8d2424;
      }
      .utilities {
        display: flex;
        flex-wrap: wrap;
        gap: 0.75rem;
        margin: 1rem 0;
      }
      textarea#export {
        width: 100%;
        min-height: 140px;
        font: inherit;
        padding: 0.75rem;
        border: 1px solid #ccc;
        border-radius: 0.5rem;
      }
      @media (max-width: 600px) {
        .metrics {
          flex-direction: column;
        }
      }
    </style>
  </head>
  <body>
    <header>
      <h1>Green Action Tracker</h1>
      <p id="intro">
        Track small daily eco‑actions and see cumulative impact. Supports SDG 13
        (Climate Action).
      </p>
    </header>
    <main>
      <section class="metrics" aria-label="Current totals">
        <div class="metric" id="total-points" role="status" aria-live="polite">
          Total Points: 0
        </div>
        <div class="metric" id="total-actions" role="status" aria-live="polite">
          Actions Logged: 0
        </div>
      </section>

      <section class="actions-panel" aria-labelledby="quick-actions-heading">
        <h2 id="quick-actions-heading">Quick Actions</h2>
        <div class="quick-actions" id="quick-actions"></div>
        <form
          class="custom-action"
          id="custom-form"
          aria-describedby="custom-desc"
        >
          <label for="custom-name" class="vis">Action Name</label>
          <input
            id="custom-name"
            name="name"
            type="text"
            placeholder="Custom action"
            required
          />
          <label for="custom-points" class="vis">Points</label>
          <input
            id="custom-points"
            name="points"
            type="number"
            min="1"
            max="100"
            placeholder="Pts"
            required
          />
          <button type="submit">Add Action</button>
        </form>
        <p id="custom-desc" style="font-size:.85rem;">
          Add a custom action with a simple point value (approximate impact).
          Keep values modest.
        </p>
      </section>

      <section aria-labelledby="log-heading">
        <h2 id="log-heading">Logged Actions</h2>
        <ul id="log"></ul>
      </section>

      <section aria-labelledby="data-tools-heading">
        <h2 id="data-tools-heading">Data Tools & Privacy</h2>
        <div class="utilities">
          <button id="export-btn">Export JSON</button>
          <button id="reset-btn" class="danger">Reset Data</button>
        </div>
        <textarea
          id="export"
          aria-label="Exported JSON"
          placeholder="Exported data will appear here."
        ></textarea>
        <details>
          <summary>What data is stored?</summary>
          <p>
            We store: actions array (name, points, timestamp) + totals. All
            stored locally in your browser via <code>localStorage</code>; no
            server upload. Use Reset or manually clear browser storage to
            delete.
          </p>
        </details>
      </section>
    </main>
    <script src="app.js" defer></script>
  </body>
</html>
```

**Accessibility Notes:**

- `aria-live="polite"` for dynamic totals.
- Clear headings (`h2`) for sections.
- `details/summary` to explain privacy.
- Focus styles for keyboard users.

Add a visually-hidden class if needed:

```css
.vis {
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  overflow: hidden;
}
```

---

## 7. JavaScript: State Model & Persistence (app.js)

Design a minimal state shape:

```javascript
// Application state
const state = {
  actions: [], // { id, name, points, ts }
  totals: { points: 0, count: 0 },
};

const STORAGE_KEY = "green-actions-v1";
```

### Loading & Saving

```javascript
function loadState() {
  const raw = localStorage.getItem(STORAGE_KEY);
  if (!raw) return;
  try {
    const parsed = JSON.parse(raw);
    if (parsed && Array.isArray(parsed.actions)) {
      state.actions = parsed.actions;
      state.totals = parsed.totals || {
        points: 0,
        count: parsed.actions.length,
      };
    }
  } catch (e) {
    console.warn("Failed to parse saved data", e);
  }
}

function saveState() {
  localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
}
```

### Predefined Quick Actions

```javascript
const QUICK_ACTIONS = [
  { name: "Reuse Bottle", points: 5 },
  { name: "Bike Commute", points: 8 },
  { name: "Vegetarian Meal", points: 6 },
  { name: "Lights Off (LED)", points: 3 },
];
```

### DOM References

```javascript
const quickActionsContainer = document.getElementById("quick-actions");
const logList = document.getElementById("log");
const totalPointsEl = document.getElementById("total-points");
const totalActionsEl = document.getElementById("total-actions");
const form = document.getElementById("custom-form");
const exportBtn = document.getElementById("export-btn");
const resetBtn = document.getElementById("reset-btn");
const exportArea = document.getElementById("export");
```

### Rendering Functions

```javascript
function updateTotals() {
  state.totals.points = state.actions.reduce((acc, a) => acc + a.points, 0);
  state.totals.count = state.actions.length;
  totalPointsEl.textContent = `Total Points: ${state.totals.points}`;
  totalActionsEl.textContent = `Actions Logged: ${state.totals.count}`;
}

function renderLog() {
  logList.innerHTML = "";
  state.actions
    .slice()
    .reverse()
    .forEach((action) => {
      const li = document.createElement("li");
      li.innerHTML = `
      <span>${action.name} (${action.points})</span>
      <button aria-label="Delete ${action.name}" data-id="${action.id}" class="danger">Delete</button>
    `;
      logList.appendChild(li);
    });
}

function renderQuickActions() {
  quickActionsContainer.innerHTML = "";
  QUICK_ACTIONS.forEach((a) => {
    const btn = document.createElement("button");
    btn.type = "button";
    btn.textContent = `${a.name} (+${a.points})`;
    btn.addEventListener("click", () => addAction(a.name, a.points));
    quickActionsContainer.appendChild(btn);
  });
}
```

### Action Operations

```javascript
function addAction(name, points) {
  const action = {
    id: crypto.randomUUID ? crypto.randomUUID() : Date.now().toString(),
    name: sanitize(name),
    points: Number(points) || 0,
    ts: Date.now(),
  };
  state.actions.push(action);
  saveAndRender();
}

function deleteAction(id) {
  state.actions = state.actions.filter((a) => a.id !== id);
  saveAndRender();
}
```

### Sanitization (Basic)

```javascript
function sanitize(str) {
  return str.replace(/[<>]/g, ""); // minimal XSS mitigation
}
```

### Composite Render

```javascript
function saveAndRender() {
  saveState();
  updateTotals();
  renderLog();
}
```

### Event Listeners

```javascript
form.addEventListener("submit", (e) => {
  e.preventDefault();
  const name = form.elements["name"].value.trim();
  const pts = form.elements["points"].value.trim();
  if (!name || !pts) return;
  addAction(name, pts);
  form.reset();
  form.elements["name"].focus();
});

logList.addEventListener("click", (e) => {
  const btn = e.target.closest("button[data-id]");
  if (!btn) return;
  if (confirm("Delete this action?")) {
    deleteAction(btn.dataset.id);
  }
});

exportBtn.addEventListener("click", () => {
  exportArea.value = JSON.stringify(state, null, 2);
  exportArea.focus();
});

resetBtn.addEventListener("click", () => {
  if (confirm("Reset ALL stored data? This cannot be undone.")) {
    localStorage.removeItem(STORAGE_KEY);
    state.actions = [];
    saveAndRender();
    exportArea.value = "";
  }
});
```

### Initialization

```javascript
function init() {
  loadState();
  renderQuickActions();
  updateTotals();
  renderLog();
}
init();
```

---

## 8. Privacy & Ethical Considerations

Even local apps collect data. You must:

- Explain **what** is stored (list of actions, timestamps) and **where** (localStorage only).
- Provide **Reset/Export** controls (user agency).
- Avoid sensitive personal data (keep categories generic: “Bike Commute” not GPS trail).
- Encourage honest scoring (points approximate impact, not exact carbon accounting).

**Add an ethics section:**

```html
<details>
  <summary>Impact & Limitations</summary>
  <p>
    Point values are rough estimates intended to motivate, not precise carbon
    calculations. This app does not store or transmit personal identity data.
    Reset at any time.
  </p>
</details>
```

---

## 9. Accessibility Checklist

| Feature             | Implementation                                              |
| ------------------- | ----------------------------------------------------------- |
| Keyboard navigation | Native buttons + focus styles                               |
| Focus indication    | CSS outline on `button:focus`                               |
| Semantic regions    | Headings (`h1`, `h2`), sections with labels                 |
| Live updates        | `aria-live` metrics for totals                              |
| Clear language      | Plain descriptions, minimal jargon                          |
| Color contrast      | Dark text on light background; test with a contrast checker |
| Motion/Flash        | No rapid flashing; limited dynamic changes                  |

Add manual testing steps: use `Tab` key to reach all controls; test screen reader (if possible) reading totals.

---

## 10. Communicating Impact (Metrics/Narrative)

**Avoid misleading representation.** Provide a short textual explanation:
“Each action adds a small encouragement point. Scores help visualize consistent habits rather than exact CO₂ measurements.”

Optional: Provide _context multipliers_ (e.g., show weekly totals = `points * 7` approximation) with disclaimers.

---

## 11. Testing & Validation

**Functional Tests:**

1. Add each quick action; totals increment correctly.
2. Add custom action with boundary values (min points 1, max points 100). Reject invalid.
3. Refresh page; data persists.
4. Delete an action; totals recalculate.
5. Export JSON; contains actions array.
6. Reset; storage cleared, UI resets.

**Edge Cases:**

- Empty export area after reset.
- Large number of actions (performance still fine).
- Non-numeric input (should be prevented by input `type='number'`).

**Manual Privacy Check:** Confirm that only one key (`green-actions-v1`) appears in DevTools > Application > Local Storage.

---

## 12. Refactoring Ideas (Optional)

- Separate rendering logic into dedicated functions (SRP).
- Introduce a simple controller pattern: `actionsService` for state operations.
- Add filtering (e.g., show actions ≥ certain points).
- Implement pagination or compression if list grows large.

---

## 13. Enhancements & Extensions

| Enhancement     | Description                                                                |
| --------------- | -------------------------------------------------------------------------- |
| Weekly Snapshot | Store weekly totals history for trend chart (requires Module 05 concepts). |
| Tagging         | Add categories (transport, food, energy) and filter.                       |
| Data Viz        | Simple canvas bar chart of daily action counts (reuse scaling logic).      |
| Sharing         | Generate shareable summary text (avoid auto‑posting).                      |
| Goals           | Allow user to set a weekly points goal; progress indicator.                |

Ensure added complexity does not compromise accessibility or clarity.

---

## 14. Performance Considerations

This app is small; still, reinforce good habits:

- Avoid unnecessary DOM reflows (batch render after changes).
- Use `innerHTML = ''` then append in loops versus repeated removals.
- Keep localStorage writes minimal (write only after changes, not every render call separately).

---

## 15. Reflection Prompts

After implementation answer:

1. What specific sustainability behavior does your app encourage?
2. Why is the scope appropriate for a mini‑project?
3. How did you ensure transparency about storage & privacy?
4. What design choices improved accessibility?
5. How could the app mislead users if expanded improperly?
6. One enhancement you would add with more time and why.

---

## 16. Common Pitfalls & Fixes

| Pitfall             | Cause                          | Fix                                                                |
| ------------------- | ------------------------------ | ------------------------------------------------------------------ |
| Data not persisting | Missed `saveState()` call      | Call after each mutation                                           |
| Duplicate IDs       | Non‑unique generation          | Use `crypto.randomUUID()` fallback to timestamp                    |
| Negative points     | Missing validation             | `min="1"` attribute + Number check                                 |
| XSS injection       | Raw user input injection       | Basic sanitize + avoid `innerHTML` concatenation with user content |
| No keyboard focus   | Custom styling removed outline | Add explicit focus style                                           |

---

## 17. Code Review Checklist

Before final submission:

- [ ] Functions have single responsibility.
- [ ] Variable names descriptive (`state`, `saveState`, not `s1`).
- [ ] No commented-out large dead blocks.
- [ ] Privacy section present and clear.
- [ ] Reset has confirmation dialog.
- [ ] All main interactions reachable by keyboard.

---

## 18. Minimal Index Variant (Optional Start)

If starting from scratch quickly:

```html
<section>
  <h2>Add</h2>
  <button data-a="Reuse Bottle" data-p="5">Reuse Bottle</button>
</section>
<ul id="list"></ul>
<script>
  const list = document.getElementById("list");
  const key = "mini-app";
  let actions = JSON.parse(localStorage.getItem(key) || "[]");
  function render() {
    list.innerHTML = "";
    actions.forEach((a) => {
      const li = document.createElement("li");
      li.textContent = `${a.name} (${a.points})`;
      list.appendChild(li);
    });
  }
  document.body.addEventListener("click", (e) => {
    if (e.target.matches("button[data-a]")) {
      actions.push({
        name: e.target.dataset.a,
        points: +e.target.dataset.p,
        ts: Date.now(),
      });
      localStorage.setItem(key, JSON.stringify(actions));
      render();
    }
  });
  render();
</script>
```

Then progressively enhance to full version.

---

## 19. Ethical & Impact Communication Tips

Avoid greenwashing: be honest about limitations. Refrain from claiming exact carbon offsets unless using verified data sources. Encourage **habit formation** rather than guilt.

Language examples:

- “Approximate points” vs “Exact CO₂ saved”.
- “Encourages reflection on daily choices” vs “Guarantees carbon reduction”.

---

## 20. Resources & Links

**UN SDGs Overview:** https://sdgs.un.org/goals  
**Web Accessibility Basics:** https://www.w3.org/WAI/fundamentals/  
**localStorage MDN:** https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage  
**Privacy Design:** https://www.dataprivacymanager.net/privacy-by-design-principles/  
**Color Contrast Checker:** https://webaim.org/resources/contrastchecker/

---

## 21. Next Steps After Completion

1. Share a short demo (2–3 min) explaining purpose, flow, impact.
2. Conduct a peer test: ask another student to add an action and export data.
3. Record improvement ideas; plan one extension if time remains.

**Transition to Future Work:** Use concepts here (state, flows, persistence) to build larger multi‑view apps or integrate data visualization (Module 05) for deeper impact metrics.

---

## 22. Final Reflection Template

| Question               | Response |
| ---------------------- | -------- |
| Primary goal clarity   |          |
| User flow simplicity   |          |
| Accessibility features |          |
| Privacy transparency   |          |
| Potential misuse risks |          |
| Enhancement idea       |          |

---

**End of Tutorial: Unit 7.1 — Sustainability Mini‑App**
