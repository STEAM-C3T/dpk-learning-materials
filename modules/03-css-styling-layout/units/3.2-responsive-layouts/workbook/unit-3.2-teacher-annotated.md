# Teacher-Annotated Workbook: Unit 3.2 — Responsive Layouts

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.2 — Responsive Layouts  
**Teacher Guide**

---

## Teaching Notes

**Estimated Time:** 55–70 minutes (tutorial) + 50–60 minutes (independent task)

**Pre-Class Preparation:**

- Test that all student devices can access DevTools responsive mode
- Prepare examples of responsive vs. non-responsive sites
- Have devices at different sizes ready (phone, tablet, laptop)
- Optional: Set up live device testing station

**Learning Progression:**
This unit builds on CSS fundamentals by introducing layout systems. Students see immediate visual feedback, which builds confidence.

**Key Teaching Goal:**
Help students think responsively from the start, not as an afterthought.

---

## Key Concepts — Answer Key

1. Responsive web design ensures websites work on all **devices**, from smartphones to desktops.

2. The three core technologies are: **flexible** layouts, **flexible** images, and **media** queries.

3. Mobile-first means designing for **small/mobile** screens first, then enhancing for larger screens.

4. Flexbox is best for **one**-dimensional layouts, while Grid is best for **two**-dimensional layouts.

5. The viewport meta tag is: `<meta name="viewport" content="width=**device-width**, initial-scale=**1.0**">`

6. Common breakpoints: Mobile < **768**px, Tablet **768**–**1024**px, Desktop > **1024**px.

---

## Guided Practice — Teaching Tips

### Part 1: Flexbox (15–18 minutes)

**Common Student Challenges:**

- Confusing `justify-content` and `align-items`
- Forgetting `display: flex` on container
- Not understanding main axis vs. cross axis
- Overusing Flexbox when simpler solution exists

**Teaching Strategy:**

- **Physical Demo:** Line up students, rearrange to show flex-direction
- **Visual Aid:** Draw main axis (justify) and cross axis (align)
- **Live Code:** Change one property at a time, show immediate effect
- **Analogy:** "Flexbox is like organizing books on a shelf"

**Main Axis vs. Cross Axis:**

- `flex-direction: row` → main axis = horizontal, cross = vertical
- `flex-direction: column` → main axis = vertical, cross = horizontal
- `justify-content` = along main axis
- `align-items` = along cross axis

**Expected Student Response to "What happened when changing flex-direction?"**

- Items switched from horizontal to vertical (or vice versa)
- Main and cross axes swapped
- justify-content and align-items affected different dimension

**Differentiation:**

- **Support:** Provide Flexbox cheat sheet with visual diagrams
- **Extension:** Introduce `flex-wrap`, `flex-grow`, `flex-shrink`

---

### Part 2: CSS Grid (18–22 minutes)

**Common Student Challenges:**

- Understanding `fr` unit
- Confusion between rows and columns
- Not seeing when Grid is better than Flexbox
- Complex `grid-template-columns` syntax

**Teaching Strategy:**

- **Graph Paper:** Show grid on paper first
- **Live Resize:** Change grid columns, watch items reflow
- **Compare:** Show same layout in Flexbox (complex) vs. Grid (simple)
- **Incremental:** Start with `repeat(2, 1fr)`, build up

**Grid Fundamentals:**

```css
/* 3 equal columns */
grid-template-columns: 1fr 1fr 1fr;
/* or */
grid-template-columns: repeat(3, 1fr);

/* 2 columns: sidebar + main */
grid-template-columns: 250px 1fr;
```

**Expected Student Response to "What does repeat(3, 1fr) mean?"**

- Creates 3 columns
- Each takes 1 fraction of available space
- All columns equal width
- Shorthand for `1fr 1fr 1fr`

**Formative Check:**
"How would you make 4 equal columns?" (Answer: `repeat(4, 1fr)`)

---

### Part 3: Media Queries (15–18 minutes)

**Common Student Challenges:**

- Forgetting viewport meta tag
- Writing desktop-first when they meant mobile-first
- Breakpoint conflicts (overlapping ranges)
- Testing only on their own device

**Teaching Strategy:**

- **Live Resize:** Drag browser, watch breakpoints trigger
- **Common Mistake:** Show desktop-first, explain why mobile-first better
- **Breakpoint Game:** Give device width, ask which breakpoint applies

**Mobile-First vs. Desktop-First:**

**Mobile-First (Recommended):**

```css
/* Base = mobile */
.nav {
  flex-direction: column;
}

/* Add desktop */
@media (min-width: 768px) {
  .nav {
    flex-direction: row;
  }
}
```

**Desktop-First (Not Recommended):**

```css
/* Base = desktop */
.nav {
  flex-direction: row;
}

/* Override for mobile */
@media (max-width: 767px) {
  .nav {
    flex-direction: column;
  }
}
```

**Expected Student Response to "Why min-width for mobile-first?"**

- Base styles = smallest screen (mobile)
- `min-width` adds styles as screen gets bigger
- Progressive enhancement
- Ensures mobile works even if media queries fail

**Accessibility Note:**
Mobile-first ensures content accessible even on oldest/slowest devices.

---

### Part 4: Responsive Testing (12–15 minutes)

**Common Student Challenges:**

- Only testing on their device
- Not testing edge cases (very small, very large)
- Missing subtle breaks at in-between sizes
- Not testing with real content (lorem ipsum hides issues)

**Teaching Strategy:**

- **Device Pass-Around:** Students test on real devices
- **DevTools Demo:** Show responsive mode, preset devices
- **Slow Drag:** Resize slowly to find exact break point
- **Content Test:** Add really long word, see if it breaks

**Testing Checklist:**

1. Test at standard breakpoints (320, 375, 768, 1024, 1440px)
2. Test between breakpoints (what about 650px?)
3. Test with slow network (does it still work?)
4. Test zoom levels (125%, 150%, 200%)
5. Test with real content (not placeholder text)

---

## Independent Task — Assessment Guidance

**Timing:** 50–60 minutes

**Scaffolding Strategies:**

**For students who struggle:**

- Provide HTML structure pre-built
- Give starter CSS with TODOs for each breakpoint
- Focus on one breakpoint at a time
- Start with simpler 1-column → 2-column grid

**For advanced students:**

- Implement hamburger menu with CSS only
- Use `grid-template-areas` for complex layouts
- Add CSS animations between breakpoints
- Implement dark mode with media query

**Monitoring Checkpoints:**

- 15 min: Mobile styles complete
- 30 min: First breakpoint (tablet) working
- 45 min: Second breakpoint (desktop) working
- Final: Full responsive test across all sizes

---

## Formative Checks — Answer Keys

**Check 1: After Step 2 (Mobile Base)**

Test: Resize browser to 320px

Expected:

- No horizontal scrolling
- All text readable (minimum 16px)
- Images scale down properly
- Single column layout
- Touch targets large enough (44x44px)

**Check 2: After Step 3 (Flexbox Navigation)**

Test: Resize from 375px to 1024px

Expected:

- Navigation stacked vertically below 768px
- Navigation horizontal row at 768px+
- Logo and nav items positioned correctly
- Smooth visual transition

**Check 3: After Step 4 (CSS Grid)**

Test: Count grid columns at each size

Expected:

- Mobile: 1 column
- Tablet (768px): 2 columns
- Desktop (1024px): 3 columns
- Large desktop (1400px): 4 columns or max-width applied
- Equal-width columns at each size

**Check 4: After Step 7 (Full Responsive Test)**

Comprehensive test:

- No layout breaks at any width
- Images responsive (don't overflow)
- Text scales appropriately
- Touch targets adequate on mobile
- No horizontal scrolling
- Content readable at all sizes

---

## Common Errors — Teaching Responses

| Error                       | Why It Happens                    | How to Address                                |
| --------------------------- | --------------------------------- | --------------------------------------------- |
| Media queries don't work    | Missing viewport meta tag         | Always check `<head>` first                   |
| Content overflows on mobile | Fixed widths or large images      | Use `max-width: 100%` on images               |
| Navigation doesn't stack    | `flex-direction` not changed      | Show base vs. breakpoint styles               |
| Grid columns don't change   | Grid not redefined in media query | Need to redefine `grid-template-columns`      |
| Breakpoints conflict        | Overlapping min/max widths        | Use consistent breakpoint system              |
| Layout breaks at 850px      | No breakpoint for that size       | Add intermediate breakpoint or use `minmax()` |

---

## Self-Assessment Rubric — Grading Guide

**Flexbox Usage (4 = Exemplary)**

- Navigation uses Flexbox appropriately
- Changes direction responsively
- Other Flexbox layouts implemented well
- Shows understanding of main/cross axis

**Grid Layout (4 = Exemplary)**

- Grid with appropriate column counts per size
- Uses `fr` units for equal widths
- Clean, simple grid syntax
- Items align properly in grid

**Media Queries (4 = Exemplary)**

- Mobile-first approach
- At least 2 well-chosen breakpoints
- Smooth transitions between sizes
- No redundant or conflicting queries

**Mobile-First (4 = Exemplary)**

- Base styles clearly for mobile
- Enhancement for larger screens
- No desktop-first patterns
- Content hierarchy preserved on mobile

**Responsiveness (4 = Exemplary)**

- Works flawlessly 320px–1920px+
- No horizontal scrolling
- All content accessible
- Images and typography scale perfectly

**Code Quality (4 = Exemplary)**

- Clean, organized media queries
- Logical breakpoint progression
- Comments explain breakpoints
- No unnecessary code duplication

---

## Reflection — Expected Responses

**1. Why is mobile-first design important in 2025?**

Look for:

- Majority of web traffic is mobile
- Mobile data may be limited/slow
- Easier to enhance than subtract
- Forces focus on essential content

**Teaching Response:** "Over 60% of web traffic is mobile. Designing mobile-first ensures your site works for the majority."

---

**2. When would you choose Flexbox over Grid? Grid over Flexbox?**

Expected:

- **Flexbox:** One-dimensional (navigation, toolbars, single row/column)
- **Grid:** Two-dimensional (page layouts, galleries, dashboards)
- **Flexbox:** When items can wrap naturally
- **Grid:** When precise placement needed

**Teaching Response:** "Flexbox = one direction, Grid = two directions. Sometimes you can use either, choose what feels simpler."

---

**3. What was most challenging about creating responsive layouts?**

Common responses:

- Choosing breakpoints
- Testing at all sizes
- Making typography scale well
- Remembering which property does what in Flexbox

**Teaching Response:** Validate challenges, emphasize practice makes perfect.

---

**4. How does responsive design relate to accessibility?**

Expected connections:

- Mobile users may have disabilities
- Zoom must work (text scaling)
- Touch targets important for motor disabilities
- Keyboard navigation works at all sizes
- Content order matters for screen readers

**Teaching Response:** "Responsive design IS accessibility. Making your site work on any device is making it work for anyone."

---

## Differentiation Strategies

**For English Language Learners:**

- Visual examples over text explanations
- Flexbox/Grid visual cheat sheets
- Pair programming with fluent speaker
- Annotate code in native language

**For Students with IEPs:**

- Extended time for independent task
- Provide responsive layout template
- Break task into smaller milestones
- Allow focus on mobile OR desktop (not both)

**For Gifted/Advanced:**

- Implement complex grid layouts (asymmetric)
- Create CSS-only hamburger menu
- Add smooth animations/transitions
- Research and implement container queries
- Build component library with variants

**For Students with Visual Impairments:**

- Focus on semantic HTML (works with screen readers)
- Emphasize keyboard navigation
- Test with screen reader at each breakpoint
- High contrast mode considerations

---

## Extension Activities

**Quick Extensions (15–20 minutes):**

- Add smooth transitions to breakpoint changes
- Implement CSS-only toggle menu
- Create responsive typography scale
- Add hover states that work on touch

**Project Extensions (60+ minutes):**

- Build full responsive website (5+ pages)
- Create responsive email template
- Design mobile app mockup with CSS
- Responsive data dashboard with charts

**Cross-Curricular:**

- **Art/Design:** Create mood board for responsive design
- **Math:** Calculate aspect ratios, grid fractions
- **Business:** Analyze mobile vs. desktop conversion rates
- **Science:** Present research in responsive format

---

## Assessment Rubric (For Teacher Grading)

| Criterion      | Weight | Exemplary (4)                     | Proficient (3)                     | Developing (2)                | Beginning (1)        |
| -------------- | ------ | --------------------------------- | ---------------------------------- | ----------------------------- | -------------------- |
| Flexbox Usage  | 15%    | Perfect navigation, other layouts | Good navigation                    | Basic Flexbox                 | Minimal/no Flexbox   |
| Grid Layout    | 20%    | Responsive grid, perfect columns  | Good grid, minor issues            | Basic grid, some issues       | Minimal grid usage   |
| Media Queries  | 20%    | Mobile-first, 2+ breakpoints      | 2 breakpoints, mostly mobile-first | 1 breakpoint or desktop-first | No media queries     |
| Mobile-First   | 15%    | Clear mobile base, enhancement    | Mostly mobile-first                | Mixed approach                | Desktop-first        |
| Responsiveness | 20%    | Flawless at all sizes             | Works well, minor issues           | Works at some sizes           | Breaks at many sizes |
| Code Quality   | 10%    | Clean, organized, commented       | Mostly clean                       | Some organization             | Disorganized         |

**Total:** **\_** / 100

**Bonus Points (+5 max):**

- Exceptional responsive features (hamburger menu, etc.)
- Advanced Grid techniques
- Smooth animations between breakpoints

---

## Live Demonstration Ideas

**Demonstration 1: Responsive in Real-Time**

- Open non-responsive site on phone → must pinch/zoom
- Open responsive site → works perfectly
- Ask: "Which would you prefer to use?"

**Demonstration 2: Flexbox vs. Grid**

- Build navigation with Flexbox → show code
- Build gallery with Grid → show code
- Explain when to use each

**Demonstration 3: Mobile-First Process**

- Start with mobile design in DevTools
- Add one breakpoint → show what changed
- Add second breakpoint → show progression
- Emphasize additive process

**Demonstration 4: Real Device Testing**

- Show same page on phone, tablet, laptop
- Point out subtle differences
- Demonstrate touch vs. mouse interactions

---

## Links to Related Resources

**For Teachers:**

- [MDN: Responsive Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
- [CSS Tricks: Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Tricks: Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Responsive Design Checker](https://responsivedesignchecker.com/)

**For Students:**

- Link to Unit 3.2 tutorial
- [Flexbox Froggy](https://flexboxfroggy.com/) (game)
- [Grid Garden](https://cssgridgarden.com/) (game)
- [Can I Use](https://caniuse.com/) (browser support)

**Videos:**

- "Flexbox in 100 Seconds" (Fireship)
- "CSS Grid in 100 Seconds" (Fireship)
- "Responsive Design Tutorial" (Traversy Media)

---

## Class Discussion Prompts

**Discussion 1: "How do you use websites on your phone vs. computer?"**

- Different contexts (on the go vs. desk)
- Different interactions (touch vs. mouse)
- Different goals (quick info vs. deep work)

**Discussion 2: "What mobile websites frustrate you? Why?"**

- Tiny text
- Buttons too small to tap
- Horizontal scrolling required
- Desktop site shrunk down

**Discussion 3: "Should you design for mobile or desktop first?"**

- Debate both sides
- Reveal: mobile-first is current best practice
- Discuss why (mobile usage statistics)

---

## Troubleshooting Guide

**Student says: "My media query isn't working"**

1. Check viewport meta tag in `<head>`
2. Verify media query syntax (parentheses, min-width)
3. Check if styles are being overridden (specificity)
4. Test in responsive mode, not just resizing browser
5. Check for typos in `@media`

**Student says: "My Flexbox isn't working"**

1. Verify `display: flex` on parent (not children)
2. Check if `flex-direction` is what they expect
3. Explain main axis vs. cross axis
4. Show DevTools Flexbox visualizer

**Student says: "My Grid has weird gaps"**

1. Check if `gap` property set too high
2. Verify number of columns matches intent
3. Explain `fr` unit (might need fixed widths)
4. Show DevTools Grid overlay

**Student says: "It looks good on my laptop but not my phone"**

1. Test in DevTools responsive mode together
2. Check for fixed widths (need max-width)
3. Verify touch target sizes (44x44px)
4. Check font sizes (16px minimum)

---

## Metadata

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.2 — Responsive Layouts  
**Version:** 1.0  
**Last Updated:** 2025-11-18  
**License:** CC BY-SA 4.0

---

<!-- End of Teacher-Annotated Workbook 3.2 -->
