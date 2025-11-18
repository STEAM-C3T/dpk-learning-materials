# Student Workbook: Unit 7.1 — Sustainability Mini‑App

**Module:** 07 — Green STEAM Challenge  
**Unit:** 7.1 — Build a Sustainability Mini‑App  
**Name:** ********\_\_\_\_********  
**Date:** ********\_\_\_\_********

---

## Learning Objectives (Check as you progress)

By the end I can:

- [ ] Define a narrow sustainability focus and SDG alignment
- [ ] Map a clear user flow (≤ 3 primary interactions)
- [ ] Implement semantic HTML structure
- [ ] Persist data responsibly with `localStorage`
- [ ] Explain what data is stored and how to reset/export it
- [ ] Provide accessible interactions (keyboard + clear labels)
- [ ] Communicate impact honestly (no exaggerated claims)
- [ ] Reflect on limitations and ethical considerations

---

## Part 1: Focus & SDG Alignment

**Pick ONE specific sustainability focus.** Examples: daily green actions tracker, water use estimator, eco tips library.

1. App Title Idea: ************************\_\_\_************************
2. SDG (number/name): **********************\_\_\_**********************
3. SDG Alignment Sentence: “This mini‑app supports SDG **\_\_** by helping users ********************\_\_********************.”
4. Primary User Goal (one sentence): ********************\_\_********************
5. Core User Story: “As a ********\_\_\_\_********, I want to ********\_\_\_\_******** so I can ********\_\_\_\_********.”

**Why is this scope small enough?**

---

---

---

## Part 2: User Flow Outline

List the _minimal_ interactions (avoid feature creep):

| Step # | Action | Result/Feedback |
| ------ | ------ | --------------- |
| 1      |        |                 |
| 2      |        |                 |
| 3      |        |                 |

Optional extras (only if time): ******************\_\_\_******************

---

## Part 3: Wireframe Sketch

Draw or describe your interface layout.

```
[Use ASCII or attach a sketch]
+---------------------------------------------+
| Title                                       |
| Intro text                                  |
| Metrics (points / count)                    |
| Quick actions buttons                       |
| Custom action form                          |
| Logged actions list                         |
| Export / Reset / Privacy info               |
+---------------------------------------------+
```

Notes on layout & responsiveness:

---

---

---

## Part 4: Semantic Structure Planning

Fill the table with planned elements.

| Element               | Purpose | Justification for Semantics |
| --------------------- | ------- | --------------------------- |
| `<header>`            |         |                             |
| `<main>`              |         |                             |
| `<section>` (metrics) |         |                             |
| `<ul>` (log)          |         |                             |
| `<form>`              |         |                             |
| `<details>`           |         |                             |

**Why headings matter for accessibility?**

---

---

## Part 5: Data & State Design

Define your initial data shape.

```
state = {
  actions: [ /* each: { id, name, points, ts } */ ],
  totals: { points: 0, count: 0 }
}
```

Explain each field:

- `id`: ******************************\_\_******************************
- `name`: ****************************\_\_\_\_****************************
- `points`: ****************************\_\_****************************
- `ts` (timestamp): ************************\_************************

**What will you store in localStorage (key name)?**
Key: ************\_\_************

**How will you avoid storing sensitive data?**

---

---

---

## Part 6: localStorage Plan

Fill in pseudo code:

```
function loadState() {
  const raw = localStorage.getItem(KEY);
  if (!raw) return; // No data yet
  try {
    const parsed = JSON.parse(raw);
    // Validate: ____________________________________
    // Assign: ______________________________________
  } catch (e) {
    // Handle error: ________________________________
  }
}

function saveState() {
  // Convert state to string: _______________________
  // Store: localStorage.setItem(KEY, _____________)
}
```

**When will you call `saveState()`?**

---

---

---

## Part 7: Accessibility Checklist

Mark each when implemented.
| Feature | Implemented? | Notes |
|---------|--------------|-------|
| Tab navigable buttons | [ ] | |
| Focus outline visible | [ ] | |
| Clear headings | [ ] | |
| aria-live for totals | [ ] | |
| Form labels or aria-labels | [ ] | |
| Contrast checked | [ ] | |
| Reset confirmation | [ ] | |
| Privacy explanation | [ ] | |

**Potential accessibility issue you resolved:**

---

---

## Part 8: Honest Impact Communication

Write a disclaimer or explanatory paragraph:
“********************************\_\_\_\_********************************

---

********************************\_\_\_\_********************************”

Check for these words you should AVOID unless backed by data: “guarantees,” “exact,” “precise CO₂,” “fully eliminates.”

Rewrite if needed:

---

---

---

## Part 9: Implementation Log

Record progress as you build.

| Time | Task Completed | Challenges | Solution |
| ---- | -------------- | ---------- | -------- |
|      |                |            |          |
|      |                |            |          |
|      |                |            |          |

**Most challenging part so far:**

---

---

## Part 10: Feature Checklist

| Feature                  | Status (Not Started / In Progress / Done) | Evidence or Notes |
| ------------------------ | ----------------------------------------- | ----------------- |
| Quick actions add points |                                           |                   |
| Custom action form       |                                           |                   |
| Actions list with delete |                                           |                   |
| Totals update correctly  |                                           |                   |
| Data persists on refresh |                                           |                   |
| Export JSON button       |                                           |                   |
| Reset data button        |                                           |                   |
| Privacy info section     |                                           |                   |
| Accessibility features   |                                           |                   |

---

## Part 11: Code Snippets to Reference

Fill blanks from your code.

**Add Action Function:**

```javascript
function addAction(name, points) {
  const action = {
    id: ____________,
    name: ____________,
    points: ____________,
    ts: Date.now(),
  };
  state.actions.push(action);
  ____________(); // Save & re-render
}
```

**Delete Action Handler:**

```javascript
function deleteAction(id) {
  state.actions = state.actions.filter((a) => a.id !== id);
  ____________();
}
```

**Totals Calculation:**

```javascript
function updateTotals() {
  state.totals.points = state.actions.reduce((sum, a) => sum + a.__________, 0);
  state.totals.count = state.actions.__________;
}
```

---

## Part 12: Testing Table

| Test Case             | Steps                       | Expected Result        | Pass? |
| --------------------- | --------------------------- | ---------------------- | ----- |
| Add quick action      | Click button                | Points increase        |       |
| Add custom action     | Enter name + points, submit | Appears in list        |       |
| Delete action         | Click delete & confirm      | Removed; totals adjust |       |
| Persist after refresh | Refresh page                | Data remains           |       |
| Export data           | Click export                | JSON appears           |       |
| Reset data            | Click reset & confirm       | Data cleared           |       |
| Keyboard navigation   | Tab through controls        | All reachable          |       |

---

## Part 13: Privacy & Ethical Reflection

Answer:

1. What data might users incorrectly assume is private? **********\_\_\_\_**********
2. How do you clearly communicate storage scope? **************\_**************
3. Could any point values create harmful assumptions? ************\_************
4. How do you mitigate misuse? **********************\_\_**********************

---

## Part 14: Performance Considerations

**Will performance be an issue? Why/why not?**

---

**Micro-optimizations not needed, but list one anyway (for learning):**

---

---

## Part 15: Enhancement Brainstorm

List up to 3 realistic future enhancements (not now):

1. ***
2. ***
3. ***

Why these could help impact:

---

---

---

## Part 16: Self-Assessment Rubric

Rate 1–4 (1 = Beginning, 4 = Advanced). Provide evidence.
| Criterion | 1 | 2 | 3 | 4 | Evidence |
|-----------|---|---|---|---|----------|
| Scope Focus | ☐ | ☐ | ☐ | ☐ | |
| User Flow Clarity | ☐ | ☐ | ☐ | ☐ | |
| Data Persistence | ☐ | ☐ | ☐ | ☐ | |
| Accessibility | ☐ | ☐ | ☐ | ☐ | |
| Ethical Transparency | ☐ | ☐ | ☐ | ☐ | |
| Code Quality | ☐ | ☐ | ☐ | ☐ | |
| Impact Communication | ☐ | ☐ | ☐ | ☐ | |
| Reflection Depth | ☐ | ☐ | ☐ | ☐ | |

---

## Part 17: Peer Review

**Partner Name:** ****************\_\_****************

| Aspect                | Feedback Received | My Response / Action |
| --------------------- | ----------------- | -------------------- |
| Clarity of Purpose    |                   |                      |
| Ease of Use           |                   |                      |
| Accessibility         |                   |                      |
| Impact Explanation    |                   |                      |
| Suggested Enhancement |                   |                      |

**One improvement I'll implement now:**

---

---

## Part 18: Final Reflection

1. Strongest aspect of my app: **********************\_\_**********************
2. One area to improve: **************************\_**************************
3. Most valuable lesson learned: ********************\_\_\_\_********************
4. How this could influence real-world behavior: **************\_\_**************
5. Potential risks if scaled/expanded: ******************\_\_\_******************
6. Ethical guardrail to keep: **********************\_\_\_**********************

---

## Part 19: Submission Package Checklist

- [ ] HTML file (semantic, commented)
- [ ] JS file (clean functions, no dead code)
- [ ] README section (purpose, SDG, data stored)
- [ ] Privacy explanation in UI
- [ ] Screenshots (optional) or short demo script
- [ ] Self-assessment rubric completed

---

## Part 20: Vocabulary Glossary

Define after implementing:

- **localStorage:** **********************\_\_\_\_**********************
- **Persistence:** ************************\_************************
- **Semantic HTML:** **********************\_\_\_**********************
- **User Flow:** ************************\_************************
- **Accessibility:** **********************\_\_**********************
- **Ethical Transparency:** ******************\_\_\_******************
- **Impact Metric:** **********************\_\_**********************
- **Scope Creep:** **********************\_\_\_\_**********************

---

## Teacher Feedback (Reserved)

Strengths:

---

Areas for Growth:

---

Next Steps:

---

Grade/Mark: ****\_\_\_\_**** | Teacher Signature: ********\_\_\_\_********

---

## Notes & Ideas

(Use this space for scratch work, alternative designs, or testing notes.)

---

---

---

---

---

**End of Student Workbook: Unit 7.1**
