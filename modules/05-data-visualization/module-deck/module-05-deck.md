---
marp: true
theme: default
paginate: true
---

<!-- _class: lead -->

# Module 05

## Data Visualization

**Digital Proficiency Kit**
STEAM Education Series

---

## Module Overview

**Duration:** ~2 lessons (90 minutes)

**Prerequisites:**

- Module 01: Introduction to the Web
- Module 02: HTML Foundations
- Module 03: CSS Styling & Layout
- Module 04: JavaScript Essentials

**Key Question:**
How can we turn numbers into visual stories that everyone can understand?

---

## What You'll Learn

By the end of this module, you will be able to:

- Draw shapes and text using HTML5 Canvas
- Map numeric data to visual encodings (height, position, color)
- Implement scaling functions for accurate representation
- Create accessible charts with companion data tables
- Explain design choices and identify misleading visualizations
- Build interactive data-driven web graphics

---

## Why Data Visualization?

**Data is everywhere:**

- Climate change metrics
- School recycling rates
- Personal fitness tracking
- Population demographics

**But raw numbers are hard to understand.**

**Visualization makes data:**

- **Accessible** — patterns emerge visually
- **Memorable** — easier to recall than tables
- **Persuasive** — supports arguments and decisions

---

## Real-World Applications

**Science:**

- Climate data (temperature, CO₂, sea levels)
- Experiment results (plant growth, chemical reactions)

**Social Studies:**

- Population trends
- Economic indicators

**Personal:**

- Fitness trackers
- Budget apps
- Screen time dashboards

**Journalism:**

- Election results
- COVID-19 dashboards

---

## Canvas vs Other Approaches

**HTML/CSS:**

- Static bar charts with styled divs
- Limited interactivity
- Accessible by default

**Canvas (this module):**

- Dynamic, pixel-based graphics
- Full control over drawing
- Good for complex visualizations
- Requires additional accessibility work

**SVG:**

- Scalable vector graphics
- Good for interactive, zoomable charts
- Each shape is a DOM element

---

## Module Structure

**Unit 5.1: Canvas Basics & Data Visualization**

- HTML5 Canvas fundamentals
- Drawing shapes, text, and lines
- Data preparation and scaling
- Creating bar charts
- Axes, labels, and legends
- Accessibility with data tables

**Estimated Time:** 90–120 minutes

---

## Unit 5.1: Canvas Basics

**What You'll Build:**
An interactive CO₂ savings tracker with:

- Bar chart showing monthly data
- Accurate scaling from zero
- Color coding (above/below average)
- Clear labels and axes
- Accessible HTML table
- Update button for new data

**Skills:**

- Canvas API (fillRect, fillText, stroke)
- Coordinate system and positioning
- Scaling calculations
- Chart design principles

---

## Learning Pathway

**Step 1:** Canvas setup and coordinate system

**Step 2:** Drawing shapes and text (rectangles, lines)

**Step 3:** Working with data arrays (min, max, average)

**Step 4:** Scaling function (data → pixels)

**Step 5:** Drawing bar chart (loops, positioning)

**Step 6:** Adding labels, axes, legends

**Step 7:** Accessibility (data tables, aria-labels)

---

## Key Concepts: Canvas Coordinate System

```
(0,0) ────────────► X increases
  │
  │
  │
  ▼
Y increases (downward!)
```

**Different from math class!**

- Origin at **top-left**, not bottom-left
- Y increases **downward**, not upward

**Implication:**
To draw bars growing upward, calculate: `y = height - barHeight`

---

## Key Concepts: Scaling

**Problem:** Data values don't match pixel dimensions

**Solution:** Proportional scaling

**Formula:**

```
pixelHeight = (dataValue / maxValue) × chartHeight
```

**Example:**

- Data: 30 kg CO₂
- Max: 60 kg
- Chart height: 300 px
- Result: (30/60) × 300 = **150 px**

**Key Insight:** Maintains accurate proportions

---

## Key Concepts: Chart Ethics

**Honest Design:**

- ✅ Start bar charts at **zero**
- ✅ Use **proportional scaling**
- ✅ Label axes with **units**
- ✅ Provide **clear title**

**Misleading Design:**

- ❌ Truncated axes (exaggerate differences)
- ❌ Inconsistent bar widths
- ❌ Missing labels or units
- ❌ Cherry-picked data

**Responsibility:** Charts influence perception and decisions

---

## Key Concepts: Accessibility

**Canvas is Not Accessible by Default**

Canvas renders as pixels; screen readers can't interpret.

**Solutions:**

1. **Companion HTML table** with all data
2. **ARIA labels** on Canvas element
3. **Fallback content** inside `<canvas>` tag
4. **Don't rely on color alone** (use labels + patterns)

**Inclusive Design = Better for Everyone**

---

## STEAM Connections

**Science:**

- Visualize experiment data
- Climate and environmental metrics

**Technology:**

- Canvas API, JavaScript programming
- Data structures and algorithms

**Engineering:**

- Problem solving (how to position bars?)
- Scaling calculations

**Arts:**

- Visual design principles
- Color theory, layout, typography

**Mathematics:**

- Ratios and proportions
- Coordinate geometry
- Statistical concepts (mean, range)

---

## Competence Mapping (DigComp 2.2)

**3.1 Developing digital content**

- Creating data visualizations with code

**3.2 Integrating and re-elaborating**

- Combining data, Canvas, and HTML tables

**3.4 Programming**

- Using JavaScript for drawing and computation

**5.2 Identifying needs and technological responses**

- Choosing appropriate chart types for data

---

## Materials You'll Need

**Software:**

- Web browser (Chrome, Firefox, Edge, Safari)
- Text editor (VS Code recommended)

**Files Provided:**

- Unit 5.1 Tutorial (step-by-step guide)
- Student Workbook (fill-ins, practice, reflection)
- Teacher-Annotated Workbook (answers, strategies)
- Starter code templates

**Optional:**

- CodePen or similar for live coding

---

## Lesson Flow (90 minutes)

**0:00–0:10** — Introduction: What is Canvas? When to use it?

**0:10–0:25** — Demo: Canvas setup and basic drawing

**0:25–0:45** — Guided Practice: Data preparation and scaling

**0:45–1:15** — Main Task: Build bar chart with labels and table

**1:15–1:25** — Accessibility & Ethics discussion

**1:25–1:30** — Reflection and sharing

---

## Assessment

**What You'll Create:**
A functional, accessible bar chart

**Criteria:**

- **Accuracy:** Data correctly scaled and represented
- **Clarity:** Labels, axes, title, legend
- **Accessibility:** Data table, aria-labels, fallback content
- **Code Quality:** Organized, commented, no errors
- **Design Reasoning:** Can explain scaling and encoding choices

**Rubric Levels:** Beginning, Developing, Proficient, Advanced

---

## Differentiation

**Support:**

- Starter code with TODOs
- Pre-calculated constants (padding, bar width)
- Pair programming with stronger student

**Challenge:**

- Multi-series bar chart (grouped or stacked)
- Animated bar growth on page load
- Different chart types (line, scatter)
- Click interaction (show exact value on hover)
- Export chart to image

---

## Extension Activities

**Activity 1:** Different chart type (line, scatter, pie)

**Activity 2:** Multi-series chart (compare two datasets)

**Activity 3:** Animated chart (bars grow from zero)

**Activity 4:** Real-world data (weather, sports, recycling)

**Activity 5:** Chart library (build reusable functions)

**Activity 6:** Misleading chart analysis (find and fix issues)

---

## Common Challenges & Solutions

**Challenge 1:** "My canvas is blank!"

- **Check:** Browser console for errors
- **Check:** Canvas size (width/height attributes)
- **Check:** Context obtained correctly

**Challenge 2:** "Bars are upside-down!"

- **Fix:** Use `y = height - padding - barHeight`

**Challenge 3:** "Bars are too tall/short!"

- **Fix:** Verify scaling function and max value

**Challenge 4:** "Text is cut off!"

- **Fix:** Check x, y coordinates and canvas size

---

## Debugging Strategy

**1. Check Console**

- Look for error messages
- Fix typos and syntax errors

**2. Log Values**

```javascript
console.log("Data:", data);
console.log("Max:", maxValue);
console.log("Bar height:", barHeight);
console.log("Position:", x, y);
```

**3. Simplify**

- Draw one bar first
- Add complexity incrementally

**4. Ask for Help**

- Show code to partner or teacher
- Explain what you expect vs what happens

---

## Professional Practice

**Version Control:**

- Save versions as you work
- Use meaningful filenames: `chart-v1.html`, `chart-v2.html`

**Code Comments:**

- Explain why, not just what
- Note assumptions and calculations

**Testing:**

- Try different data values
- Test on different browsers
- Check with screen reader (if available)

**Documentation:**

- Write brief explanation of chart
- Note data sources

---

## Reflection Questions

**Technical:**

- How does scaling maintain accurate proportions?
- Why does Y increase downward in Canvas?

**Design:**

- What makes a chart easy to understand?
- How can charts mislead?

**Ethical:**

- What responsibility do data visualizers have?
- How would you explain your design choices?

**Practical:**

- When would you choose Canvas over HTML/CSS?
- What real-world data would you visualize?

---

## Beyond This Module

**Next Module:**

- **Module 06: Creative Web Projects** — Generative art, animation
- Apply Canvas to creative coding

**Future Learning:**

- Chart libraries (Chart.js, D3.js)
- Advanced Canvas (gradients, patterns, clipping)
- SVG for interactive graphics
- Data-driven storytelling

**Career Connections:**

- Data analyst
- UX/UI designer
- Journalist (data visualization)
- Scientist (research communication)

---

## Resources

**Official Documentation:**

- [MDN: Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [MDN: Canvas Tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)

**Data Visualization:**

- [Chart Chooser](https://www.qlik.com/us/data-visualization/chart-types)
- [Data Viz Principles](https://www.interaction-design.org/literature/article/data-visualization-principles)

**Datasets:**

- [Our World in Data](https://ourworldindata.org/)
- [Data.gov](https://data.gov/)

---

## Success Criteria

**You'll know you've succeeded when you can:**

✅ Draw shapes and text on Canvas with JavaScript

✅ Map data values to pixel coordinates using scaling

✅ Create accurate bar charts that start at zero

✅ Add clear labels, axes, and legends

✅ Provide accessible data tables alongside charts

✅ Explain your design choices and identify misleading charts

---

<!-- _class: lead -->

# Let's Visualize Data!

**Module 05: Data Visualization**

Ready to turn numbers into visual stories?

---

<!-- End of Module 05 Deck -->
