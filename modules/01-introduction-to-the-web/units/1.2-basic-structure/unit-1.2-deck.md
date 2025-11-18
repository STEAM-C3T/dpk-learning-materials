---
marp: true
theme: default
paginate: true
header: "Digital Proficiency Kit | Module 01: Unit 1.2"
footer: "STEAM-C3T | CC BY-SA 4.0"
---

# Unit 1.2: Basic HTML Structure

Module 01: Introduction to the Web

---

## Warm-Up

**Prompt:**
What are the essential parts of an HTML document?

_Think, pair, share your ideas._

---

## Unit Objectives

- Identify the basic structure of an HTML document (doctype, html, head, body)
- Create a simple HTML file with semantic tags
- Explain the purpose of key HTML elements (headings, paragraphs, lists, images)

---

## The HTML Document Structure

Every HTML document has the same foundation:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Page Title</title>
  </head>
  <body>
    <!-- Your content here -->
  </body>
</html>
```

---

## Breaking It Down

| Part | Purpose |
|------|---------|
| `<!DOCTYPE html>` | Tells browser this is HTML5 |
| `<html>` | Root container for entire page |
| `<head>` | Metadata (not visible on page) |
| `<body>` | Visible page content |

---

## The `<head>` Section

Contains information **about** the page:

- `<meta charset="UTF-8">` — character encoding
- `<title>` — page title (appears in browser tab)
- Links to CSS, icons, metadata

**Not displayed** on the page itself.

---

## The `<body>` Section

Contains everything **visible** on the page:

- Headings, paragraphs, images
- Links, lists, tables
- Sections, articles, navigation

This is where content lives.

---

## Semantic HTML Tags

Use tags that **describe** the content:

- `<header>` — site or page header
- `<main>` — primary content
- `<footer>` — site or page footer
- `<article>` — self-contained content
- `<section>` — thematic grouping

_Why?_ Better for accessibility and SEO.

---

## Headings: `<h1>` to `<h6>`

Create hierarchy:

```html
<h1>Main Title</h1>
<h2>Section Title</h2>
<h3>Subsection Title</h3>
```

- Only **one** `<h1>` per page
- Don't skip levels (h1 → h3)

---

## Paragraphs: `<p>`

Group related sentences:

```html
<p>This is a paragraph of text.</p>
<p>Another paragraph here.</p>
```

Browsers add default spacing between paragraphs.

---

## Lists

**Unordered (bullets):**

```html
<ul>
  <li>Item one</li>
  <li>Item two</li>
</ul>
```

**Ordered (numbered):**

```html
<ol>
  <li>First step</li>
  <li>Second step</li>
</ol>
```

---

## Images: `<img>`

```html
<img src="photo.jpg" alt="Description of image">
```

- `src` — path to image file
- `alt` — text description (accessibility)

**Always include `alt` text!**

---

## Links: `<a>`

```html
<a href="https://example.com">Visit Example</a>
```

- `href` — destination URL
- Text between tags is clickable

---

## Code-Along: Your First HTML Page

Let's create `index.html`:

1. Set up document structure
2. Add a heading and paragraph
3. Include a list
4. Add an image
5. Open in browser

---

## Testing in the Browser

**Steps:**
1. Save your `.html` file
2. Right-click → "Open with" → Browser
3. See your page!

**Tip:** Refresh (Cmd+R / Ctrl+R) to see changes.

---

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Forgot closing tag | Every `<tag>` needs `</tag>` |
| Missing `alt` on image | Add descriptive text |
| No `DOCTYPE` | Always start with `<!DOCTYPE html>` |
| Skipped heading levels | Use h1, h2, h3 in order |

---

## Practice: Build a Simple Page

**Task:**
Create a page about your favorite topic with:
- One `<h1>` heading
- Two paragraphs
- A list (ordered or unordered)
- One image with `alt` text

**Time:** 15 minutes

---

## Reflection

- What surprised you about HTML structure?
- Which tag will you use most often?
- How does semantic HTML help accessibility?

---

## Key Takeaways

1. Every HTML document has `<!DOCTYPE>`, `<html>`, `<head>`, and `<body>`
2. Semantic tags (header, main, footer) improve structure
3. Always include `alt` text on images
4. Test your code in a browser frequently

---

## Next Steps

- Unit 1.2 Tutorial: Step-by-step HTML page creation
- Unit 1.2 Workbook: Scaffolded practice and reflection
- Module 02: Dive deeper into HTML content and accessibility

---

## Resources

- [MDN HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
- [W3C HTML Validator](https://validator.w3.org/)
- [WebAIM: Semantic Structure](https://webaim.org/articles/semanticstructure/)

---

**Questions?**

---
