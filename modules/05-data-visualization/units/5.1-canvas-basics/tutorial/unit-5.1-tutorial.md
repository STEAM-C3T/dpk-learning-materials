# Tutorial: Unit 5.1 — Canvas Basics & Data Visualization

**Module:** 05 — Data Visualization  
**Unit:** 5.1 — Canvas Basics  
**Estimated Time:** 75–90 minutes  
**Author:** Digital Proficiency Kit Team  
**Last Updated:** 2025-11-18

---

## Overview

**What You Will Learn:**
In this tutorial, you will learn to use HTML5 Canvas to create visual representations of data, focusing on creating an accessible bar chart from an array of values.

**What You Will Build:**
An interactive bar chart visualizing CO₂ savings data with proper scaling, labels, axes, and an accessible HTML table companion.

**Learning Outcomes:**

- Draw shapes and text on HTML5 Canvas using JavaScript
- Map numeric data to visual encodings (bar heights, positions)
- Implement proper scaling from data values to pixel coordinates
- Add axes, labels, and legends for chart clarity
- Create accessible data tables alongside visual charts
- Explain chart design choices and potential misinterpretations

---

## Prerequisites

Before starting this tutorial, you should:

- [ ] Have completed Module 04 (JavaScript Essentials) or be comfortable with arrays, loops, and functions
- [ ] Understand basic HTML and CSS
- [ ] Know how to use browser DevTools

**Tools Required:**

- Text editor
- Modern web browser with Canvas support (all modern browsers)

---

## Concept Overview

**What is HTML5 Canvas?**

The Canvas element provides a drawing surface for creating graphics with JavaScript. Unlike SVG (vector graphics), Canvas is **raster-based** (pixel by pixel), making it efficient for dynamic visualizations.

**Canvas vs. Other Approaches:**

| Approach      | Best For                           | Accessibility                  |
| ------------- | ---------------------------------- | ------------------------------ |
| **Canvas**    | Dynamic, data-driven graphics      | Requires companion HTML table  |
| **SVG**       | Scalable, interactive graphics     | Individual elements accessible |
| **CSS**       | Simple charts, decorative graphics | Limited data representation    |
| **Libraries** | Complex visualizations             | Varies by library              |

**Why Data Visualization Matters:**

- Makes patterns visible that are hidden in tables
- Enables quick comparisons and trend identification
- Supports decision-making with visual evidence
- Communicates quantitative information effectively

**Key Visualization Principles:**

1. **Accuracy:** Visual encoding must represent data truthfully
2. **Clarity:** Labels, axes, and legends must be clear
3. **Accessibility:** Provide text alternatives for screen readers
4. **Honesty:** Don't mislead with truncated axes or inappropriate scales

---

## Step-by-Step Guide

### Step 1: Set Up Canvas Environment

**Objective:** Create HTML structure with Canvas element and accessible table.

**Instructions:**

Create `data-viz.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Data Visualization with Canvas</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        max-width: 900px;
        margin: 50px auto;
        padding: 20px;
        background-color: #f5f5f5;
      }
      .container {
        background-color: white;
        padding: 30px;
        border-radius: 8px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      }
      h1 {
        color: #2c3e50;
        margin-bottom: 10px;
      }
      .description {
        color: #7f8c8d;
        margin-bottom: 30px;
      }
      canvas {
        border: 1px solid #ddd;
        border-radius: 4px;
        display: block;
        margin: 20px auto;
        background-color: white;
      }
      table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 30px;
      }
      th,
      td {
        padding: 12px;
        text-align: left;
        border-bottom: 1px solid #ddd;
      }
      th {
        background-color: #3498db;
        color: white;
      }
      tr:hover {
        background-color: #f5f5f5;
      }
      .chart-controls {
        margin: 20px 0;
        padding: 15px;
        background-color: #ecf0f1;
        border-radius: 4px;
      }
      button {
        background-color: #3498db;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        margin: 5px;
      }
      button:hover {
        background-color: #2980b9;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>CO₂ Savings Tracker</h1>
      <p class="description">
        Visualizing monthly carbon dioxide savings from green actions
      </p>

      <canvas
        id="chart-canvas"
        width="800"
        height="400"
        aria-label="Bar chart showing CO2 savings by month"
      >
        Your browser doesn't support Canvas. Please see the data table below.
      </canvas>

      <div class="chart-controls">
        <button id="update-data-btn">Update with Random Data</button>
        <button id="reset-btn">Reset to Original</button>
      </div>

      <!-- Accessible data table -->
      <h2>Data Table</h2>
      <table id="data-table">
        <caption>
          Monthly CO₂ Savings in Kilograms
        </caption>
        <thead>
          <tr>
            <th>Month</th>
            <th>CO₂ Saved (kg)</th>
          </tr>
        </thead>
        <tbody id="table-body">
          <!-- Will be populated by JavaScript -->
        </tbody>
      </table>
    </div>

    <script src="viz.js"></script>
  </body>
</html>
```

Create empty `viz.js` file.

**Expected Result:**

- Canvas element displays with border
- Accessible table structure ready
- Fallback text for non-Canvas browsers

**Why This Step:**
Proper HTML structure ensures accessibility and provides semantic context for the visualization.

**Quick Self-Check:**

- [ ] Page loads without errors
- [ ] Canvas element visible
- [ ] Table structure displays

---

### Step 2: Canvas Basics—Draw Simple Shapes

**Objective:** Learn fundamental Canvas drawing commands.

**Instructions:**

Add to `viz.js`:

```javascript
// Get canvas and context
const canvas = document.getElementById("chart-canvas");
const ctx = canvas.getContext("2d");

// Canvas dimensions
const width = canvas.width;
const height = canvas.height;

console.log("Canvas size:", width, "x", height);

// Draw a rectangle
ctx.fillStyle = "#3498db"; // Blue
ctx.fillRect(50, 50, 100, 200); // x, y, width, height

// Draw text
ctx.fillStyle = "#2c3e50"; // Dark gray
ctx.font = "16px Arial";
ctx.fillText("My First Bar", 60, 270);

// Draw a line
ctx.strokeStyle = "#e74c3c"; // Red
ctx.lineWidth = 2;
ctx.beginPath();
ctx.moveTo(0, height - 50); // Start point
ctx.lineTo(width, height - 50); // End point
ctx.stroke();
```

**Expected Result:**

- Blue rectangle appears
- Text label below rectangle
- Red horizontal line at bottom

**Why This Step:**
Understanding basic drawing commands is essential before creating charts.

**Canvas Coordinate System:**

```
(0,0) ──────────────> x
  │
  │
  │
  │
  ↓
  y

Top-left is (0,0)
X increases to the right
Y increases downward
```

**Common Drawing Methods:**

| Method                     | Purpose                |
| -------------------------- | ---------------------- |
| `fillRect(x, y, w, h)`     | Draw filled rectangle  |
| `strokeRect(x, y, w, h)`   | Draw rectangle outline |
| `fillText(text, x, y)`     | Draw text              |
| `beginPath()` / `stroke()` | Draw lines/paths       |
| `arc()`                    | Draw circles/arcs      |

**Common Pitfall:**
⚠️ **Watch Out:** Canvas Y-axis increases downward (opposite of typical math graphs).  
✅ **Tip:** To position bars from bottom, use `height - barHeight`.

**Quick Self-Check:**

- [ ] Rectangle drawn at correct position
- [ ] Text appears
- [ ] Line visible across bottom

---

### Step 3: Work with Data Arrays

**Objective:** Prepare data for visualization.

**Instructions:**

Replace `viz.js` content with:

```javascript
// Get canvas and context
const canvas = document.getElementById("chart-canvas");
const ctx = canvas.getContext("2d");
const width = canvas.width;
const height = canvas.height;

// Data: Monthly CO₂ savings in kg
const originalData = [12, 19, 15, 25, 22, 30, 28, 35, 32, 38, 42, 45];
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

let data = [...originalData]; // Create copy

// Find min and max values
function getDataRange(dataArray) {
  const min = Math.min(...dataArray);
  const max = Math.max(...dataArray);
  return { min, max };
}

const range = getDataRange(data);
console.log("Data range:", range);
console.log("Number of data points:", data.length);

// Populate HTML table
function updateTable() {
  const tableBody = document.getElementById("table-body");
  tableBody.innerHTML = "";

  data.forEach((value, index) => {
    const row = document.createElement("tr");
    row.innerHTML = `
            <td>${months[index]}</td>
            <td>${value} kg</td>
        `;
    tableBody.appendChild(row);
  });
}

updateTable();
```

**Expected Result:**

- Console shows data range
- Table populates with all 12 months and values

**Why This Step:**
Understanding your data (range, count, distribution) is crucial before choosing visual encodings.

**Data Preparation Checklist:**

- [x] Data in array format
- [x] Values are numeric
- [x] Data range calculated
- [x] Labels/categories defined
- [x] Accessible table created

**Quick Self-Check:**

- [ ] Console shows correct min/max
- [ ] Table displays all 12 months
- [ ] Data values appear in table

---

### Step 4: Implement Scaling Function

**Objective:** Map data values to pixel coordinates.

**Instructions:**

Add to `viz.js`:

```javascript
// Chart layout constants
const PADDING = 60; // Space for labels
const CHART_WIDTH = width - PADDING * 2;
const CHART_HEIGHT = height - PADDING * 2;
const BAR_WIDTH = CHART_WIDTH / data.length;

/**
 * Scale a data value to pixel height
 * @param {number} value - Data value
 * @param {number} maxValue - Maximum data value
 * @param {number} chartHeight - Available height in pixels
 * @returns {number} Pixel height
 */
function scaleValue(value, maxValue, chartHeight) {
  // Proportional scaling: value/max = pixelHeight/chartHeight
  return (value / maxValue) * chartHeight;
}

// Test scaling
console.log(
  "Max value (45 kg) scales to:",
  scaleValue(45, range.max, CHART_HEIGHT),
  "pixels"
);
console.log(
  "Min value (" + range.min + " kg) scales to:",
  scaleValue(range.min, range.max, CHART_HEIGHT),
  "pixels"
);
```

**Expected Result:**

- Console shows scaled pixel values
- Maximum value scales to full chart height
- Minimum value scales proportionally

**Why This Step:**
Scaling is the heart of data visualization—accurately mapping data space to visual space.

**Scaling Formula:**

```
pixelHeight = (dataValue / maxValue) × availableHeight

Example:
- Data value: 30 kg
- Max value: 45 kg
- Available height: 280 pixels
- Result: (30 / 45) × 280 = 186.67 pixels
```

**Important:** Always start scale at 0 for bar charts (unless you have a specific reason and clearly indicate otherwise).

**Common Pitfall:**
⚠️ **Watch Out:** Truncated axes can mislead viewers about magnitudes.  
✅ **Tip:** For bar charts, always include 0 baseline.

**Quick Self-Check:**

- [ ] Scaling function returns correct pixel values
- [ ] Maximum value uses full available height
- [ ] Proportions are correct

---

### Step 5: Draw Complete Bar Chart

**Objective:** Create full bar chart with proper spacing and positioning.

**Instructions:**

Add to `viz.js`:

```javascript
/**
 * Draw the bar chart
 */
function drawChart() {
  // Clear canvas
  ctx.clearRect(0, 0, width, height);

  // Set up colors
  const barColor = "#3498db";
  const textColor = "#2c3e50";

  // Get current max for scaling
  const currentMax = Math.max(...data);

  // Draw each bar
  data.forEach((value, index) => {
    // Calculate bar dimensions
    const barHeight = scaleValue(value, currentMax, CHART_HEIGHT);
    const x = PADDING + index * BAR_WIDTH;
    const y = height - PADDING - barHeight; // Position from bottom
    const barWidth = BAR_WIDTH * 0.8; // 80% width (20% gap)

    // Draw bar
    ctx.fillStyle = barColor;
    ctx.fillRect(x, y, barWidth, barHeight);

    // Draw value on top of bar
    ctx.fillStyle = textColor;
    ctx.font = "12px Arial";
    ctx.textAlign = "center";
    ctx.fillText(value + "kg", x + barWidth / 2, y - 5);

    // Draw month label
    ctx.fillText(months[index], x + barWidth / 2, height - PADDING + 20);
  });

  // Draw axes
  drawAxes();

  // Draw title
  ctx.fillStyle = textColor;
  ctx.font = "bold 16px Arial";
  ctx.textAlign = "center";
  ctx.fillText("Monthly CO₂ Savings", width / 2, 30);
}

/**
 * Draw chart axes and labels
 */
function drawAxes() {
  ctx.strokeStyle = "#2c3e50";
  ctx.lineWidth = 2;

  // Y-axis (vertical)
  ctx.beginPath();
  ctx.moveTo(PADDING, PADDING);
  ctx.lineTo(PADDING, height - PADDING);
  ctx.stroke();

  // X-axis (horizontal)
  ctx.beginPath();
  ctx.moveTo(PADDING, height - PADDING);
  ctx.lineTo(width - PADDING, height - PADDING);
  ctx.stroke();

  // Y-axis label
  ctx.save(); // Save current context
  ctx.translate(20, height / 2); // Move to label position
  ctx.rotate(-Math.PI / 2); // Rotate 90 degrees
  ctx.textAlign = "center";
  ctx.fillStyle = "#2c3e50";
  ctx.font = "14px Arial";
  ctx.fillText("CO₂ Saved (kg)", 0, 0);
  ctx.restore(); // Restore context

  // Add scale markers on Y-axis
  const currentMax = Math.max(...data);
  const steps = 5;
  const stepValue = currentMax / steps;

  ctx.font = "10px Arial";
  ctx.textAlign = "right";
  for (let i = 0; i <= steps; i++) {
    const value = Math.round(i * stepValue);
    const y = height - PADDING - (i * CHART_HEIGHT) / steps;

    // Draw tick mark
    ctx.beginPath();
    ctx.moveTo(PADDING - 5, y);
    ctx.lineTo(PADDING, y);
    ctx.stroke();

    // Draw value label
    ctx.fillText(value, PADDING - 10, y + 4);
  }
}

// Initial draw
drawChart();
```

**Expected Result:**

- Complete bar chart with 12 bars
- Values labeled on top of each bar
- Month labels on X-axis
- Y-axis with scale markers
- Title at top
- Rotated Y-axis label

**Why This Step:**
Complete charts include all necessary context: titles, labels, axes, and legends.

**Chart Anatomy:**

```
        Title
          ↓
    ┌─────────────────┐
Y   │ ███             │
│   │ ███ ███         │
L   │ ███ ███ ███     │
a   │ ███ ███ ███ ███ │
b   └─────────────────┘
e←      X Labels
```

**Quick Self-Check:**

- [ ] All 12 bars display
- [ ] Bars positioned from bottom
- [ ] Labels readable
- [ ] Axes visible
- [ ] Scale markers accurate

---

### Step 6: Add Interactivity

**Objective:** Update chart with new data dynamically.

**Instructions:**

Add to `viz.js`:

```javascript
// Button: Update with random data
document
  .getElementById("update-data-btn")
  .addEventListener("click", function () {
    // Generate random data (10-50 kg range)
    data = data.map(() => Math.floor(Math.random() * 40) + 10);

    // Redraw chart and update table
    drawChart();
    updateTable();
  });

// Button: Reset to original data
document.getElementById("reset-btn").addEventListener("click", function () {
  data = [...originalData];
  drawChart();
  updateTable();
});
```

**Expected Result:**

- "Update" button generates new random values and redraws chart
- "Reset" button restores original data
- Table updates alongside chart

**Why This Step:**
Interactivity demonstrates that visualizations can respond to changing data dynamically.

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting to update both chart AND table.  
✅ **Tip:** Always update all representations of the data.

**Quick Self-Check:**

- [ ] Update button changes data
- [ ] Chart redraws correctly
- [ ] Table updates
- [ ] Reset button works

---

### Step 7: Enhance Accessibility & Add Color

**Objective:** Improve accessibility and visual design.

**Instructions:**

Add to beginning of `drawChart()` function:

```javascript
function drawChart() {
    // Clear canvas
    ctx.clearRect(0, 0, width, height);

    // Get current max for scaling
    const currentMax = Math.max(...data);

    // Color coding: green for above average, blue for below
    const average = data.reduce((sum, val) => sum + val, 0) / data.length;

    // Draw each bar
    data.forEach((value, index) => {
        // Calculate bar dimensions
        const barHeight = scaleValue(value, currentMax, CHART_HEIGHT);
        const x = PADDING + (index * BAR_WIDTH);
        const y = height - PADDING - barHeight;
        const barWidth = BAR_WIDTH * 0.8;

        // Color based on comparison to average
        const barColor = value >= average ? "#27ae60" : "#3498db";  // Green or blue

        // Draw bar
        ctx.fillStyle = barColor;
        ctx.fillRect(x, y, barWidth, barHeight);

        // Add highlight on hover effect (simplified)
        // In real app, would track mouse position

        // ... rest of drawing code
```

Add legend after drawAxes() call:

```javascript
// Draw legend
const legendX = width - PADDING - 150;
const legendY = PADDING + 20;

// Above average
ctx.fillStyle = "#27ae60";
ctx.fillRect(legendX, legendY, 20, 20);
ctx.fillStyle = "#2c3e50";
ctx.font = "12px Arial";
ctx.textAlign = "left";
ctx.fillText(
  "≥ Average (" + Math.round(average) + " kg)",
  legendX + 30,
  legendY + 15
);

// Below average
ctx.fillStyle = "#3498db";
ctx.fillRect(legendX, legendY + 30, 20, 20);
ctx.fillStyle = "#2c3e50";
ctx.fillText("< Average", legendX + 30, legendY + 45);
```

**Expected Result:**

- Bars colored green (above average) or blue (below average)
- Legend explains color coding
- Table remains accessible alternative

**Why This Step:**
Color enhances understanding but must be supplemented with other cues (labels, legends) for accessibility.

**Accessibility Best Practices:**

- ✅ **Do:** Provide HTML table alongside chart
- ✅ **Do:** Use color + labels/patterns
- ✅ **Do:** Add `aria-label` to Canvas
- ✅ **Do:** Include text descriptions
- ❌ **Don't:** Rely on color alone
- ❌ **Don't:** Use low-contrast colors

**Quick Self-Check:**

- [ ] Colors change based on data
- [ ] Legend explains color coding
- [ ] Chart still comprehensible in grayscale

---

## Debugging Section

**Scenario 1: Bars don't appear**

- **Possible Causes:**
  - Canvas context not obtained
  - Incorrect coordinate calculations
  - Bars drawn outside visible area
- **Solution:**
  - Console.log coordinates: `console.log(x, y, barWidth, barHeight)`
  - Check that y-coordinate is within canvas height
  - Verify data array is not empty

**Scenario 2: Bars upside-down or in wrong position**

- **Possible Cause:** Y-axis confusion (increases downward)
- **Solution:** Use `height - PADDING - barHeight` for y-coordinate

**Scenario 3: Text doesn't appear or is cut off**

- **Possible Causes:**
  - Text drawn outside canvas bounds
  - Font size too large
  - `textAlign` not set appropriately
- **Solution:**
  - Set `ctx.textAlign` before drawing
  - Check x, y coordinates are within canvas
  - Reduce font size if needed

**Scenario 4: Chart doesn't update**

- **Possible Cause:** Not calling `drawChart()` after data change
- **Solution:** Always call `drawChart()` and `updateTable()` after modifying data

**Scenario 5: Scaling looks wrong**

- **Possible Cause:** Using wrong max value or not accounting for padding
- **Solution:**
  - Recalculate max after data changes
  - Verify `scaleValue()` function logic
  - Check CHART_HEIGHT vs. canvas height

**General Debugging Tips:**

- **Console.log liberally:** Log coordinates, dimensions, data values
- **DevTools:** Use browser DevTools to inspect Canvas
- **Incremental testing:** Test each drawing step independently
- **Visual guides:** Draw guidelines to verify positioning

---

## Consolidated Key Concepts

**1. Canvas Setup**

```javascript
const canvas = document.getElementById("canvas-id");
const ctx = canvas.getContext("2d");
```

**2. Drawing Rectangles**

```javascript
ctx.fillStyle = "color";
ctx.fillRect(x, y, width, height);
```

**3. Drawing Text**

```javascript
ctx.font = "16px Arial";
ctx.textAlign = "center";
ctx.fillText("Text", x, y);
```

**4. Scaling Data**

```javascript
const pixelValue = (dataValue / maxData) * availableHeight;
```

**5. Clearing Canvas**

```javascript
ctx.clearRect(0, 0, canvas.width, canvas.height);
```

**6. Canvas Coordinates**

- Origin (0,0) is top-left
- X increases rightward
- Y increases downward
- Position bars from bottom: `y = height - barHeight`

---

## Practice Variations

**Variation 1: Different Chart Type**

- Create a line chart instead of bar chart
- Use `lineTo()` to connect data points
- Add filled area under line

**Variation 2: Multi-Series Chart**

- Display two datasets (e.g., 2023 vs 2024)
- Use grouped or stacked bars
- Add legend for each series

**Variation 3: Enhanced Interactivity**

- Add hover tooltips showing exact values
- Implement click to highlight specific month
- Add zoom/pan capabilities

**Variation 4: Different Data**

- Visualize different sustainability metrics (water usage, recycling rates)
- Import data from CSV or JSON file
- Add data filtering options

---

## Reflection Prompts

1. **Why is it important to provide a data table alongside the chart?**

   - [Space for student response]

2. **How does scaling affect the visual perception of differences in data?**

   - [Space for student response]

3. **What could mislead viewers if the chart is not designed carefully?**

   - [Space for student response]

4. **When would a line chart be better than a bar chart?**
   - [Space for student response]

---

## Further Reading

**Official Documentation:**

- [MDN: Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [MDN: Canvas Tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)

**Data Visualization Resources:**

- [Data Visualization Principles](https://www.interaction-design.org/literature/article/data-visualization-principles)
- [Chart Chooser](https://www.qlik.com/us/data-visualization/chart-types)

**Related Tutorials:**

- Previous: Module 04 — JavaScript Essentials
- Next: Unit 6.1 — Generative Art

**Visualization Libraries (for future exploration):**

- Chart.js (simple charts)
- D3.js (advanced, data-driven)
- Plotly (scientific/statistical)

---

## Accessibility Considerations

**This Tutorial Emphasized:**

- ✅ HTML table companion for screen readers
- ✅ Canvas `aria-label` attribute
- ✅ Fallback content for non-Canvas browsers
- ✅ Color + labels (not color alone)
- ✅ Clear axis labels and legends

**Additional Accessibility Tips:**

- Provide text description of key insights
- Ensure sufficient color contrast (WCAG AA: 4.5:1)
- Consider pattern fills in addition to colors
- Test with screen readers
- Allow keyboard navigation for interactive charts

---

## Metadata

**Module:** 05 — Data Visualization  
**Unit:** 5.1 — Canvas Basics  
**Author:** Digital Proficiency Kit Team  
**Contributors:** N/A  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Unit 5.1 Tutorial -->
