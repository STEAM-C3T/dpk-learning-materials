# Tutorial: Unit 2.1 — Building Content

**Module:** 02 — HTML Foundations  
**Unit:** 2.1 — Building Content  
**Estimated Time:** 45–60 minutes  
**Author:** Digital Proficiency Kit Team  
**Last Updated:** 2025-11-18

---

## Overview

**What You Will Learn:**
In this tutorial, you will learn to structure content using semantic HTML elements including headings, paragraphs, lists, links, and images.

**What You Will Build:**
A well-structured content page about a topic of your choice, using proper heading hierarchy, lists, descriptive links, and images with alt text.

**Learning Outcomes:**

- Use headings to create clear document hierarchy
- Add paragraphs, lists, links, and images with proper markup
- Write descriptive alt text for images
- Structure content semantically for accessibility

---

## Prerequisites

Before starting this tutorial, you should:

- [ ] Have completed Module 01 or be familiar with basic HTML structure
- [ ] Know how to create and save an HTML file
- [ ] Have access to a text editor and web browser

**Tools Required:**

- Text editor (VS Code, Notepad++, or similar)
- Modern web browser

---

## Concept Overview

**Why Semantic HTML Matters:**
Semantic HTML uses tags that describe the meaning of content, not just its appearance. This helps:

- Screen readers navigate content
- Search engines understand page structure
- Developers maintain and update code

**Core Content Elements:**

- **Headings** (`<h1>` through `<h6>`): Create document structure
- **Paragraphs** (`<p>`): Group text into logical blocks
- **Lists** (`<ul>`, `<ol>`, `<li>`): Organize related items
- **Links** (`<a>`): Connect to other pages or resources
- **Images** (`<img>`): Add visual content with accessibility

---

## Step-by-Step Guide

### Step 1: Create Your HTML File

**Objective:** Set up a basic HTML document structure.

**Instructions:**

1. Open your text editor
2. Create a new file named `my-topic-page.html`
3. Type the following basic structure:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My Topic Page</title>
  </head>
  <body></body>
</html>
```

**Expected Result:**

- A valid HTML file that opens in your browser (currently blank)

**Why This Step:**
The DOCTYPE, meta tags, and structure create a standards-compliant foundation.

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting the closing tags (`</head>`, `</body>`, `</html>`).  
✅ **Tip:** Most editors auto-complete tags. Use them!

**Quick Self-Check:**

- [ ] File saved with `.html` extension
- [ ] Opens in browser without errors

---

### Step 2: Add a Heading Hierarchy

**Objective:** Create a clear document structure using headings.

**Instructions:**

1. Inside the `<body>` tag, add a main heading:

```html
<h1>My Favorite Hobby: Photography</h1>
```

2. Add section headings:

```html
<h2>Why I Love Photography</h2>

<h2>Types of Photography</h2>

<h3>Landscape Photography</h3>

<h3>Portrait Photography</h3>

<h2>Getting Started</h2>
```

**Expected Result:**

- Headings display in decreasing size (`<h1>` largest, `<h3>` smaller)
- Clear visual hierarchy

**Why This Step:**

- `<h1>` = page title (use once per page)
- `<h2>` = major sections
- `<h3>` = subsections within `<h2>`
- Never skip levels (don't jump from `<h1>` to `<h3>`)

**Common Pitfall:**
⚠️ **Watch Out:** Using headings for styling instead of structure (e.g., `<h3>` for small text).  
✅ **Tip:** Use CSS for styling; headings are for structure.

**Quick Self-Check:**

- [ ] One `<h1>` per page
- [ ] Headings follow logical order
- [ ] No skipped heading levels

---

### Step 3: Add Paragraphs

**Objective:** Add text content in paragraph blocks.

**Instructions:**

Under each heading, add paragraphs:

```html
<h2>Why I Love Photography</h2>
<p>
  Photography allows me to capture moments and express creativity. It teaches
  patience and observation skills.
</p>
<p>
  Every photo tells a story and preserves memories that might otherwise be
  forgotten.
</p>

<h2>Types of Photography</h2>
<p>
  There are many different styles of photography, each with its own techniques
  and challenges.
</p>

<h3>Landscape Photography</h3>
<p>
  Landscape photography focuses on capturing natural scenes like mountains,
  oceans, and forests.
</p>

<h3>Portrait Photography</h3>
<p>
  Portrait photography captures the personality and mood of individuals or
  groups.
</p>
```

**Expected Result:**

- Text appears in readable blocks
- Space between paragraphs

**Why This Step:**
Paragraphs (`<p>`) group related sentences and improve readability.

**Common Pitfall:**
⚠️ **Watch Out:** Using `<br>` tags instead of paragraphs for spacing.  
✅ **Tip:** Use `<p>` for semantic structure; style spacing with CSS.

**Quick Self-Check:**

- [ ] Each paragraph wrapped in `<p>` tags
- [ ] Paragraphs contain related content

---

### Step 4: Add Lists

**Objective:** Organize items using unordered and ordered lists.

**Instructions:**

Add an unordered list:

```html
<h2>Getting Started</h2>
<p>Here's what you need to begin:</p>
<ul>
  <li>A camera (even a smartphone works)</li>
  <li>Curiosity and willingness to experiment</li>
  <li>Time to practice regularly</li>
</ul>
```

Add an ordered list:

```html
<p>Steps to take a great photo:</p>
<ol>
  <li>Find interesting light</li>
  <li>Choose your subject</li>
  <li>Frame your composition</li>
  <li>Adjust settings and take the shot</li>
</ol>
```

**Expected Result:**

- Unordered list shows bullets
- Ordered list shows numbers

**Why This Step:**

- `<ul>` = unordered (bullets) for items without sequence
- `<ol>` = ordered (numbers) for sequential items
- `<li>` = list item (used in both)

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting to wrap `<li>` items in `<ul>` or `<ol>`.  
✅ **Tip:** List items must be inside a list container.

**Quick Self-Check:**

- [ ] Used `<ul>` for non-sequential items
- [ ] Used `<ol>` for sequential steps
- [ ] All items wrapped in `<li>`

---

### Step 5: Add Links

**Objective:** Connect to other pages or resources.

**Instructions:**

Add internal and external links:

```html
<p>Learn more about photography from these resources:</p>
<ul>
  <li>
    <a href="https://www.nationalgeographic.com/photography"
      >National Geographic Photography</a
    >
  </li>
  <li>
    <a href="https://digital-photography-school.com"
      >Digital Photography School</a
    >
  </li>
</ul>

<p>Want to see more? Check out my <a href="gallery.html">photo gallery</a>.</p>
```

**Expected Result:**

- Links appear underlined (default browser style)
- Clicking external links opens websites
- Clicking internal link looks for `gallery.html`

**Why This Step:**
Links (`<a>` = anchor) connect pages and resources:

- `href` attribute specifies destination
- Link text should be descriptive ("Read tutorial" not "click here")

**Common Pitfall:**
⚠️ **Watch Out:** Using "click here" or "read more" as link text.  
✅ **Tip:** Use descriptive text that makes sense out of context.

**Quick Self-Check:**

- [ ] All links have `href` attribute
- [ ] Link text is descriptive
- [ ] External links use full URLs (https://)

---

### Step 6: Add Images

**Objective:** Include images with accessible alt text.

**Instructions:**

Add an image:

```html
<h3>Landscape Photography</h3>
<img
  src="mountain-sunset.jpg"
  alt="Orange sunset over snow-capped mountains with dark silhouettes in foreground"
/>
<p>
  Landscape photography focuses on capturing natural scenes like mountains,
  oceans, and forests.
</p>
```

Add another with a figure and caption:

```html
<figure>
  <img
    src="portrait-example.jpg"
    alt="Black and white portrait of elderly woman smiling, showing deep laugh lines"
  />
  <figcaption>
    Example of portrait photography showing emotion and character
  </figcaption>
</figure>
```

**Expected Result:**

- Images display (if files exist in same folder)
- Alt text shows if image fails to load
- Caption appears below figure

**Why This Step:**

- `<img>` embeds images
- `src` = file path
- `alt` = text description for accessibility
- `<figure>` and `<figcaption>` group image with caption

**Common Pitfall:**
⚠️ **Watch Out:** Empty or missing `alt` attributes.  
✅ **Tip:** Describe what's in the image. If decorative, use `alt=""`.

**Quick Self-Check:**

- [ ] All images have `alt` attribute
- [ ] Alt text describes image content
- [ ] Image paths are correct

---

## Debugging Section

**Scenario 1: Headings don't show hierarchy**

- **Possible Cause:** Skipped heading levels or too many `<h1>` tags
- **Solution:** Check heading order; use one `<h1>`, then `<h2>`, then `<h3>`

**Scenario 2: List items don't display correctly**

- **Possible Cause:** `<li>` tags outside `<ul>` or `<ol>`
- **Solution:** Ensure all `<li>` elements are wrapped in list container

**Scenario 3: Links don't work**

- **Possible Cause:** Missing `href` or incorrect path
- **Solution:** Check `href` attribute; verify file paths for internal links

**Scenario 4: Images don't appear**

- **Possible Cause:** Incorrect file path or missing image file
- **Solution:** Verify image file is in correct folder; check `src` path

**General Debugging Tips:**

- Use browser DevTools (F12) → Elements tab to inspect HTML
- Check console for errors
- Validate HTML at https://validator.w3.org/

---

## Consolidated Key Concepts

**1. Heading Hierarchy**

- One `<h1>` per page (main title)
- Use `<h2>` for sections, `<h3>` for subsections
- Don't skip levels

**2. Semantic Structure**

- `<p>` for paragraphs
- `<ul>` for unordered lists
- `<ol>` for ordered lists
- `<li>` for list items

**3. Links**

- `<a href="url">Descriptive text</a>`
- Use descriptive link text
- External links need full URL

**4. Images**

- `<img src="path" alt="description">`
- Alt text required for accessibility
- `<figure>` and `<figcaption>` for images with captions

---

## Practice Variations

**Variation 1: Add More Sections**

- Add 2–3 more sections with headings and paragraphs
- Include both ordered and unordered lists

**Variation 2: Nested Lists**

- Create a list with sub-items:

```html
<ul>
  <li>
    Equipment
    <ul>
      <li>Camera</li>
      <li>Tripod</li>
      <li>Lenses</li>
    </ul>
  </li>
  <li>Software</li>
</ul>
```

**Variation 3: Multiple Images**

- Add a gallery section with 3–4 images
- Use `<figure>` for each with captions

---

## Reflection Prompts

1. **How does heading hierarchy help readers navigate your page?**

   - [Space for student response]

2. **Why is descriptive alt text important?**

   - [Space for student response]

3. **What's the difference between using `<ul>` and `<ol>`?**
   - [Space for student response]

---

## Further Reading

**Official Documentation:**

- [MDN: HTML Text Fundamentals](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals)
- [MDN: Creating Hyperlinks](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)
- [MDN: Images in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML)

**Related Tutorials:**

- Next: Unit 2.2 — Structuring for Access (Forms and Tables)

**Advanced Topics:**

- Semantic HTML5 elements (`<article>`, `<section>`, `<aside>`)
- Responsive images with `srcset`

---

## Accessibility Considerations

**This Tutorial Emphasized:**

- ✅ Proper heading hierarchy for screen reader navigation
- ✅ Descriptive alt text for images
- ✅ Meaningful link text

**Why Accessibility Matters:**

- Over 1 billion people use assistive technologies
- Semantic structure benefits all users
- Good structure improves SEO

**Next Steps:**

- In Unit 2.2, you'll learn about forms and tables with accessibility

---

## Metadata

**Module:** 02 — HTML Foundations  
**Unit:** 2.1 — Building Content  
**Author:** Digital Proficiency Kit Team  
**Contributors:** N/A  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Unit 2.1 Tutorial -->
