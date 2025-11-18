# Student Workbook: Unit 2.2 — Structuring for Access

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Name:** ******\*\*\*\*******\_\_\_******\*\*\*\*******  
**Date:** ******\*\*\*\*******\_\_\_******\*\*\*\*******

---

## Learning Objectives

By the end of this unit, I will be able to:

- [ ] Build forms with accessible label-input associations
- [ ] Create data tables with proper headers and captions
- [ ] Understand semantic structure for accessibility
- [ ] Test pages with keyboard navigation

---

# Student Workbook: Unit 2.2 — Structuring for Access

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Name:** ****************\_\_\_****************  
**Date:** ****************\_\_\_****************

---

## Learning Objectives

By the end of this unit, I will be able to:

- [ ] Create accessible forms with properly associated labels
- [ ] Use fieldset and legend to group related form controls
- [ ] Build data tables with headers, captions, and proper structure
- [ ] Test web pages using keyboard-only navigation
- [ ] Understand why accessibility matters for all users

---

## Key Concepts

**Fill in the blanks as you progress through the tutorial:**

1. The `for` attribute in a `<label>` must match the ****\_\_**** of the input.

2. `<fieldset>` groups related form controls, and `<legend>` provides a ****\_\_****.

3. In tables, use `<th>` for ****\_\_**** and `<td>` for ****\_\_****.

4. The `<caption>` element describes the ****\_\_**** of a table.

5. Radio buttons with the same `name` attribute create a ****\_\_**** group.

6. The `scope` attribute on `<th>` can be "****\_\_****" or "****\_\_****".

---

## Guided Practice Notes

### Part 1: Form Labels

**My form topic:** ****************\_\_\_****************

**Label-input pairs:**

| Label Text   | Input ID     | Input Type   |
| ------------ | ------------ | ------------ |
| ****\_\_**** | **\_\_\_\_** | ****\_\_**** |
| ****\_\_**** | **\_\_\_\_** | ****\_\_**** |
| ****\_\_**** | **\_\_\_\_** | ****\_\_**** |

**Question:** Why must the `for` and `id` match exactly?

---

---

---

### Part 2: Grouping Form Controls

**My fieldset groups:**

**Group 1 Legend:** ****************\_\_\_****************

Controls in this group:

- ***
- ***
- ***

**Group 2 Legend:** ****************\_\_\_****************

Controls in this group:

- ***
- ***

---

### Part 3: Data Tables

**My table caption:** ****************\_\_\_****************

**Column headers:**

1. ***
2. ***
3. ***

**Number of data rows:** ****\_\_\_****

**Question:** What's the difference between `<th>` and `<td>`?

---

---

---

## Independent Task Checklist

**Task:** Create an accessible survey form and results table.

**Form Requirements:**

- [ ] At least 3 text inputs with associated labels
- [ ] One fieldset with radio buttons (minimum 3 options)
- [ ] One fieldset with checkboxes (minimum 3 options)
- [ ] One dropdown (`<select>`) with at least 5 options
- [ ] One textarea for comments
- [ ] Submit button with descriptive text
- [ ] All labels properly associated using `for` and `id`

**Table Requirements:**

- [ ] Table caption describing content
- [ ] Header row using `<th>` with `scope="col"`
- [ ] At least 4 data rows with 3 columns each
- [ ] Proper structure with `<thead>` and `<tbody>`

**Accessibility Requirements:**

- [ ] Form fully navigable with keyboard only
- [ ] No label-input associations broken
- [ ] Focus indicators visible on all controls

---

## Formative Checks

**Check 1: After Step 2 (Labels)**

- [ ] Clicking each label focuses its input
- [ ] All `for` attributes match corresponding `id`
- [ ] No duplicate `id` values

**Check 2: After Step 3 (Radio/Checkbox)**

- [ ] Radio buttons mutually exclusive within group
- [ ] Fieldset surrounds grouped controls
- [ ] Legend describes group purpose

**Check 3: After Step 6 (Table)**

- [ ] Table has caption
- [ ] Headers use `<th>` not `<td>`
- [ ] Scope attributes on headers

**Check 4: After Step 7 (Keyboard Test)**

- [ ] Tab key moves through all form controls
- [ ] Focus indicator visible
- [ ] Can complete form without mouse

---

## Common Errors Log

| Error                              | What Happened  | How I Fixed It              |
| ---------------------------------- | -------------- | --------------------------- |
| Example: Label doesn't focus input | `for` had typo | Matched `for` to exact `id` |
|                                    |                |                             |
|                                    |                |                             |

---

## Code Snippets Collection

**Labeled Text Input:**

```html

```

**Radio Button Group:**

```html

```

**Table with Headers:**

```html

```

---

## Self-Assessment Rubric

Rate yourself (1 = Beginning, 2 = Developing, 3 = Proficient, 4 = Exemplary):

| Criterion                                                       | 1   | 2   | 3   | 4   | Evidence |
| --------------------------------------------------------------- | --- | --- | --- | --- | -------- |
| **Label Associations**: All inputs properly labeled             | ☐   | ☐   | ☐   | ☐   |          |
| **Form Structure**: Fieldsets, legends, appropriate input types | ☐   | ☐   | ☐   | ☐   |          |
| **Table Structure**: Caption, headers, proper scope             | ☐   | ☐   | ☐   | ☐   |          |
| **Keyboard Accessibility**: Fully navigable without mouse       | ☐   | ☐   | ☐   | ☐   |          |
| **Code Quality**: Valid, well-formatted HTML                    | ☐   | ☐   | ☐   | ☐   |          |

---

## Reflection

**1. How does keyboard navigation help users with disabilities?**

---

---

**2. Why is programmatic label-input association important for screen readers?**

---

---

**3. What would make a table inaccessible?**

---

---

---

## Glossary

| Term                     | Definition                                            | Example                                       |
| ------------------------ | ----------------------------------------------------- | --------------------------------------------- |
| Programmatic association | Connecting elements via attributes for assistive tech | `<label for="name">` with `<input id="name">` |
| Fieldset                 | Groups related form controls                          | Wraps radio buttons                           |
| Legend                   | Describes a fieldset group                            | "Gender:" for gender radio buttons            |
| Scope                    | Defines header's relationship to cells                | `scope="col"` or `scope="row"`                |
| Caption                  | Provides table description                            | `<caption>Student Grades</caption>`           |

---

## Next Steps

**Preparing for Module 03:**

- [ ] Review CSS basics (you'll style forms and tables)
- [ ] Think about how forms/tables could look better
- [ ] Explore accessibility resources (WebAIM, MDN)

---

## Metadata

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Version:** 1.0  
**Last Updated:** 2025-11-18  
**License:** CC BY-SA 4.0

---

**End of Workbook**
