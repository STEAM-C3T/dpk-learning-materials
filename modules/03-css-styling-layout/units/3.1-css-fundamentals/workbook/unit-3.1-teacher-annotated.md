# Teacher-Annotated Workbook: Unit 3.1 — CSS Fundamentals

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.1 — CSS Fundamentals  
**Teacher Guide**

---

## Teaching Notes

**Estimated Time:** 50–65 minutes (tutorial) + 40–50 minutes (independent task)

**Pre-Class Preparation:**

- Ensure students can access browser DevTools (F12)
- Prepare example of well-designed website to analyze
- Have color contrast checker ready (WebAIM)
- Optional: Prepare "CSS in 5 minutes" refresher slides

**Learning Progression:**
This is students' first introduction to CSS. Focus on fundamentals and visual feedback to build confidence.

**Key Teaching Goal:**
Help students see CSS as creative tool, not just technical syntax.

---

## Key Concepts — Answer Key

1. CSS stands for **Cascading** **Style** **Sheets**.

2. The three ways to add CSS are: **external** (stylesheet), **internal** (`<style>` tag), and **inline** (`style` attribute).

3. Class selectors start with a **period/dot** (`.`), ID selectors start with a **hashtag/pound** (`#`).

4. The four parts of the box model (from inside out) are: **content**, **padding**, **border**, **margin**.

5. Hexadecimal colors start with the **#** (hashtag/pound) symbol.

6. The property that controls space between lines of text is **line-height**.

---

## Guided Practice — Teaching Tips

### Part 1: CSS Selectors (12–15 minutes)

**Common Student Challenges:**

- Confusing class (.) and ID (#) syntax
- Forgetting curly braces or semicolons
- Not understanding specificity
- Typos in class/ID names

**Teaching Strategy:**

- **Visual Demo:** Show same page unstyled vs. styled
- **Live Coding:** Write CSS together, refresh browser after each rule
- **Selector Game:** Give HTML, ask "which selector would target this?"

**Selector Specificity (Simplified):**

- ID > Class > Element
- More specific wins
- If equal, last one wins

**Expected Student Response to "When to use class vs. ID?"**

- Class: Reusable styles, multiple elements
- ID: Unique element, once per page
- In CSS, prefer classes for styling

**Differentiation:**

- **Support:** Provide selector reference chart
- **Extension:** Introduce descendant selectors (`.parent .child`)

---

### Part 2: The Box Model (15–18 minutes)

**Common Student Challenges:**

- Confusing margin and padding
- Not understanding box-sizing
- Difficulty calculating total width
- Forgetting shorthand order (top, right, bottom, left)

**Teaching Strategy:**

- **Physical Demo:** Use boxes/books to show content, padding, border, margin
- **DevTools:** Show box model visualizer (Computed tab)
- **Interactive:** Have students adjust values, predict outcome

**Box Model Visual Aid:**

```
Margin (orange in DevTools)
  Border (yellow)
    Padding (green)
      Content (blue)
```

**Shorthand Values:**

- 1 value: all sides
- 2 values: top/bottom, left/right
- 3 values: top, left/right, bottom
- 4 values: top, right, bottom, left (clockwise)

**Formative Check:**
"If padding is 20px and border is 2px, how much space total around content?" (44px)

---

### Part 3: Color Systems (10–12 minutes)

**Common Student Challenges:**

- Forgetting # for hex colors
- Not understanding RGB values
- Confusion about when to use which system
- Poor color contrast for accessibility

**Teaching Strategy:**

- **Color Wheel:** Show how colors relate
- **Converter Tool:** Demonstrate converting between formats
- **Contrast Check:** Test foreground/background combinations
- **Accessibility:** Emphasize WCAG 4.5:1 ratio

**Color System Comparison:**

| System | Pros                  | Cons                 | Use When           |
| ------ | --------------------- | -------------------- | ------------------ |
| Named  | Easy to remember      | Limited choices      | Quick prototypes   |
| Hex    | Industry standard     | Hard to adjust       | Design handoffs    |
| RGB    | Familiar to designers | Verbose              | Programmatic color |
| RGBA   | Adds transparency     | Need browser support | Overlays           |
| HSL    | Intuitive adjustments | Less common          | Color schemes      |

**Expected Student Response to "Advantage of RGBA?"**

- Adds transparency/opacity (alpha channel)
- Can layer colors
- Creates subtle effects

---

### Part 4: Typography (12–15 minutes)

**Common Student Challenges:**

- Font stack confusion
- Absolute vs. relative units
- Too many fonts (visual chaos)
- Poor line-height for readability

**Teaching Strategy:**

- **Type Specimen:** Show different fonts, discuss personality
- **Readability Test:** Compare line-heights, ask which is easier to read
- **Hierarchy:** Show how size/weight create visual structure

**Font Stack Best Practice:**

```css
font-family: "Preferred Font", "Fallback", generic-family;
```

**Unit Recommendations:**

- Base font: 16px
- Headings: em or rem (relative)
- Line-height: 1.5–1.8 for body text
- Avoid px for accessibility (users can't resize)

**Expected Student Response to "Why em/rem over px?"**

- Scales with user settings
- Better accessibility
- Responsive by default

---

## Independent Task — Assessment Guidance

**Timing:** 40–50 minutes

**Scaffolding Strategies:**

**For students who struggle:**

- Provide HTML structure pre-built
- Give starter CSS with comments indicating what to add
- Limit color palette to 3 colors
- Focus on one section at a time

**For advanced students:**

- Require CSS animations or transitions
- Add gradient backgrounds
- Implement Google Fonts
- Create multiple color themes (light/dark mode)

**Monitoring Checkpoints:**

- 15 min: External stylesheet linked, basic colors applied
- 30 min: Box model spacing complete
- 40 min: Typography and finishing touches

---

## Formative Checks — Answer Keys

**Check 1: After Step 2 (External Stylesheet)**

Expected:

- Background color changed from white
- Font family applied to all text
- Link tag in HTML `<head>`
- No broken file path (check Network tab)

**Check 2: After Step 3 (Selectors)**

Expected:

- Classes apply to multiple elements correctly
- ID applies to single element
- Inspect element shows correct rules
- No selector typos

**Check 3: After Step 4 (Box Model)**

Test: Inspect element, view box model diagram

Expected:

- Padding creates inner spacing
- Margin creates outer spacing
- Border visible if specified
- Correct understanding of total width

**Check 4: After Step 7 (Final Styling)**

Checklist:

- Color contrast passes WCAG AA (4.5:1)
- Typography hierarchy clear
- Shadows enhance, don't overwhelm
- Hover states on interactive elements

---

## Common Errors — Teaching Responses

| Error                         | Why It Happens                    | How to Address                                |
| ----------------------------- | --------------------------------- | --------------------------------------------- |
| Stylesheet doesn't load       | Wrong file path or name           | Check DevTools → Network, verify path         |
| Selector doesn't work         | Typo in class/ID name             | Use DevTools → Elements to verify class names |
| Wrong syntax (missing ; or }) | New to CSS syntax                 | Syntax highlighting helps; validate CSS       |
| Colors don't show             | Missing # or wrong format         | Show color picker in DevTools                 |
| Box too wide                  | Not accounting for padding/border | Explain box-sizing; show calculation          |
| Text illegible                | Poor contrast                     | Use WebAIM contrast checker                   |

---

## Self-Assessment Rubric — Grading Guide

**Selector Usage (4 = Exemplary)**

- Multiple element selectors
- Meaningful class names (not generic)
- Appropriate use of ID (0–2 total)
- Advanced selectors (pseudo-classes, combinators)

**Box Model (4 = Exemplary)**

- Strategic use of margin/padding
- Borders enhance design
- Proper spacing creates visual rhythm
- Understanding of total element dimensions

**Color Application (4 = Exemplary)**

- Cohesive color scheme
- Excellent contrast (7:1+ ratio)
- Colors support content hierarchy
- Optional: Uses RGBA or HSL

**Typography (4 = Exemplary)**

- Clear hierarchy (h1 > h2 > p)
- Readable line-height and letter-spacing
- Font choices support content
- Relative units used

**Code Quality (4 = Exemplary)**

- Well-organized, commented CSS
- Consistent formatting
- Validates without errors
- Logical rule order

**Visual Design (4 = Exemplary)**

- Professional, polished appearance
- Consistent visual language
- Details (shadows, borders) enhance
- Page feels complete and intentional

---

## Reflection — Expected Responses

**1. How does CSS improve UX compared to unstyled HTML?**

Look for:

- Visual hierarchy guides attention
- Colors and spacing improve readability
- Aesthetics build trust/engagement
- Branding and personality

**Teaching Response:** "CSS turns information into experience. Users form impressions in milliseconds."

---

**2. What was most challenging about the box model?**

Common responses:

- Remembering margin vs. padding
- Calculating total width
- Shorthand notation (order)
- Understanding when to use each

**Teaching Response:** "Box model takes practice! Use DevTools visualizer until it's second nature."

---

**3. How did you choose your color scheme? Why?**

Look for:

- Intentional choices (not random)
- Consideration of mood/tone
- Awareness of contrast/accessibility
- Reference to color theory or tools

**Teaching Response:** Validate their reasoning; suggest palette generators for inspiration.

---

**4. What website has CSS you admire? Why?**

Encourage:

- Specific observations (not just "looks nice")
- Connection to techniques learned
- Critical analysis of design choices

**Teaching Response:** "Let's inspect that site together in DevTools and see how they did it!"

---

## Differentiation Strategies

**For English Language Learners:**

- Provide CSS property reference in native language
- Allow content in native language (focus on CSS)
- Visual examples over text explanations

**For Students with IEPs:**

- Extended time on independent task
- Provide CSS template with TODOs
- Break task into smaller steps with checkpoints
- Allow use of CSS generators for complex properties

**For Gifted/Advanced:**

- Introduce CSS variables (custom properties)
- Implement CSS animations
- Create multiple themes (dark mode, high contrast)
- Research and present on CSS preprocessors

**For Students with Visual Impairments:**

- Focus on semantic HTML (structure over appearance)
- Emphasize accessibility properties
- Use screen reader to test their CSS choices
- Discuss high-contrast themes

---

## Extension Activities

**Quick Extensions (10–15 minutes):**

- Add CSS transitions to hover states
- Implement gradient backgrounds
- Use Google Fonts or web fonts
- Create button styles with hover effects

**Project Extensions (60+ minutes):**

- Build complete personal website (multi-page)
- Create CSS art (drawings using only CSS)
- Design system: document color palette, typography scale
- Recreate design of favorite website

**Cross-Curricular:**

- **Art:** Study color theory, apply to web design
- **Science:** Create styled data presentation
- **Math:** Calculate aspect ratios, grid layouts
- **Language Arts:** Style poetry or short story

---

## Assessment Rubric (For Teacher Grading)

| Criterion         | Weight | Exemplary (4)                            | Proficient (3)                   | Developing (2)                        | Beginning (1)          |
| ----------------- | ------ | ---------------------------------------- | -------------------------------- | ------------------------------------- | ---------------------- |
| Selector Usage    | 15%    | Varied, appropriate selectors            | Basic selectors work             | Some selectors broken                 | Minimal selector use   |
| Box Model         | 20%    | Masterful spacing, perfect understanding | Good spacing, minor issues       | Some spacing, confusion               | Little spacing applied |
| Color Application | 20%    | Cohesive palette, excellent contrast     | Good colors, adequate contrast   | Limited palette, some contrast issues | Poor color choices     |
| Typography        | 20%    | Clear hierarchy, professional            | Adequate hierarchy, readable     | Minimal hierarchy                     | No typographic control |
| Code Quality      | 10%    | Pristine, organized, commented           | Clean, mostly organized          | Some organization                     | Disorganized, errors   |
| Visual Design     | 15%    | Professional, polished, cohesive         | Good appearance, mostly cohesive | Basic styling applied                 | Minimal styling effort |

**Total:** **\_** / 100

---

## Live Demonstration Ideas

**Demonstration 1: CSS Transformation**

- Show ugly HTML page
- Add CSS step-by-step
- Narrate decisions ("I'll add padding here because...")
- Show before/after

**Demonstration 2: DevTools Deep Dive**

- Inspect element on professional site
- Show Computed styles
- Toggle properties on/off
- Edit values live
- Copy changes to file

**Demonstration 3: Color Contrast**

- Show text on background
- Use WebAIM checker
- Demonstrate fail vs. pass
- Adjust until accessible

**Demonstration 4: Box Model in Action**

- Add padding → content grows inward
- Add margin → element moves
- Add border → visible boundary
- Show calculation in DevTools

---

## Links to Related Resources

**For Teachers:**

- [MDN: CSS Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)
- [CSS Tricks: Almanac](https://css-tricks.com/almanac/)
- [WebAIM: Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Google Fonts](https://fonts.google.com/)

**For Students:**

- Link to Unit 3.1 tutorial
- [Coolors.co](https://coolors.co/) (color palette generator)
- [CSS Diner](https://flukeout.github.io/) (selector game)

**Videos:**

- "CSS in 100 Seconds" (Fireship)
- "Learn CSS in 20 Minutes" (Web Dev Simplified)

---

## Class Discussion Prompts

**Discussion 1: "Why does visual design matter?"**

- Credibility and trust
- User engagement and retention
- Accessibility and inclusivity
- Brand identity

**Discussion 2: "When have you stopped using a website because of bad design?"**

- Illegible text
- Confusing layout
- Slow performance
- Poor mobile experience

**Discussion 3: "What makes a website look 'professional'?"**

- Consistent spacing
- Limited color palette
- Clear typography
- Attention to details

---

## Troubleshooting Guide (For Teacher Reference)

**Student says: "My CSS isn't working"**

1. Check file path in `<link>` tag
2. Open DevTools → Network → look for 404
3. Verify selector matches HTML (case-sensitive)
4. Check for syntax errors (missing ; or })
5. Look for more specific rule overriding

**Student says: "Colors look wrong"**

1. Check for missing # in hex
2. Verify RGB values (0-255 range)
3. Use DevTools color picker
4. Check for conflicting rules

**Student says: "Spacing is weird"**

1. Show DevTools box model diagram
2. Check for conflicting margin/padding
3. Explain box-sizing if needed
4. Demo margin collapse

**Student says: "Fonts don't work"**

1. Check font-family spelling
2. Verify fallback fonts
3. Check if web font loaded (Network tab)
4. Use DevTools Computed → see actual font

---

## Metadata

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.1 — CSS Fundamentals  
**Version:** 1.0  
**Last Updated:** 2025-11-18  
**License:** CC BY-SA 4.0

---

<!-- End of Teacher-Annotated Workbook 3.1 -->
