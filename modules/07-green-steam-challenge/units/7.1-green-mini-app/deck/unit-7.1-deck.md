# Unit 7.1 Deck — Sustainability Mini‑App

---

### 1. Why This Mini‑App?

- Purpose: Encourage mindful daily sustainability actions
- Scope: Small, finishable; avoid feature sprawl
- SDG Link: Choose ONE clear alignment (e.g., SDG 13 Climate Action)
- Success = Honest impact + Accessible UI + Ethical transparency

---

### 2. User Story & Flow

User Story Template: "As a (person type) I want (goal) so that (impact)."
Flow Example:

1. Add an action (quick or custom)
2. See totals update instantly
3. Review list / delete mistakes
4. Export or reflect; optionally reset
   Keep ≤4 core steps.

---

### 3. Semantic HTML Skeleton

Key Landmarks: <header>, <main>, sections for metrics & log
Why Semantic? Improves screen reader navigation & maintainability
Include a <details> block for privacy & impact disclaimer early

---

### 4. Data & State Model

State Shape:
{
actions: [ { id, name, points, ts } ],
totals: { points, count }
}
Persistence: localStorage JSON under single key
Points = Motivational indicator (NOT precise CO₂)

---

### 5. Core Functions (Conceptual)

- loadState() / saveState()
- addAction() / deleteAction(id)
- updateTotals()
- renderQuickActions(), renderLog()
- sanitize(input) to prevent injection
  One responsibility per function for clarity.

---

### 6. Accessibility Checklist

- Visible focus ring on all interactive elements
- Proper heading hierarchy (h1 > h2 > h3)
- Form labels explicitly tied to inputs
- aria-live region for totals updates
- Keyboard: Tab through add, delete, reset without traps
  Test accessibility mid‑build, not last minute.

---

### 7. Ethical Transparency

Disclaimers Should:

- Clarify data scope (local only)
- Avoid greenwashing ("approximate encouragement points")
- State limitations (no real carbon calculator)
  Sample: "Data stays in your browser; points motivate habits, not exact emissions."

---

### 8. Testing Strategy

Manual Cases:

- Add quick action → totals increment
- Delete action → totals decrement
- Refresh page → state persists
- Reset → state clears; disclaimer still visible
  Edge Cases:
- Empty name input (block)
- Large number input (clamp or warn)
- Duplicate actions (allowed? clarify)

---

### 9. Reflection Prompts

- Which design decision most improved usability?
- How might scoring mislead users? Mitigation?
- One enhancement for inclusivity?
- If scaling to public users, what changes first?

---

### 10. Common Pitfalls

Pitfall → Fix:

- Overclaim impact → Rephrase with cautious language
- Feature overload → Revisit original scope statement
- Invisible focus style → Reinstate default or custom outline
- Stale totals after delete → Always call updateTotals() after mutation

---

### 11. Extension Ideas

Pick ONE after core complete:

- Category filters (transport / food / energy)
- Weekly goal progress bar
- Simple trend chart (reuse Canvas logic from Module 05)
- Import / export presets JSON
  Impact narrative must evolve with added features.

---

### 12. Quality Indicators

- Scope statement matches final feature set
- Code modular; functions short & named clearly
- Disclaimer specific & honest
- Accessibility verified via keyboard + screen reader simulation
- Reflection includes concrete improvement idea

---

### 13. Mini Rubric Snapshot

| Aspect        | Proficient Signal                         |
| ------------- | ----------------------------------------- |
| Scope         | Single focused goal; limited interactions |
| Persistence   | Stable across refresh; reset works        |
| Accessibility | All checklist items met                   |
| Ethics        | Transparent, non-exaggerated claims       |
| Code          | Readable, minimal duplication             |
| Reflection    | Specific learning + next step             |

---

### 14. Launch & Share

- Quick peer demo (2 min each)
- Peer gives: Praise – Question – Suggest
- Capture improvement idea before final submission

---

### 15. Key Takeaway

Small, honest, accessible tools can drive sustained behavior more effectively than complex, overstated platforms.

---

### 16. Next Module Bridge (Optional)

Combine with visualization (Module 05) for weekly trend—revisit disclaimer with added representation.

---

Prepared: 2025-11-18  
Version: 1.0
