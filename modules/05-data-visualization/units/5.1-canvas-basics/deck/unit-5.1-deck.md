---
marp: true
theme: default
paginate: true
---

<!-- _class: lead -->

# Unit 5.1

## Canvas Basics & Data Visualization

**Module 05: Data Visualization**

---

## Learning Outcomes

By the end of this unit, you will be able to:

- Draw shapes and text on HTML5 Canvas using JavaScript
- Map numeric data to visual encodings (bar heights, positions)
- Implement scaling functions for proportional representation
- Create axes, labels, and legends for chart clarity
- Build accessible data tables alongside visual charts

---

## What is HTML5 Canvas?

**Canvas** is a raster-based drawing surface for creating graphics with JavaScript.

**Key Features:**

- Pixel-based (bitmap) graphics
- Controlled entirely with JavaScript
- Good for dynamic, data-driven visualizations
- Supports animations and interactivity

**When to Use:**

- Charts and graphs
- Animations
- Image manipulation
- Games

---

## Canvas vs SVG

| Canvas                    | SVG                             |
| ------------------------- | ------------------------------- |
| **Raster** (pixels)       | **Vector** (shapes)             |
| Good for many objects     | Good for few objects            |
| Loses quality when scaled | Scales without quality loss     |
| No DOM elements           | Each shape is DOM element       |
| Better for dynamic data   | Better for interactive graphics |

**Choose Canvas for:** Data visualization with many data points, animations, pixel manipulation

---

## Canvas Coordinate System

```
(0,0) ────────────► X increases
  │
  │
  │
  ▼
Y increases (downward!)
```

**Key Points:**

- Origin (0,0) at **top-left** corner
- X-axis increases to the **right**
- Y-axis increases **downward** (unlike math graphs!)
- All positions and sizes in **pixels**

---

## Setting Up Canvas

**HTML:**

```html
<canvas id="my-chart" width="800" height="400">
  Fallback text for browsers without Canvas support
</canvas>
```

**JavaScript:**

```javascript
const canvas = document.getElementById("my-chart");
const ctx = canvas.getContext("2d");
```

**Important:**

- Set `width` and `height` as **attributes**, not CSS
- Always provide **fallback content** for accessibility
- The **context** (`ctx`) is where all drawing methods live

---

## Drawing Shapes

**Rectangle:**

```javascript
ctx.fillStyle = "green";
ctx.fillRect(x, y, width, height);
```

**Text:**

```javascript
ctx.font = "16px Arial";
ctx.textAlign = "center";
ctx.fillText("Hello Canvas", x, y);
```

**Line:**

```javascript
ctx.beginPath();
ctx.moveTo(x1, y1);
ctx.lineTo(x2, y2);
ctx.stroke();
```

---

## Live Demo: Drawing Basics

**Let's draw:**

1. A rectangle at position (50, 50) with size 100×80
2. Text saying "My Chart" centered at (400, 30)
3. A line from (50, 100) to (750, 100)

```javascript
// Rectangle
ctx.fillStyle = "steelblue";
ctx.fillRect(50, 50, 100, 80);

// Text
ctx.font = "24px Arial";
ctx.textAlign = "center";
ctx.fillText("My Chart", 400, 30);

// Line
ctx.beginPath();
ctx.moveTo(50, 100);
ctx.lineTo(750, 100);
ctx.stroke();
```

---

## Data Visualization Basics

**Data Encoding:** Mapping data values to visual properties

**Examples:**

- **Height** of bar = magnitude of value
- **Position** on X-axis = category or time
- **Color** = category or above/below threshold

**Core Principle:** Visual representation should accurately reflect the data

---

## Working with Data

**Sample Dataset:**

```javascript
const data = [12, 19, 15, 25, 22, 30];
const labels = ["Jan", "Feb", "Mar", "Apr", "May", "Jun"];
```

**Find Data Range:**

```javascript
const min = Math.min(...data); // 12
const max = Math.max(...data); // 30
```

**Why?** We need the range to scale values proportionally to fit in our chart area.

---

## Scaling: The Key Concept

**Problem:** Data values (e.g., 0–100) don't match pixel heights (e.g., 0–300)

**Solution:** **Scaling function** maps data to pixels

**Formula:**

```
pixelHeight = (dataValue / maxValue) × chartHeight
```

**Example:**

- Data value: 30
- Max value: 60
- Chart height: 300 pixels
- Result: (30 / 60) × 300 = **150 pixels**

---

## Scaling Code

```javascript
function scaleValue(value, maxValue, chartHeight) {
  return (value / maxValue) * chartHeight;
}
```

**Usage:**

```javascript
const maxValue = Math.max(...data);
const chartHeight = 280;

data.forEach((value) => {
  const barHeight = scaleValue(value, maxValue, chartHeight);
  // Draw bar with this height
});
```

**Key Insight:** This maintains **proportional relationships** between data values

---

## Why Start at Zero?

**Bar charts should start at zero** to show accurate proportions.

**Example:**

- Data: [20, 30]
- If axis starts at 0: Second bar is 1.5× first
- If axis starts at 15: Second bar looks 3× first!

**Truncated axes** can mislead viewers about magnitudes

**Exception:** Sometimes appropriate for small variations in large numbers, but **always label clearly**

---

## Drawing a Bar Chart

**Steps:**

1. Calculate bar width and spacing
2. For each data value:
   - Scale value to pixel height
   - Calculate X position (based on index)
   - Calculate Y position (**from bottom!**)
   - Draw rectangle

**Y-Position Trick:**

```javascript
const y = canvasHeight - padding - barHeight;
```

Why? Canvas Y increases downward, but bars grow upward from bottom.

---

## Bar Chart Code

```javascript
const barWidth = 50;
const barSpacing = 60;
const padding = 50;

data.forEach((value, index) => {
  // Scale value to pixels
  const barHeight = scaleValue(value, maxValue, chartHeight);

  // Calculate position
  const x = padding + index * barSpacing;
  const y = height - padding - barHeight;

  // Draw bar
  ctx.fillStyle = "green";
  ctx.fillRect(x, y, barWidth, barHeight);
});
```

---

## Adding Labels

**Month Labels (Below Bars):**

```javascript
ctx.font = "14px Arial";
ctx.textAlign = "center";
ctx.fillStyle = "black";

labels.forEach((label, index) => {
  const x = padding + index * barSpacing + barWidth / 2;
  const y = height - padding + 20;
  ctx.fillText(label, x, y);
});
```

**Value Labels (On Top of Bars):**

```javascript
data.forEach((value, index) => {
  const x = padding + index * barSpacing + barWidth / 2;
  const y = height - padding - barHeight - 5;
  ctx.fillText(value.toString(), x, y);
});
```

---

## Drawing Axes

**Y-Axis (Vertical):**

```javascript
ctx.beginPath();
ctx.moveTo(padding, padding);
ctx.lineTo(padding, height - padding);
ctx.stroke();
```

**X-Axis (Horizontal):**

```javascript
ctx.beginPath();
ctx.moveTo(padding, height - padding);
ctx.lineTo(width - padding, height - padding);
ctx.stroke();
```

**Axes provide reference** and frame the chart

---

## Rotated Text for Y-Axis Label

```javascript
ctx.save(); // Save current state

// Move to rotation point and rotate
ctx.translate(20, height / 2);
ctx.rotate(-Math.PI / 2); // 90° counter-clockwise

// Draw text
ctx.fillText("CO₂ Saved (kg)", 0, 0);

ctx.restore(); // Restore state
```

**Why save/restore?** Prevents rotation from affecting subsequent drawing

---

## Accessibility: Data Tables

**Always provide an HTML table** with the same data:

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

**Why?**

- Screen readers can't interpret Canvas pixels
- Exact values clearer in table format
- Works without JavaScript or Canvas support

---

## Accessibility Best Practices

**For Canvas:**

- Add `aria-label` to Canvas element
- Provide fallback content inside `<canvas>` tag
- Use companion HTML table

**For Chart Design:**

- Don't rely on color alone (use labels + patterns)
- Ensure sufficient contrast
- Provide clear title and axis labels
- Include units (kg, %, dollars, etc.)

---

## Color Coding Example

```javascript
const average = data.reduce((a, b) => a + b) / data.length;

data.forEach((value) => {
  // Green if above average, blue otherwise
  ctx.fillStyle = value >= average ? "green" : "steelblue";
  ctx.fillRect(x, y, barWidth, barHeight);
});
```

**Important:** Also add a **legend** explaining colors:

```
■ Green: Above Average
■ Blue: Below Average
```

---

## Complete Example: CO₂ Savings Tracker

**Data:**

```javascript
const monthlyData = [12, 19, 15, 25, 22, 30, 28, 24, 20, 18, 26, 31];
const months = [
  "Jan",
  "Feb",
  "Mar",
  "Apr",
  "May",
  "Jun",
  "Jul",
  "Aug",
  "Sep",
  "Oct",
  "Nov",
  "Dec",
];
```

**Chart Features:**

- Bars scaled proportionally
- Month labels below each bar
- Value labels on top of bars
- Y-axis with scale markers
- Color-coded by above/below average
- Legend explaining colors
- Accessible HTML table

---

## Common Mistakes to Avoid

**1. Y-Position Confusion**

- ❌ `y = barHeight` → Bars at top, upside-down
- ✅ `y = height - padding - barHeight` → Bars from bottom

**2. Forgetting to Scale**

- ❌ Using data values directly as pixel heights
- ✅ Using scaling function

**3. Truncated Axis**

- ❌ Starting bar chart at non-zero value (misleading)
- ✅ Starting at zero

**4. Missing Accessibility**

- ❌ Canvas only
- ✅ Canvas + data table

---

## Debugging Tips

**Canvas is blank?**

- Check browser console for errors
- Verify Canvas size (width/height attributes)
- Ensure context obtained: `ctx = canvas.getContext("2d")`

**Bars not showing?**

- Log x, y, width, height values: `console.log(x, y, barWidth, barHeight)`
- Check if drawing outside canvas bounds

**Incorrect heights?**

- Verify scaling: log `(value / maxValue) * chartHeight`
- Check that max value is correct

---

## Interactive Charts

**Add Update Button:**

```html
<button onclick="updateData()">Update Chart</button>
```

```javascript
function updateData() {
  // Generate new random data
  data = data.map(() => Math.floor(Math.random() * 50) + 10);

  // Clear canvas
  ctx.clearRect(0, 0, canvas.width, canvas.height);

  // Redraw chart
  drawChart();

  // Update table
  updateTable();
}
```

**Key:** Always clear canvas before redrawing

---

## Chart Design Principles

**Accuracy:**

- Data accurately encoded (proportional scaling)
- Axes start at zero (for bar charts)
- No misleading visual tricks

**Clarity:**

- Clear title and labels
- Appropriate units
- Legend if needed
- Not cluttered

**Accessibility:**

- Companion data table
- Not relying on color alone
- Sufficient contrast
- Descriptive labels

---

## When to Use Different Chart Types

**Bar Chart:**

- Categorical data (months, products, categories)
- Comparing discrete values
- Emphasis on individual values

**Line Chart:**

- Continuous data (temperature over time)
- Showing trends and change rate
- Connecting data points

**Scatter Plot:**

- Showing relationship between two variables
- Finding correlations

**Pie Chart:**

- Showing parts of a whole
- Best for few categories (2–5)

---

## Practice Task

**Create a Bar Chart:**

1. Use this data: `[40, 55, 30, 70, 65, 50]`
2. Labels: `["Q1", "Q2", "Q3", "Q4", "Q5", "Q6"]`
3. Include:
   - Scaled bars (start at zero)
   - X and Y axes
   - Labels below bars
   - Y-axis label: "Sales (units)"
   - Chart title: "Quarterly Sales"
   - Accessible data table

---

## Extension Challenges

**Challenge 1:** Add color coding

- Green for values > 50
- Red for values < 50

**Challenge 2:** Add value labels on top of bars

**Challenge 3:** Add Y-axis scale markers (tick marks and numbers)

**Challenge 4:** Make chart responsive (resize with window)

**Challenge 5:** Create a line chart instead of bars

---

## Reflection Questions

1. Why is it important to provide a data table alongside the chart?
2. How does scaling affect the visual perception of differences in data?
3. What could mislead viewers if the chart is not designed carefully?
4. When would you use Canvas instead of creating a chart with HTML/CSS?

**Discuss with a partner, then share with the class.**

---

## Key Takeaways

✅ Canvas is a powerful raster-based drawing surface controlled with JavaScript

✅ Scaling maps data values to pixel dimensions proportionally

✅ Bar charts should start at zero to show accurate proportions

✅ Always provide accessible data tables alongside visual charts

✅ Chart design affects perception—design ethically and clearly

---

## Next Steps

**In this unit, you learned:**

- Canvas API basics (drawing shapes, text, lines)
- Data visualization principles (encoding, scaling, axes)
- Creating accessible bar charts

**Next:**

- **Module 06: Creative Web Projects** — Generative art, animation, interactive visuals
- Apply Canvas skills to creative coding

**Practice:**

- Create charts with your own data (sleep, exercise, screen time)
- Experiment with different chart types
- Share and critique charts with peers

---

<!-- _class: lead -->

# Questions?

**Let's draw some charts!**

---

## Resources

**Documentation:**

- [MDN: Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [MDN: Canvas Tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)

**Data Visualization:**

- [Chart Chooser Guide](https://www.qlik.com/us/data-visualization/chart-types)
- [Data Viz Principles](https://www.interaction-design.org/literature/article/data-visualization-principles)

**Tutorial:** Unit 5.1 Tutorial (detailed step-by-step guide)

---

<!-- End of Unit 5.1 Deck -->
