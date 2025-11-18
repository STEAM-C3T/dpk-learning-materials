# Teacher-Annotated Workbook: Unit 1.2 — Basic HTML Structure

**Module:** 01 — Introduction to the Web  
**Unit:** 1.2 — Basic HTML Structure  
**Duration:** 60–90 minutes  
**Prerequisites:** Unit 1.1 (What Is the Web?)

---

## Purpose & Pedagogical Focus

This unit transitions students from conceptual understanding (Unit 1.1) to hands-on HTML coding. The workbook scaffolds independent practice while building confidence with essential HTML structure and semantic tags.

### Key Teaching Aims

| Aim                     | Strategy                                               |
| ----------------------- | ------------------------------------------------------ |
| Build coding confidence | Start with fill-in-the-blank, progress to open-ended   |
| Reinforce semantic HTML | Require `<header>`, `<main>`, `<footer>` in every task |
| Emphasize accessibility | Make `alt` text mandatory, not optional                |
| Develop testing habits  | Include validation checklist before submission         |

### DigComp 2.2 Mapping

| Competence                       | Evidence in Unit                                    |
| -------------------------------- | --------------------------------------------------- |
| 3.1 Developing digital content   | Creating structured HTML documents                  |
| 3.2 Integrating & re-elaborating | Combining multiple HTML elements into cohesive page |
| 3.4 Programming                  | Writing HTML code with proper syntax                |

---

## Answer Key: Student Workbook Fill-Ins

### Part 1: Document Structure

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Any valid title</title>
  </head>
  <body>
    <!-- Content goes here -->
  </body>
</html>
```

### Part 2: Semantic Tags

- `<header>`: **B** (Introductory content or site header)
- `<main>`: **A** (Primary content area)
- `<footer>`: **C** (Footer content or site footer)

### Part 3: Heading Hierarchy

**Expected answer:** "Using one `<h1>` creates clear document hierarchy and improves accessibility for screen readers. It signals the main topic of the page."

**Sample hierarchy:**

```html
<h1>My School</h1>
<h2>About Our School</h2>
<h3>Our Mission</h3>
```

### Part 4: Lists

**Unordered list example:**

```html
<ul>
  <li>HTML structure</li>
  <li>CSS styling</li>
  <li>JavaScript interactivity</li>
</ul>
```

**Ordered list example:**

```html
<ol>
  <li>Save the HTML file</li>
  <li>Right-click the file and select "Open with"</li>
  <li>Choose a web browser (Chrome, Firefox, Safari)</li>
</ol>
```

### Part 5: Images

```html
<img src="photo.jpg" alt="Description of the image" />
```

**Purpose of `alt`:** "Provides text description for screen readers, improves accessibility, displays if image fails to load."

### Part 6: Links

```html
<a href="https://example.com">Example Website</a>
```

**`href` explanation:** "Hypertext reference; it specifies the URL destination of the link."

---

## Teaching Sequence (Suggested)

| Phase                | Time      | Focus                          | Teacher Actions                                      |
| -------------------- | --------- | ------------------------------ | ---------------------------------------------------- |
| Introduction         | 5–10 min  | Review document structure      | Quick recap of Unit 1.1 concepts                     |
| Fill-in practice     | 15–20 min | Parts 1–6 scaffolded exercises | Circulate; check syntax carefully                    |
| Build page           | 30–40 min | Part 7 independent creation    | Provide starter template; encourage creativity       |
| Testing & validation | 10–15 min | Part 9 browser & W3C check     | Model validation process; troubleshoot common errors |
| Reflection           | 5–10 min  | Parts 10–11 self-assessment    | Prompt sharing of challenges & successes             |

---

## Differentiation Strategies

| Learner Profile | Support                                                                            | Extension                                                      |
| --------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Emerging        | Provide completed HTML template; students modify content only                      | Add second page with navigation                                |
| On Track        | Offer starter code with TODOs for students to complete                             | Create multi-page site with consistent header/footer           |
| Advanced        | Minimal scaffolding; challenge to add extra elements (tables, forms)               | Research and implement HTML5 elements (details, summary, time) |
| ELL             | Vocabulary list (tag, attribute, element, semantic); sentence stems for reflection | Translate page content into home language                      |
| Visual learners | Diagram HTML structure as nested boxes before coding                               | Create visual sitemap before building pages                    |

---

## Common Misconceptions & Responses

| Misconception                      | Response                                                                            |
| ---------------------------------- | ----------------------------------------------------------------------------------- |
| "More `<h1>` tags = more emphasis" | Explain hierarchy; only one `<h1>` per page establishes clear main topic            |
| "Alt text is optional"             | Stress accessibility; screen readers rely on alt text for image context             |
| "Spacing in code affects display"  | Clarify browser ignores extra whitespace; formatting aids readability for humans    |
| "DOCTYPE isn't necessary"          | Explain modern browsers assume HTML5, but explicit declaration prevents quirks mode |

---

## Troubleshooting Table

| Symptom                   | Likely Cause                    | Fix                                                   |
| ------------------------- | ------------------------------- | ----------------------------------------------------- |
| Image doesn't appear      | Incorrect file path             | Verify image is in same folder; check spelling & case |
| Tags visible on page      | Missing `<` or `>`              | Check opening/closing brackets on all tags            |
| Layout looks wrong        | Missing closing tag             | Validate HTML; use editor's tag matching              |
| Title doesn't show in tab | `<title>` outside `<head>`      | Move `<title>` inside `<head>` section                |
| Link doesn't work         | Missing `http://` or `https://` | Add protocol to external URLs                         |

---

## Assessment Rubric (Formative)

| Criterion          | Beginning (1)                 | Developing (2)                    | Proficient (3)                   | Advanced (4)                                     |
| ------------------ | ----------------------------- | --------------------------------- | -------------------------------- | ------------------------------------------------ |
| Document Structure | Missing major elements        | Has structure but errors          | Complete & valid structure       | Includes metadata (viewport, description)        |
| Semantic Tags      | No semantic tags used         | One or two present                | Header, main, footer all used    | Additional semantic tags (article, section, nav) |
| Headings           | No headings or all same level | Multiple `<h1>` or skipped levels | Proper hierarchy with one `<h1>` | Clear, descriptive headings with logical flow    |
| Images             | Missing or no `alt` text      | `alt` text generic or missing     | Descriptive `alt` text           | Multiple images with captions                    |
| Links              | Non-functional or missing     | Works but generic text            | Descriptive link text            | Internal and external links                      |
| Validation         | Many errors                   | Some warnings                     | Passes W3C validation            | Zero errors, optimized markup                    |

---

## Formative Checkpoints

| Checkpoint    | Prompt                                   | Expected Evidence                             |
| ------------- | ---------------------------------------- | --------------------------------------------- |
| Structure     | "Show me your `<!DOCTYPE>` and `<head>`" | Correct opening tags present                  |
| Semantics     | "Point to your `<main>` section"         | Semantic tag wrapping primary content         |
| Accessibility | "Read your image `alt` text aloud"       | Descriptive, specific text (not "image1.jpg") |
| Testing       | "Refresh your browser and show me"       | Page displays without errors                  |

---

## Extension Ideas (Advanced Learners)

1. **Multi-page site:** Create `index.html`, `about.html`, `contact.html` with consistent navigation.
2. **HTML entities:** Research and use symbols (`&copy;`, `&trade;`, `&hearts;`).
3. **Accessibility audit:** Use browser dev tools to inspect heading hierarchy.
4. **Meta tags:** Add `<meta name="description">` and `<meta name="author">`.
5. **Favicon:** Add a small icon that appears in the browser tab.

---

## Teacher Reflection Prompts

After session:

- Did students struggle more with syntax or concepts?
- Which tag caused the most confusion?
- How many validated their HTML without prompting?
- What percentage included meaningful `alt` text?
- Next time: more live coding demo? Pair programming?

---

## Language Support

**Vocabulary List:**

- **Element:** A complete HTML tag with opening, content, and closing
- **Attribute:** Extra information added to a tag (e.g., `src`, `alt`, `href`)
- **Semantic:** Tags that describe meaning, not just appearance
- **Hierarchy:** Ordered structure from most to least important
- **Validation:** Checking code against official HTML standards

**Sentence Stems for Reflection:**

- "The most challenging part was ****\_\_**** because ****\_\_****."
- "Semantic HTML is important for accessibility because ****\_\_****."
- "Next, I want to add ****\_\_**** to my page."

---

## Sample Teacher Demonstration

**Live code a simple page together:**

1. Start with empty file; save as `demo.html`
2. Type `!` + Tab (in VS Code) to generate boilerplate
3. Add `<header>`, explain purpose
4. Add `<h1>`, ask class for title suggestion
5. Add `<main>` with paragraph
6. Add `<footer>` with copyright
7. Open in browser, show instant result
8. Deliberately make error (forget closing tag), show browser behavior
9. Fix error, refresh, show correction
10. Validate at W3C, explain green "Document checking completed" message

**Time:** 10–15 minutes

---

## Peer Review Facilitation

**Pair students:**

- Exchange HTML files
- Check each other's code for:
  - Complete structure (DOCTYPE, html, head, body)
  - Semantic tags used
  - Descriptive `alt` text
  - Proper heading hierarchy
- Provide one "praise" and one "suggestion"

**Template:**

- **Praise:** "I like how you ****\_\_****."
- **Suggestion:** "You could improve ****\_\_**** by ****\_\_****."

---

## Performance Notes

**Potential bottlenecks:**

- Students unfamiliar with file systems (saving, locating files)
- Text editor features (autocomplete, syntax highlighting) causing confusion
- Slow typing speeds delaying progress

**Solutions:**

- Pre-create folders; demonstrate save process
- Disable advanced editor features for first session
- Provide code snippets to copy/paste for slower typists

---

## Summary for Teachers

A successful submission: valid HTML5 structure, semantic tags, meaningful content, descriptive `alt` text, working links, passes W3C validation, thoughtful reflection.

Celebrate both technical correctness and creative content choices. Encourage students to personalize their pages while maintaining standards.

**Next Step:** Module 02 dives deeper into content hierarchy, forms, and advanced accessibility patterns.

---

**Version 1.0 — 2025-11-18**  
Prepared by assistant (review for classroom adaptation)

<!-- End Teacher-Annotated Workbook: Unit 1.2 -->
