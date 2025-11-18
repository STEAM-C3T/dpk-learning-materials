# Student Workbook: Unit 5.1 — Canvas Basics & Data Visualization

**Module:** 05 — Data Visualization  
**Unit:** 5.1 — Canvas Basics  
**Name:** ********\_\_\_\_********  
**Date:** ********\_\_\_\_********

---

## Learning Objectives

By the end of this unit, I will be able to:

- [ ] Explain what HTML5 Canvas is and when to use it
- [ ] Draw shapes and text on Canvas using JavaScript
- [ ] Map numeric data values to visual encodings (bar heights, positions)
- [ ] Implement scaling functions to convert data to pixel coordinates
- [ ] Create axes, labels, and legends for chart clarity
- [ ] Build an accessible data table alongside visual charts
- [ ] Explain chart design choices and identify potential misinterpretations

---

## Part 1: Key Concepts Fill-In

**Canvas Basics**

1. Canvas is a ****\_\_\_\_****-based drawing surface (raster/vector)

2. To draw on Canvas, you need the drawing ****\_\_\_\_**** from `getContext()`

3. Canvas coordinates start at (0, 0) in the ****\_\_\_\_****-****\_\_\_\_**** corner

4. In Canvas, the Y-axis increases ****\_\_\_\_**** (upward/downward)

5. To clear the entire canvas, use: `ctx.____________(0, 0, width, height)`

**Data Visualization**

6. The process of mapping data values to visual properties is called ****\_\_\_\_****

7. For bar charts, the scale should typically start at ****\_\_\_\_****

8. A ****\_\_\_\_**** axis can mislead viewers about data magnitudes

9. Always provide a(n) ****\_\_\_\_**** ****\_\_\_\_**** for screen reader accessibility

10. The formula for scaling is: pixelHeight = (dataValue / ****\_\_\_\_****) × availableHeight

**Drawing Methods**

11. To draw a filled rectangle: `ctx.____________(x, y, width, height)`

12. To draw text: `ctx.____________(text, x, y)`

13. Before drawing text, set the font with: `ctx.____________ = "16px Arial"`

14. To set text alignment: `ctx.____________ = "center"`

15. To change fill color: `ctx.____________ = "blue"`

---

## Part 2: Guided Practice Notes

### Step 1: Canvas Setup

**Create Canvas element:**

```html
<canvas id="my-canvas" width="____" height="____">
  Fallback text for browsers without Canvas support
</canvas>
```

**Get Canvas context in JavaScript:**

```javascript
const canvas = document.getElementById("____________");
const ctx = canvas.____________("2d");
```

**Why is fallback content important?**

---

---

**What I learned:**

---

---

---

### Step 2: Drawing Shapes

**Draw a rectangle:**

```javascript
ctx.fillStyle = "____________"; // Color
ctx.fillRect(x, y, width, height);
```

**Rectangle parameters:**

- `x`: ****\_\_\_\_**** position from left
- `y`: ****\_\_\_\_**** position from top
- `width`: Rectangle ****\_\_\_\_****
- `height`: Rectangle ****\_\_\_\_****

**Draw text:**

```javascript
ctx.font = "____________";
ctx.textAlign = "____________";
ctx.fillText("____________", x, y);
```

**Coordinate System Notes:**

```
(0,0) is at: ____________-____________
X increases: ____________ (direction)
Y increases: ____________ (direction)
```

**What I learned:**

---

---

---

### Step 3: Working with Data

**Sample data array:**

```javascript
const data = [12, 19, 15, 25, 22, 30];
const labels = ["Jan", "Feb", "Mar", "Apr", "May", "Jun"];
```

**Find minimum and maximum:**

```javascript
const min = Math.____________(...data);
const max = Math.____________(...data);
```

**Why do we need to know the data range?**

---

---

**Create accessible data table:**

```html
<table>
  <caption>
    ____________
  </caption>
  <thead>
    <tr>
      <th>Month</th>
      <th>____________</th>
    </tr>
  </thead>
  <tbody id="table-body">
    <!-- Populated by JavaScript -->
  </tbody>
</table>
```

**What I learned:**

---

---

---

### Step 4: Scaling Function

**Scaling formula:**

```
pixelHeight = (____________ / maxValue) × chartHeight
```

**Implement scaling function:**

```javascript
function scaleValue(value, maxValue, chartHeight) {
  return (value / ____________) * chartHeight;
}
```

**Example calculation:**

- Data value: 30
- Max value: 45
- Chart height: 280 pixels
- Result: (30 / 45) × 280 = ****\_\_\_\_**** pixels

**Why start bar charts at zero?**

---

---

**What happens if you don't start at zero?**

---

---

**What I learned:**

---

---

---

### Step 5: Drawing Bar Chart

**Calculate bar position and height:**

```javascript
data.forEach((value, index) => {
  // Scale value to pixels
  const barHeight = scaleValue(value, maxValue, CHART_HEIGHT);

  // Calculate X position
  const x = PADDING + index * ____________;

  // Calculate Y position (from bottom!)
  const y = height - PADDING - ____________;

  // Draw bar
  ctx.fillStyle = "____________";
  ctx.fillRect(x, y, barWidth, barHeight);
});
```

**Why calculate Y as `height - PADDING - barHeight`?**

---

---

**Bar spacing:**

- Total width for each bar: ****\_\_\_\_****
- Actual bar width (80%): ****\_\_\_\_****
- Gap (20%): ****\_\_\_\_****

**What I learned:**

---

---

---

### Step 6: Adding Labels and Axes

**Draw axes:**

```javascript
// Y-axis (vertical)
ctx.beginPath();
ctx.moveTo(PADDING, PADDING);
ctx.lineTo(PADDING, height - ____________);
ctx.stroke();

// X-axis (horizontal)
ctx.beginPath();
ctx.moveTo(____________, height - PADDING);
ctx.lineTo(width - PADDING, height - PADDING);
ctx.stroke();
```

**Add rotated Y-axis label:**

```javascript
ctx.save();
ctx.translate(20, height / 2);
ctx.rotate(-Math.PI / ____________); // Rotate 90 degrees
ctx.fillText("Y-Axis Label", 0, 0);
ctx.____________(); // Restore context
```

**What does `ctx.save()` and `ctx.restore()` do?**

---

---

**What I learned:**

---

---

---

## Part 3: Code Snippet Collection

**Useful Canvas Patterns:**

**1. Clear canvas:**

```javascript
ctx.clearRect(0, 0, canvas.width, canvas.height);
```

**2. Draw filled rectangle:**

```javascript
ctx.fillStyle = "color";
ctx.fillRect(x, y, width, height);
```

**3. Draw text (centered):**

```javascript
ctx.font = "16px Arial";
ctx.textAlign = "center";
ctx.fillText("Text", x, y);
```

**4. Draw line:**

```javascript
ctx.beginPath();
ctx.moveTo(x1, y1);
ctx.lineTo(x2, y2);
ctx.stroke();
```

**5. Scale data value:**

```javascript
const pixels = (value / maxValue) * availableHeight;
```

**6. Position bar from bottom:**

```javascript
const y = canvasHeight - padding - barHeight;
```

**Notes on when to use each pattern:**

---

---

---

---

## Part 4: Independent Task Checklist

**Task: Create CO₂ Savings Bar Chart**

**Data Preparation:**

- [ ] Define data array (12 monthly values)
- [ ] Define month labels array
- [ ] Calculate min and max values
- [ ] Create HTML table with data

**Canvas Setup:**

- [ ] Create Canvas element with appropriate size
- [ ] Get 2D context
- [ ] Define padding and chart dimensions

**Scaling:**

- [ ] Implement scaling function
- [ ] Test scaling with sample values
- [ ] Verify proportions are correct

**Drawing Chart:**

- [ ] Clear canvas
- [ ] Calculate bar width and spacing
- [ ] Loop through data
- [ ] Draw each bar with correct height and position
- [ ] Add value labels on top of bars
- [ ] Add month labels below bars

**Axes and Labels:**

- [ ] Draw Y-axis (vertical)
- [ ] Draw X-axis (horizontal)
- [ ] Add Y-axis scale markers
- [ ] Add Y-axis label (rotated)
- [ ] Add chart title

**Accessibility:**

- [ ] Populate HTML table with all data
- [ ] Add `aria-label` to Canvas
- [ ] Include fallback content
- [ ] Test with table-only view

**Interactivity (Bonus):**

- [ ] Add button to update data
- [ ] Redraw chart when data changes
- [ ] Update table when data changes

**My Progress Notes:**

---

---

---

**Challenges I faced:**

---

---

**How I solved them:**

---

---

---

## Part 5: Self-Assessment Rubric

Rate yourself on each criterion (1 = Beginning, 2 = Developing, 3 = Proficient, 4 = Advanced):

| Criterion                                                           | 1   | 2   | 3   | 4   | Evidence |
| ------------------------------------------------------------------- | --- | --- | --- | --- | -------- |
| **Canvas Drawing:** I can draw shapes and text on Canvas            | ☐   | ☐   | ☐   | ☐   |          |
| **Data Handling:** I can work with data arrays and find ranges      | ☐   | ☐   | ☐   | ☐   |          |
| **Scaling:** I can map data values to pixel coordinates             | ☐   | ☐   | ☐   | ☐   |          |
| **Bar Chart:** I created accurate bar chart with proper positioning | ☐   | ☐   | ☐   | ☐   |          |
| **Labels & Axes:** I added clear labels, axes, and title            | ☐   | ☐   | ☐   | ☐   |          |
| **Accessibility:** I provided accessible table and fallback content | ☐   | ☐   | ☐   | ☐   |          |
| **Code Quality:** My code is organized and well-commented           | ☐   | ☐   | ☐   | ☐   |          |
| **Design Choices:** I can explain scaling and encoding decisions    | ☐   | ☐   | ☐   | ☐   |          |

**Overall Self-Assessment:**

What I did well:

---

---

What I need to improve:

---

---

Questions I still have:

---

---

---

## Part 6: Reflection

**1. Why is it important to provide a data table alongside the chart?**

---

---

---

**2. How does scaling affect the visual perception of differences in data?**

---

---

---

**3. What could mislead viewers if the chart is not designed carefully?**

---

---

---

**4. When would you use Canvas instead of creating a chart with HTML/CSS?**

---

---

---

**5. How would you choose between a bar chart and a line chart?**

---

---

---

---

## Part 7: Vocabulary Glossary

Define these terms in your own words:

**Canvas:** ****************************\_****************************

---

**Context (ctx):** ************************\_\_\_************************

---

**Raster Graphics:** ************************\_************************

---

**Scaling:** ****************************\_****************************

---

**Data Encoding:** ************************\_\_\_************************

---

**Axis:** ****************************\_\_\_\_****************************

---

**Legend:** ****************************\_\_****************************

---

**Accessibility:** ************************\_\_\_************************

---

**Coordinate System:** **********************\_\_\_**********************

---

**Pixel:** ****************************\_\_\_****************************

---

---

## Part 8: Chart Design Analysis

**Analyze this chart design:**

```
Data: [10, 20, 30, 40, 50]
Y-axis starts at 20 (not 0)
Bars have different widths
No units on Y-axis
Red/green colors without labels
```

**Problems I identified:**

1. ***
2. ***
3. ***
4. ***
5. ***

**How to fix each problem:**

1. ***
2. ***
3. ***
4. ***
5. ***

---

## Part 9: Debugging Log

**Common Errors & Solutions:**

| Error                     | What Caused It   | How I Fixed It                  |
| ------------------------- | ---------------- | ------------------------------- |
| Example: Bars upside-down | Y-axis confusion | Used `height - barHeight` for y |
|                           |                  |                                 |
|                           |                  |                                 |
|                           |                  |                                 |
|                           |                  |                                 |

**Console Debugging:**

**Useful console.log statements:**

```javascript
console.log("Data range:", min, max);
console.log("Bar position:", x, y, barWidth, barHeight);
console.log("Scaled value:", scaledValue);
```

**How I used DevTools to debug:**

---

---

---

## Part 10: Scaling Practice

**Practice scaling calculations:**

**Example 1:**

- Data value: 25
- Max value: 50
- Chart height: 200 pixels
- Calculation: (25 / 50) × 200 = ****\_\_\_\_**** pixels

**Example 2:**

- Data value: 80
- Max value: 100
- Chart height: 300 pixels
- Calculation: ****\_\_\_\_**** = ****\_\_\_\_**** pixels

**Example 3:**

- Data value: 15
- Max value: 60
- Chart height: 240 pixels
- Calculation: ****\_\_\_\_**** = ****\_\_\_\_**** pixels

**Why is the calculation proportional?**

---

---

---

## Part 11: Extension Activities

**Activity 1: Different Chart Type**

- Create a line chart instead of bars
- Connect data points with lines
- Add filled area under line

**Activity 2: Multi-Series Chart**

- Display two datasets on same chart
- Use different colors for each series
- Add legend to identify series

**Activity 3: Animated Chart**

- Animate bars growing from 0 to full height
- Use `requestAnimationFrame()`
- Add transition effects

**Activity 4: Different Data**

- Visualize temperature data
- Create chart for school recycling rates
- Display personal fitness tracking

**Which extension activity did I try?** **************\_\_\_\_**************

**What I learned:** ************************\_\_\_************************

---

---

## Part 12: Chart Checklist

**Before submitting your chart, verify:**

**Accuracy:**

- [ ] Data values correctly represented
- [ ] Scaling is proportional
- [ ] Bars positioned accurately

**Clarity:**

- [ ] Title describes what chart shows
- [ ] Axes labeled with units
- [ ] Values labeled (on bars or axis)
- [ ] Legend included if needed

**Accessibility:**

- [ ] HTML table provided
- [ ] Canvas has aria-label
- [ ] Fallback content included
- [ ] Not relying on color alone

**Code Quality:**

- [ ] Code organized and readable
- [ ] Functions have clear names
- [ ] Comments explain logic
- [ ] No console errors

---

## Part 13: Peer Review

**Partner's Name:** ************************\_\_\_************************

**What I learned from reviewing their chart:**

---

---

**One strength of their visualization:**

---

---

**One suggestion for improvement:**

---

---

**Partner's feedback for me:**

---

---

---

## Teacher Feedback Section

**Strengths:**

---

---

**Areas for Growth:**

---

---

**Next Steps:**

---

---

**Grade/Mark:** ****\_\_\_\_****  
**Teacher Signature:** ********\_\_\_\_******** **Date:** ****\_\_\_\_****

---

## Resources & Links

**Official Documentation:**

- [MDN: Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [MDN: Canvas Tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)

**Data Visualization Resources:**

- [Chart Chooser Guide](https://www.qlik.com/us/data-visualization/chart-types)
- [Data Viz Principles](https://www.interaction-design.org/literature/article/data-visualization-principles)

**Related Tutorials:**

- Unit 5.1 Tutorial: Canvas Basics (this unit)
- Next: Module 06 — Creative Web Projects

---

**Notes to Self:**

---

---

---

---

---

<!-- End of Student Workbook: Unit 5.1 -->
