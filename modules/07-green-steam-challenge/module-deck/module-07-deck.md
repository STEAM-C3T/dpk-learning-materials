# Module 07 Deck — Green STEAM Challenge

---

### 1. Module Purpose

Empower students to build a focused sustainability mini‑app that fosters mindful habits while practicing honest impact communication, ethical transparency, and inclusive design.

---

### 2. Learning Outcomes (Aligned to DigComp)

Students will:

- Define a narrow sustainability scope & user story (3.1, 5.2)
- Implement semantic, accessible UI (3.1, 4.2)
- Use JavaScript for state, persistence & rendering (3.4)
- Communicate ethical & privacy considerations transparently (4.2)
- Reflect on impact limits & improvement paths (5.2)

---

### 3. SDG Alignment Guidance

Choose ONE primary SDG (e.g., 12 Responsible Consumption, 13 Climate Action) and articulate support via behavior awareness—not overstated emissions claims.

SDG Sentence Template:
“This app supports SDG ** by encouraging consistent ** actions.”

---

### 4. Scope & Focus

Why Small?

- Increases completion probability
- Enables deeper reflection
- Easier accessibility auditing
  Success Criteria:
- ≤4 core user interactions
- Clear disclaimer & accessibility checklist completed

---

### 5. Architecture Snapshot

Layers:

- Semantic HTML (header, main, sections)
- CSS for focus visibility & readability
- JS state object { actions[], totals{} }
- Persistence via localStorage single key
- Rendering functions (log, quick actions, totals)
  Principle: Single responsibility per function.

---

### 6. Ethical Transparency Emphasis

Disclaimers Answer:

- What data is stored?
- Where is it stored?
- What are the limitations of the scoring?
  Greenwashing Avoidance: Replace exact carbon claims with motivational framing.

---

### 7. Accessibility Integration

Checklist Mid‑Build:

- Headings hierarchy
- Visible keyboard focus
- Labels & aria-live for dynamic totals
- No color-only distinctions
  Student Reflection Prompt: “How did you ensure a non‑mouse user can fully use the app?”

---

### 8. Assessment Rubric Overview

| Dimension         | Proficient Signal                       |
| ----------------- | --------------------------------------- |
| Scope             | Focused goal + constrained interactions |
| Data Persistence  | Reliable save/load/reset                |
| Accessibility     | All required elements validated         |
| Ethical Messaging | Honest, specific, non-exaggerated       |
| Code Quality      | Modular, readable, minimal duplication  |
| Reflection        | Specific improvement + ethical insight  |

Use rubric formatively at midpoint.

---

### 9. Build Phases

1. Scope & user story
2. Semantic skeleton + disclaimer
3. State & persistence functions
4. Rendering & interactivity
5. Accessibility + ethics validation
6. Testing & reflection
   Encourage commit messages per phase.

---

### 10. Common Risks & Mitigations

| Risk                | Mitigation                               |
| ------------------- | ---------------------------------------- |
| Feature creep       | Revisit written scope; defer extras      |
| Overstated impact   | Peer review disclaimer language          |
| Poor accessibility  | Early keyboard testing; adjust structure |
| Fragile persistence | Centralize save in one helper function   |

---

### 11. Extension Paths (Post-Core)

Select ONE after proficiency:

- Category filtering
- Weekly goal progress bar
- Trend visualization (Canvas from Module 05)
- Import/export presets
  Each extension triggers disclaimer review.

---

### 12. Reflection Prompts

- Which feature most supported the user’s sustainable behavior?
- Where could bias or exclusion occur?
- How might scaling to multiple devices change design?
- What new data would risk privacy issues?

---

### 13. Cross-Module Integration

Combine with:

- Visualization (Module 05) for trend chart
- Generative aesthetics (Module 06) for motivational subtle visuals
  Ensure added visuals remain accessible & non-distracting.

---

### 14. Teacher Facilitation Tips

- Require scope card before coding
- Run a “Disclaimers Clinic” mini-peer review
- Keyboard-only demo by volunteer mid-session
- Model rewriting exaggerated impact claims live

---

### 15. Indicators of Deep Learning

- Student self-corrects language around impact
- Accessibility issues caught before final review
- Reflection includes limitation + concrete next action
- Code shows deliberate modular design choices

---

### 16. Future Iteration Discussion (Optional)

Ask: “If we introduced remote sync, what ethical considerations change?”
Highlights shift from local-only to potential data governance concerns.

---

### 17. Sample Disclaimer Library (For Review)

1. “Data stays only in your browser (localStorage).”
2. “Point totals motivate habits; they are not exact carbon calculations.”
3. “Reset permanently removes saved actions.”
   Encourage personalization without exaggeration.

---

### 18. Success Snapshot Slide

A strong final artifact = Focused scope + Clear flow + Honest messaging + Accessible interactions + Reflective insights.

---

### 19. Wrap-Up

Celebrate thoughtful disclaimers & inclusive design decisions as much as technical completeness.

---

Prepared: 2025-11-18  
Version: 1.0
