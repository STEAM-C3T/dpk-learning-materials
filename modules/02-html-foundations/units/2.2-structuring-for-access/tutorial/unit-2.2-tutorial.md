# Tutorial: Unit 2.2 — Structuring for Access

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Estimated Time:** 45–60 minutes  
**Author:** Digital Proficiency Kit Team  
**Last Updated:** 2025-11-18

---

## Overview

**What You Will Learn:**
In this tutorial, you will learn to build accessible forms and data tables using proper semantic markup and programmatic associations.

**What You Will Build:**
A survey form with accessible labels and a data table with proper headers, demonstrating best practices for accessibility.

**Learning Outcomes:**

- Build forms with accessible label-input associations
- Create data tables with proper headers and captions
- Understand semantic structure for accessibility
- Test pages with keyboard navigation

---

## Prerequisites

Before starting this tutorial, you should:

- [ ] Have completed Unit 2.1 or be familiar with basic HTML content elements
- [ ] Understand heading hierarchy and semantic structure
- [ ] Have access to a text editor and web browser

**Tools Required:**

- Text editor (VS Code, Notepad++, or similar)
- Modern web browser

---

## Concept Overview

**Why Accessible Forms and Tables Matter:**
Forms and tables are core interaction and data presentation tools on the web. Properly structured, they enable all users—including those using assistive technologies—to understand and interact with content.

**Core Accessibility Principles:**

- **Labels:** Every form input needs an associated label
- **Programmatic Association:** Use `for` and `id` to connect labels and inputs
- **Table Headers:** Use `<th>` to identify row/column headers
- **Table Captions:** Provide context for data tables

---

## Step-by-Step Guide

### Step 1: Create Your HTML File

**Objective:** Set up a basic HTML document for an accessible form.

**Instructions:**

1. Create a new file named `accessible-survey.html`
2. Add the basic HTML structure:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Accessible Survey Form</title>
  </head>
  <body>
    <h1>Student Interest Survey</h1>
  </body>
</html>
```

**Expected Result:**

- File opens in browser with heading visible

**Why This Step:**
Starting with proper structure ensures compliance from the beginning.

**Quick Self-Check:**

- [ ] File saved with `.html` extension
- [ ] Page displays heading

---

### Step 2: Create a Form with Text Input

**Objective:** Build a form with properly labeled text inputs.

**Instructions:**

Add a form with name field:

```html
<form>
  <h2>About You</h2>

  <label for="student-name">Your Name:</label>
  <input type="text" id="student-name" name="student-name" required />

  <br /><br />

  <label for="email">Email Address:</label>
  <input type="email" id="email" name="email" required />
</form>
```

**Expected Result:**

- Labels appear before input fields
- Clicking label focuses corresponding input
- Email field validates email format

**Why This Step:**
The `for` attribute in `<label>` matches the `id` in `<input>`, creating programmatic association. Screen readers announce the label when users focus the input.

**Common Pitfall:**
⚠️ **Watch Out:** `for` and `id` must match exactly (case-sensitive).  
✅ **Tip:** Copy-paste IDs to avoid typos.

**Quick Self-Check:**

- [ ] Clicking label focuses input
- [ ] Each input has unique `id`
- [ ] `for` attribute matches `id`

---

### Step 3: Add Radio Buttons and Checkboxes

**Objective:** Create accessible choice inputs.

**Instructions:**

Add grade level radio buttons:

```html
<fieldset>
  <legend>Grade Level:</legend>

  <input type="radio" id="grade-9" name="grade" value="9" />
  <label for="grade-9">9th Grade</label>

  <input type="radio" id="grade-10" name="grade" value="10" />
  <label for="grade-10">10th Grade</label>

  <input type="radio" id="grade-11" name="grade" value="11" />
  <label for="grade-11">11th Grade</label>

  <input type="radio" id="grade-12" name="grade" value="12" />
  <label for="grade-12">12th Grade</label>
</fieldset>
```

Add interest checkboxes:

```html
<fieldset>
  <legend>Areas of Interest (check all that apply):</legend>

  <input
    type="checkbox"
    id="interest-science"
    name="interests"
    value="science"
  />
  <label for="interest-science">Science</label>

  <input
    type="checkbox"
    id="interest-tech"
    name="interests"
    value="technology"
  />
  <label for="interest-tech">Technology</label>

  <input
    type="checkbox"
    id="interest-engineering"
    name="interests"
    value="engineering"
  />
  <label for="interest-engineering">Engineering</label>

  <input type="checkbox" id="interest-arts" name="interests" value="arts" />
  <label for="interest-arts">Arts</label>

  <input
    type="checkbox"
    id="interest-math"
    name="interests"
    value="mathematics"
  />
  <label for="interest-math">Mathematics</label>
</fieldset>
```

**Expected Result:**

- Radio buttons allow one selection per group
- Checkboxes allow multiple selections
- Screen readers announce field group via `<legend>`

**Why This Step:**

- `<fieldset>` groups related form controls
- `<legend>` provides group description
- Same `name` groups radio buttons together

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting `name` attribute—radio buttons won't be mutually exclusive.  
✅ **Tip:** Radio buttons in same group must share same `name`.

**Quick Self-Check:**

- [ ] Only one radio button selectable at a time
- [ ] Multiple checkboxes can be selected
- [ ] Legend describes field group

---

### Step 4: Add Dropdown and Textarea

**Objective:** Include selection and multi-line text inputs.

**Instructions:**

Add dropdown menu:

```html
<label for="favorite-subject">Favorite Subject:</label>
<select id="favorite-subject" name="favorite-subject">
  <option value="">--Select One--</option>
  <option value="biology">Biology</option>
  <option value="chemistry">Chemistry</option>
  <option value="physics">Physics</option>
  <option value="cs">Computer Science</option>
  <option value="math">Mathematics</option>
</select>

<br /><br />
```

Add textarea for comments:

```html
<label for="comments">Additional Comments:</label>
<br />
<textarea
  id="comments"
  name="comments"
  rows="4"
  cols="50"
  placeholder="Tell us more about your interests..."
></textarea>
```

**Expected Result:**

- Dropdown shows selectable options
- Textarea allows multi-line input
- Placeholder text provides guidance

**Why This Step:**

- `<select>` creates dropdown menus
- `<textarea>` for longer text input
- `placeholder` provides hints (but not a replacement for labels!)

**Common Pitfall:**
⚠️ **Watch Out:** Using placeholder instead of label.  
✅ **Tip:** Always use `<label>`; placeholder is supplementary.

**Quick Self-Check:**

- [ ] Dropdown has default "Select One" option
- [ ] Textarea resizable
- [ ] Both have associated labels

---

### Step 5: Add Submit Button

**Objective:** Complete the form with a submission button.

**Instructions:**

```html
<br>
<button type="submit">Submit Survey</button>
</form>
```

**Expected Result:**

- Button displays with text "Submit Survey"
- Clicking button submits form (currently refreshes page)

**Why This Step:**
Accessible buttons use `<button>` or `<input type="submit">` with descriptive text.

**Quick Self-Check:**

- [ ] Button text is descriptive
- [ ] Form can be submitted

---

### Step 6: Create an Accessible Data Table

**Objective:** Build a table with proper headers and caption.

**Instructions:**

After the form, add:

```html
<h2>Survey Results Summary</h2>

<table>
  <caption>
    Student Interest Survey Results — Fall 2025
  </caption>
  <thead>
    <tr>
      <th scope="col">Subject Area</th>
      <th scope="col">Number of Students</th>
      <th scope="col">Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Science</td>
      <td>24</td>
      <td>60%</td>
    </tr>
    <tr>
      <td>Technology</td>
      <td>32</td>
      <td>80%</td>
    </tr>
    <tr>
      <td>Engineering</td>
      <td>18</td>
      <td>45%</td>
    </tr>
    <tr>
      <td>Arts</td>
      <td>28</td>
      <td>70%</td>
    </tr>
    <tr>
      <td>Mathematics</td>
      <td>20</td>
      <td>50%</td>
    </tr>
  </tbody>
</table>
```

**Expected Result:**

- Table displays with headers in bold
- Caption appears above table
- Data organized in rows and columns

**Why This Step:**

- `<caption>` describes table purpose
- `<thead>` groups header rows
- `<th scope="col">` identifies column headers
- `<tbody>` groups data rows
- `<td>` contains data cells

**Common Pitfall:**
⚠️ **Watch Out:** Using `<td>` for headers instead of `<th>`.  
✅ **Tip:** Always use `<th>` with appropriate `scope` attribute.

**Quick Self-Check:**

- [ ] Table has caption
- [ ] Headers use `<th>` with `scope`
- [ ] Data organized logically

---

### Step 7: Test Keyboard Navigation

**Objective:** Verify form is keyboard-accessible.

**Instructions:**

1. Click in browser address bar
2. Press `Tab` key repeatedly
3. Observe focus moving through form fields in order
4. Use arrow keys in radio buttons and dropdown
5. Press `Space` to check checkboxes
6. Press `Enter` on submit button

**Expected Result:**

- Focus moves logically through form
- Visual focus indicator on each element
- All controls accessible without mouse

**Why This Step:**
Keyboard navigation is essential for accessibility—many users don't use mice.

**Common Pitfall:**
⚠️ **Watch Out:** Custom styles that hide focus indicators.  
✅ **Tip:** Never remove focus outlines without replacing with visible alternative.

**Quick Self-Check:**

- [ ] Can tab through all inputs
- [ ] Focus indicator visible
- [ ] Can complete entire form with keyboard

---

## Debugging Section

**Scenario 1: Clicking label doesn't focus input**

- **Possible Cause:** `for` attribute doesn't match `id`
- **Solution:** Check spelling and case; they must match exactly

**Scenario 2: Radio buttons all selectable at once**

- **Possible Cause:** Different `name` attributes
- **Solution:** Give all radio buttons in group the same `name`

**Scenario 3: Table headers don't stand out**

- **Possible Cause:** Used `<td>` instead of `<th>`
- **Solution:** Change header cells to `<th scope="col">` or `<th scope="row">`

**Scenario 4: Form submits but doesn't validate**

- **Possible Cause:** Missing `required` attribute or wrong `type`
- **Solution:** Add `required` to inputs; use appropriate `type` (email, text, etc.)

**General Debugging Tips:**

- Use browser DevTools Accessibility Inspector
- Test with keyboard only (unplug mouse)
- Use screen reader (NVDA, VoiceOver) to test
- Validate HTML at https://validator.w3.org/

---

## Consolidated Key Concepts

**1. Form Accessibility**

- Every input needs a `<label>` with `for` attribute
- `for` must match input's `id`
- Use `<fieldset>` and `<legend>` to group related inputs
- Use `required` for mandatory fields

**2. Input Types**

- `text`: single-line text
- `email`: email validation
- `radio`: single selection from group
- `checkbox`: multiple selections
- `select`: dropdown menu
- `textarea`: multi-line text

**3. Table Accessibility**

- `<caption>`: describes table
- `<thead>`, `<tbody>`, `<tfoot>`: structure sections
- `<th scope="col">`: column header
- `<th scope="row">`: row header
- `<td>`: data cell

**4. Keyboard Navigation**

- `Tab`: move to next focusable element
- `Shift + Tab`: move to previous
- Arrow keys: navigate radio buttons, dropdowns
- `Space`: toggle checkboxes
- `Enter`: submit form

---

## Practice Variations

**Variation 1: Enhanced Form**

- Add password field with confirmation
- Include date-of-birth input with `type="date"`
- Add phone number field with pattern validation

**Variation 2: Complex Table**

- Create table with row headers (`scope="row"`)
- Add `<tfoot>` with totals
- Include spanning cells with `colspan` or `rowspan`

**Variation 3: Multi-Page Form**

- Split form into sections with headings
- Add "Next" and "Previous" buttons
- Include progress indicator

---

## Reflection Prompts

1. **Why is it important to associate labels with inputs programmatically?**

   - [Space for student response]

2. **How does keyboard navigation improve accessibility?**

   - [Space for student response]

3. **What's the difference between `<th>` and `<td>` in tables?**
   - [Space for student response]

---

## Further Reading

**Official Documentation:**

- [MDN: HTML Forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [MDN: HTML Tables](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables)
- [WebAIM: Forms Accessibility](https://webaim.org/techniques/forms/)
- [W3C: Tables Tutorial](https://www.w3.org/WAI/tutorials/tables/)

**Related Tutorials:**

- Previous: Unit 2.1 — Building Content
- Next: Module 03 — CSS Styling & Layout

**Advanced Topics:**

- ARIA attributes for custom widgets
- Form validation with JavaScript
- Responsive tables

---

## Accessibility Considerations

**This Tutorial Emphasized:**

- ✅ Label-input associations with `for` and `id`
- ✅ Fieldset and legend for grouped inputs
- ✅ Proper table structure with headers and caption
- ✅ Keyboard navigation testing

**Why Accessibility Matters:**

- Over 15% of the global population has some form of disability
- Legal requirement in many countries (ADA, Section 508, etc.)
- Benefits all users (clearer structure, better usability)

**Next Steps:**

- In Module 03, you'll learn to style forms and tables with CSS

---

## Metadata

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Author:** Digital Proficiency Kit Team  
**Contributors:** N/A  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Unit 2.2 Tutorial -->

## Metadata

**Module:** 02 — HTML Foundations  
**Unit:** 2.2 — Structuring for Access  
**Author:** Digital Proficiency Kit Team  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Unit 2.2 Tutorial -->
