# Teacher Annotated Workbook: Unit 1.1 — What Is the Web?

**Module:** 01 — Introduction to the Web  
**Unit:** 1.1 — What Is the Web?  
**Instructor Use Only**

---

## Overview for Teachers

**Estimated Time:** 60–90 minutes

- Warm-Up: 5 minutes
- Concept Instruction (Internet vs Web, Client-Server, HTML/CSS/JS): 20 minutes
- Live Demonstration (DevTools): 10 minutes
- Guided Practice (Explore webpage): 15 minutes
- Check for Understanding: 10 minutes
- Independent Task Introduction: 5 minutes
- Reflection: 5 minutes

**Materials Needed:**

- Computers with modern web browsers
- Unit deck slides (`unit-1.1-deck.md`)
- Student workbooks (this document, student version)
- Internet access

**Learning Objectives:**
By the end of this unit, students will be able to:

- Explain the difference between the internet and the web
- Describe how clients, servers, and browsers communicate
- Identify the roles of HTML, CSS, and JavaScript

**DigComp 2.2 Alignment:**

- 1.2 Evaluating data, information and digital content (Understanding web infrastructure)

---

## Warm-Up Question

**Prompt:**
"When you type 'youtube.com' into your browser and press Enter, what happens behind the scenes?"

**Purpose:**
Activate prior knowledge and gauge students' mental models of how the web works.

**Expected Responses:**

- "The website loads."
- "Google searches for it." (Misconception: conflating search engine with browser)
- "It connects to YouTube's server."
- "Magic!" (honest answer indicating need for instruction)

**Teaching Notes:**

- Accept all answers without judgment; this is diagnostic.
- Use responses to identify misconceptions (e.g., browser vs. search engine).
- Transition: "Today we'll see exactly what happens!"

**Timing:** 5 minutes

---

## Key Concepts

### Concept 1: Internet vs. Web

**Student-Facing Definitions:**

- **Internet:** Global network of interconnected computers.
- **Web:** System of linked documents accessed via browsers.

**Teacher Explanation:**
The internet is the physical infrastructure (cables, routers, servers). The web is a service that runs on top of the internet, consisting of webpages linked via hyperlinks.

**Common Misconceptions:**

- **Misconception:** "Internet and web are the same."
  - **Correction Strategy:** Use the road analogy: Internet = roads; Web = one type of vehicle (cars). Other "vehicles" = email, file sharing, gaming.

**Analogy to Use:**
"The internet is like the postal system (infrastructure), and the web is like sending letters (one type of communication that uses that infrastructure)."

**Differentiation:**

- **Support:** Show visual diagram; use concrete examples (email vs. browsing a website).
- **Challenge:** Ask: "What other services use the internet besides the web?"

**Formative Check:**
Ask: "True or False: The web is part of the internet."  
Expected answer: "True."

**Timing:** 5 minutes

---

### Concept 2: Client-Server Model

**Student-Facing Explanation:**

- Client (browser) requests a webpage.
- Server sends back files (HTML, CSS, JS).
- Browser renders the page.

**Teacher Explanation:**
HTTP (HyperText Transfer Protocol) governs this request-response cycle. When you type a URL, the browser sends an HTTP request to the server's IP address (resolved via DNS). The server responds with files, which the browser interprets.

**Common Misconceptions:**

- **Misconception:** "The webpage is stored on my computer."
  - **Correction Strategy:** Explain caching vs. permanent storage. Show that refreshing reloads from the server.

**Analogy to Use:**
"You (client) order food at a restaurant (server). You request a menu item (webpage), and the kitchen sends it to you."

**Differentiation:**

- **Support:** Draw the diagram on board; use think-aloud while drawing.
- **Challenge:** Introduce DNS: "How does the browser know which server to contact?"

**Formative Check:**
Ask: "What does the server send back to the client?"  
Expected answer: "HTML, CSS, and JavaScript files."

**Timing:** 7 minutes

---

### Concept 3: The Big Three Technologies

**Student-Facing Roles:**

- HTML: Structure and content
- CSS: Visual style
- JavaScript: Interactivity

**Teacher Explanation:**
HTML defines elements (headings, paragraphs, images). CSS applies rules to style those elements (colors, fonts, layout). JavaScript manipulates the DOM (Document Object Model) to add dynamic behavior (e.g., button clicks, animations).

**Common Misconceptions:**

- **Misconception:** "HTML is a programming language."
  - **Correction Strategy:** Clarify: "HTML is markup (structure), not programming. JavaScript is programming."

**Analogy to Use:**

- HTML = Skeleton
- CSS = Skin/clothing
- JavaScript = Muscles/nervous system

**Differentiation:**

- **Support:** Show a simple webpage; point out each technology in DevTools.
- **Challenge:** Ask students to predict what happens if CSS or JS is disabled.

**Formative Check:**
Ask: "Which technology would you use to change the color of text?"  
Expected answer: "CSS."

**Timing:** 8 minutes

---

## Guided Practice Notes

**Task:** Explore `example.com` using browser developer tools.

**Teaching Strategy:**

- Model first: Open `example.com`, right-click → Inspect, walk through Elements and Styles tabs.
- Students follow along on their devices.
- Pause frequently: "What do you see in the Elements tab?"

**Expected Challenges:**

1. **Challenge:** Students can't find DevTools.

   - **Solution:** Demonstrate keyboard shortcut (F12 or Cmd+Option+I). Walk around to help individually.

2. **Challenge:** Overwhelmed by amount of HTML code.
   - **Solution:** Start with `example.com` (very simple). Focus on `<html>`, `<head>`, `<body>` only.

**Formative Assessment:**

- Ask: "Can someone point out where the heading is in the HTML?"
- Check: Walk around; verify 3–5 students have DevTools open and are exploring.

**Differentiation:**

- **Support:** Pair struggling students with peers.
- **Challenge:** Ask early finishers to inspect a more complex site (e.g., wikipedia.org) and find 5 different tags.

**Timing:** 15 minutes

---

## Independent Task

**Task:** Research and explain one web technology (HTML, CSS, or JavaScript).

**Acceptance Criteria (Answer Key):**

- [ ] Chose one technology — Student clearly states which one.
- [ ] Found 2–3 facts — Facts are accurate (check against MDN or W3Schools).
- [ ] Wrote 3–5 sentences — Paragraph is coherent and in student's own words.
- [ ] Included one example — Example is relevant (e.g., an HTML tag, a CSS property, or a JS command).

**Sample Student Response (Proficient):**

> "I chose HTML. HTML stands for HyperText Markup Language. It is used to create the structure of webpages by using tags like `<h1>` for headings and `<p>` for paragraphs. HTML is not a programming language; it's markup. An example is `<h1>Welcome!</h1>`, which creates a big heading that says 'Welcome!'"

**Differentiation:**

- **Support:** Provide sentence starters: "HTML is used for... An example is..."
- **Challenge:** Ask students to compare two technologies or explain how they work together.

**Timing:**

- Introduction: 5 minutes
- Work time: Assign as homework or 10–15 minutes in class

---

## Self-Assessment

**Purpose:**
Students reflect on confidence levels; teacher identifies who needs support.

**Teacher Use:**

- Collect workbooks or digital responses before next session.
- Look for patterns: If many students rate "1–2" on client-server model, plan a review activity.

**Interpreting Ratings:**

- **1–2:** Needs significant support; consider peer tutoring or 1-on-1 check-in.
- **3:** Progressing; needs more practice and examples.
- **4–5:** Confident; ready for Unit 1.2; offer extension.

**Follow-Up:**

- Acknowledge: "It's okay to not feel confident yet. We'll practice more in Unit 1.2."

**Timing:** 5 minutes

---

## Reflection

**Prompts:**

1. What was the most surprising thing you learned?
2. What's one question you still have?
3. How does this change how you think about websites?

**Teacher Analysis:**

- **Prompt 1:** Reveals what resonated; use examples in future lessons.
- **Prompt 2:** Identifies gaps; address in next session or office hours.
- **Prompt 3:** Assesses transfer of learning; celebrates diverse insights.

**Sample Responses & Insights:**

- "I didn't know the internet and web were different!" → Common surprise; validates instruction.
- "How does the browser know which server to contact?" → Opportunity to introduce DNS in extension.
- "I can create my own website now!" → Shows motivation; encourage in next unit.

**Timing:** 5 minutes

---

## Glossary (Answer Key)

| Term       | Correct Definition                                                              |
| ---------- | ------------------------------------------------------------------------------- |
| Internet   | Global network of interconnected computers that exchange data.                  |
| Web        | System of linked documents (webpages) accessed via browsers using the internet. |
| Client     | A device or program (like a browser) that requests information from a server.   |
| Server     | A computer that stores and sends files (webpages) to clients.                   |
| Browser    | Software that interprets and displays web content (e.g., Chrome, Firefox).      |
| HTML       | HyperText Markup Language; structures web content.                              |
| CSS        | Cascading Style Sheets; styles and layouts webpages.                            |
| JavaScript | Programming language that adds interactivity to webpages.                       |

**Teaching Note:**

- Review glossary at end of session or start of next.
- Quiz students verbally or via quick formative check.

---

## Next Steps (for Teacher Planning)

**Preparation for Unit 1.2:**

- [ ] Review student reflections and self-assessments.
- [ ] Identify students who rated themselves 1–2; plan support strategy.
- [ ] Prepare Unit 1.2 deck and materials (students will write their first HTML file).
- [ ] Grade independent tasks using criteria above.

**To Share with Students:**

- "Next session, you'll write your own HTML code!"
- Remind to bring questions about today's concepts.

---

## Accessibility & Inclusion Notes

**This Unit Emphasized:**

- ✅ Conceptual understanding (foundation for accessible coding in Unit 1.2)
- ✅ Using DevTools to inspect structure

**Accommodations to Offer:**

- Provide printed diagrams for visual learners.
- Allow extra time for students with processing difficulties.
- Use captions or transcripts if showing video demos.

**Equity Considerations:**

- Ensure all students have access to a device and internet.
- Provide offline handouts or screenshots if needed.

---

## Resources for Teachers

**Unit Materials:**

- Unit deck: `unit-1.1-deck.md`
- Tutorial: `unit-1.1-tutorial.md`
- Student workbook: `unit-1.1-student-workbook.md`

**Teacher Toolkit:**

- Lesson plan: `unit-1.1-lesson-plan.md`
- Module overview: `module-overview.md`

**External Resources:**

- [MDN: How the Web Works](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)
- [Khan Academy: Internet 101](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:the-internet)

---

## Metadata

**Module:** 01 — Introduction to the Web  
**Unit:** 1.1 — What Is the Web?  
**Author:** Digital Proficiency Kit Team  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Teacher Annotated Workbook -->
