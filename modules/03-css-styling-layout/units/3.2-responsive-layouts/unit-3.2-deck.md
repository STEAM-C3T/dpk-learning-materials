---
marp: true
theme: default
paginate: true
header: "Digital Proficiency Kit | Module 03: Unit 3.2"
footer: "STEAM-C3T | CC BY-SA 4.0"
---

# Unit 3.2: Responsive Layouts

Module 03: CSS Styling & Layout
Digital Proficiency Kit

---

## Warm-Up

How do websites look different on phones vs. computers? What changes?

_Think, pair, share your ideas._

---

## Unit Objectives

- Build layouts with Flexbox and Grid
- Create responsive designs with media queries
- Understand mobile-first approach
- Test layouts at different screen sizes

---

## Quick Check

What does "responsive" mean for web design?

---

## Flexbox

One-dimensional layouts (row or column):

```css
.container {
  display: flex;
  gap: 1rem;
}
```

---

## Grid

Two-dimensional layouts (rows and columns):

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}
```

---

## Media Queries

Adapt styles for different screen sizes:

```css
@media (max-width: 768px) {
  .container {
    grid-template-columns: 1fr;
  }
}
```

---

## Mobile-First

- Start with mobile styles
- Add complexity for larger screens
- Use `min-width` media queries

---

## Guided Practice

Create a responsive card grid that adapts to screen size

---

## Check for Understanding

1. When would you use Flexbox vs. Grid?
2. What does `1fr` mean in Grid?
3. How do media queries work?

---

## Independent Task

Build a responsive layout for your portfolio page

---

## Reflection

What surprised you about responsive design? What's still unclear?

---

## Accessibility

- Test with browser zoom
- Ensure touch targets are large enough (44x44px minimum)
- Maintain readable text at all sizes

---

## Extension

- Add responsive navigation
- Create multi-column layouts
- Experiment with CSS Grid areas

---

## Summary & Next Steps

Today: Flexbox, Grid, media queries, responsive design

Next: Module 04 — JavaScript Essentials

---

## Questions?

Ask now, or check the tutorial and workbook for more info.

---

# Thank You!

Next: Module 04 — JavaScript Essentials

---

<!-- End of Unit 3.2 Deck -->
