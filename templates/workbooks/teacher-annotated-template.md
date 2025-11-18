# Teacher Annotated Workbook: Unit X.Y — [Unit Title]

**Module:** [Module Number & Title]  
**Unit:** X.Y — [Unit Title]  
**Instructor Use Only**

---

## Overview for Teachers

**Estimated Time:** [Total time, broken down by activity]

- Warm-Up: [X minutes]
- Concept Instruction: [X minutes]
- Code-Along: [X minutes]
- Guided Practice: [X minutes]
- Independent Task Introduction: [X minutes]
- Reflection: [X minutes]

**Materials Needed:**

- Computers with web browsers
- Text editors (VS Code recommended)
- Unit deck slides (Marp)
- Student workbooks (printed or digital)
- [Any additional materials, e.g., example files, handouts]

**Learning Objectives:**
By the end of this unit, students will be able to:

- [Objective 1]
- [Objective 2]
- [Objective 3]

**DigComp 2.2 Alignment:**

- [Competence Area X.Y: Descriptor]

---

## Warm-Up Question

**Prompt:**
[Same prompt as student workbook]

**Purpose:**
[Why this warm-up activates prior knowledge or engages interest.]

**Expected Responses:**

- [Typical student answer 1]
- [Typical student answer 2]

**Teaching Notes:**

- Accept all answers without judgment.
- Use responses to gauge readiness and adjust pacing.
- If students struggle, provide a quick review of [prerequisite concept].

**Timing:** 3–5 minutes

---

## Key Concepts

### Concept 1: [Concept Name]

**Student-Facing Definition:**
[Same as workbook]

**Teacher Explanation:**
[Deeper or more technical explanation for teacher understanding.]

**Common Misconceptions:**

- **Misconception:** [What students often get wrong]
  - **Correction Strategy:** [How to address it]

**Analogy to Use:**
[Concrete comparison to make concept accessible.]

**Differentiation:**

- **Support:** [Scaffolding for struggling students, e.g., provide partially completed code]
- **Challenge:** [Extension for advanced students, e.g., ask them to predict edge cases]

**Formative Check:**
Ask: "[Quick question to assess understanding]"  
Expected answer: "[Correct response]"

**Timing:** 5 minutes

---

### Concept 2: [Concept Name]

**Student-Facing Definition:**
[Same as workbook]

**Teacher Explanation:**
[Technical detail or context.]

**Common Misconceptions:**

- **Misconception:** [Error students make]
  - **Correction Strategy:** [Intervention]

**Analogy to Use:**
[Example comparison.]

**Differentiation:**

- **Support:** [How to simplify or provide visual aids]
- **Challenge:** [How to deepen or extend]

**Formative Check:**
Ask: "[Assessment question]"  
Expected answer: "[Correct response]"

**Timing:** 5 minutes

---

### Concept 3: [Concept Name]

**Student-Facing Definition:**
[Same as workbook]

**Teacher Explanation:**
[Additional context.]

**Common Misconceptions:**

- **Misconception:** [What trips students up]
  - **Correction Strategy:** [How to fix]

**Analogy to Use:**
[Relatable example.]

**Differentiation:**

- **Support:** [Scaffolding approach]
- **Challenge:** [Advanced variation]

**Formative Check:**
Ask: "[Quick quiz question]"  
Expected answer: "[Correct answer]"

**Timing:** 5 minutes

---

## Guided Practice Notes

**Task:** [Brief description, same as student workbook]

**Teaching Strategy:**

- Model the first step live; students follow along.
- Pause frequently to check for understanding.
- Circulate to monitor progress and provide individual support.

**Expected Challenges:**

1. **Challenge:** [Common issue students face]

   - **Solution:** [How to help, e.g., provide hint, pair students, mini re-teach]

2. **Challenge:** [Another common issue]
   - **Solution:** [Intervention strategy]

**Formative Assessment:**

- Observe: Are students successfully completing each step?
- Ask: "Who can explain what we just did and why?"
- Check: Review 2–3 student screens to verify correctness.

**Differentiation:**

- **Support:** Provide step-by-step handout with screenshots.
- **Challenge:** Ask early finishers to add [extra feature].

**Timing:** 10–15 minutes

---

## Code-Along Scaffold

**Purpose:**
Provide a partially completed code structure to reduce cognitive load and focus on key concepts.

**Teacher Notes:**

- Display code on screen and type along with students.
- Intentionally make 1 small error (e.g., missing closing tag) and debug aloud to model process.
- Encourage students to predict next steps before typing.

**Answer Key:**

**File: `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Unit X.Y Example</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Welcome to Unit X.Y</h1>
    <p>This is an example paragraph.</p>
    <script src="script.js"></script>
  </body>
</html>
```

**File: `styles.css`**

```css
body {
  font-family: Arial, sans-serif;
  background-color: #f9f9f9;
  color: #333;
}

h1 {
  color: #0066cc;
}
```

**File: `script.js`**

```javascript
console.log("Script loaded successfully!");

document.addEventListener("DOMContentLoaded", function () {
  const heading = document.querySelector("h1");
  heading.textContent = "Welcome to the Digital Proficiency Kit!";
});
```

**Expected Browser Output:**

- Heading: "Welcome to the Digital Proficiency Kit!"
- Paragraph: "This is an example paragraph."
- Console: "Script loaded successfully!"

**Common Errors to Watch For:**

- Missing closing tags
- Typo in `href` or `src` paths
- Script placed in `<head>` instead of before `</body>`

**Timing:** 15–20 minutes

---

## Independent Task Checklist

**Task:** [Same as student workbook]

**Acceptance Criteria (Answer Key):**

- [ ] [Criterion 1] — What this looks like when done correctly: [Description]
- [ ] [Criterion 2] — Check for: [Specific evidence]
- [ ] [Criterion 3] — Verify: [Observable outcome]
- [ ] [Criterion 4] — Test: [Functional requirement]

**Assessment Rubric Quick Reference:**
| Criterion | Emerging | Proficient | Exemplary |
|-----------|----------|------------|-----------|
| [Criterion 1] | [Descriptor] | [Descriptor] | [Descriptor] |
| [Criterion 2] | [Descriptor] | [Descriptor] | [Descriptor] |

(Full rubric available in Teacher Toolkit `assessment-rubric-0X.md`)

**Differentiation:**

- **Support:** Pair struggling students with peers; provide starter code template.
- **Challenge:** Ask students to add [advanced feature, e.g., form validation, animation].

**Timing:**

- Introduction: 5 minutes
- Work time: [Assign as homework or allocate 20–30 minutes in class]

---

## Self-Assessment

**Purpose:**
Students reflect on their own learning and identify areas for growth.

**Teacher Use:**

- Collect workbooks or digital responses.
- Look for patterns: If many students rate themselves low on [Objective X], plan a review session.
- Use data to adjust pacing or re-teach concepts.

**Interpreting Ratings:**

- **1–2:** Student needs significant support; consider 1-on-1 intervention or peer tutoring.
- **3:** Student is progressing but needs more practice.
- **4–5:** Student is confident; offer extension activities.

**Follow-Up:**

- Acknowledge honesty: "It's okay to not be confident yet; that's why we practice."
- Provide resources for students who need more help.

**Timing:** 5 minutes

---

## Reflection

**Prompts (Same as Student Workbook):**

1. What was the most challenging part of this unit?
2. What's one thing you're proud of learning?
3. How could you use what you learned outside of class?

**Teacher Analysis:**

- **Prompt 1:** Identifies common pain points; use to improve future lessons.
- **Prompt 2:** Builds student confidence and metacognition.
- **Prompt 3:** Connects learning to real-world applications; promotes transfer.

**Sample Responses & Insights:**

- If many students cite [specific challenge], plan additional practice or mini-lesson.
- Celebrate diverse applications students imagine (share examples in next session).

**Timing:** 5 minutes at end of session

---

## Glossary (Answer Key)

| Term     | Correct Definition    |
| -------- | --------------------- |
| [Term 1] | [Accurate definition] |
| [Term 2] | [Accurate definition] |
| [Term 3] | [Accurate definition] |
| [Term 4] | [Accurate definition] |

**Teaching Note:**

- Review glossary terms at start or end of session.
- Use terms consistently in explanations and slides.
- Quiz students verbally or via quick formative check.

---

## Next Steps (for Teacher Planning)

**Preparation for Next Unit:**

- [ ] Review student reflections and self-assessments.
- [ ] Identify 2–3 students who need extra support; plan intervention.
- [ ] Prepare extension materials for advanced students.
- [ ] Update lesson plan based on what worked / didn't work.
- [ ] Grade independent tasks using rubric.

**To Share with Students:**

- Remind them to complete [action item 1] before next session.
- Post answers to common questions on [forum/LMS].
- Office hours: [Time/platform].

---

## Accessibility & Inclusion Notes

**This Unit Emphasized:**

- ✅ [Specific practice, e.g., "Using semantic HTML"]
- ✅ [Specific practice, e.g., "Alt text on images"]

**Accommodations to Offer:**

- Provide printed code examples for students who prefer paper.
- Allow extra time for students with processing or motor difficulties.
- Use screen-reader-friendly materials for visually impaired students.
- Offer audio recordings of lesson explanations for auditory learners.

**Equity Considerations:**

- Ensure all students have access to a working computer and internet.
- Provide offline alternatives (e.g., screenshots, PDFs) if needed.
- Use inclusive examples and language in all materials.

---

## Resources for Teachers

**Unit Materials:**

- Unit deck: `unit-X.Y-deck.md`
- Tutorial: `unit-X.Y-tutorial.md`
- Student workbook: `unit-X.Y-student-workbook.md`

**Teacher Toolkit:**

- Lesson plan: `unit-X.Y-lesson-plan.md`
- Assessment rubric: `assessment-rubric-0X.md`

**Professional Development:**

- [Link to relevant PD resource or workshop]
- [Link to pedagogy guide for teaching coding to novices]

**External Resources:**

- [MDN Web Docs]
- [W3Schools tutorials]
- [Accessibility testing tools]

---

## Metadata

**Module:** [Module Number & Title]  
**Unit:** X.Y — [Unit Title]  
**Author:** [Name]  
**Contributors:** [Names, if any]  
**License:** CC BY-SA 4.0  
**Repository:** [Link to dpk-learning-materials repo]

---

<!-- End of Teacher Annotated Workbook Template -->
