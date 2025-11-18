# Teacher Annotated Workbook: Unit 2.2 — Structuring for Access

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Instructor Use Only**

---

## Overview for Teachers

**Estimated Time:** 45–60 minutes

**Learning Objectives:**
By the end of this unit, students will be able to:

- Build forms with accessible label-input associations
- Create data tables with proper headers and captions
- Understand semantic structure for accessibility
- Test pages with keyboard navigation

**DigComp 2.2 Alignment:**

- 3.1 Developing digital content
- 4.1 Protecting devices and digital content

---

# Teacher-Annotated Workbook: Unit 2.2 — Structuring for Access

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Teacher Guide**

---

## Teaching Notes

**Estimated Time:** 50–65 minutes (tutorial) + 35–45 minutes (independent task)

**Pre-Class Preparation:**

- Test screen reader software (NVDA for Windows, VoiceOver for Mac, ChromeVox extension)
- Prepare example of inaccessible form to demonstrate problems
- Set up keyboard navigation demonstration
- Optional: Invite someone who uses assistive tech to speak to class

**Learning Progression:**
This unit introduces accessibility as a core web development principle. Students learn that semantic structure serves real users with real needs.

**Key Mindset Shift:**
From "accessibility is extra work" to "accessibility is fundamental design"

---

## Key Concepts — Answer Key

1. The `for` attribute in a `<label>` must match the **id** (or **ID**) of the input.

2. `<fieldset>` groups related form controls, and `<legend>` provides a **description** (or **label** / **title**).

3. In tables, use `<th>` for **headers** and `<td>` for **data** (or **cells**).

4. The `<caption>` element describes the **purpose** (or **content** / **subject**) of a table.

5. Radio buttons with the same `name` attribute create a **mutually exclusive** (or **single-choice**) group.

6. The `scope` attribute on `<th>` can be "**col**" or "**row**".

---

## Guided Practice — Teaching Tips

### Part 1: Form Labels (12–15 minutes)

**Common Student Challenges:**

- Forgetting `for` attribute entirely
- Typos between `for` and `id`
- Wrapping input inside label (works but less explicit)
- Not understanding why association matters

**Teaching Strategy:**

- **Demonstrate:** Use screen reader to navigate form without labels → confusion
- **Then show:** Same form with proper labels → clarity
- **Interactive:** Have students close eyes, navigate form by ear only

**Live Demo Script:**

1. Show form with no labels (just placeholders)
2. Try to fill it out with screen reader → "Edit text, blank"
3. Show form with labels → "Name, edit text"
4. Ask: "Which would you prefer?"

**Expected Student Response to "Why must for and id match?"**

- So screen reader announces label when input is focused
- Creates programmatic connection
- Makes clicking label focus input

**Differentiation:**

- **Support:** Provide label-input pair templates to copy
- **Extension:** Research ARIA labels for complex widgets

---

### Part 2: Grouping Form Controls (10–12 minutes)

**Common Student Challenges:**

- Forgetting fieldset around radio buttons
- Using `<div>` instead of `<fieldset>`
- Missing legend
- Not understanding when grouping is needed

**Teaching Strategy:**

- Show visual: fieldset creates visible border
- Explain semantic meaning beyond appearance
- Demonstrate screen reader: "Gender, group, Male, radio button"

**When to Use Fieldset:**

- Radio button groups
- Checkbox groups (related options)
- Sections of larger forms
- Address fields, payment info, etc.

**Formative Check:**
Show three scenarios, ask: "Does this need fieldset?"

1. Five separate checkboxes for pizza toppings → YES
2. Single email input → NO
3. Three radio buttons for shirt size → YES

---

### Part 3: Data Tables (12–15 minutes)

**Common Student Challenges:**

- Using tables for layout (old practice)
- Using `<td>` for headers
- Forgetting `scope` attribute
- Missing caption

**Teaching Strategy:**

- Show bad table: all `<td>`, no structure
- Show good table: `<th>`, caption, scope
- Navigate both with screen reader
- Emphasize: "Tables are for data, not layout"

**Table Structure Hierarchy:**

```
<table>
  <caption> (what's this table about?)
  <thead>
    <tr>
      <th scope="col"> (column headers)
  <tbody>
    <tr>
      <td> (data cells)
```

**Real-World Connection:**
"Ever tried to understand a spreadsheet without column headers? That's what screen reader users experience with bad tables."

---

## Independent Task — Assessment Guidance

**Timing:** 35–45 minutes

**Scaffolding Strategies:**

**For students who struggle:**

- Pre-fill form topic and first few inputs
- Provide fieldset/legend template
- Give table with headers, students add data

**For advanced students:**

- Add form validation with `pattern` attribute
- Create complex table with `rowspan`/`colspan`
- Implement multi-step form with JavaScript

**Monitoring Checkpoints:**

- 15 min: Check label-input associations
- 25 min: Verify fieldset groups exist
- 35 min: Confirm table structure complete
- Final: Keyboard navigation test

---

## Formative Checks — Answer Keys

**Check 1: After Step 2 (Labels)**

Test method: Click each label → should focus input

Expected results:

- All labels clickable
- Each focuses corresponding input
- No console errors
- Unique IDs (no duplicates)

**Check 2: After Step 3 (Radio/Checkbox)**

Test method: Try selecting multiple radio buttons

Expected results:

- Only one radio button selectable per group
- Multiple checkboxes selectable
- Screen reader announces legend
- Tab key moves between groups

**Check 3: After Step 6 (Table)**

Test method: Inspect table in DevTools

Expected results:

- `<caption>` present and descriptive
- Header row uses `<th>` with `scope="col"`
- Data rows use `<td>`
- Proper nesting: table > thead > tr > th

**Check 4: After Step 7 (Keyboard Test)**

Test method: Navigate form with Tab key only

Expected results:

- Can reach all form controls
- Visual focus indicator on each element
- Logical tab order (top to bottom, left to right)
- Can submit form with Enter

---

## Common Errors — Teaching Responses

| Error                        | Why It Happens                  | How to Address                                       |
| ---------------------------- | ------------------------------- | ---------------------------------------------------- |
| Label doesn't focus input    | `for` ≠ `id` (typo or mismatch) | Use copy-paste for IDs; verify in DevTools           |
| All radio buttons selectable | Different `name` attributes     | Explain: same `name` = one group                     |
| Table headers not bold       | Used `<td>` instead of `<th>`   | Show: browsers style `<th>` differently              |
| Missing fieldset             | Seems unnecessary/extra         | Demo screen reader: grouped vs ungrouped             |
| Can't tab to element         | Missing `tabindex` or hidden    | Check CSS: `display:none` removes from tab order     |
| Focus indicator invisible    | Custom CSS removed outline      | Emphasize: never `outline: none` without replacement |

---

## Self-Assessment Rubric — Grading Guide

**Label Associations (4 = Exemplary)**

- All inputs have explicit labels with `for`/`id`
- No orphaned inputs
- Labels descriptive and clear

**Form Structure (4 = Exemplary)**

- Fieldsets group related controls appropriately
- Legends describe each group clearly
- All input types appropriate for data collected
- Includes various input types (text, radio, checkbox, select, textarea)

**Table Structure (4 = Exemplary)**

- Caption clearly describes table purpose
- All column headers use `<th scope="col">`
- Proper semantic structure (thead, tbody)
- Data organized logically and clearly

**Keyboard Accessibility (4 = Exemplary)**

- Entire form navigable without mouse
- Focus indicators clearly visible
- Logical tab order maintained
- All controls reachable and operable

**Code Quality (4 = Exemplary)**

- Valid HTML (passes W3C validator)
- Consistent formatting and indentation
- No errors in browser console
- Semantic and clean code

---

## Reflection — Expected Responses

**1. How does keyboard navigation help users with disabilities?**

Look for mentions of:

- Motor disabilities (can't use mouse)
- Screen reader users navigate by keyboard
- Temporary disabilities (broken arm, etc.)
- Power users prefer keyboard efficiency

**Teaching Response:** "About 15-20% of web users rely on keyboard navigation for various reasons. It's not just screen readers!"

---

**2. Why is programmatic label-input association important for screen readers?**

Expected elements:

- Screen readers announce label when input is focused
- Without association, user hears only "edit text, blank"
- Visual users can see context; screen reader users need programmatic context
- Association works even if CSS changes visual layout

**Teaching Response:** "Imagine filling out a form blindfolded. You need someone to read the question before you answer. Labels are that 'someone' for screen readers."

---

**3. What would make a table inaccessible?**

Common correct answers:

- No headers (all `<td>`)
- Missing caption
- No `scope` attributes
- Using table for layout instead of data
- Merged cells without proper attributes

**Teaching Response:** "Screen readers announce row/column for each cell. Without headers, it's like hearing random numbers with no context."

---

## Differentiation Strategies

**For English Language Learners:**

- Provide vocabulary list: fieldset, legend, scope, caption
- Allow forms/tables in native language
- Pair with fluent English speaker for screen reader demos

**For Students with IEPs:**

- Extended time on independent task
- Pre-structured form template (add labels only)
- Simplify table (3 columns vs. 5)
- Provide step-by-step checklist

**For Gifted/Advanced:**

- Add form validation with `pattern` regex
- Research and implement ARIA attributes
- Create responsive table that collapses on mobile
- Build multi-page form with progress indicator

**For Students with Visual Impairments:**

- This unit is perfect opportunity for student to be expert!
- Have them test classmates' forms with screen reader
- Share their real-world experience with accessibility

---

## Extension Activities

**Quick Extensions (10–15 minutes):**

- Add `required` and `pattern` validation
- Create dropdown with `<optgroup>` for categorized options
- Add table footer with totals or summary

**Project Extensions (45+ minutes):**

- Build complete registration system (multi-step form)
- Create data table with sortable columns (JavaScript)
- Audit real website for accessibility issues
- Present findings to class with recommendations

**Cross-Curricular:**

- **Science:** Create data table from experiment results
- **Social Studies:** Survey form about current events
- **Math:** Table with calculations using formulas
- **Language Arts:** Form for peer editing feedback

---

## Assessment Rubric (For Teacher Grading)

| Criterion          | Weight | Exemplary (4)                      | Proficient (3)                   | Developing (2)           | Beginning (1)            |
| ------------------ | ------ | ---------------------------------- | -------------------------------- | ------------------------ | ------------------------ |
| Label Associations | 25%    | All perfect, explicit associations | 1-2 minor issues                 | Some broken associations | Many missing/broken      |
| Form Structure     | 20%    | Multiple fieldsets, varied inputs  | Basic fieldset, most input types | Minimal structure        | No fieldsets or grouping |
| Table Structure    | 20%    | Caption, headers, scope, semantic  | Most elements present            | Missing some structure   | Minimal/no structure     |
| Keyboard Access    | 20%    | Fully navigable, clear focus       | Mostly navigable, some issues    | Partially navigable      | Not keyboard-accessible  |
| Code Quality       | 15%    | Valid, clean, professional         | Minor errors, mostly valid       | Several errors           | Many errors, invalid     |

**Total:** **\_** / 100

**Bonus Points (+5 max):**

- Exceptional accessibility features
- Creative form/table implementation
- Helping peers with accessibility testing

---

## Accessibility Testing Checklist (For Teachers)

Use this when grading student work:

**Form Testing:**

- [ ] Click each label → focuses input
- [ ] Tab through form → reaches all controls
- [ ] Radio buttons mutually exclusive per group
- [ ] Screen reader announces labels clearly
- [ ] Required fields indicated

**Table Testing:**

- [ ] Caption describes table purpose
- [ ] Headers use `<th>` with appropriate `scope`
- [ ] Screen reader announces headers with cells
- [ ] Logical reading order
- [ ] Data aligned properly

**General Testing:**

- [ ] Page validates (W3C validator)
- [ ] No console errors
- [ ] Zoom to 200% → still usable
- [ ] Works without CSS (semantic structure)

---

## Screen Reader Testing Guide

**For Teachers New to Screen Readers:**

**Windows (NVDA - Free):**

1. Download from nvaccess.org
2. Install and restart
3. NVDA+Q to quit, Insert+Down to read

**Mac (VoiceOver - Built-in):**

1. Command+F5 to enable
2. Control+Option+Right Arrow to navigate
3. Command+F5 to disable

**Chrome Extension (ChromeVox):**

1. Install from Chrome Web Store
2. Alt+Shift+A to activate
3. Search+B to read

**Basic Commands (Most Screen Readers):**

- Tab: Next form field
- H: Next heading
- T: Next table
- Forms mode: Auto-enter when focusing input

---

## Links to Related Resources

**For Teachers:**

- [WebAIM: Forms Accessibility](https://webaim.org/techniques/forms/)
- [W3C: Tables Tutorial](https://www.w3.org/WAI/tutorials/tables/)
- [Accessible Form Examples](https://www.w3.org/WAI/tutorials/forms/)
- [NVDA Screen Reader](https://www.nvaccess.org/)

**For Students:**

- Link to Unit 2.2 tutorial
- Link to Module 02 assessment rubric (teacher-toolkit)
- WebAIM articles (simplified)

**Videos:**

- "How Blind People Use Technology" (various YouTube)
- Screen reader demonstrations

---

## Discussion Prompts

**Class Discussion Ideas:**

1. **"Have you ever broken your arm or hand? How would you use a computer?"**

   - Leads to: temporary disabilities matter

2. **"Why do you think websites are legally required to be accessible?"**

   - Leads to: civil rights, equal access

3. **"Who benefits from accessibility features?"**

   - Answer: Everyone! (captions help in noisy places, voice control helps while cooking, etc.)

4. **"What websites have you used that were hard to navigate? Why?"**
   - Leads to: recognizing bad design

---

## Metadata

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Version:** 1.0  
**Last Updated:** 2025-11-18  
**License:** CC BY-SA 4.0

---

<!-- End of Teacher-Annotated Workbook 2.2 -->

---

## Metadata

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Author:** Digital Proficiency Kit Team  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Teacher Annotated Workbook -->
