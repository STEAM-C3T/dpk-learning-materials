# Student Workbook: Unit 6.1 — Generative Art

**Module:** 06 — Creative Web Projects  
**Unit:** 6.1 — Generative Art  
**Name:** ********\_\_\_\_********  
**Date:** ********\_\_\_\_********

---

## Learning Objectives

By the end of this unit, I will be able to:

- [ ] Use `requestAnimationFrame()` for smooth animation loops
- [ ] Generate random values within ranges for visual variety
- [ ] Parameterize visual properties (size, color, position, rotation)
- [ ] Create UI controls (sliders, buttons) linked to visual parameters
- [ ] Apply Canvas transformations (translate, rotate, scale)
- [ ] Combine repetition, randomness, and rules to create patterns
- [ ] Explain generative art concepts and my creative decisions

---

## Part 1: Key Concepts Fill-In

**Generative Art Basics**

1. Generative art is created using ****\_\_\_\_**** systems (code/rules)

2. Each run of generative art can produce ****\_\_\_\_**** results

3. ****\_\_\_\_**** are adjustable variables that control the outcome

4. Complex patterns that emerge from simple rules are called ****\_\_\_\_**** patterns

5. Generative art combines ****\_\_\_\_****, randomness, and repetition

**Animation**

6. The browser-optimized animation method is called ****\_\_\_\_****

7. Typical frame rate for smooth animation is ****\_\_\_\_**** FPS

8. To create a trail effect, use a ****\_\_\_\_****-transparent fill instead of clearing

9. The ****\_\_\_\_**** variable tracks time progression in animations

10. To pause animation, set ****\_\_\_\_**** to true/false

**Canvas Transformations**

11. `ctx.____________()` saves the current transformation state

12. `ctx.____________(x, y)` moves the origin to a new position

13. `ctx.____________(angle)` rotates the coordinate system

14. Angle values for rotation are in ****\_\_\_\_**** (radians/degrees)

15. `ctx.____________()` restores the saved transformation state

**Random Values**

16. `Math.random()` returns a value between ****\_\_\_\_**** and ****\_\_\_\_****

17. To get a random integer, use Math.****\_\_\_\_****

18. HSL stands for ****\_\_\_\_****, Saturation, Lightness

19. In HSL, ****\_\_\_\_**** ranges from 0–360 (color wheel)

20. Controlled color palettes use ****\_\_\_\_**** (RGB/HSL)

---

## Part 2: Animation Loop Practice

**Basic Animation Structure:**

```javascript
let frame = 0;
let isPaused = false;

function animate() {
  if (!isPaused) {
    // Clear canvas
    ctx.____________("white");
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // Draw pattern
    ____________();

    // Increment frame
    frame += ____________;
  }

  // Request next frame
  ____________(animate);
}

// Start animation
____________();
```

**Fill in the blanks above, then answer:**

**What does `requestAnimationFrame()` do?**

---

---

**Why increment the frame counter?**

---

---

**What happens if you don't check `isPaused`?**

---

---

---

## Part 3: Random Number Functions

**Complete these functions:**

```javascript
// Random integer between min and max (inclusive)
function randomInt(min, max) {
  return Math.____________(Math.random() * (max - min + 1)) + min;
}

// Random float between min and max
function randomFloat(min, max) {
  return Math.random() * (____________ - ____________) + min;
}

// Random HSL color
function randomHSL(hueMin = 0, hueMax = 360) {
  const hue = randomInt(____________, ____________);
  return `hsl(${hue}, 70%, 50%)`;
}
```

**Test your functions:**

- `randomInt(1, 10)` might return: ****\_\_\_\_****
- `randomFloat(0, 1)` might return: ****\_\_\_\_****
- `randomHSL(200, 240)` produces ****\_\_\_\_**** tones (color)

**Why use HSL instead of hex colors?**

---

---

---

## Part 4: Circular Arrangement Math

**Positioning circles in a ring:**

```javascript
const centerX = canvas.width / 2;
const centerY = canvas.height / 2;
const orbitRadius = 200;
const circleCount = 12;

for (let i = 0; i < circleCount; i++) {
  const angle = (i / circleCount) * Math.PI * ____________;
  const x = centerX + Math.____________(angle) * orbitRadius;
  const y = centerY + Math.____________(angle) * orbitRadius;

  // Draw circle at (x, y)
}
```

**Fill in the blanks above.**

**Sketch the coordinate system:**

```
Draw a circle showing how trigonometry positions points:

       y
       │
   ────┼──── x
       │

For angle θ and radius r:
x = centerX + ______(θ) × r
y = centerY + ______(θ) × r
```

**What happens if you add `frame * 0.01` to the angle?**

---

---

---

## Part 5: Canvas Transformations

**Drawing a rotated rectangle:**

```javascript
function drawRotatedRect(x, y, width, height, angle, color) {
  ctx.____________(); // Save state

  ctx.____________(x, y); // Move origin
  ctx.____________(angle); // Rotate

  ctx.fillStyle = color;
  ctx.fillRect(-width / 2, -height / 2, width, height);

  ctx.____________(); // Restore state
}
```

**Fill in the blanks above.**

**Why draw at `(-width/2, -height/2)` instead of `(0, 0)`?**

---

---

**What happens if you forget `ctx.restore()`?**

---

---

**Draw a diagram showing transformation sequence:**

```
1. Original canvas:     2. After translate:    3. After rotate:
   (0,0)                   (0,0)                  (0,0) ↻
   └─────                  └─────                 └─────
                           origin→(x,y)           rotated
```

---

## Part 6: UI Controls — Slider Code

**Linking a slider to a parameter:**

```html
<label for="circle-count"
  >Circle Count:
  <span id="count-value">50</span>
</label>
<input type="range" id="circle-count" min="10" max="200" value="50" />
```

```javascript
const slider = document.getElementById("____________");
const display = document.getElementById("____________");

slider.addEventListener("____________", (e) => {
  circleCount = ____________(e.target.value);
  display.textContent = circleCount;
});
```

**Fill in the blanks above.**

**What does `parseInt()` do?**

---

**Why use the `input` event instead of `change`?**

---

---

---

## Part 7: Particle System Design

**Particle class structure:**

```javascript
class Particle {
  constructor() {
    this.x = randomFloat(0, canvas.width);
    this.y = randomFloat(0, canvas.height);
    this.vx = randomFloat(____________, ____________); // velocity X
    this.vy = randomFloat(____________, ____________); // velocity Y
    this.radius = randomFloat(2, 8);
    this.hue = randomInt(0, 360);
  }

  update() {
    // Move particle
    this.x += ____________;
    this.y += ____________;

    // Wrap around edges
    if (this.x < 0) this.x = canvas.width;
    if (this.x > canvas.width) this.x = 0;
    // Add wrap for y:
    ____________________________________________;
    ____________________________________________;
  }

  draw() {
    ctx.fillStyle = `hsl(${this.hue}, 70%, 50%)`;
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
    ctx.fill();
  }
}
```

**Fill in the blanks above.**

**What does "wrap around edges" mean?**

---

---

**How would you make particles bounce instead of wrap?**

---

---

---

## Part 8: Code Snippet Collection

**Useful Generative Art Patterns:**

**1. Clear canvas (full):**

```javascript
ctx.fillStyle = "white";
ctx.fillRect(0, 0, canvas.width, canvas.height);
```

**2. Clear canvas (trail effect):**

```javascript
ctx.fillStyle = "rgba(255, 255, 255, 0.1)";
ctx.fillRect(0, 0, canvas.width, canvas.height);
```

**3. Circular position:**

```javascript
const angle = (i / total) * Math.PI * 2;
const x = centerX + Math.cos(angle) * radius;
const y = centerY + Math.sin(angle) * radius;
```

**4. Size variation over time:**

```javascript
const size = baseSize + Math.sin(frame * 0.05) * variation;
```

**5. Color gradient (rainbow):**

```javascript
const hue = (i / total) * 360;
ctx.fillStyle = `hsl(${hue}, 70%, 50%)`;
```

**6. Random position:**

```javascript
const x = randomFloat(0, canvas.width);
const y = randomFloat(0, canvas.height);
```

**Notes on when to use each pattern:**

---

---

---

---

## Part 9: Independent Task Checklist

**Task: Create Generative Art Piece**

**Planning:**

- [ ] Choose theme or concept (nature, geometry, abstract)
- [ ] Sketch algorithm on paper
- [ ] List parameters to control (count, size, speed, color)

**Implementation:**

- [ ] Set up canvas and animation loop
- [ ] Implement drawing function
- [ ] Add randomness for variety
- [ ] Test different parameter values

**UI Controls:**

- [ ] Create sliders for 2–3 key parameters
- [ ] Link sliders to variables
- [ ] Display current values
- [ ] Add pause/resume button
- [ ] Add reset button

**Polish:**

- [ ] Choose cohesive color palette
- [ ] Adjust animation speed for smooth motion
- [ ] Ensure shapes don't flicker or overlap messily
- [ ] Test at different parameter settings

**Accessibility:**

- [ ] Provide pause control (motion sensitivity)
- [ ] Ensure sufficient contrast
- [ ] Avoid rapid flashing (seizure risk)

**Documentation:**

- [ ] Comment code to explain algorithm
- [ ] Take screenshots of 2–3 variations
- [ ] Write brief description of concept

**My Progress Notes:**

---

---

---

---

## Part 10: Self-Assessment Rubric

Rate yourself on each criterion (1 = Beginning, 2 = Developing, 3 = Proficient, 4 = Advanced):

| Criterion                                              | 1   | 2   | 3   | 4   | Evidence |
| ------------------------------------------------------ | --- | --- | --- | --- | -------- |
| **Animation:** I can create smooth animation loops     | ☐   | ☐   | ☐   | ☐   |          |
| **Random Values:** I use randomness effectively        | ☐   | ☐   | ☐   | ☐   |          |
| **Parameters:** I expose controls for key variables    | ☐   | ☐   | ☐   | ☐   |          |
| **Transformations:** I can rotate/translate shapes     | ☐   | ☐   | ☐   | ☐   |          |
| **Creativity:** My art has a clear concept/theme       | ☐   | ☐   | ☐   | ☐   |          |
| **UI Controls:** Sliders/buttons work correctly        | ☐   | ☐   | ☐   | ☐   |          |
| **Code Quality:** Code is organized and commented      | ☐   | ☐   | ☐   | ☐   |          |
| **Accessibility:** Motion can be paused, good contrast | ☐   | ☐   | ☐   | ☐   |          |

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

## Part 11: Reflection

**1. How do parameters change the emergent pattern?**

---

---

---

**2. What balance of randomness vs. order creates interesting visuals?**

---

---

---

**3. How does color palette impact mood or meaning?**

---

---

---

**4. What's the difference between generative art and traditional art?**

---

---

---

**5. How could you use generative art in other contexts (games, design, data)?**

---

---

---

---

## Part 12: Algorithm Sketching

**Sketch your generative art algorithm:**

**Concept/Theme:**

---

**Visual Elements (shapes, colors, movements):**

---

---

**Rules (how elements are arranged/animated):**

---

---

**Randomness (what varies each time):**

---

---

**Parameters (what user controls):**

| Parameter | Range | Effect |
| --------- | ----- | ------ |
|           |       |        |
|           |       |        |
|           |       |        |

**Sketch (draw what it might look like):**

```
┌───────────────────────────────┐
│                               │
│                               │
│        (your sketch)          │
│                               │
│                               │
└───────────────────────────────┘
```

---

## Part 13: Debugging Log

**Common Errors & Solutions:**

| Error                    | What Caused It  | How I Fixed It      |
| ------------------------ | --------------- | ------------------- |
| Example: Animation jerky | Too many shapes | Reduced count to 50 |
|                          |                 |                     |
|                          |                 |                     |
|                          |                 |                     |

**Console Debugging:**

**Useful console.log statements:**

```javascript
console.log("Frame:", frame);
console.log("Particle count:", particles.length);
console.log("Position:", x, y);
console.log("Angle:", angle, "Radians");
```

**How I used DevTools to debug:**

---

---

---

## Part 14: Iteration Notes

**Version 1:**

**What I tried:**

---

---

**Sketch or screenshot:**

```
┌───────────────────────────────┐
│                               │
│                               │
│                               │
└───────────────────────────────┘
```

**What worked:**

---

**What didn't work:**

---

---

**Version 2:**

**Changes I made:**

---

---

**Sketch or screenshot:**

```
┌───────────────────────────────┐
│                               │
│                               │
│                               │
└───────────────────────────────┘
```

**Improvements:**

---

**Remaining issues:**

---

---

**Final Version:**

**Key features:**

---

---

**Parameters exposed:**

- 1. ***
- 2. ***
- 3. ***

**Why I'm satisfied with this version:**

---

---

---

## Part 15: Vocabulary Glossary

Define these terms in your own words:

**Generative Art:** ************************\_************************

---

**Parameter:** **************************\_\_\_**************************

---

**Emergent Pattern:** **********************\_\_\_\_**********************

---

**Animation Loop:** ************************\_\_************************

---

**requestAnimationFrame:** ********************\_\_\_********************

---

**Transformation:** ************************\_\_************************

---

**HSL:** ******************************\_******************************

---

**Particle System:** ************************\_************************

---

**Frame Rate (FPS):** **********************\_\_\_\_**********************

---

**Trigonometry:** ************************\_\_\_\_************************

---

---

## Part 16: Creative Exploration

**Try these variations:**

**Variation 1: Nature-Inspired**

- Organic shapes (leaves, waves, cells)
- Earth tones or ocean colors
- Flowing, irregular movement

**Variation 2: Geometric**

- Perfect shapes (circles, squares, triangles)
- Grid or symmetrical arrangement
- Precise, mathematical patterns

**Variation 3: Abstract**

- Random shapes and sizes
- Bold, contrasting colors
- Chaotic or unpredictable motion

**Which variation did I try?** ****************\_\_\_\_****************

**What I learned:** ************************\_\_\_************************

---

---

---

## Part 17: Peer Review

**Partner's Name:** ************************\_\_\_************************

**Their generative art concept:**

---

---

**One strength of their piece:**

---

---

**One suggestion for improvement:**

---

---

**Interesting parameter combination they used:**

---

---

**Partner's feedback for me:**

---

---

---

## Part 18: Extension Challenges

**Challenge 1: Mouse Interaction**

- Particles follow or avoid cursor
- Click to spawn new particles
- Drag to change parameter

**Challenge 2: Export Function**

- Save canvas as PNG image
- Download button with custom filename
- Optional: Save parameter settings as JSON

**Challenge 3: Presets**

- Create 3 preset configurations
- Buttons to load each preset
- Smooth transition between presets

**Challenge 4: Sound Reactive**

- Use Web Audio API to analyze sound
- Animate based on frequency or amplitude
- Visualize music or mic input

**Which challenge did I attempt?** ****************\_\_\_\_****************

**How far did I get?**

---

---

**What I learned:**

---

---

---

## Part 19: Generative Art Analysis

**Analyze this algorithm:**

```
For each of 100 circles:
  - Random position
  - Size = 10 + index × 2
  - Color hue = index × 3.6
  - Move upward slowly
  - Wrap to bottom when off-screen
```

**What patterns would emerge?**

---

---

**What role does randomness play?**

---

---

**How would you improve this algorithm?**

---

---

**What parameters would you expose?**

---

---

---

## Part 20: Project Checklist

**Before submitting your generative art:**

**Functionality:**

- [ ] Animation runs smoothly (no errors)
- [ ] Sliders update visuals in real-time
- [ ] Pause/reset buttons work
- [ ] No console errors

**Creative Quality:**

- [ ] Clear concept or theme
- [ ] Cohesive color palette
- [ ] Interesting emergent patterns
- [ ] Visually appealing at different settings

**Code Quality:**

- [ ] Code organized (functions, classes)
- [ ] Meaningful variable names
- [ ] Comments explain algorithm
- [ ] No redundant or unused code

**Accessibility:**

- [ ] Motion can be paused
- [ ] No rapid flashing (seizure risk)
- [ ] Sufficient contrast for visibility

**Documentation:**

- [ ] Brief description of concept
- [ ] Screenshots of 2–3 variations
- [ ] Notes on parameters and their effects

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

**Creative Coding Frameworks:**

- [p5.js](https://p5js.org/) — JavaScript creative coding library
- [Processing](https://processing.org/) — Visual arts programming
- [three.js](https://threejs.org/) — 3D graphics

**Tutorials:**

- [The Coding Train](https://www.youtube.com/c/TheCodingTrain) — Dan Shiffman
- [Generative Artistry](https://generativeartistry.com/) — Tutorials

**Inspiration:**

- [OpenProcessing](https://openprocessing.org/) — Creative coding community
- [Chrome Experiments](https://experiments.withgoogle.com/)

**Related Tutorials:**

- Unit 6.1 Tutorial: Generative Art (this unit)
- Previous: Module 05 — Data Visualization
- Next: Module 07 — Green STEAM Challenge

---

**Notes to Self:**

---

---

---

---

---

<!-- End of Student Workbook: Unit 6.1 -->
