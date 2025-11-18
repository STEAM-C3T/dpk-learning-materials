# Tutorial: Unit X.Y — [Unit Title]

**Module:** [Module Number & Title]  
**Unit:** X.Y — [Unit Title]  
**Estimated Time:** [X minutes / Y hours]  
**Author:** [Name]  
**Last Updated:** [Date]

---

## Overview

**What You Will Learn:**
In this tutorial, you will learn how to [brief summary of what the tutorial teaches].

**What You Will Build:**
By the end, you will have created [description of final artefact].

**Learning Outcomes:**

- [Outcome 1]
- [Outcome 2]
- [Outcome 3]

---

## Prerequisites

Before starting this tutorial, you should:

- [ ] [Prerequisite skill or knowledge 1]
- [ ] [Prerequisite skill or knowledge 2]
- [ ] [Have completed: [Previous unit or module if applicable]]

**Tools Required:**

- A modern web browser (Chrome, Firefox, Safari, or Edge)
- A text editor (e.g., VS Code, Sublime Text, or any plain-text editor)
- [Any other specific tools]

---

## Concept Overview

**What Is [Key Concept]?**
[Clear explanation of the main concept(s) covered in this tutorial, written in student-friendly language.]

**Why Does It Matter?**
[Real-world relevance or problem this concept solves.]

**How Does It Work?**
[High-level explanation of mechanism or process.]

**Visual Diagram:**

```
[ASCII diagram, flowchart, or reference to image in assets/]
Example:
┌─────────────┐
│   Browser   │
├─────────────┤
│  HTML File  │
│  CSS File   │
│  JS File    │
└─────────────┘
```

---

## Step-by-Step Implementation

### Step 1: [Step Title]

**Objective:** [What this step accomplishes]

**Instructions:**

1. [Action 1, e.g., "Create a new file named `index.html`."]
2. [Action 2]
3. [Action 3]

**Code:**

```html
<!-- File: index.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>[Page Title]</title>
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

**Expected Result:**

- Open `index.html` in your browser.
- You should see: [Description of what appears, e.g., "A heading that says 'Hello, World!'"]

**Why It Matters:**
[Explanation of why this step is important and how it connects to the concept.]

**Common Pitfall:**
⚠️ **Watch Out:** [Describe a common mistake students make at this step.]  
✅ **Tip:** [How to avoid or fix it.]

**Quick Self-Check:**

- [ ] [Checkpoint question, e.g., "Does your file save with `.html` extension?"]
- [ ] [Checkpoint question, e.g., "Does the browser display your heading?"]

---

### Step 2: [Step Title]

**Objective:** [What this step adds or changes]

**Instructions:**

1. [Action]
2. [Action]

**Code:**

```css
/* File: styles.css */
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  color: #333;
}

h1 {
  color: #0066cc;
}
```

**Link the CSS:**
Add this line inside the `<head>` section of your `index.html`:

```html
<link rel="stylesheet" href="styles.css" />
```

**Expected Result:**

- Refresh your browser.
- The background should now be light gray, and the heading should be blue.

**Why It Matters:**
[Explain how separating structure (HTML) and style (CSS) improves maintainability.]

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting to link the CSS file or misspelling the filename.  
✅ **Tip:** Double-check the `href` path matches your file name exactly.

**Quick Self-Check:**

- [ ] Does the page styling change when you refresh?
- [ ] Did you save both `index.html` and `styles.css`?

---

### Step 3: [Step Title]

**Objective:** [What this step completes or extends]

**Instructions:**

1. [Action]
2. [Action]

**Code:**

```javascript
// File: script.js
console.log("Hello from JavaScript!");

document.addEventListener("DOMContentLoaded", function () {
  const heading = document.querySelector("h1");
  heading.textContent = "Welcome to the Digital Proficiency Kit!";
});
```

**Link the JavaScript:**
Add this line just before the closing `</body>` tag in `index.html`:

```html
<script src="script.js"></script>
```

**Expected Result:**

- Refresh your browser.
- The heading should now say "Welcome to the Digital Proficiency Kit!"
- Open the browser console (F12 or right-click → Inspect → Console) and you should see: `Hello from JavaScript!`

**Why It Matters:**
[Explain how JavaScript adds interactivity and dynamic behavior.]

**Common Pitfall:**
⚠️ **Watch Out:** Placing the `<script>` tag in the `<head>` before the DOM loads can cause the code to fail.  
✅ **Tip:** Always place script tags at the end of `<body>` or use `DOMContentLoaded`.

**Quick Self-Check:**

- [ ] Does the heading text change?
- [ ] Do you see the console message?

---

### Step 4: [Optional Extension or Final Touch]

**Objective:** [What this optional step adds]

**Instructions:**

1. [Action]
2. [Action]

**Code:**

```html
<!-- Add an image -->
<img src="assets/logo.png" alt="Digital Proficiency Kit Logo" width="200" />
```

**Expected Result:**
[What appears when you add this element.]

**Why It Matters:**
[Explain importance of semantic HTML and accessibility (alt text).]

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting the `alt` attribute makes images inaccessible to screen readers.  
✅ **Tip:** Always include descriptive `alt` text.

---

## Debugging Section

**Scenario 1: Page is blank / nothing displays**

- **Possible Cause:** File not saved, or browser cache issue.
- **Solution:** Save all files and hard-refresh (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows).

**Scenario 2: CSS not applying**

- **Possible Cause:** Incorrect file path in `<link>` tag, or typo in filename.
- **Solution:** Check `href` matches file name exactly (case-sensitive!).

**Scenario 3: JavaScript not running**

- **Possible Cause:** Script placed in `<head>` before DOM loads, or syntax error.
- **Solution:** Move `<script>` to end of `<body>` and check console for error messages.

**General Debugging Tips:**

- Open browser developer tools (F12).
- Check the Console tab for error messages.
- Use `console.log()` to test if code is running.
- Validate HTML with [W3C Validator](https://validator.w3.org/).

---

## Consolidated Full Code

**File: `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>[Page Title]</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Hello, World!</h1>
    <img src="assets/logo.png" alt="Digital Proficiency Kit Logo" width="200" />
    <script src="script.js"></script>
  </body>
</html>
```

**File: `styles.css`**

```css
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  color: #333;
}

h1 {
  color: #0066cc;
}
```

**File: `script.js`**

```javascript
console.log("Hello from JavaScript!");

document.addEventListener("DOMContentLoaded", function () {
  const heading = document.querySelector("h1");
  heading.textContent = "Welcome to the Digital Proficiency Kit!";
});
```

---

## Practice Variations

**Variation 1: Change the Theme**

- Modify `styles.css` to use a dark theme (dark background, light text).
- Test for sufficient contrast using browser Lighthouse audit.

**Variation 2: Add Interactivity**

- Add a button that, when clicked, changes the heading text.
- Hint: Use `addEventListener('click', ...)`.

**Variation 3: Semantic Structure**

- Wrap the heading and image in a `<header>` element.
- Add a `<main>` section with a paragraph of text.

---

## Reflection Prompts

1. **What was the most challenging part of this tutorial?**

   - [Space for student response]

2. **What's one thing you're proud of learning or creating?**

   - [Space for student response]

3. **How could you apply these skills to a project you care about?**
   - [Space for student response]

---

## Further Reading

**Official Documentation:**

- [MDN Web Docs: HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [MDN Web Docs: CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [MDN Web Docs: JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

**Related Tutorials:**

- [Link to previous unit tutorial]
- [Link to next unit tutorial]

**Advanced Topics:**

- [Link to extension topic, e.g., "CSS Grid Layout"]
- [Link to related DPK module]

---

## Accessibility Considerations

**This Tutorial Emphasized:**

- ✅ Semantic HTML (`<h1>`, `<header>`, etc.)
- ✅ `alt` attributes on images
- ✅ Sufficient color contrast (check with Lighthouse)

**Additional Accessibility Checks:**

- [ ] Keyboard navigation: Can you tab through interactive elements?
- [ ] Screen reader test: Does content make sense when read aloud?
- [ ] Responsive design: Does the page work on mobile and desktop?

**Resources:**

- [WebAIM: Introduction to Web Accessibility](https://webaim.org/intro/)
- [WAVE Accessibility Evaluation Tool](https://wave.webaim.org/)

---

## Metadata

**Module:** [Module Number & Title]  
**Unit:** X.Y — [Unit Title]  
**Author:** [Name]  
**Contributors:** [Names, if any]  
**License:** CC BY-SA 4.0  
**Repository:** [Link to dpk-learning-materials repo]

---

<!-- End of Tutorial Template -->
