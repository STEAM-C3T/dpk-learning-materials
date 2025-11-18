# Teacher Annotated Workbook: Unit 2.1 — Building Content

**Module:** 02 — HTML Foundations  
**Unit:** 2.1 — Building Content  
**Instructor Use Only**

---

## Overview for Teachers

**Estimated Time:** 45–60 minutes

**Learning Objectives:**
By the end of this unit, students will be able to:

- Use headings to create clear document hierarchy
- Add paragraphs, lists, links, and images with proper markup
- Write descriptive alt text for images
- Structure content semantically for accessibility

**DigComp 2.2 Alignment:**

- 3.1 Developing digital content
- 1.2 Evaluating data, information and digital content

---

# Teacher-Annotated Workbook: Unit 2.1 — Building Content

**Module:** 02 — HTML Foundations  
**Unit:** 2.1 — Building Content  
**Teacher Guide**

---

## Teaching Notes

**Estimated Time:** 45–60 minutes (tutorial) + 30–40 minutes (independent task)

**Pre-Class Preparation:**

- Ensure all students have text editors installed
- Test that browser DevTools are accessible on student machines
- Prepare example images or have students bring their own
- Optional: Create a sample topic page to show as exemplar

**Learning Progression:**
This unit builds on Module 01 by introducing content-focused HTML elements. Students apply basic structure knowledge to create meaningful, accessible content.

---

## Key Concepts — Answer Key

1. The `<h1>` element should be used **once** per page for the main title.

2. Headings create a **hierarchy** (or **structure**) that helps screen readers navigate.

3. Use `<ul>` for **unordered** (or **bullet**) lists and `<ol>` for **ordered** (or **numbered**) lists.

4. The `href` attribute in an `<a>` tag specifies the **destination** (or **URL** / **link**).

5. Alt text for images should **describe** what's in the image.

6. Link text should be **descriptive** (or **meaningful**) and make sense out of context.

---

## Guided Practice — Teaching Tips

### Part 1: Heading Hierarchy (10–12 minutes)

**Common Student Challenges:**

- Confusing heading levels with font sizes
- Using headings for styling instead of structure
- Skipping heading levels

**Teaching Strategy:**

- Show bad example: website with random heading levels
- Demonstrate screen reader navigation (NVDA, VoiceOver, or browser extension)
- Emphasize: "Headings are like a table of contents"

**Differentiation:**

- **Support:** Provide heading structure template
- **Extension:** Have students audit a real website's heading structure

**Expected Student Response to "Why shouldn't I skip from `<h1>` to `<h3>`?":**

- It breaks the logical flow/hierarchy
- Screen readers expect sequential levels
- Creates confusion for navigation

---

### Part 2: Lists (8–10 minutes)

**Common Student Challenges:**

- Forgetting to wrap `<li>` in list container
- Choosing wrong list type for content
- Inconsistent formatting

**Teaching Strategy:**

- Show real-world examples: recipes (ordered), shopping lists (unordered)
- Practice identifying which list type fits different scenarios
- Demonstrate nested lists for advanced students

**When to Use Each:**

- `<ul>`: Items without sequence (shopping list, features, navigation)
- `<ol>`: Steps, rankings, instructions

**Formative Check:**
Ask students: "Would a recipe use `<ul>` or `<ol>`?" (Answer: `<ol>` for steps)

---

### Part 3: Links (8–10 minutes)

**Common Student Challenges:**

- Using "click here" or "read more" as link text
- Missing `href` attribute
- Broken internal links (wrong path)

**Teaching Strategy:**

- Show bad example: "Click here to read more about accessibility"
- Show good example: "Read accessibility guidelines from W3C"
- Explain: Screen readers can list all links—should make sense alone

**Why "click here" is bad:**

- Not descriptive out of context
- Assumes mouse interaction (not keyboard/screen reader)
- Doesn't indicate destination

**Accessibility Tip:**
Have students close their eyes while you read only link text—do they know where links go?

---

### Part 4: Images (8–10 minutes)

**Common Student Challenges:**

- Empty or missing alt text
- Alt text that says "image of..." (redundant)
- Incorrect file paths

**Teaching Strategy:**

- Show image, ask students to describe it without looking
- Explain decorative vs. informative images
- Demonstrate broken image showing alt text

**Alt Text Guidelines:**

- **Informative image:** Describe content ("Orange sunset over snow-capped mountains")
- **Decorative image:** Use empty alt (`alt=""`)
- **Complex image:** Provide longer description

**Formative Check:**
Show an image, have students write alt text, compare answers

---

## Independent Task — Assessment Guidance

**Timing:** 30–40 minutes

**Scaffolding Strategies:**

**For students who struggle:**

- Provide topic suggestions
- Pre-written heading structure template
- Starter code with one section completed

**For advanced students:**

- Require nested lists
- Add internal navigation links
- Create multiple linked pages

**Monitoring Progress:**

- Check headings first (15 min mark)
- Verify list structure (25 min mark)
- Final check before submission

---

## Formative Checks — Answer Keys

**Check 1: After Step 2 (Headings)**

Expected: Students should have:

- Exactly one `<h1>`
- Multiple `<h2>` for main sections
- `<h3>` nested under relevant `<h2>`
- No skipped levels

**Check 2: After Step 4 (Lists)**

Expected:

- All `<li>` wrapped in `<ul>` or `<ol>`
- Appropriate list type for content
- Proper nesting if advanced

**Check 3: After Step 5 (Links)**

Expected:

- All links have `href`
- Descriptive link text (not "click here")
- External links use https://

**Check 4: After Step 6 (Images)**

Expected:

- All images have alt attribute
- Alt text describes image meaningfully
- Images display (paths correct)

---

## Common Errors — Teaching Responses

| Error                  | Why It Happens                      | How to Address                                  |
| ---------------------- | ----------------------------------- | ----------------------------------------------- |
| Missing closing tag    | Typing quickly, overlooking syntax  | Teach: Use editor auto-complete, check DevTools |
| Wrong list type        | Unsure when to use `<ul>` vs `<ol>` | Ask: "Does order matter?"                       |
| "Click here" link text | Copying common pattern              | Show screen reader demo listing only links      |
| Empty alt text         | Don't understand purpose            | Explain accessibility, show broken image        |
| Skipped heading levels | Thinking about visual size          | Emphasize structure over appearance             |

---

## Self-Assessment Rubric — Grading Guide

**Criterion Descriptions:**

**Heading Hierarchy (4 = Exemplary)**

- One `<h1>`, logical `<h2>` and `<h3>` structure
- No skipped levels
- Headings clearly organize content

**Content Quality (4 = Exemplary)**

- Meaningful, well-written paragraphs
- Clear topic with developed ideas
- Proper grammar and spelling

**List Structure (4 = Exemplary)**

- Appropriate list types chosen
- Properly nested tags
- Optional: includes nested list

**Link Quality (4 = Exemplary)**

- Descriptive, meaningful link text
- All links functional
- Mix of internal and external

**Image Accessibility (4 = Exemplary)**

- Descriptive alt text for all images
- Alt text concise yet informative
- Optional: uses `<figure>` and `<figcaption>`

**Code Quality (4 = Exemplary)**

- Clean, well-formatted HTML
- Proper indentation
- No errors in browser/validator

---

## Reflection — Expected Responses

**1. What was the most challenging part of this unit?**

Common responses:

- Writing good alt text
- Choosing right list type
- Understanding heading hierarchy
- Making links descriptive

**Teaching Response:** Validate challenge, reinforce that these are skills developed with practice.

---

**2. How does semantic HTML help users with disabilities?**

Expected elements:

- Screen readers use structure to navigate
- Headings create "table of contents"
- Alt text describes images for visually impaired
- Proper markup makes content accessible to assistive tech

**Teaching Response:** Emphasize that accessibility benefits all users (SEO, clarity).

---

**3. What real-world website could benefit from better heading structure? Why?**

Look for:

- Specific website identified
- Concrete issues noted (multiple `<h1>`, skipped levels)
- Understanding of how it affects users

**Teaching Response:** Great critical thinking! Have students share examples in class discussion.

---

**4. How might you use these skills in future projects?**

Encourage connections to:

- Other subjects (science reports, history timelines)
- Personal interests (blog, portfolio)
- Real-world applications (club websites, event pages)

---

## Differentiation Strategies

**For English Language Learners:**

- Allow use of native language for content
- Provide vocabulary list with HTML terms
- Pair with fluent English speaker

**For Students with IEPs:**

- Extended time on independent task
- Pre-written content (focus on HTML structure)
- Allow use of speech-to-text for content creation
- Provide template with partial completion

**For Gifted/Advanced:**

- Create multi-page site with navigation
- Research and implement advanced semantic elements (`<article>`, `<section>`)
- Audit and improve accessibility of real website

---

## Extension Activities

**Quick Extensions (5–10 minutes):**

- Add internal navigation with anchor links
- Create nested list with 3 levels
- Use `<figure>` and `<figcaption>` for all images

**Project Extensions (30+ minutes):**

- Build a multi-page personal website
- Create a class resource page (collaborate with peers)
- Research and add semantic HTML5 elements

---

## Assessment Rubric (For Teacher Grading)

| Criterion           | Weight | Exemplary (4)                                 | Proficient (3)                | Developing (2)                   | Beginning (1)               |
| ------------------- | ------ | --------------------------------------------- | ----------------------------- | -------------------------------- | --------------------------- |
| Heading Hierarchy   | 20%    | Perfect structure, one `<h1>`, logical levels | Minor issues, mostly correct  | Skipped levels, multiple `<h1>`  | No clear structure          |
| Content Quality     | 15%    | Clear, well-developed, error-free             | Mostly clear, minor errors    | Underdeveloped, several errors   | Minimal effort, many errors |
| List Structure      | 15%    | Both list types, properly nested              | One list type, mostly correct | Lists present, structural errors | Missing or broken lists     |
| Link Quality        | 20%    | Descriptive, functional, varied               | Mostly descriptive, all work  | Some poor link text, most work   | "Click here," broken links  |
| Image Accessibility | 20%    | All images, excellent alt text                | All images, adequate alt text | Some alt text missing/poor       | Most alt text missing       |
| Code Quality        | 10%    | Clean, valid, well-formatted                  | Minor errors, mostly valid    | Several errors, poor formatting  | Many errors, invalid HTML   |

**Total:** **\_** / 100

---

## Links to Related Resources

**For Teachers:**

- [WebAIM: Alternative Text](https://webaim.org/techniques/alttext/)
- [W3C: Headings](https://www.w3.org/WAI/tutorials/page-structure/headings/)
- [MDN: HTML Elements Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

**For Students:**

- Link to Unit 2.1 tutorial
- Link to Module 02 assessment rubric (in teacher-toolkit)

---

## Metadata

**Module:** 02 — HTML Foundations  
**Unit:** 2.1 — Building Content  
**Version:** 1.0  
**Last Updated:** 2025-11-18  
**License:** CC BY-SA 4.0

---

<!-- End of Teacher-Annotated Workbook 2.1 -->

---

## Metadata

**Module:** 02 — HTML Foundations  
**Unit:** 2.1 — Building Content  
**Author:** Digital Proficiency Kit Team  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Teacher Annotated Workbook -->
