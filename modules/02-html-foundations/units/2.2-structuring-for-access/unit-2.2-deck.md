---
marp: true
theme: default
paginate: true
header: "Digital Proficiency Kit | Module 02: Unit 2.2"
footer: "STEAM-C3T | CC BY-SA 4.0"
---

# Unit 2.2: Structuring for Access

Module 02: HTML Foundations
Digital Proficiency Kit

---

## Warm-Up

Have you ever filled out an online form? What made it easy or confusing to use?

_Think, pair, share your ideas._

---

## Unit Objectives

- Build forms with accessible label-input associations
- Create data tables with proper headers
- Understand semantic structure for accessibility
- Test pages with keyboard navigation

---

## Quick Check

What's a label? Why can't we just use placeholder text?

---

## Forms: Labels & Inputs

Every input needs a label:

```html
<label for="email">Email:</label> <input type="email" id="email" />
```

Association via `for`/`id` helps screen readers

---

## Form Elements

- `<input>`: Text, email, password, etc.
- `<textarea>`: Multi-line text
- `<select>`: Dropdown menu
- `<button>`: Submit button

---

## Tables: Structure Data

- `<table>`: Container
- `<tr>`: Table row
- `<th>`: Header cell
- `<td>`: Data cell
- `<caption>`: Table description

---

## Table Example

```html
<table>
  <caption>
    Class Schedule
  </caption>
  <tr>
    <th>Day</th>
    <th>Subject</th>
  </tr>
  <tr>
    <td>Monday</td>
    <td>Math</td>
  </tr>
</table>
```

---

## Guided Practice

Create a simple survey form with:

- Name and email inputs (with labels)
- Dropdown for grade level
- Submit button

---

## Check for Understanding

1. How do you associate a label with an input?
2. What's the difference between `<th>` and `<td>`?
3. When should you use a table?

---

## Independent Task

Add a form and small data table to your content page

---

## Reflection

Why does accessibility matter? How do labels help users?

---

## Accessibility

- Labels must be programmatically associated
- Placeholders are not labels
- Tables need headers (`<th>`)
- Test with keyboard: Can you tab through?

---

## Extension

- Add fieldset/legend for grouped inputs
- Include required field indicators
- Create a more complex table (3+ columns)

---

## Summary & Next Steps

Today: Forms with labels, data tables

Next: Module 03 — Styling with CSS

---

## Questions?

Ask now, or check the tutorial and workbook for more info.

---

# Thank You!

Next: Module 03 — CSS Styling & Layout

---

<!-- End of Unit 2.2 Deck -->
