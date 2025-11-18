# Tutorial: Unit 1.1 — What Is the Web?

**Module:** 01 — Introduction to the Web  
**Unit:** 1.1 — What Is the Web?  
**Estimated Time:** 45 minutes  
**Author:** Digital Proficiency Kit Team  
**Last Updated:** 2025-11-18

---

## Overview

**What You Will Learn:**
In this tutorial, you will learn the foundational concepts of how the web works, including the difference between the internet and the web, the client-server model, and the roles of HTML, CSS, and JavaScript.

**What You Will Build:**
This is a conceptual unit. You won't write code yet, but you'll explore live webpages using browser developer tools to understand how they're constructed.

**Learning Outcomes:**

- Explain the difference between the internet and the web
- Describe how clients, servers, and browsers communicate
- Identify the roles of HTML, CSS, and JavaScript

---

## Prerequisites

Before starting this tutorial, you should:

- [ ] Have used a web browser before
- [ ] Know how to type a URL and navigate to a website
- [ ] Have access to a computer with a modern web browser (Chrome, Firefox, Safari, or Edge)

**Tools Required:**

- A modern web browser with developer tools (all major browsers include these)

---

## Concept Overview

**What Is the Internet?**
The internet is the global network of interconnected computers that can exchange data. It's the infrastructure that supports many services: email, file sharing, video streaming, and the web.

**What Is the Web?**
The World Wide Web (WWW) is a system of linked documents (webpages) accessed via the internet using web browsers. The web is built on three core technologies: HTML, CSS, and JavaScript.

**Why Does It Matter?**
Understanding how the web works helps you transition from being a passive consumer of web content to an active creator.

**How Does It Work?**
When you visit a website:

1. Your browser (the client) sends a request to a server.
2. The server sends back files (HTML, CSS, JavaScript).
3. Your browser interprets and displays those files as a webpage.

**Visual Diagram:**

```
┌─────────────┐          Request (URL)          ┌──────────┐
│   Browser   │ ──────────────────────────────> │  Server  │
│  (Client)   │                                 │          │
│             │ <────────────────────────────── │          │
└─────────────┘   Response (HTML, CSS, JS)      └──────────┘
       ↓
   Renders webpage
```

---

## Step-by-Step Exploration

### Step 1: Open a Simple Webpage

**Objective:** See a basic webpage in action.

**Instructions:**

1. Open your web browser.
2. In the address bar, type: `example.com`
3. Press Enter.

**Expected Result:**

- You should see a simple webpage with a heading and some text.
- The page says something like "Example Domain" and "This domain is for use in illustrative examples..."

**Why It Matters:**
This is one of the simplest webpages on the internet. It's a great starting point for learning because it uses minimal HTML.

**Quick Self-Check:**

- [ ] Did the page load successfully?
- [ ] Can you see text and a heading?

---

### Step 2: Open Browser Developer Tools

**Objective:** Access the tools that let you inspect how webpages are built.

**Instructions:**

1. While still on `example.com`, right-click anywhere on the page.
2. Select **Inspect** (or **Inspect Element**) from the menu.
   - Alternatively, press `F12` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. The browser developer tools panel should open, usually at the bottom or side of your window.

**Expected Result:**

- A panel opens showing tabs like "Elements," "Console," "Network," etc.
- The "Elements" tab is usually selected by default and shows HTML code.

**Why It Matters:**
Developer tools (DevTools) let you peek "under the hood" of any webpage. You can see the HTML, CSS, and JavaScript that make it work.

**Common Pitfall:**
⚠️ **Watch Out:** If the panel doesn't open, make sure you right-clicked on the webpage itself (not the address bar or browser toolbar).  
✅ **Tip:** Try the keyboard shortcut (F12 or Cmd+Option+I) if right-click doesn't work.

**Quick Self-Check:**

- [ ] Can you see a panel with tabs?
- [ ] Do you see HTML code (tags like `<html>`, `<head>`, `<body>`)?

---

### Step 3: Explore the HTML Structure

**Objective:** Understand how HTML organizes webpage content.

**Instructions:**

1. In the **Elements** tab of DevTools, look at the HTML code.
2. Find the `<html>` tag at the top. This wraps the entire page.
3. Inside `<html>`, find two main sections:
   - `<head>`: Contains metadata (title, links to CSS, etc.)
   - `<body>`: Contains visible content (headings, paragraphs, images, etc.)
4. Click the small arrows (▶) next to tags to expand and collapse them.

**Expected Result:**

- You can see tags nested inside each other (like boxes inside boxes).
- The `<head>` contains tags like `<title>` and `<meta>`.
- The `<body>` contains tags like `<h1>`, `<p>`, and `<a>`.

**Why It Matters:**
HTML is hierarchical. Understanding this structure is the foundation of writing your own webpages.

**Common Pitfall:**
⚠️ **Watch Out:** Don't be overwhelmed by all the tags! Focus on the big picture: `<html>` contains `<head>` and `<body>`.  
✅ **Tip:** Think of it like a book: `<head>` is the cover (title, metadata), and `<body>` is the content (chapters, text).

**Quick Self-Check:**

- [ ] Can you find the `<title>` tag? (It sets the page title shown in the browser tab.)
- [ ] Can you find the `<h1>` tag in `<body>`? (This is the main heading.)

---

### Step 4: Inspect CSS Styles

**Objective:** See how CSS controls the appearance of HTML elements.

**Instructions:**

1. In the **Elements** tab, click on the `<h1>` tag (the heading).
2. Look at the panel on the right (usually labeled **Styles** or **Computed**).
3. You should see CSS rules like:
   ```css
   h1 {
     font-size: 32px;
     color: #333;
   }
   ```
4. Try clicking the checkbox next to a CSS rule to toggle it on/off and see the effect.

**Expected Result:**

- When you uncheck a CSS property (e.g., `color`), the heading's color changes.
- You can see how CSS modifies the default appearance of HTML elements.

**Why It Matters:**
CSS separates structure (HTML) from presentation (visual style). This makes websites easier to maintain and update.

**Common Pitfall:**
⚠️ **Watch Out:** Changes you make in DevTools are temporary (only in your browser session). They don't change the actual website.  
✅ **Tip:** DevTools is great for experimenting safely!

**Quick Self-Check:**

- [ ] Can you toggle a CSS property on/off?
- [ ] Do you see the webpage update in real-time?

---

### Step 5: Run JavaScript in the Console

**Objective:** See how JavaScript adds interactivity to webpages.

**Instructions:**

1. Click the **Console** tab in DevTools.
2. You'll see a blank area with a prompt (usually `>`).
3. Type the following and press Enter:
   ```javascript
   alert("Hello, Web!");
   ```
4. A pop-up alert box should appear with your message.

**Expected Result:**

- An alert box pops up saying "Hello, Web!"
- You've just run your first line of JavaScript!

**Why It Matters:**
JavaScript is the programming language of the web. It allows webpages to respond to user actions (clicks, typing, etc.) and update dynamically.

**Common Pitfall:**
⚠️ **Watch Out:** Make sure you type the code exactly as shown, including quotes and parentheses.  
✅ **Tip:** JavaScript is case-sensitive: `alert` works, but `Alert` doesn't.

**Quick Self-Check:**

- [ ] Did the alert box appear?
- [ ] Can you type another command, like `console.log('Test');`, and see it in the console?

---

## Debugging Section

**Scenario 1: DevTools won't open**

- **Possible Cause:** Browser extension blocking it, or keyboard shortcut disabled.
- **Solution:** Try right-click → Inspect. If that fails, check browser settings or restart the browser.

**Scenario 2: Can't find specific HTML tags**

- **Possible Cause:** Trying to find tags in a complex webpage.
- **Solution:** Start with `example.com` (very simple). Use the search function in DevTools (Ctrl+F / Cmd+F).

**Scenario 3: JavaScript command doesn't work**

- **Possible Cause:** Typo in syntax (missing quotes, parentheses, or semicolon).
- **Solution:** Check for exact syntax: `alert('message');`. Copy-paste if needed.

**General Debugging Tips:**

- DevTools Console will show error messages if something is wrong.
- Read error messages carefully; they often tell you what to fix.
- If stuck, refresh the page and try again.

---

## Consolidated Key Concepts

**1. Internet vs. Web**

- **Internet:** Physical network infrastructure.
- **Web:** System of linked documents accessed via browsers.

**2. Client-Server Model**

- **Client (Browser):** Requests webpages.
- **Server:** Stores and sends files.
- **Communication:** Request → Response (HTML, CSS, JS).

**3. The Big Three Technologies**

- **HTML:** Structure and content.
- **CSS:** Visual style and layout.
- **JavaScript:** Interactivity and behavior.

**4. Browser DevTools**

- **Elements Tab:** Inspect HTML and CSS.
- **Console Tab:** Run JavaScript and see errors.
- **Network Tab:** See files loading from server.

---

## Practice Variations

**Variation 1: Inspect Your Favorite Website**

- Visit a website you use often (e.g., YouTube, Wikipedia, a news site).
- Open DevTools and explore its HTML structure.
- Find at least 3 different types of tags (e.g., `<div>`, `<img>`, `<a>`).

**Variation 2: Change Styles Live**

- On any webpage, use DevTools to change a CSS property (e.g., `background-color`).
- Take a screenshot of your modified page.

**Variation 3: Run More JavaScript**

- In the Console, try:
  ```javascript
  console.log("My name is [Your Name]");
  ```
- See your message appear in the console.

---

## Reflection Prompts

1. **What was the most surprising thing you learned about how the web works?**

   - [Space for student response]

2. **What's one question you still have about clients, servers, or browsers?**

   - [Space for student response]

3. **How does understanding these concepts change the way you think about using websites?**
   - [Space for student response]

---

## Further Reading

**Official Documentation:**

- [MDN: How the Web Works](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)
- [MDN: What is a Web Server?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server)

**Related Tutorials:**

- Next: Unit 1.2 — Basic HTML Structure
- [MDN: Getting Started with the Web](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web)

**Advanced Topics:**

- How does HTTP (HyperText Transfer Protocol) work?
- What is the difference between HTTP and HTTPS?

---

## Accessibility Considerations

**This Tutorial Emphasized:**

- ✅ Understanding semantic HTML structure (which we'll explore in Unit 1.2)
- ✅ Using browser tools to inspect and learn

**Why Accessibility Matters:**

- Properly structured HTML (semantic tags) helps screen readers navigate content.
- Accessible web design benefits everyone, including users with disabilities.

**Next Steps:**

- In Unit 1.2, you'll write HTML using semantic tags like `<header>`, `<main>`, and `<footer>`.

---

## Metadata

**Module:** 01 — Introduction to the Web  
**Unit:** 1.1 — What Is the Web?  
**Author:** Digital Proficiency Kit Team  
**Contributors:** N/A  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Unit 1.1 Tutorial -->
