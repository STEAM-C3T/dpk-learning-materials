# Student Workbook: Unit 3.2 — Responsive Layouts

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.2 — Responsive Layouts  
**Name:** ****************\_\_\_****************  
**Date:** ****************\_\_\_****************

---

## Learning Objectives

By the end of this unit, I will be able to:

- [ ] Create flexible layouts using CSS Flexbox
- [ ] Build grid-based layouts with CSS Grid
- [ ] Write media queries for responsive breakpoints
- [ ] Apply mobile-first design principles
- [ ] Test responsive designs across multiple screen sizes
- [ ] Make images and typography responsive

---

## Key Concepts

**Fill in the blanks as you progress through the tutorial:**

1. Responsive web design ensures websites work on all ****\_\_****, from smartphones to desktops.

2. The three core technologies of responsive design are: ****\_\_**** layouts, ****\_\_**** images, and ****\_\_**** queries.

3. Mobile-first means designing for ****\_\_**** screens first, then enhancing for larger screens.

4. Flexbox is best for ****\_\_****-dimensional layouts, while Grid is best for ****\_\_****-dimensional layouts.

5. The viewport meta tag is: `<meta name="viewport" content="width=__________, initial-scale=__________">`

6. Common breakpoints: Mobile < ****\_\_****px, Tablet ****\_\_****–****\_\_****px, Desktop > ****\_\_****px.

---

## Guided Practice Notes

### Part 1: Flexbox

**My Flexbox experiments:**

**Flex container properties I used:**

- `display: __________`
- `flex-direction: __________`
- `justify-content: __________`
- `align-items: __________`
- `gap: __________`

**What happened when I changed flex-direction from row to column?**

---

---

---

### Part 2: CSS Grid

**My Grid layout:**

**Number of columns on:**

- Mobile: ****\_\_****
- Tablet (768px+): ****\_\_****
- Desktop (1024px+): ****\_\_****

**Grid properties I used:**

```css
display: __________;
grid-template-columns: __________;
gap: __________;
```

**Question:** What does `repeat(3, 1fr)` mean?

---

---

---

### Part 3: Media Queries

**My breakpoints:**

**Tablet breakpoint:**

```css
@media (min-width: __________px) {
  /* What changed: __________ */
}
```

**Desktop breakpoint:**

```css
@media (min-width: __________px) {
  /* What changed: __________ */
}
```

**Question:** Why use `min-width` instead of `max-width` for mobile-first?

---

---

---

### Part 4: Responsive Testing

**Devices I tested:**

| Device/Width     | What Worked | What Broke | How I Fixed It |
| ---------------- | ----------- | ---------- | -------------- |
| Mobile (375px)   | ****\_****  | ****\_**** | ******\_****** |
| Tablet (768px)   | ****\_****  | ****\_**** | ******\_****** |
| Desktop (1024px) | ****\_****  | ****\_**** | ******\_****** |

---

## Independent Task Checklist

**Task:** Create a responsive portfolio or landing page.

**HTML Requirements:**

- [ ] Viewport meta tag in `<head>`
- [ ] Semantic structure (header, main, sections, footer)
- [ ] Navigation with multiple links
- [ ] Grid of items (minimum 4–6 cards/items)
- [ ] Contact form or content section
- [ ] Meaningful class names

**CSS Requirements:**

**Base (Mobile) Styles:**

- [ ] External stylesheet linked
- [ ] Reset or normalize margins/padding
- [ ] Single-column layout for mobile
- [ ] Responsive images (`max-width: 100%`)
- [ ] Readable typography (16px minimum)

**Flexbox:**

- [ ] Navigation uses Flexbox
- [ ] Changes from vertical (mobile) to horizontal (desktop)
- [ ] At least one other Flexbox layout

**CSS Grid:**

- [ ] Project/content grid with `display: grid`
- [ ] 1 column on mobile
- [ ] 2+ columns on tablet
- [ ] 3+ columns on desktop
- [ ] Equal-width columns using `fr` unit

**Media Queries:**

- [ ] At least 2 breakpoints (tablet, desktop)
- [ ] Typography scales for larger screens
- [ ] Layout adapts at each breakpoint
- [ ] Max-width on content for very large screens

**Testing:**

- [ ] Tested at 320px, 768px, 1024px, 1440px
- [ ] No horizontal scrolling at any width
- [ ] All content accessible
- [ ] Touch targets 44x44px minimum on mobile

**Optional Extensions:**

- [ ] Hamburger menu for mobile navigation
- [ ] Advanced Grid with `grid-template-areas`
- [ ] Smooth transitions between breakpoints
- [ ] Dark mode media query

---

## Formative Checks

**Check 1: After Step 2 (Mobile Base)**

- [ ] Viewport meta tag present
- [ ] Page looks good at 320px width
- [ ] No horizontal scrolling
- [ ] All text readable

**Check 2: After Step 3 (Flexbox Navigation)**

- [ ] Navigation vertical on mobile
- [ ] Navigation horizontal on tablet+
- [ ] Items evenly spaced
- [ ] Breakpoint at 768px works

**Check 3: After Step 4 (CSS Grid)**

- [ ] Grid displays 1 column on mobile
- [ ] Grid displays 2+ columns on tablet
- [ ] Grid displays 3+ columns on desktop
- [ ] Equal-width columns

**Check 4: After Step 7 (Full Responsive Test)**

- [ ] Smooth transitions at all breakpoints
- [ ] Typography scales appropriately
- [ ] Images responsive
- [ ] Layout never breaks

---

## Common Errors Log

| Error                            | What Happened        | How I Fixed It          |
| -------------------------------- | -------------------- | ----------------------- |
| Example: Media query not working | Styles didn't change | Added viewport meta tag |
|                                  |                      |                         |
|                                  |                      |                         |

---

## Code Snippets Collection

**Flexbox Container:**

```css

```

**Responsive Grid:**

```css

```

**Media Query:**

```css

```

**Responsive Images:**

```css

```

---

## Self-Assessment Rubric

Rate yourself (1 = Beginning, 2 = Developing, 3 = Proficient, 4 = Exemplary):

| Criterion                                                 | 1   | 2   | 3   | 4   | Evidence |
| --------------------------------------------------------- | --- | --- | --- | --- | -------- |
| **Flexbox Usage**: Appropriate use for navigation/layouts | ☐   | ☐   | ☐   | ☐   |          |
| **Grid Layout**: Effective responsive grid                | ☐   | ☐   | ☐   | ☐   |          |
| **Media Queries**: Proper breakpoints, smooth transitions | ☐   | ☐   | ☐   | ☐   |          |
| **Mobile-First**: Starts mobile, enhances for desktop     | ☐   | ☐   | ☐   | ☐   |          |
| **Responsiveness**: Works perfectly at all sizes          | ☐   | ☐   | ☐   | ☐   |          |
| **Code Quality**: Clean, organized, commented CSS         | ☐   | ☐   | ☐   | ☐   |          |

**What I did well:**

---

---

**What I want to improve:**

---

---

---

## Reflection

**1. Why is mobile-first design important in 2025?**

---

---

---

**2. When would you choose Flexbox over Grid? Grid over Flexbox?**

---

---

---

**3. What was most challenging about creating responsive layouts?**

---

---

---

**4. How does responsive design relate to accessibility?**

---

---

---

---

## Glossary

| Term              | Definition                                    | Example                         |
| ----------------- | --------------------------------------------- | ------------------------------- |
| Responsive Design | Websites that adapt to different screen sizes | Looks good on phone and desktop |
| Flexbox           | CSS layout for one-dimensional arrangements   | Navigation bar                  |
| Grid              | CSS layout for two-dimensional arrangements   | Photo gallery                   |
| Media Query       | CSS that applies at specific screen sizes     | `@media (min-width: 768px)`     |
| Breakpoint        | Screen width where layout changes             | 768px, 1024px                   |
| Viewport          | Visible area of webpage                       | Set with meta tag               |
| Mobile-First      | Design for small screens, enhance for large   | Base styles = mobile            |
| `fr` unit         | Fraction of available space in Grid           | `1fr 1fr` = 50% each            |

---

## DevTools Practice

**Responsive Design Mode:**

1. **Open responsive mode** (Ctrl+Shift+M / Cmd+Shift+M)

   - Current viewport width: ****\_\_****

2. **Test different devices:**

   - iPhone SE (375px): ☐ Works ☐ Needs fix
   - iPad (768px): ☐ Works ☐ Needs fix
   - Laptop (1024px): ☐ Works ☐ Needs fix

3. **Drag to resize:**

   - At what width does navigation change? ****\_\_****
   - At what width does grid change columns? ****\_\_****

4. **Network throttling:**
   - Test on "Slow 3G" — does page load reasonably?

---

## Next Steps

**Preparing for Module 04:**

- [ ] Review JavaScript basics (you'll add interactivity)
- [ ] Think about what could be interactive on your page
- [ ] Explore responsive websites for inspiration

**Additional Practice:**

- Rebuild a responsive website you admire
- Create a responsive photo gallery
- Build a responsive dashboard layout
- Make a responsive pricing table

---

## Metadata

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.2 — Responsive Layouts  
**Version:** 1.0  
**Last Updated:** 2025-11-18  
**License:** CC BY-SA 4.0

---

<!-- End of Student Workbook 3.2 -->
