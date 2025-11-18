# Tutorial: Unit 3.2 — Responsive Layouts

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.2 — Responsive Layouts  
**Estimated Time:** 55–70 minutes  
**Author:** Digital Proficiency Kit Team  
**Last Updated:** 2025-11-18

---

## Overview

**What You Will Learn:**
In this tutorial, you will learn to create responsive web layouts using Flexbox, CSS Grid, and media queries that adapt to different screen sizes.

**What You Will Build:**
A responsive portfolio page that works beautifully on mobile phones, tablets, and desktop computers.

**Learning Outcomes:**

- Create flexible layouts with CSS Flexbox
- Build grid-based layouts with CSS Grid
- Use media queries to adapt designs for different screen sizes
- Implement mobile-first responsive design principles
- Test responsive designs across devices

---

## Prerequisites

Before starting this tutorial, you should:

- [ ] Have completed Unit 3.1 or be familiar with CSS fundamentals
- [ ] Understand the box model and CSS selectors
- [ ] Know how to link external stylesheets

**Tools Required:**

- Text editor (VS Code, Notepad++, or similar)
- Modern web browser with responsive design mode (DevTools)

---

## Concept Overview

**What is Responsive Design?**
Responsive web design ensures websites work well on all devices—from smartphones to large desktop monitors—by adapting layout, images, and interactions.

**Three Core Technologies:**

1. **Flexible Layouts:** CSS Flexbox and Grid
2. **Flexible Images:** Max-width and responsive images
3. **Media Queries:** CSS rules that apply at specific screen sizes

**Mobile-First Approach:**
Design for small screens first, then enhance for larger screens. This ensures core content is always accessible.

**Common Breakpoints:**

- Mobile: < 768px
- Tablet: 768px – 1024px
- Desktop: > 1024px

---

## Step-by-Step Guide

### Step 1: Create HTML Structure

**Objective:** Set up semantic HTML for a responsive portfolio.

**Instructions:**

Create `portfolio.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Responsive Portfolio</title>
    <link rel="stylesheet" href="responsive-styles.css" />
  </head>
  <body>
    <header class="site-header">
      <nav class="main-nav">
        <a href="#" class="logo">My Portfolio</a>
        <ul class="nav-links">
          <li><a href="#about">About</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <section class="hero">
        <h1>Welcome to My Portfolio</h1>
        <p>Creating beautiful, responsive web experiences</p>
      </section>

      <section id="about" class="about-section">
        <h2>About Me</h2>
        <p>
          I'm a web developer focused on creating accessible, user-friendly
          websites that work on any device.
        </p>
      </section>

      <section id="projects" class="projects-section">
        <h2>My Projects</h2>
        <div class="project-grid">
          <article class="project-card">
            <h3>Project One</h3>
            <p>A responsive website for a local business.</p>
          </article>
          <article class="project-card">
            <h3>Project Two</h3>
            <p>An interactive data visualization.</p>
          </article>
          <article class="project-card">
            <h3>Project Three</h3>
            <p>A mobile-first web application.</p>
          </article>
          <article class="project-card">
            <h3>Project Four</h3>
            <p>An accessible form interface.</p>
          </article>
        </div>
      </section>

      <section id="contact" class="contact-section">
        <h2>Get In Touch</h2>
        <form class="contact-form">
          <input type="text" placeholder="Your Name" required />
          <input type="email" placeholder="Your Email" required />
          <textarea placeholder="Your Message" rows="5" required></textarea>
          <button type="submit">Send Message</button>
        </form>
      </section>
    </main>

    <footer class="site-footer">
      <p>&copy; 2025 My Portfolio. All rights reserved.</p>
    </footer>
  </body>
</html>
```

**Expected Result:**

- Unstyled but structured HTML page
- Viewport meta tag ensures proper mobile scaling

**Why This Step:**
The viewport meta tag is crucial for responsive design—without it, mobile browsers render at desktop width and zoom out.

**Quick Self-Check:**

- [ ] Page opens in browser
- [ ] All sections visible
- [ ] Viewport meta tag present

---

### Step 2: Add Mobile-First Base Styles

**Objective:** Create foundational styles optimized for mobile.

**Instructions:**

Create `responsive-styles.css`:

```css
/* Mobile-First Base Styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  color: #333;
}

/* Header & Navigation */
.site-header {
  background-color: #2c3e50;
  color: #fff;
  padding: 1rem;
}

.main-nav {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
  color: #fff;
  text-decoration: none;
}

.nav-links {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.nav-links a {
  color: #fff;
  text-decoration: none;
  padding: 0.5rem;
  display: block;
}

.nav-links a:hover {
  background-color: #34495e;
}

/* Hero Section */
.hero {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: #fff;
  padding: 3rem 1rem;
  text-align: center;
}

.hero h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

/* Sections */
section {
  padding: 2rem 1rem;
}

h2 {
  margin-bottom: 1rem;
  color: #2c3e50;
}

/* Project Grid (starts as single column on mobile) */
.project-grid {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.project-card {
  background-color: #f8f9fa;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.project-card h3 {
  color: #667eea;
  margin-bottom: 0.5rem;
}

/* Contact Form */
.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 500px;
}

.contact-form input,
.contact-form textarea {
  padding: 0.75rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-family: inherit;
}

.contact-form button {
  background-color: #667eea;
  color: #fff;
  padding: 0.75rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
}

.contact-form button:hover {
  background-color: #5568d3;
}

/* Footer */
.site-footer {
  background-color: #2c3e50;
  color: #fff;
  text-align: center;
  padding: 1.5rem;
}
```

**Expected Result:**

- Page styled for mobile devices
- Single-column layout
- Navigation stacked vertically

**Why This Step:**
Starting with mobile styles ensures the site works on the smallest screens. We'll enhance for larger screens later.

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting `box-sizing: border-box` causes width calculations to break.  
✅ **Tip:** Always include this in universal selector.

**Quick Self-Check:**

- [ ] Page looks good at 320px width
- [ ] All content readable without zooming
- [ ] Navigation accessible

---

### Step 3: Introduce Flexbox for Navigation

**Objective:** Use Flexbox to create flexible navigation layout.

**Instructions:**

Update navigation styles in `responsive-styles.css`:

```css
/* Flexbox Navigation for Tablet+ */
@media (min-width: 768px) {
  .main-nav {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .nav-links {
    flex-direction: row;
    gap: 2rem;
  }
}
```

**Expected Result:**

- On screens 768px+: horizontal navigation
- On smaller screens: vertical navigation (mobile-first base)

**Why This Step:**
Flexbox makes navigation flexible and easy to rearrange without changing HTML.

**Flexbox Key Properties:**

- `display: flex`: Enable flexbox
- `flex-direction`: row (horizontal) or column (vertical)
- `justify-content`: Align along main axis
- `align-items`: Align along cross axis
- `gap`: Space between flex items

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting to set `display: flex` on parent.  
✅ **Tip:** Flexbox only works on direct children of flex container.

**Quick Self-Check:**

- [ ] Navigation horizontal on wide screens
- [ ] Navigation vertical on mobile
- [ ] Items spaced evenly

---

### Step 4: Create Responsive Grid with CSS Grid

**Objective:** Build a responsive project grid using CSS Grid.

**Instructions:**

Update project grid styles:

```css
/* Responsive Project Grid */
@media (min-width: 768px) {
  .project-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }
}

@media (min-width: 1024px) {
  .project-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (min-width: 1400px) {
  .project-grid {
    grid-template-columns: repeat(4, 1fr);
    max-width: 1400px;
    margin: 0 auto;
  }
}
```

**Expected Result:**

- Mobile: 1 column
- Tablet: 2 columns
- Desktop: 3 columns
- Large desktop: 4 columns, centered

**Why This Step:**
CSS Grid is perfect for two-dimensional layouts. `1fr` (fractional unit) creates equal-width columns.

**CSS Grid Key Properties:**

- `display: grid`: Enable grid
- `grid-template-columns`: Define column structure
- `grid-template-rows`: Define row structure
- `gap`: Space between grid items
- `repeat()`: Shorthand for repeated values
- `1fr`: One fraction of available space

**Common Pitfall:**
⚠️ **Watch Out:** Mixing Flexbox and Grid unnecessarily.  
✅ **Tip:** Grid for 2D layouts, Flexbox for 1D layouts.

**Quick Self-Check:**

- [ ] Cards arranged in responsive columns
- [ ] Equal-width columns
- [ ] Appropriate for each screen size

---

### Step 5: Add Media Queries for Typography

**Objective:** Scale typography for different screen sizes.

**Instructions:**

Add responsive typography rules:

```css
/* Base (Mobile) Typography already set */

/* Tablet Typography */
@media (min-width: 768px) {
  .hero h1 {
    font-size: 2.5rem;
  }

  h2 {
    font-size: 2rem;
  }

  .contact-form {
    max-width: 600px;
  }
}

/* Desktop Typography */
@media (min-width: 1024px) {
  body {
    font-size: 18px;
  }

  .hero {
    padding: 5rem 2rem;
  }

  .hero h1 {
    font-size: 3rem;
  }

  section {
    padding: 3rem 2rem;
  }

  .about-section,
  .contact-section {
    max-width: 800px;
    margin: 0 auto;
  }
}
```

**Expected Result:**

- Text scales appropriately for each device
- Larger headings on bigger screens
- Content centered with max-width on desktop

**Why This Step:**
Readable text size varies by device. Mobile users hold phones close; desktop users sit farther away.

**Common Pitfall:**
⚠️ **Watch Out:** Text too small on mobile or too large on desktop.  
✅ **Tip:** Test at each breakpoint; aim for 16px minimum on mobile.

**Quick Self-Check:**

- [ ] Text readable at all sizes
- [ ] Headings scale proportionally
- [ ] Content doesn't stretch too wide on large screens

---

### Step 6: Make Images Responsive

**Objective:** Ensure images scale properly on all devices.

**Instructions:**

Add to `responsive-styles.css`:

```css
/* Responsive Images */
img {
  max-width: 100%;
  height: auto;
  display: block;
}

/* If you add images to project cards */
.project-card img {
  width: 100%;
  border-radius: 8px 8px 0 0;
  margin-bottom: 1rem;
}
```

Update HTML to add images (optional):

```html
<article class="project-card">
  <img src="project1.jpg" alt="Screenshot of Project One" />
  <h3>Project One</h3>
  <p>A responsive website for a local business.</p>
</article>
```

**Expected Result:**

- Images never overflow their container
- Maintain aspect ratio
- Scale down on small screens

**Why This Step:**
`max-width: 100%` prevents images from breaking layout on small screens while `height: auto` maintains proportions.

**Common Pitfall:**
⚠️ **Watch Out:** Fixed-width images break mobile layout.  
✅ **Tip:** Always use `max-width: 100%` on images.

**Quick Self-Check:**

- [ ] Images resize with container
- [ ] No horizontal scrolling
- [ ] Aspect ratio preserved

---

### Step 7: Test Responsive Design

**Objective:** Verify layout works across all screen sizes.

**Instructions:**

**In Browser DevTools:**

1. Open DevTools (F12)
2. Click device toolbar icon (or Ctrl+Shift+M / Cmd+Shift+M)
3. Test these sizes:
   - iPhone SE: 375px
   - iPad: 768px
   - Laptop: 1024px
   - Desktop: 1440px

**What to Check:**

- Navigation changes from vertical to horizontal
- Project grid columns increase with screen width
- Text scales appropriately
- No horizontal scrolling
- Touch targets large enough on mobile (44x44px minimum)

**Expected Result:**

- Smooth transitions between breakpoints
- Content readable at all sizes
- Layout never breaks

**Why This Step:**
Testing ensures responsive design works in practice, not just theory.

**Common Pitfall:**
⚠️ **Watch Out:** Testing only on your device.  
✅ **Tip:** Test on real devices when possible; emulators don't catch everything.

**Quick Self-Check:**

- [ ] Tested at mobile, tablet, desktop sizes
- [ ] All content accessible
- [ ] No layout breaks

---

## Debugging Section

**Scenario 1: Media queries not working**

- **Possible Causes:**
  - Missing viewport meta tag
  - Syntax error in media query
  - Specificity issue (base styles too specific)
- **Solution:**
  - Check `<meta name="viewport">` in HTML head
  - Validate CSS syntax
  - Use DevTools to see which rules apply

**Scenario 2: Grid/Flexbox not behaving**

- **Possible Cause:** `display: grid` or `display: flex` not on parent
- **Solution:** Check parent element has correct display property

**Scenario 3: Layout breaks at specific width**

- **Possible Cause:** Missing breakpoint or hard-coded widths
- **Solution:** Add intermediate breakpoint or remove fixed widths

**Scenario 4: Images overflow on mobile**

- **Possible Cause:** No `max-width: 100%` on images
- **Solution:** Add responsive image CSS

**General Debugging Tips:**

- Use DevTools responsive mode to test
- Temporarily add `border: 1px solid red` to see element boundaries
- Check Computed styles to see which rules apply
- Reduce browser width slowly to find exact break point

---

## Consolidated Key Concepts

**1. Mobile-First Approach**

- Start with mobile styles (base)
- Add desktop styles in media queries
- Progressive enhancement

**2. Flexbox (One-Dimensional)**

- `display: flex`
- `flex-direction`: row or column
- `justify-content`, `align-items`
- Perfect for navigation, toolbars

**3. CSS Grid (Two-Dimensional)**

- `display: grid`
- `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))`
- Perfect for card layouts, galleries

**4. Media Queries**

```css
@media (min-width: 768px) {
  /* Styles for tablets and up */
}
```

**5. Responsive Units**

- `%`: Relative to parent
- `em`: Relative to element font-size
- `rem`: Relative to root font-size
- `vw/vh`: Viewport width/height
- `fr`: Fraction of available space (Grid)

---

## Practice Variations

**Variation 1: Different Breakpoints**

- Research breakpoints for specific devices
- Add intermediate breakpoints (e.g., 480px, 1200px)
- Test on actual devices

**Variation 2: Advanced Grid**

- Use `grid-template-areas` for named layout regions
- Create asymmetric layouts
- Implement magazine-style layouts

**Variation 3: Container Queries**

- Research and implement container queries (newer feature)
- Compare to media queries

---

## Reflection Prompts

1. **Why start with mobile-first design instead of desktop-first?**

   - [Space for student response]

2. **When would you use Flexbox vs. CSS Grid?**

   - [Space for student response]

3. **How does responsive design improve accessibility?**
   - [Space for student response]

---

## Further Reading

**Official Documentation:**

- [MDN: Responsive Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
- [MDN: Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [MDN: CSS Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
- [MDN: Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)

**Related Tutorials:**

- Previous: Unit 3.1 — CSS Fundamentals
- Next: Module 04 — JavaScript Essentials

**Interactive Learning:**

- [Flexbox Froggy](https://flexboxfroggy.com/)
- [Grid Garden](https://cssgridgarden.com/)

**Advanced Topics:**

- Container queries
- Responsive images with `<picture>` and `srcset`
- CSS custom properties for theming

---

## Accessibility Considerations

**This Tutorial Emphasized:**

- ✅ Mobile-first ensures content accessible on all devices
- ✅ Touch targets sized appropriately (44x44px minimum)
- ✅ Text scales with viewport
- ✅ No horizontal scrolling required

**Responsive & Accessible:**

- Zoom should work without breaking layout
- Keyboard navigation works at all sizes
- Content order logical for screen readers
- Focus indicators visible at all breakpoints

**Next Steps:**

- Module 04 will add interactivity with JavaScript

---

## Metadata

**Module:** 03 — CSS Styling & Layout  
**Unit:** 3.2 — Responsive Layouts  
**Author:** Digital Proficiency Kit Team  
**Contributors:** N/A  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Unit 3.2 Tutorial -->
