# Teacher-Annotated Workbook: Unit 7.1 — Sustainability Mini‑App

**Module:** 07 — Green STEAM Challenge  
**Unit:** 7.1 — Build a Sustainability Mini‑App  
**Core Duration:** 3–4 lessons (135–180 minutes); optional persistence or dataset work may add 30–60 minutes.  
**Prerequisites:** Semantic HTML (1–2), CSS (3), JS DOM & events (4), optional Canvas/Data Viz (5–6)

---

## Purpose & Pedagogical Focus

Students consolidate core web development skills into a _purpose-driven_ artifact. Emphasis shifts from purely technical implementation toward _usability_, _ethics_, _accessibility_, and _impact communication._ The mini‑app should be intentionally small to promote completion and reflection over feature sprawl.

### Key Teaching Aims

| Aim                            | Strategy                                         |
| ------------------------------ | ------------------------------------------------ |
| Encourage scoped thinking      | Require explicit acceptance criteria early       |
| Foster ethical awareness       | Mandate privacy & impact explanation section     |
| Reinforce accessibility habits | Integrate checklist mid‑build, not at end        |
| Cultivate reflection           | Use iteration log & peer review frameworks       |
| Avoid greenwashing             | Provide language samples emphasizing limitations |

### DigComp 2.2 Mapping

| Competence                           | Evidence in Unit                                        |
| ------------------------------------ | ------------------------------------------------------- |
| 3.1 Developing digital content       | Building functional mini‑app with UI & persistence      |
| 3.2 Integrating & re-elaborating     | Combining storage, UI, metrics, explanatory text        |
| 3.3 Copyright & licensing (implicit) | Avoid external unlicensed assets; encourage disclaimers |
| 3.4 Programming                      | DOM manipulation, data structures, event handling       |
| 4.2 Protecting personal data         | Transparency about localStorage usage                   |
| 5.2 Technological problem solving    | Minimal solution to defined sustainability need         |

---

## Answer Key: Student Workbook Fill‑Ins

**Part 1 (Focus & Alignment)**

- Scope criterion: Should mention limited interactions (add/view/reset) and manageable data.
- SDG sentence example: “This mini‑app supports SDG 13 (Climate Action) by helping users consistently track small daily emission-reducing actions.”

**Part 4 (Semantic Structure Justifications)**
| Element | Purpose | Justification |
|---------|---------|---------------|
| `<header>` | Branding & intro | Distinguishes page identity & purpose |
| `<main>` | Core interactive region | Landmarks improve screen reader navigation |
| Metrics `<section>` | Live summary | Group dynamic totals semantically |
| `<ul>` log | List of recorded actions | Ordered or unordered semantic grouping of entries |
| `<form>` | Data input (custom action) | Clear submission semantics, built‑in accessibility |
| `<details>` | Disclosure of storage/ethics | Progressive disclosure; improves clarity |

**Part 5 (State Field Explanations)**

- `id`: Unique identifier for deletion & potential future filtering.
- `name`: Action label (user input sanitized).
- `points`: Approximate motivational value (not exact carbon measure).
- `ts`: Timestamp for potential chronological sorting or future time‑based stats.

**Part 6 (Pseudo Code)**
Validation = ensure `parsed.actions` is an array & totals numeric; Error handling = catch JSON parse errors & recover with empty state.

**Part 7 Accessibility**
Potential issue: Missing visible focus ring after custom button styling; solution: explicit `outline` style.

**Part 10 Feature Checklist**
Evidence examples: Console screenshot of persisted data key, GIF of adding + deleting action, snippet of JSON export.

**Part 11 Code Snippets**

- `id` generation: `crypto.randomUUID()` fallback to `Date.now().toString()`.
- `saveAndRender()` expected placeholder.
- Totals reduce callback referencing `a.points` & `state.actions.length`.

**Part 12 Testing**
All expected results: totals update; export contains `actions` + `totals`; reset clears list & metrics.

**Part 13 Privacy & Ethics**
Potential harmful assumption: Overclaiming real carbon offsets; mitigation: disclaim approximate motivational points.

**Part 15 Enhancements**
Valid examples: Weekly goal progress bar, category filtering, simple trend visualization.

**Vocabulary** (Model Answers)

- **localStorage:** Browser key‑value storage persisting across sessions.
- **Persistence:** Retention of state between page loads.
- **Semantic HTML:** Meaningful structural tags conveying document purpose.
- **User Flow:** Sequence of steps a user takes to accomplish goal.
- **Accessibility:** Inclusive design enabling use by people with diverse abilities.
- **Ethical Transparency:** Honest disclosure of data use & limitations.
- **Impact Metric:** Simplified quantitative indicator (points, counts) representing behavior.
- **Scope Creep:** Gradual uncontrolled expansion of project features.

---

## Teaching Sequence (Suggested)

| Phase              | Time      | Focus                        | Teacher Actions                                       |
| ------------------ | --------- | ---------------------------- | ----------------------------------------------------- |
| Kickoff            | 10–15 min | Scope & SDG selection        | Prompt specificity; review examples                   |
| Planning           | 15–25 min | User story + wireframe       | Circulate; challenge vague goals                      |
| Build I            | 30–40 min | HTML structure + base JS     | Conduct accessibility pre‑check early                 |
| Build II           | 30–40 min | Interaction, state, and refining UI; optional persistence | Keep the core usable for the session; persistence is opt-in, with clear disclosure and failure handling |
| Testing & Ethics   | 15–20 min | Checklist + impact messaging | Pair testing; analyze language                        |
| Reflection & Share | 10–20 min | Demo + feedback              | Facilitate constructive critique                      |

Adapt durations based on class pacing and engagement.

---

## Differentiation Strategies

| Learner Profile                   | Support                                                    | Extension                                       |
| --------------------------------- | ---------------------------------------------------------- | ----------------------------------------------- |
| Emerging                          | Provide starter template with stub functions               | Add live filtering or sorting                   |
| On Track                          | Offer action array; student implements state and rendering | Add opt-in persistence with graceful failure handling or integrate a simple chart |
| Advanced                          | Allow designing own data model + modular architecture      | Implement preset goals + progress notifications |
| ELL                               | Vocabulary mini‑glossary; sentence stems for disclaimers   | Multi‑language UI toggle                        |
| Neurodivergent / Motion Sensitive | Emphasize stable, non‑flashing UI; quick break schedule    | Research minimalist UI comparisons              |

---

## Accessibility & Ethics Emphasis

Early embed: Introduce privacy explanation before building interactions. Students who postpone ethical text tend to underplay its importance. Encourage writing disclaimers once user story locked.

### Sample Disclaimer

"The action count tracks selected activities; it does not measure environmental impact. If you opt in to remembering choices, they are saved in this browser only. No identity or location data is stored. Reset removes saved choices when browser storage allows it."

### Greenwashing Avoidance Language

| Overclaim           | Replacement                            |
| ------------------- | -------------------------------------- |
| “Exact CO₂ saved”   | “Approximate encouragement points”     |
| “Guaranteed impact” | “Supports awareness & habit formation” |
| “Fully sustainable” | “Promotes mindful daily choices”       |

---

## Assessment Rubric (Teacher Version)

| Criterion | Emerging (1) | Developing (2) | Proficient (3) | Advanced (4) | Evidence to collect |
| --- | --- | --- | --- | --- | --- |
| Scope and user flow | User, purpose, or sequence is unclear. | Identifies a user and goal, but scope or steps need clarification. | Defines a focused goal and a logical, small set of interactions. | Explains constraints and improves the flow based on user feedback. | User story, wireframe, and peer-test note. |
| State and optional persistence | Core interaction or state is missing or unreliable. | Core interaction partly works; state or feedback has gaps. | Core interaction works for the session; persistence is optional. | If persistence is offered, it is opt-in, handles unavailable storage, and explains reset behavior. | Working prototype and interaction/storage check. |
| Accessibility | Controls or content are difficult to understand or operate. | Some accessible features are present, with notable gaps. | Uses semantic structure, labels, visible focus, and perceivable feedback. | Tests with keyboard or peer feedback and makes a specific improvement. | Keyboard check and peer-test observation. |
| Ethical transparency and impact communication | Data use or impact claims are missing or misleading. | Gives a general explanation but leaves important limits unclear. | Discloses optional data storage and reset limits; describes counts as activity indicators, not measured impact. | Explains trade-offs and supports claims with relevant evidence. | Disclosure text and a reviewed impact statement. |
| Code quality and reflection | Code or reflection is incomplete; no useful next step is identified. | Describes the work but gives a broad or unclear improvement. | Uses understandable functions and identifies a specific improvement. | Justifies design choices and proposes a realistic next iteration. | Source review and short reflection. |

Use rubric mid‑way for formative self‑correction.

---

## Formative Checkpoints

| Checkpoint     | Prompt                          | Expected Evidence              |
| -------------- | ------------------------------- | ------------------------------ |
| Scope Draft    | “List your user flow steps”     | ≤3 clear steps                 |
| Prototype HTML | “Show headings & landmark tags” | Semantic structure present     |
| Storage (optional) | “If you opted in, refresh after adding an action; what happens if storage is unavailable?” | Persistence works when available, failure is handled, or the app clearly remains session-only |
| Accessibility  | “Tab through interface”         | All focusable; visible outline |
| Ethics         | “Explain what data you store”   | Clear, specific disclosure     |

---

## Common Misconceptions & Responses

| Misconception                  | Response                                                                                |
| ------------------------------ | --------------------------------------------------------------------------------------- |
| Need many features for impact  | Focus depth > breadth enhances usability and finishability                              |
| Carbon numbers must be exact   | Emphasize difficulty of precise measurement; encourage approximate motivational scoring |
| Accessibility done last        | Integrate early; cheaper to adjust structure than retro‑fit                             |
| localStorage is private/secure | Clarify it’s plain text accessible to user & any scripts on the domain                  |

---

## Troubleshooting Table

| Symptom          | Likely Cause                            | Fix                                                             |
| ---------------- | --------------------------------------- | --------------------------------------------------------------- |
| Totals incorrect | Points parsed as string                 | Use `Number()` or unary `+` when adding                         |
| Saved choices missing | Persistence is off, browser storage was cleared or unavailable, or a save failed | Keep the session usable; explain the storage status and do not treat persistence as required |
| Delete fails     | ID mismatch                             | Log IDs; ensure using unique generation technique               |
| Export empty     | Export triggered before load            | Call `loadState()` before rendering; guard null state           |
| Keyboard trap    | Custom component missing focus handling | Replace with native elements / ensure `tabindex` & ARIA correct |

---

## Extension Ideas (Advanced Learners)

1. **Goal Progress Visualization:** Weekly goal bar; color-coded threshold.
2. **Action Categories:** Filter panel (transport/food/energy). Avoid overwhelming UI.
3. **Simple Trend Chart:** Reuse Canvas bar chart logic from Module 05 for daily/weekly totals.
4. **Preset Import/Export:** JSON config for quick setup of predefined action sets.
5. **Multi-Session Reflection:** Append reflection logs tied to timestamps.

Ensure ethical messaging evolves with complexity (different disclaimers for included calculations).

---

## Performance Notes

Scale is minimal: emphasize _not_ prematurely optimizing. Use opportunity to teach responsible code patterns (no infinite loops, minimal DOM thrash).

Introduce simple profiling using `performance.now()` if advanced learners add charts or larger loops.

---

## Teacher Reflection Prompts

After session:

- Did students articulate privacy clearly without prompting?
- Were claims about impact cautious or overstated?
- What accessibility gaps persisted?
- Which support strategies most improved focus (timer, milestone checklist, pair review)?
- Next time: earlier peer critique on disclaimers? Provide template disclaimers?

Record actionable adjustments for future iteration.

---

## Peer Review Facilitation

Encourage _specific_ language:

- “Adding a pause control would aid accessibility” vs “Looks fine.”
  Offer a quick feedback scaffold: _Praise – Question – Suggest._

---

## Ethical Lens Emphasis

Highlight risk of psychological guilt if scoring system becomes punitive. Frame as encouragement and reflection, never punishment.

Encourage inclusive metric choices (avoid culturally biased actions—e.g., assume bike access). Provide alternative actions or generic categories.

---

## Language Templates

| Purpose | Template                                                   |
| ------- | ---------------------------------------------------------- |
| Intro   | “This tool helps track small daily sustainability habits.” |
| Impact  | “Point totals are motivational only; they are not emissions estimates or measurements of environmental impact.” |
| Privacy | “If enabled, choices are stored in this browser’s localStorage and this example does not upload them. Browser storage is accessible to scripts on the same site; do not store sensitive data.” |
| Reset   | “Reset clears this session and attempts to remove saved choices; browser restrictions may prevent saved data from being removed.” |

---

## Minimal Starter Snippet (Teacher Distribution)

If students struggle: provide smaller scaffold (found in tutorial Part 18); differentiate by having advanced learners refactor into modular structure.

---

## Versioning & Authenticity

Encourage students to include a version comment header at top of JS:

```javascript
// green-mini-app.js v1.0 (Student Name, Date)
```

This models professional documentation habits.

---

## Licensing & Attribution (Optional Guidance)

If students add third-party icons or style snippets, require attribution comment block. Reinforces responsible digital citizenship.

---

## Summary for Teachers

A successful submission: simple scope, clear flow, ethical transparency, accessible UI, honest impact narrative, and reflective commentary. Resist pressure to add complexity at the expense of clarity. Celebrate thoughtful disclaimers as strongly as polished code.

**Next Step After Module 07:** Encourage combining sustainability mini‑app with visualization patterns (Module 05) or creative generative aesthetics (Module 06) carefully—revisit ethical messaging with expanded feature sets.

---

**Version 1.0 — 2025-11-18**  
Prepared by assistant (review for classroom adaptation)

<!-- End Teacher-Annotated Workbook: Unit 7.1 -->
