# Teacher-Annotated Workbook: Unit 5.1 — Canvas Basics & Data Visualization

**Module:** 05 — Data Visualization  
**Unit:** 5.1 — Canvas Basics  
**Recommended Time:** 90–120 minutes  
**Prerequisites:** Modules 01–04 (HTML, CSS, JavaScript basics)

---

## Teaching Guide Overview

### Learning Objectives

By the end of this unit, students will be able to:

1. **Explain** what HTML5 Canvas is and when to use it
2. **Draw** shapes and text on Canvas using JavaScript
3. **Map** numeric data values to visual encodings (bar heights, positions)
4. **Implement** scaling functions to convert data to pixel coordinates
5. **Create** axes, labels, and legends for chart clarity
6. **Build** an accessible data table alongside visual charts
7. **Explain** chart design choices and identify potential misinterpretations

### Competence Mapping (DigComp 2.2)

- **3.1 Developing digital content:** Creating data visualizations
- **3.2 Integrating and re-elaborating:** Combining data, Canvas, and accessibility
- **3.4 Programming:** Using JavaScript to draw and compute visual encodings
- **5.2 Identifying needs and technological responses:** Choosing appropriate visualization types

### Lesson Flow (90 minutes)

1. **Introduction (10 min):** What is Canvas? When to use raster vs vector?
2. **Demonstration (15 min):** Canvas setup and basic drawing
3. **Guided Practice (20 min):** Data preparation and scaling
4. **Main Task (30 min):** Building the bar chart
5. **Accessibility & Ethics (10 min):** Tables, labels, honest scaling
6. **Reflection & Sharing (5 min):** Chart review, design choices

---

## Answer Key: Part 1 — Key Concepts Fill-In

**Canvas Basics**

1. Canvas is a **raster**-based drawing surface
2. To draw on Canvas, you need the drawing **context** from `getContext()`
3. Canvas coordinates start at (0, 0) in the **top-left** corner
4. In Canvas, the Y-axis increases **downward**
5. To clear the entire canvas, use: `ctx.**clearRect**(0, 0, width, height)`

**Data Visualization**

6. The process of mapping data values to visual properties is called **encoding** (or **visual encoding**)
7. For bar charts, the scale should typically start at **zero** (or **0**)
8. A **truncated** (or **non-zero**) axis can mislead viewers about data magnitudes
9. Always provide a(n) **data table** (or **HTML table**) for screen reader accessibility
10. The formula for scaling is: pixelHeight = (dataValue / **maxValue**) × availableHeight

**Drawing Methods**

11. To draw a filled rectangle: `ctx.**fillRect**(x, y, width, height)`
12. To draw text: `ctx.**fillText**(text, x, y)`
13. Before drawing text, set the font with: `ctx.**font** = "16px Arial"`
14. To set text alignment: `ctx.**textAlign** = "center"`
15. To change fill color: `ctx.**fillStyle** = "blue"`

### Teaching Notes

**Common Misconceptions:**

- Students may confuse Canvas (raster) with SVG (vector). Clarify: Canvas is pixel-based and good for dynamic/data-driven graphics; SVG is shape-based and better for scalable, interactive graphics.
- Y-axis direction: In Canvas, Y increases downward (unlike math class graphs). Use visual diagrams.
- Coordinate origin: Always at top-left, not bottom-left.

**Formative Assessment:**

- Ask students to sketch coordinate system on paper
- Have students calculate scaled values by hand before coding
- Check understanding: "Why start bar charts at zero?"

---

## Answer Key: Part 2 — Guided Practice Notes

### Step 1: Canvas Setup

**Create Canvas element:**

```html
<canvas id="my-canvas" width="800" height="400">
  Fallback text for browsers without Canvas support
</canvas>
```

**Get Canvas context:**

```javascript
const canvas = document.getElementById("my-canvas");
const ctx = canvas.getContext("2d");
```

**Why is fallback content important?**

_Expected Answer:_ For browsers without Canvas support, assistive technologies, and search engines. Ensures accessibility and progressive enhancement.

### Teaching Notes

**Key Points to Emphasize:**

- Canvas requires JavaScript; without it, only fallback is shown
- Width/height should be set as attributes, not CSS (to avoid distortion)
- The context (`ctx`) is where all drawing methods live

**Common Student Errors:**

- Forgetting to get context before drawing → `Cannot read property 'fillRect' of null`
- Setting size with CSS instead of attributes → blurry/stretched canvas
- Using wrong context string: `"2D"` instead of `"2d"` (case-sensitive)

**Differentiation:**

- **Support:** Provide pre-written HTML structure; focus on JavaScript
- **Extension:** Have students explore `canvas.toDataURL()` to export image

---

### Step 2: Drawing Shapes

**Answer Key:**

```javascript
ctx.fillStyle = "green"; // Color
ctx.fillRect(50, 50, 100, 80);
```

**Rectangle parameters:**

- `x`: **Horizontal** position from left
- `y`: **Vertical** position from top
- `width`: Rectangle **width**
- `height`: Rectangle **height**

**Draw text:**

```javascript
ctx.font = "16px Arial";
ctx.textAlign = "center";
ctx.fillText("Hello Canvas", 100, 100);
```

**Coordinate System:**

```
(0,0) is at: top-left
X increases: rightward
Y increases: downward
```

### Teaching Notes

**Demonstration Strategy:**

1. Draw rectangle live while explaining each parameter
2. Show effect of changing x, y, width, height in real-time
3. Use `console.log` to show coordinate values
4. Draw grid overlay to visualize coordinate system

**Common Student Errors:**

- Negative width/height (draws nothing)
- Confusing x/y with width/height order
- Forgetting to set `fillStyle` before drawing (uses previous color)

**Formative Check:**

Ask: "What coordinates would center a 100×100 rectangle in an 800×400 canvas?"  
_Answer:_ x = 350, y = 150 (canvas center is 400, 200; subtract half dimensions)

---

### Step 3: Working with Data

**Answer Key:**

```javascript
const min = Math.min(...data);
const max = Math.max(...data);
```

**Why do we need to know the data range?**

_Expected Answer:_ To scale values proportionally to fit in the available chart height. Without knowing the max, we can't determine how tall each bar should be.

**Accessible table example:**

```html
<table>
  <caption>
    CO₂ Savings by Month
  </caption>
  <thead>
    <tr>
      <th>Month</th>
      <th>CO₂ Saved (kg)</th>
    </tr>
  </thead>
  <tbody id="table-body">
    <!-- Populated by JavaScript -->
  </tbody>
</table>
```

### Teaching Notes

**Key Concepts:**

- **Spread operator (`...`):** Expands array for Math functions
- **Data range:** Necessary for proportional scaling
- **Accessible tables:** Not "extra work"—core requirement for inclusive design

**Common Student Errors:**

- Using `Math.max(data)` without spread → returns `NaN`
- Finding min but not using it (for bar charts starting at 0, min isn't used in scaling)
- Forgetting `<caption>` for table context

**Discussion Prompt:**

"Why is a data table important even if we have a visual chart?"

_Expected Answers:_

- Screen readers can't interpret Canvas pixels
- Exact values are clearer in table format
- Tables are searchable, sortable, can be copied
- Fallback for Canvas-unsupported browsers

**Extension:**

- Have students populate table dynamically with JavaScript
- Show how `aria-labelledby` can link Canvas to table

---

### Step 4: Scaling Function

**Answer Key:**

```javascript
function scaleValue(value, maxValue, chartHeight) {
  return (value / maxValue) * chartHeight;
}
```

**Example calculation:**

- Data value: 30
- Max value: 45
- Chart height: 280 pixels
- Result: (30 / 45) × 280 = **186.67 pixels** (or ~187)

**Why start bar charts at zero?**

_Expected Answer:_ To show accurate proportions and avoid misleading comparisons. If the axis starts at a non-zero value, small differences appear exaggerated.

**What happens if you don't start at zero?**

_Expected Answer:_ Viewers can be misled about the magnitude of differences. A bar that looks twice as tall might represent only a 10% difference in data.

### Teaching Notes

**Deep Dive: Scaling Logic**

Explain the ratio:

```
(dataValue / maxValue) = fraction of maximum
× chartHeight = pixel height for this bar
```

Use visual fraction diagrams:

- If value is 30 and max is 60, that's 30/60 = 0.5 = 50% of max
- So bar should be 50% of chart height

**Common Student Errors:**

- Dividing by chart height instead of max value
- Using min instead of max
- Forgetting to multiply by chart height (returns fraction instead of pixels)
- Integer division issues (rare in JS, but explain float results)

**Formative Assessment:**

Provide scaling scenarios and have students calculate by hand:

| Data | Max | Height | Expected Result |
| ---- | --- | ------ | --------------- |
| 20   | 40  | 200    | 100 px          |
| 15   | 60  | 300    | 75 px           |
| 100  | 100 | 250    | 250 px          |

**Extension: Non-Zero Baselines**

For advanced students, discuss when non-zero baselines might be appropriate:

- Small variations in large numbers (e.g., stock prices)
- BUT: Always label clearly and consider dual-axis or broken-axis notation
- Best practice: Include context and never hide the baseline

---

### Step 5: Drawing Bar Chart

**Answer Key:**

```javascript
data.forEach((value, index) => {
  // Scale value to pixels
  const barHeight = scaleValue(value, maxValue, CHART_HEIGHT);

  // Calculate X position
  const x = PADDING + index * barSpacing;

  // Calculate Y position (from bottom!)
  const y = height - PADDING - barHeight;

  // Draw bar
  ctx.fillStyle = "green";
  ctx.fillRect(x, y, barWidth, barHeight);
});
```

**Why calculate Y as `height - PADDING - barHeight`?**

_Expected Answer:_ Because Canvas Y-axis increases downward, but we want bars to grow upward from the bottom. We start from the bottom edge (`height - PADDING`) and move up by the bar's height.

**Bar spacing:**

- Total width for each bar: _Depends on canvas width and number of bars_
- Actual bar width (80%): `barSpacing * 0.8`
- Gap (20%): `barSpacing * 0.2`

### Teaching Notes

**Whiteboard Visual:**

Draw Canvas coordinate system showing:

```
Top: y = 0
Bottom: y = height

For bar at bottom:
y_top = height - barHeight
```

**Common Student Errors:**

- Calculating y as just `barHeight` → bars appear upside-down at top
- Forgetting padding → bars overlap axes
- Using wrong index for x-position (off-by-one errors)
- Hardcoding bar width instead of calculating from canvas width

**Step-by-Step Debugging:**

If bars don't appear:

1. Check console for errors
2. `console.log(x, y, barWidth, barHeight)` to verify values
3. Ensure values are within canvas bounds
4. Check that barHeight > 0
5. Verify fillStyle is set

**Differentiation:**

- **Support:** Provide partial code with TODOs; students fill in calculations
- **Challenge:** Add color gradient based on value (high = dark green, low = light green)

---

### Step 6: Adding Labels and Axes

**Answer Key:**

```javascript
// Y-axis
ctx.beginPath();
ctx.moveTo(PADDING, PADDING);
ctx.lineTo(PADDING, height - PADDING);
ctx.stroke();

// X-axis
ctx.beginPath();
ctx.moveTo(PADDING, height - PADDING);
ctx.lineTo(width - PADDING, height - PADDING);
ctx.stroke();
```

**Rotated Y-axis label:**

```javascript
ctx.save();
ctx.translate(20, height / 2);
ctx.rotate(-Math.PI / 2); // Rotate 90 degrees counter-clockwise
ctx.fillText("CO₂ Saved (kg)", 0, 0);
ctx.restore();
```

**What does `ctx.save()` and `ctx.restore()` do?**

_Expected Answer:_ `save()` stores the current drawing state (transformations, styles). `restore()` returns to that saved state. This prevents rotation from affecting subsequent drawing.

### Teaching Notes

**Canvas State Management:**

Explain the "state stack":

- `save()`: Push current state onto stack
- `restore()`: Pop state from stack
- Useful for temporary transformations

**Common Student Errors:**

- Forgetting `beginPath()` → lines connect unexpectedly
- Not calling `stroke()` → nothing appears
- Rotating without save/restore → everything afterward is rotated
- Wrong rotation angle (radians vs degrees)

**Visual Demonstration:**

1. Draw axis without `beginPath()` → show unintended connections
2. Rotate text without restore → show subsequent elements rotated
3. Fix with proper save/restore

**Math Connection:**

- π radians = 180°
- π/2 = 90°
- -π/2 = -90° (counter-clockwise)

**Extension:**

- Add tick marks on Y-axis at regular intervals
- Label tick marks with values
- Add grid lines for easier reading

---

## Answer Key: Part 3 — Code Snippet Collection

**Notes on when to use each pattern:**

_Expected Answers:_

1. **Clear canvas:** Before redrawing entire chart (e.g., on data update)
2. **Draw filled rectangle:** Bars, backgrounds, colored blocks
3. **Draw text (centered):** Labels, titles, values
4. **Draw line:** Axes, grid lines, connecting points
5. **Scale data value:** Converting any data to visual encoding
6. **Position bar from bottom:** Any upward-growing bar chart

### Teaching Notes

**Pattern Recognition:**

Help students see these as reusable "recipes"

- Encourage creating a personal reference sheet
- Have students annotate with their own comments

**Code Organization:**

Suggest extracting patterns into functions:

```javascript
function drawBar(ctx, x, y, width, height, color) {
  ctx.fillStyle = color;
  ctx.fillRect(x, y, width, height);
}
```

---

## Answer Key: Part 4 — Independent Task Checklist

### Completion Criteria

**Minimum Viable Product (Proficient Level):**

- [ ] Canvas displays 12 bars (one per month)
- [ ] Bars scaled correctly and positioned from bottom
- [ ] Month labels below each bar
- [ ] Y-axis with label
- [ ] HTML table with all data
- [ ] No console errors

**Advanced Features:**

- [ ] Color coding (e.g., above/below average)
- [ ] Value labels on top of bars
- [ ] Legend explaining colors
- [ ] Interactive update button
- [ ] Chart title and caption

### Teaching Notes

**Time Management:**

- **Minimum task:** 20–30 minutes
- **With extensions:** 40–60 minutes

**Scaffolding Strategies:**

1. **Heavy Support:** Provide starter code with TODOs
2. **Medium Support:** Provide data and constants; students write drawing code
3. **Light Support:** Provide only the tutorial; students build from scratch

**Circulating Questions:**

- "Show me how you calculated this bar's height."
- "What would happen if you changed the max value?"
- "How did you decide on your padding values?"
- "Can you explain this line of code to me?"

**Common Blockers:**

1. **Bars not showing:** Check y-position calculation
2. **Bars wrong height:** Verify scaling function
3. **Labels misaligned:** Check x-position and textAlign
4. **Canvas blank:** Check for JS errors, verify context

---

## Answer Key: Part 5 — Self-Assessment Rubric

### Rubric Interpretation

**4 = Advanced:**

- Goes beyond requirements
- Code is elegant and reusable
- Demonstrates deep understanding

**3 = Proficient:**

- Meets all requirements
- Code works correctly
- Can explain all concepts

**2 = Developing:**

- Partial completion
- Some errors or missing features
- Understanding is surface-level

**1 = Beginning:**

- Minimal progress
- Significant errors
- Needs substantial support

### Teaching Notes

**Using Self-Assessment:**

- Have students complete before teacher assessment
- Discuss discrepancies (helps calibrate understanding)
- Use as starting point for one-on-one conferences

**Evidence Examples:**

- "I drew 12 bars with correct heights" → Proficient in Bar Chart
- "I can change data and chart updates correctly" → Advanced in Data Handling
- "My chart has aria-label and data table" → Proficient in Accessibility

---

## Answer Key: Part 6 — Reflection

**1. Why is it important to provide a data table alongside the chart?**

_Expected Answer:_ For accessibility (screen readers can't interpret Canvas pixels), precision (exact values), and compatibility (works without Canvas support). It's an inclusive design practice.

**2. How does scaling affect the visual perception of differences in data?**

_Expected Answer:_ Scaling determines how large differences appear. Proportional scaling from zero shows true ratios. Non-proportional or truncated scales can exaggerate or minimize differences, potentially misleading viewers.

**3. What could mislead viewers if the chart is not designed carefully?**

_Expected Answers:_

- Truncated axis (not starting at zero)
- Inconsistent bar widths
- Missing units or labels
- Misleading colors (e.g., red/green without labels—accessibility issue)
- Cherry-picked data or time ranges

**4. When would you use Canvas instead of creating a chart with HTML/CSS?**

_Expected Answers:_

- Dynamic data that updates frequently
- Complex visualizations (scatter plots, heat maps)
- Animations or interactive graphics
- When pixel-level control is needed
- Large datasets (Canvas can be more performant)

**5. How would you choose between a bar chart and a line chart?**

_Expected Answers:_

- **Bar chart:** Categorical data, comparing discrete values, showing individual data points
- **Line chart:** Continuous data, showing trends over time, emphasizing change rate

### Teaching Notes

**Discussion Facilitation:**

- Use think-pair-share for each question
- Display charts with ethical issues; have students identify problems
- Show real-world examples of misleading charts

**Extension:**

- Research "How to Lie with Statistics" examples
- Find misleading chart in news; redesign it honestly
- Create two versions of same data: honest vs misleading

---

## Answer Key: Part 7 — Vocabulary Glossary

**Model Answers:**

**Canvas:** An HTML element that provides a raster-based drawing surface for graphics, controlled by JavaScript.

**Context (ctx):** The drawing interface for Canvas; obtained via `getContext("2d")`. All drawing methods are called on the context.

**Raster Graphics:** Pixel-based images. Each pixel has a specific color. Scaling can cause blurriness.

**Scaling:** The process of mapping data values to visual dimensions (e.g., data value → pixel height).

**Data Encoding:** Translating data into visual properties (position, size, color, shape).

**Axis:** A reference line showing the scale of measurement (X-axis = horizontal, Y-axis = vertical).

**Legend:** A key explaining what colors, symbols, or patterns represent in the chart.

**Accessibility:** Designing so everyone, including people with disabilities, can access and understand content.

**Coordinate System:** The framework for positioning elements. Canvas uses (0,0) at top-left, X increases right, Y increases down.

**Pixel:** The smallest unit of a raster image. Canvas draws by setting pixel colors.

### Teaching Notes

**Vocabulary Strategies:**

- Have students create illustrated definitions
- Use vocabulary in context during lessons
- Quiz with "match term to definition"
- Encourage students to use terms when explaining code

---

## Answer Key: Part 8 — Chart Design Analysis

**Problems Identified:**

1. **Y-axis starts at 20:** Exaggerates differences; bars don't show true proportions
2. **Bars have different widths:** Visually misleading; area doesn't match value
3. **No units on Y-axis:** Reader doesn't know what numbers mean
4. **Red/green colors without labels:** Inaccessible to colorblind users; meaning unclear
5. _Bonus:_ No title, no data source, no legend

**How to Fix:**

1. **Start Y-axis at 0:** Shows true proportional differences
2. **Make all bars same width:** Ensures only height encodes value
3. **Add units:** Label axis "Sales (thousands)" or similar
4. **Add text labels/patterns:** Don't rely on color alone; add legend
5. **Add title, source, legend:** Provide context and clarity

### Teaching Notes

**Critical Thinking:**

This exercise builds "chart literacy"—ability to evaluate visualizations critically.

**Activity Idea:**

- Collect misleading charts from news/web
- Students identify issues in small groups
- Share findings with class
- Discuss why these designs might be intentional or accidental

**Ethical Discussion:**

- Intent vs impact (accidental vs deliberate misleading)
- Responsibility of data visualizers
- How design choices can influence public opinion

---

## Answer Key: Part 9 — Debugging Log

**Common Errors & Solutions:**

| Error             | What Caused It                     | How I Fixed It                               |
| ----------------- | ---------------------------------- | -------------------------------------------- |
| Bars upside-down  | Y-axis confusion                   | Used `height - padding - barHeight` for y    |
| Bars not showing  | Drawing outside canvas bounds      | Checked x, y, width, height with console.log |
| Text not centered | Forgot `textAlign = "center"`      | Set textAlign before fillText                |
| Canvas blank      | JavaScript error halting execution | Checked console, fixed typo                  |
| Bars overlapping  | Incorrect x-position calculation   | Recalculated barSpacing                      |
| Scaling incorrect | Used wrong max value               | Verified Math.max(...data)                   |

### Teaching Notes

**Debugging Process:**

1. **Check console:** Look for error messages
2. **Console.log values:** Verify calculations
3. **Isolate problem:** Comment out code, add back piece-by-piece
4. **Check assumptions:** Is max correct? Is y-position right?
5. **Simplify:** Draw one bar first, then loop

**DevTools Tips:**

- Use breakpoints to pause execution
- Inspect canvas element to verify size
- Use `console.table(data)` to view array data
- Check `ctx` in console to see current state

**Growth Mindset:**

Frame errors as learning opportunities:

- "Bugs are normal and expected"
- "Each error teaches you something"
- "Debugging is a core programming skill"

---

## Answer Key: Part 10 — Scaling Practice

**Example 1:**

- Calculation: (25 / 50) × 200 = **100 pixels**

**Example 2:**

- Data value: 80, Max: 100, Height: 300
- Calculation: (80 / 100) × 300 = **240 pixels**

**Example 3:**

- Data value: 15, Max: 60, Height: 240
- Calculation: (15 / 60) × 240 = **60 pixels**

**Why is the calculation proportional?**

_Expected Answer:_ We're finding what fraction of the maximum the value represents, then applying that same fraction to the pixel height. This maintains accurate proportions.

### Teaching Notes

**Mental Math Practice:**

Simplify before multiplying:

- (25/50) = 0.5 → 0.5 × 200 = 100
- (80/100) = 0.8 → 0.8 × 300 = 240
- (15/60) = 0.25 → 0.25 × 240 = 60

**Conceptual Understanding:**

Ask: "If a value is half the maximum, how tall should the bar be?"  
_Answer:_ Half the chart height

This builds intuition before formula

---

## Teaching Strategies

### Differentiation

**Support Strategies:**

- Provide starter code with clear TODOs
- Pair students (stronger with developing)
- Create step-by-step checklist with mini-deadlines
- Offer pre-calculated constants (padding, bar width)

**Challenge Strategies:**

- Multi-series bar chart (grouped or stacked)
- Animated bar growth on page load
- Add click interaction (show data value on hover)
- Create different chart type (line, scatter, pie)
- Implement chart export to image

**ELL Support:**

- Provide vocabulary list with visuals
- Use diagrams and annotations liberally
- Pair with language-strong partner
- Allow use of translation tools for documentation

### Formative Assessment Checkpoints

**Checkpoint 1 (After Step 2):**

- Can student draw a rectangle at specific coordinates?
- Can they explain why y increases downward?

**Checkpoint 2 (After Step 4):**

- Can student calculate scaled value by hand?
- Do they understand why we divide by max?

**Checkpoint 3 (After Step 5):**

- Are bars positioned correctly from bottom?
- Can student explain y-position calculation?

**Checkpoint 4 (End):**

- Is chart accurate and accessible?
- Can student explain design choices?

### Common Misconceptions & How to Address

**Misconception 1:** "Canvas is just for games and animations"

**Reality:** Canvas is excellent for data visualization, generative art, image manipulation, and any pixel-based graphics.

**How to Address:** Show diverse Canvas examples (charts, art, simulations, filters).

---

**Misconception 2:** "Accessibility is extra work"

**Reality:** Accessibility is core design. HTML tables are simple to add and benefit everyone.

**How to Address:** Frame as "inclusive design" from the start. Show how tables help all users (copy/paste data, screen readers, mobile).

---

**Misconception 3:** "Any scale is fine as long as it fits"

**Reality:** Scale choices dramatically affect perception and can mislead.

**How to Address:** Show side-by-side: same data, different scales. Discuss impact.

---

**Misconception 4:** "Y-axis in Canvas is like math class (up is positive)"

**Reality:** Canvas Y increases downward (screen coordinate system).

**How to Address:** Draw large diagram on board. Practice with physical objects. Use consistent "from bottom" language.

---

### Extension Projects

**Project 1: Real-World Data**

- Find dataset (weather, sports, environment)
- Clean and prepare data
- Visualize with Canvas chart
- Write analysis paragraph

**Project 2: Chart Chooser**

- Research chart types (bar, line, pie, scatter, etc.)
- Create decision tree for choosing chart type
- Implement 2-3 different chart types in Canvas

**Project 3: Interactive Dashboard**

- Create multi-chart dashboard
- Add filters or date range selectors
- Update all charts on interaction
- Style as professional report

**Project 4: Chart Library**

- Build reusable chart functions
- Create documentation for each chart type
- Share with class as resource

---

### Assessment Rubric (Teacher Use)

| Criterion            | Beginning (1)             | Developing (2)                 | Proficient (3)                   | Advanced (4)                                |
| -------------------- | ------------------------- | ------------------------------ | -------------------------------- | ------------------------------------------- |
| **Canvas Drawing**   | Cannot draw shapes        | Draws shapes with errors       | Draws accurate shapes and text   | Uses advanced techniques (gradients, paths) |
| **Data Handling**    | Cannot work with arrays   | Finds min/max with support     | Correctly prepares data          | Transforms and validates data               |
| **Scaling**          | No scaling or incorrect   | Partial scaling implementation | Correct proportional scaling     | Implements dynamic/adaptive scaling         |
| **Bar Chart**        | Bars missing or incorrect | Some bars positioned wrong     | All bars accurate and positioned | Chart fully responsive and polished         |
| **Labels & Axes**    | Missing or unclear        | Some labels present            | All labels clear and accurate    | Professional labeling with units            |
| **Accessibility**    | No accessibility features | Partial table or labels        | Complete table and aria-labels   | Exceeds standards (ARIA, keyboard nav)      |
| **Code Quality**     | Disorganized, many errors | Functional but messy           | Clean, commented, organized      | Modular, reusable functions                 |
| **Design Reasoning** | Cannot explain choices    | Limited explanation            | Explains most choices clearly    | Articulates design rationale expertly       |

**Grading Scale:**

- **Advanced (28-32 points):** A
- **Proficient (21-27 points):** B
- **Developing (14-20 points):** C
- **Beginning (8-13 points):** Needs significant rework

---

## Session Planning

### 90-Minute Lesson Plan

**0:00–0:10 — Introduction**

- What is Canvas? (show examples)
- Canvas vs SVG comparison
- When to use raster graphics

**0:10–0:25 — Demo: Canvas Basics**

- Live code: Setup canvas and context
- Draw shapes and text
- Explain coordinate system with diagram
- Students follow along (optional)

**0:25–0:45 — Guided Practice: Data & Scaling**

- Work through Step 3 (data preparation)
- Whiteboard: Scaling calculation
- Step 4: Implement scaling function
- Check for understanding

**0:45–1:15 — Main Task: Build Bar Chart**

- Students work on Steps 5-6
- Circulate and support
- Encourage peer help
- Monitor progress checkpoints

**1:15–1:25 — Accessibility & Ethics**

- Demo: Adding data table
- Discuss chart honesty
- Show misleading chart examples
- Quick ethical reflection

**1:25–1:30 — Reflection & Sharing**

- 2-3 students share their charts
- Class identifies strengths
- Preview next module

**Homework/Extension:**

- Complete chart if unfinished
- Try extension activity
- Bring real-world dataset for next class

---

### 120-Minute Extended Lesson Plan

Includes all of above, plus:

**1:30–1:45 — Chart Design Analysis**

- Complete Part 8 in pairs
- Share findings with class
- Discuss chart literacy

**1:45–2:00 — Extension Projects**

- Students choose extension activity
- Begin implementation
- Share plans with partner

---

## Resources for Teachers

### Official Documentation

- [MDN: Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [MDN: Canvas Tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)
- [W3C: Canvas 2D Context](https://www.w3.org/TR/2dcontext/)

### Data Visualization Resources

- [Chart Chooser](https://www.qlik.com/us/data-visualization/chart-types)
- [Data Viz Principles](https://www.interaction-design.org/literature/article/data-visualization-principles)
- [Misleading Graphs](https://www.statisticshowto.com/misleading-graphs/)

### Accessibility

- [WebAIM: Canvas Accessibility](https://webaim.org/techniques/canvas/)
- [W3C: Making Canvas Accessible](https://www.w3.org/WAI/WCAG21/Techniques/html/H67)

### Example Datasets

- Weather data: [OpenWeatherMap](https://openweathermap.org/)
- Environmental: [Our World in Data](https://ourworldindata.org/)
- Sports: [Basketball Reference](https://www.basketball-reference.com/)
- School data: Create sample datasets for recycling, attendance, etc.

---

## Adaptation Notes

### For Remote/Hybrid Learning

- Use CodePen or similar for live coding demos
- Breakout rooms for pair programming
- Screen share for debugging support
- Record demonstration for asynchronous review

### For Mixed-Ability Classes

- **Tiered tasks:** All create basic chart; extension options for advanced
- **Choice boards:** Students choose from multiple datasets or chart types
- **Flexible grouping:** Pair students strategically; rotate pairs

### For Time Constraints

**60-Minute Version:**

- Skip Part 8 (analysis) → assign as homework
- Provide more starter code
- Focus on one checkpoint: accurate bar chart with table

**45-Minute Version:**

- Provide complete HTML/CSS
- Students focus only on JavaScript drawing code
- Skip extensions

### Cross-Curricular Connections

**Science:**

- Visualize experiment results (plant growth, temperature)
- Graph climate data

**Math:**

- Explore functions and scaling
- Practice ratio and proportion
- Coordinate geometry

**Social Studies:**

- Visualize demographic data
- Historical trends (population, trade)

**Art:**

- Explore color theory in data encoding
- Design principles (balance, contrast)

---

## Professional Development Notes

### Key Teaching Points

1. **Emphasize accessibility from the start** — not an afterthought
2. **Use real-world data** — increases engagement and relevance
3. **Connect to ethics** — charts can mislead; discuss responsibility
4. **Build intuition before formula** — scaling makes sense conceptually first
5. **Celebrate debugging** — normalize errors as learning

### Reflection Questions for Teachers

- Did students understand Y-axis directionality? How can I clarify?
- Were students engaged with the dataset? Should I use different data?
- Did accessibility feel integrated or tacked-on?
- What misconceptions emerged that I should address earlier next time?
- How can I better scaffold the scaling concept?

### Peer Collaboration

- Share effective datasets with colleagues
- Co-create rubrics for assessing visualizations
- Discuss ethical examples and case studies
- Build shared resource library of Canvas examples

---

## Additional Challenge Problems

**Challenge 1: Dual-Axis Chart**
Create chart with two Y-axes (different scales) for comparing different units (e.g., temperature in °C and rainfall in mm).

**Challenge 2: Stacked Bar Chart**
Show multiple categories stacked in each bar (e.g., renewable vs non-renewable energy sources).

**Challenge 3: Horizontal Bar Chart**
Adapt vertical bar chart to horizontal orientation.

**Challenge 4: Responsive Chart**
Chart resizes based on window size using `window.addEventListener('resize', ...)`.

**Challenge 5: Export to Image**
Add button to download chart as PNG using `canvas.toDataURL()`.

---

## Troubleshooting Guide

### Issue: Canvas is blank

**Possible Causes:**

- JavaScript error (check console)
- Canvas size is 0×0
- Drawing outside bounds
- Context not obtained

**Solutions:**

- Check browser console for errors
- Verify canvas width/height attributes
- Log x, y, width, height values
- Ensure `getContext("2d")` succeeds

---

### Issue: Bars upside-down

**Cause:** Y-position calculated incorrectly

**Solution:** Use `y = height - padding - barHeight` to position from bottom

---

### Issue: Scaling produces weird values

**Possible Causes:**

- Using wrong max value
- Dividing by chart height instead of max
- Data not numeric

**Solutions:**

- Verify `Math.max(...data)` is correct
- Check formula: `(value / maxValue) * chartHeight`
- Ensure data is numbers, not strings

---

### Issue: Text cut off or misaligned

**Possible Causes:**

- Text drawn outside canvas
- Wrong textAlign setting
- Font size too large

**Solutions:**

- Check x, y coordinates
- Set `ctx.textAlign = "center"` or "left"/"right"
- Reduce font size or increase canvas width

---

### Issue: Bars not showing after update

**Cause:** Forgot to clear canvas before redrawing

**Solution:** Call `ctx.clearRect(0, 0, canvas.width, canvas.height)` before drawing

---

## Summary & Next Steps

**What Students Learned:**

- Canvas API basics (drawing shapes, text, lines)
- Data visualization principles (encoding, scaling, axes)
- Accessibility (data tables, fallback content)
- Chart ethics (honest scaling, clear labels)

**Next Module Preview:**

- **Module 06: Creative Web Projects** — Generative art, animation, interactive visuals
- Students will apply Canvas skills to creative coding

**Ongoing Practice:**

- Encourage students to visualize personal data (sleep, screen time, exercise)
- Share charts on class website or digital portfolio
- Peer review for design and accuracy

---

## Changelog

**Version 1.0** (2025-11-18)

- Initial teacher-annotated workbook for Unit 5.1
- Complete answer keys for all sections
- Teaching notes, differentiation strategies, assessment rubric
- Troubleshooting guide and professional development notes

---

<!-- End of Teacher-Annotated Workbook: Unit 5.1 -->
