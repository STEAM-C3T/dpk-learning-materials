# Tutorial: Unit 3.1 — CSS Fundamentals

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.1 — CSS Fundamentals  
**Estimated Time:** 50–65 minutes  
**Author:** Digital Proficiency Kit Team  
**Last Updated:** 2025-11-18

---

## Overview

**What You Will Learn:**
In this tutorial, you will learn CSS basics including selectors, properties, the box model, typography, and color systems.

**What You Will Build:**
A styled personal profile page demonstrating CSS fundamentals with custom colors, fonts, spacing, and layout.

**Learning Outcomes:**

- Write CSS using selectors, properties, and values
- Apply the box model (margin, border, padding, content)
- Style typography with font properties
- Use color systems (named, hex, RGB, HSL)
- Link external stylesheets and use inline/internal CSS

---

## Prerequisites

Before starting this tutorial, you should:

- [ ] Have completed Module 02 or be familiar with HTML structure
- [ ] Know how to create HTML files
- [ ] Understand basic HTML elements (headings, paragraphs, divs)

**Tools Required:**

- Text editor (VS Code, Notepad++, or similar)
- Modern web browser with DevTools

---

## Concept Overview

**What is CSS?**
Cascading Style Sheets (CSS) control the presentation and layout of HTML. While HTML provides structure, CSS provides style.

**CSS Syntax:**

```css
selector {
  property: value;
}
```

**Three Ways to Add CSS:**

1. **External:** Separate `.css` file (recommended)
2. **Internal:** `<style>` tag in HTML `<head>`
3. **Inline:** `style` attribute on element (avoid except for testing)

**The Cascade:**
When multiple rules apply, specificity and source order determine which wins.

---

## Step-by-Step Guide

### Step 1: Create HTML Structure

**Objective:** Set up an HTML file ready for styling.

**Instructions:**

1. Create `profile.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My Profile</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header>
      <h1>Alex Chen</h1>
      <p class="subtitle">Web Developer & Designer</p>
    </header>

    <main>
      <section class="about">
        <h2>About Me</h2>
        <p>
          I'm a student passionate about creating accessible, beautiful
          websites. I love combining creativity with technology.
        </p>
      </section>

      <section class="skills">
        <h2>Skills</h2>
        <ul>
          <li>HTML5</li>
          <li>CSS3</li>
          <li>JavaScript</li>
          <li>Web Accessibility</li>
        </ul>
      </section>

      <section id="contact">
        <h2>Contact</h2>
        <p>Email: <a href="mailto:alex@example.com">alex@example.com</a></p>
      </section>
    </main>

    <footer>
      <p>&copy; 2025 Alex Chen</p>
    </footer>
  </body>
</html>
```

**Expected Result:**

- Unstyled HTML page displays
- Content visible but no custom styling yet

**Why This Step:**
Starting with semantic HTML ensures proper structure before adding style.

**Quick Self-Check:**

- [ ] File opens in browser
- [ ] All content visible
- [ ] Linked stylesheet reference present

---

### Step 2: Create External Stylesheet

**Objective:** Set up a CSS file and apply basic element selectors.

**Instructions:**

1. Create `styles.css` in the same folder:

```css
/* Element Selectors */
body {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  color: #333333;
  background-color: #f4f4f4;
}

h1 {
  color: #2c3e50;
  font-size: 2.5em;
}

h2 {
  color: #34495e;
  font-size: 1.8em;
  border-bottom: 2px solid #3498db;
  padding-bottom: 0.5em;
}

p {
  margin-bottom: 1em;
}

a {
  color: #3498db;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
```

**Expected Result:**

- Page now has custom fonts and colors
- Headings styled differently
- Links change on hover

**Why This Step:**
Element selectors apply styles to all instances of an element type.

**Common Pitfall:**
⚠️ **Watch Out:** CSS file not in same folder as HTML → styles don't load.  
✅ **Tip:** Check browser DevTools → Network tab for 404 errors.

**Quick Self-Check:**

- [ ] Background changed to light gray
- [ ] Headings have custom colors
- [ ] Link underlines appear on hover

---

### Step 3: Apply Class and ID Selectors

**Objective:** Use classes and IDs for specific styling.

**Instructions:**

Add to `styles.css`:

```css
/* Class Selectors */
.subtitle {
  font-size: 1.2em;
  color: #7f8c8d;
  font-style: italic;
}

.about {
  background-color: #ffffff;
  padding: 20px;
  margin-bottom: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.skills {
  background-color: #ffffff;
  padding: 20px;
  margin-bottom: 20px;
  border-radius: 8px;
}

.skills ul {
  list-style-type: none;
  padding-left: 0;
}

.skills li {
  background-color: #3498db;
  color: #ffffff;
  padding: 10px;
  margin-bottom: 8px;
  border-radius: 4px;
}

/* ID Selector */
#contact {
  background-color: #ecf0f1;
  padding: 20px;
  border-radius: 8px;
  border-left: 4px solid #e74c3c;
}
```

**Expected Result:**

- Subtitle appears italic and gray
- Sections have white backgrounds with shadows
- Skills display as colored boxes
- Contact section has distinctive left border

**Why This Step:**

- **Classes** (`.classname`): Reusable styles for multiple elements
- **IDs** (`#idname`): Unique styles for single elements
- Classes more flexible than IDs for styling

**Common Pitfall:**
⚠️ **Watch Out:** Using `#` for class or `.` for ID.  
✅ **Tip:** Classes start with `.`, IDs start with `#`.

**Quick Self-Check:**

- [ ] Sections have white backgrounds
- [ ] Skills appear as colored boxes
- [ ] Contact section has red left border

---

### Step 4: Understand the Box Model

**Objective:** Apply margin, border, padding to control spacing.

**Instructions:**

Add to `styles.css`:

```css
/* Box Model Demonstration */
header {
  background-color: #2c3e50;
  color: #ffffff;
  padding: 40px 20px; /* top/bottom left/right */
  margin-bottom: 30px;
  text-align: center;
}

header h1 {
  color: #ffffff;
  margin: 0 0 10px 0; /* top right bottom left */
}

main {
  max-width: 800px;
  margin: 0 auto; /* center the main content */
  padding: 0 20px;
}

footer {
  background-color: #34495e;
  color: #ffffff;
  text-align: center;
  padding: 20px;
  margin-top: 40px;
}
```

**Expected Result:**

- Header has dark background with padding
- Main content centered with max-width
- Footer at bottom with spacing above

**Why This Step:**
The box model controls element dimensions:

- **Content:** The actual content (text, images)
- **Padding:** Space between content and border
- **Border:** Line around padding
- **Margin:** Space outside border

**Visual Box Model:**

```
┌─── Margin ────────────────────┐
│ ┌─── Border ─────────────────┐│
│ │ ┌─── Padding ───────────┐ ││
│ │ │                       │ ││
│ │ │      Content          │ ││
│ │ │                       │ ││
│ │ └───────────────────────┘ ││
│ └───────────────────────────┘│
└───────────────────────────────┘
```

**Common Pitfall:**
⚠️ **Watch Out:** Confusing margin and padding.  
✅ **Tip:** Padding inside, margin outside. Use DevTools box model visualizer.

**Quick Self-Check:**

- [ ] Header has dark background with white text
- [ ] Content doesn't touch browser edges
- [ ] Footer separated from content above

---

### Step 5: Work with Color Systems

**Objective:** Use different color formats (named, hex, RGB, HSL).

**Instructions:**

Add to `styles.css`:

```css
/* Color Systems Examples */

/* Named Colors */
.example-named {
  background-color: lightblue;
  color: darkslategray;
}

/* Hexadecimal Colors */
.example-hex {
  background-color: #3498db; /* blue */
  color: #ffffff; /* white */
}

/* RGB Colors */
.example-rgb {
  background-color: rgb(52, 152, 219); /* same blue */
  color: rgb(255, 255, 255); /* white */
}

/* RGBA (with alpha/transparency) */
.example-rgba {
  background-color: rgba(52, 152, 219, 0.7); /* 70% opacity */
  color: rgba(0, 0, 0, 0.9);
}

/* HSL Colors */
.example-hsl {
  background-color: hsl(204, 70%, 53%); /* same blue */
  color: hsl(0, 0%, 100%); /* white */
}
```

**Expected Result:**
Different ways to specify the same colors work identically.

**Why This Step:**
Understanding color systems gives flexibility:

- **Named:** Easy to remember (red, blue, green)
- **Hex:** Common in design (#RRGGBB)
- **RGB:** Red, Green, Blue values (0-255)
- **RGBA:** RGB with alpha (transparency)
- **HSL:** Hue, Saturation, Lightness (intuitive adjustments)

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting `#` before hex values.  
✅ **Tip:** Hex always starts with `#`.

**Quick Self-Check:**

- [ ] Understand each color format
- [ ] Can convert between formats using DevTools color picker

---

### Step 6: Style Typography

**Objective:** Control fonts, sizes, weights, and spacing.

**Instructions:**

Add to `styles.css`:

```css
/* Typography Styling */
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-size: 16px; /* base font size */
}

h1 {
  font-weight: 700; /* bold */
  letter-spacing: -1px;
  text-transform: uppercase;
}

h2 {
  font-weight: 600; /* semi-bold */
  margin-top: 0;
}

.subtitle {
  font-size: 1.2em; /* relative to parent */
  font-weight: 300; /* light */
  letter-spacing: 0.5px;
}

.about p {
  font-size: 1.1em;
  line-height: 1.8; /* spacing between lines */
  text-align: justify;
}

footer p {
  font-size: 0.9em;
  margin: 0;
}
```

**Expected Result:**

- Custom font stack applied
- Headings have different weights
- Text spacing improved for readability

**Why This Step:**
Typography significantly impacts readability and aesthetics.

**Key Properties:**

- `font-family`: Specify fonts (with fallbacks)
- `font-size`: Size (px, em, rem, %)
- `font-weight`: Boldness (100-900 or keywords)
- `line-height`: Space between lines
- `letter-spacing`: Space between characters
- `text-transform`: Uppercase, lowercase, capitalize

**Common Pitfall:**
⚠️ **Watch Out:** Font stack without fallback → defaults to system if font unavailable.  
✅ **Tip:** Always end font stack with generic family (sans-serif, serif).

**Quick Self-Check:**

- [ ] Headings visually distinct
- [ ] Body text readable
- [ ] Different font weights applied

---

### Step 7: Add Borders and Shadows

**Objective:** Use borders, border-radius, and box-shadow for depth.

**Instructions:**

Update existing styles in `styles.css`:

```css
/* Enhanced Sections with Borders and Shadows */
.about,
.skills {
  border: 1px solid #dfe6e9;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease;
}

.about:hover,
.skills:hover {
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}

.skills li {
  border: 2px solid #2980b9;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

#contact {
  border: 2px solid #e74c3c;
  border-radius: 12px;
}
```

**Expected Result:**

- Sections have subtle shadows
- Shadows intensify on hover
- Contact section has rounded corners

**Why This Step:**
Visual depth makes interfaces more engaging and helps establish visual hierarchy.

**Border Properties:**

- `border`: Shorthand (width style color)
- `border-radius`: Rounded corners
- `box-shadow`: X Y blur spread color

**Common Pitfall:**
⚠️ **Watch Out:** Too many shadows → cluttered design.  
✅ **Tip:** Use shadows sparingly for emphasis.

**Quick Self-Check:**

- [ ] Sections have visible borders
- [ ] Shadows create depth
- [ ] Hover effects work

---

## Debugging Section

**Scenario 1: Styles not applying**

- **Possible Causes:**
  - CSS file not linked correctly
  - Typo in selector
  - More specific rule overriding
- **Solution:**
  - Check `<link>` tag in HTML
  - Inspect element in DevTools → see which rules apply
  - Check for typos in class/ID names

**Scenario 2: Colors look different than expected**

- **Possible Cause:** Wrong color format or typo
- **Solution:** Use DevTools color picker to verify values

**Scenario 3: Box model spacing incorrect**

- **Possible Cause:** Confusing margin and padding
- **Solution:** Use DevTools → Elements → Computed → Box Model diagram

**Scenario 4: Fonts not displaying**

- **Possible Cause:** Font name misspelled or not available
- **Solution:** Check DevTools → Computed → font-family shows actual font used

**General Debugging Tips:**

- **Chrome DevTools:** F12 → Elements → Styles panel
- **Inspect Element:** Right-click element → Inspect
- **Toggle Properties:** Click checkbox next to property to disable/enable
- **Edit Live:** Change values in DevTools to test before updating file

---

## Consolidated Key Concepts

**1. CSS Syntax**

```css
selector {
  property: value;
}
```

**2. Three Types of Selectors**

- Element: `p { }`
- Class: `.classname { }`
- ID: `#idname { }`

**3. The Box Model**

- Content → Padding → Border → Margin (outside to inside)

**4. Color Formats**

- Named: `red`
- Hex: `#ff0000`
- RGB: `rgb(255, 0, 0)`
- HSL: `hsl(0, 100%, 50%)`

**5. Typography Properties**

- `font-family`, `font-size`, `font-weight`
- `line-height`, `letter-spacing`, `text-transform`

---

## Practice Variations

**Variation 1: Color Scheme**

- Choose a color palette (use tools like coolors.co)
- Replace all colors with your palette
- Maintain contrast for accessibility

**Variation 2: Different Layout**

- Change header to left-aligned instead of centered
- Make skills display in columns using float or inline-block
- Add a sidebar section

**Variation 3: Advanced Styling**

- Add Google Fonts instead of system fonts
- Create gradient backgrounds
- Add hover effects to links and buttons

---

## Reflection Prompts

1. **How does the box model help you control layout?**

   - [Space for student response]

2. **Why use external stylesheets instead of inline styles?**

   - [Space for student response]

3. **What's the difference between margin and padding?**
   - [Space for student response]

---

## Further Reading

**Official Documentation:**

- [MDN: CSS Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)
- [MDN: The Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
- [MDN: CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)

**Related Tutorials:**

- Previous: Module 02 — HTML Foundations
- Next: Unit 3.2 — Responsive Layouts

**Advanced Topics:**

- CSS specificity and the cascade
- CSS custom properties (variables)
- CSS preprocessors (Sass, Less)

---

## Accessibility Considerations

**This Tutorial Emphasized:**

- ✅ Sufficient color contrast for readability
- ✅ Relative units (em, %) for scalable text
- ✅ Clear visual hierarchy with typography
- ✅ Hover states for interactive elements

**Color Contrast:**

- WCAG requires 4.5:1 contrast ratio for normal text
- Use tools like WebAIM Contrast Checker
- Don't rely on color alone to convey information

**Next Steps:**

- In Unit 3.2, you'll learn responsive design for all devices

---

## Metadata

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.1 — CSS Fundamentals  
**Author:** Digital Proficiency Kit Team  
**Contributors:** N/A  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Unit 3.1 Tutorial -->
