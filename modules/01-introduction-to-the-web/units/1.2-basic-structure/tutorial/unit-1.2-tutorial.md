# Tutorial: Unit 1.2 — Basic HTML Structure

**Module:** 01 — Introduction to the Web  
**Unit:** 1.2 — Basic HTML Structure  
**Duration:** 60–90 minutes  
**Prerequisites:** Unit 1.1 (What Is the Web?)

---

## Learning Objectives

By the end of this tutorial, you will be able to:

1. **Create** a complete HTML document with proper structure.
2. **Use** semantic HTML tags (`<header>`, `<main>`, `<footer>`).
3. **Add** headings, paragraphs, lists, images, and links.
4. **Test** your HTML page in a web browser.

---

## Overview

This tutorial walks you through creating your first HTML page from scratch. You'll learn the essential document structure, add common content elements, and see your work come to life in a browser.

**What You'll Build:**
A simple "About Me" webpage with:
- Document structure (DOCTYPE, html, head, body)
- Semantic sections
- Heading, paragraphs, list, image, link

---

## Part 1: Setting Up Your HTML File

### Step 1.1: Create a New File

1. Open your text editor (VS Code, Sublime Text, or similar).
2. Create a new file.
3. Save it as `index.html` in a dedicated folder (e.g., `my-first-webpage`).

**Why `index.html`?**  
Web servers default to serving `index.html` as the homepage of a directory.

---

### Step 1.2: Add the Document Structure

Type the following foundation into your `index.html` file:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Me</title>
  </head>
  <body>
    
  </body>
</html>
```

**What Each Part Does:**

| Element | Purpose |
|---------|---------|
| `<!DOCTYPE html>` | Declares this is an HTML5 document |
| `<html lang="en">` | Root element; `lang` sets language to English |
| `<head>` | Contains metadata (title, character set, viewport settings) |
| `<meta charset="UTF-8">` | Ensures proper text encoding |
| `<meta name="viewport"...>` | Makes page responsive on mobile devices |
| `<title>` | Text shown in browser tab |
| `<body>` | All visible page content goes here |

**Save your file** (Cmd+S / Ctrl+S).

---

### Step 1.3: Test in Browser

1. Right-click `index.html` in your file explorer.
2. Select "Open with" → your web browser.
3. You should see a blank page with "About Me" in the tab.

**Checkpoint:** If you see the title in the browser tab, you're on the right track!

---

## Part 2: Adding Semantic Structure

Semantic tags give meaning to different parts of your page, improving accessibility and SEO.

### Step 2.1: Add a Header

Inside the `<body>` tags, add:

```html
<header>
  <h1>Welcome to My Page</h1>
</header>
```

**Explanation:**
- `<header>`: Semantic container for introductory content
- `<h1>`: The main heading (only one per page)

---

### Step 2.2: Add Main Content Area

Below the `<header>`, add:

```html
<main>
  <h2>About Me</h2>
  <p>Hello! I'm a student learning web development.</p>
</main>
```

**Explanation:**
- `<main>`: Contains the primary content of the page
- `<h2>`: Second-level heading
- `<p>`: Paragraph of text

---

### Step 2.3: Add a Footer

Below the `<main>`, add:

```html
<footer>
  <p>&copy; 2025 My First Webpage</p>
</footer>
```

**Explanation:**
- `<footer>`: Semantic container for footer content
- `&copy;`: HTML entity for copyright symbol ©

**Full `<body>` so far:**

```html
<body>
  <header>
    <h1>Welcome to My Page</h1>
  </header>
  
  <main>
    <h2>About Me</h2>
    <p>Hello! I'm a student learning web development.</p>
  </main>
  
  <footer>
    <p>&copy; 2025 My First Webpage</p>
  </footer>
</body>
```

**Save and refresh your browser.** You should see headings and text!

---

## Part 3: Adding Content Elements

### Step 3.1: Add More Paragraphs

Inside `<main>`, after the first paragraph, add:

```html
<p>I enjoy coding, reading, and exploring new technologies.</p>
```

**Tip:** Browsers automatically add spacing between paragraphs.

---

### Step 3.2: Add a List

Add a list of your favorite hobbies:

```html
<h3>My Hobbies</h3>
<ul>
  <li>Coding</li>
  <li>Reading</li>
  <li>Hiking</li>
</ul>
```

**Explanation:**
- `<h3>`: Third-level heading
- `<ul>`: Unordered (bulleted) list
- `<li>`: List item

**Alternative:** Use `<ol>` for a numbered (ordered) list.

---

### Step 3.3: Add an Image

Add an image after your list:

```html
<h3>A Photo I Like</h3>
<img src="photo.jpg" alt="A beautiful landscape">
```

**Important:**
- Replace `photo.jpg` with the path to an actual image file in your folder.
- The `alt` attribute describes the image for screen readers (accessibility).

**Common Issue:** If the image doesn't show, check:
- Is the image file in the same folder as `index.html`?
- Is the filename spelled correctly (including extension)?

---

### Step 3.4: Add a Link

Add a link to an external website:

```html
<p>Learn more about web development at 
<a href="https://developer.mozilla.org">MDN Web Docs</a>.</p>
```

**Explanation:**
- `<a>`: Anchor (link) element
- `href`: Hypertext reference (destination URL)
- Text between `<a>` and `</a>` is clickable

**Save and refresh.** Click the link to test it!

---

## Part 4: Full Code Review

Your complete `index.html` should look like this:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Me</title>
  </head>
  <body>
    <header>
      <h1>Welcome to My Page</h1>
    </header>
    
    <main>
      <h2>About Me</h2>
      <p>Hello! I'm a student learning web development.</p>
      <p>I enjoy coding, reading, and exploring new technologies.</p>
      
      <h3>My Hobbies</h3>
      <ul>
        <li>Coding</li>
        <li>Reading</li>
        <li>Hiking</li>
      </ul>
      
      <h3>A Photo I Like</h3>
      <img src="photo.jpg" alt="A beautiful landscape">
      
      <p>Learn more about web development at 
      <a href="https://developer.mozilla.org">MDN Web Docs</a>.</p>
    </main>
    
    <footer>
      <p>&copy; 2025 My First Webpage</p>
    </footer>
  </body>
</html>
```

---

## Part 5: Testing & Validation

### Step 5.1: Visual Check

Open your page in multiple browsers (Chrome, Firefox, Safari) to ensure consistent display.

---

### Step 5.2: Validate Your HTML

1. Go to [W3C HTML Validator](https://validator.w3.org/#validate_by_upload)
2. Upload your `index.html` file
3. Fix any errors or warnings

**Common errors:**
- Missing closing tags
- Misspelled tag names
- Missing `alt` attribute on images

---

## Part 6: Common Pitfalls

| Problem | Solution |
|---------|----------|
| Image doesn't display | Check file path and spelling; ensure image is in correct folder |
| Tags not working | Verify opening and closing tags match |
| Page looks different in different browsers | Use semantic HTML and avoid deprecated tags |
| Forgot `alt` on image | Always include descriptive `alt` text for accessibility |

---

## Part 7: Extensions

Ready for more? Try these challenges:

1. **Add another section:** Create a "My Goals" section with an ordered list.
2. **Link to another page:** Create a second HTML file (`about.html`) and link to it from your homepage.
3. **Experiment with headings:** Add `<h4>`, `<h5>`, and `<h6>` to see hierarchy.
4. **Add more images:** Create a small gallery with 3 images and captions.

---

## Reflection Questions

1. What was the most challenging part of creating your HTML page?
2. Why is it important to use semantic tags like `<header>`, `<main>`, and `<footer>`?
3. How does the `alt` attribute improve accessibility?
4. What would you like to add to your page next?

---

## Key Takeaways

- Every HTML document needs `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>`.
- Semantic tags (`<header>`, `<main>`, `<footer>`) improve structure and accessibility.
- Headings create hierarchy; use only one `<h1>` per page.
- Always include `alt` text on images for screen readers.
- Test your page in a browser frequently to catch errors early.

---

## Next Steps

- Complete the **Unit 1.2 Student Workbook** for scaffolded practice.
- Move on to **Module 02: HTML Foundations** to dive deeper into content and accessibility.
- Experiment with your page: add more content, try different tags, and make it your own!

---

## Resources

- [MDN: HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
- [W3C HTML Validator](https://validator.w3.org/)
- [WebAIM: Semantic Structure](https://webaim.org/articles/semanticstructure/)
- [HTML5 Element Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

---

**Version 1.0 — 2025-11-18**  
Prepared by assistant (review for classroom adaptation)

<!-- End Tutorial: Unit 1.2 -->
