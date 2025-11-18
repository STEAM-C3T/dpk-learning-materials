---
marp: true
theme: default
paginate: true
---

<!-- _class: lead -->

# Unit 6.1

## Generative Art (Canvas + Parameters)

Module 06 — Creative Web Projects

---

## Learning Outcomes

By end of unit you can:

- Animate with `requestAnimationFrame()`
- Use randomness + rules for patterns
- Parameterize visuals (size, count, speed)
- Apply transformations (translate, rotate)
- Build UI sliders & buttons
- Reflect on creative + algorithmic choices

---

## What Is Generative Art?

Art produced by **algorithmic rules** + **randomness** + **repetition**.

Keywords:

- Algorithm
- Parameter
- Emergence
- Variation
- Iteration

---

## Canvas Recap

Coordinate system:

```
(0,0) top-left
X → right
Y → down
```

Common API:

- `fillRect(x,y,w,h)`
- `beginPath()/arc()/fill()`
- `translate()/rotate()/save()/restore()`

---

## Animation Loop

```javascript
function animate() {
  if (!isPaused) {
    drawPattern();
    frame += speed;
  }
  requestAnimationFrame(animate);
}
animate();
```

Use frame as time variable (rotation, pulsing).

---

## Random Functions

```javascript
const rInt = (a, b) => Math.floor(Math.random() * (b - a + 1)) + a;
const rFloat = (a, b) => Math.random() * (b - a) + a;
const rHSL = (h1, h2) => `hsl(${rInt(h1, h2)},70%,50%)`;
```

Control palette via hue range.

---

## Circular Placement

```javascript
const angle = (i / count) * Math.PI * 2 + frame * 0.01;
const x = cx + Math.cos(angle) * radius;
const y = cy + Math.sin(angle) * radius;
```

Emergent rotation over time.

---

## Transformations

```javascript
ctx.save();
ctx.translate(x, y);
ctx.rotate(angle); // radians
ctx.fillRect(-w / 2, -h / 2, w, h);
ctx.restore();
```

Rotate around center; isolate transformation.

---

## Particle System (Concept)

Class encapsulates:

- Position (x,y)
- Velocity (vx, vy)
- Appearance (radius, hue)
  Methods:
- `update()` motion + wrap
- `draw()` render

---

## UI Controls

Slider pattern:

```javascript
slider.addEventListener("input", (e) => {
  value = parseInt(e.target.value);
  display.textContent = value;
});
```

Real-time adaptation encourages exploration.

---

## Emergent Patterns

Balance:

- Too random = noise
- Too rigid = sterile
  Aim for _structured variation_.

---

## Accessibility & Motion

Provide:

- Pause button
- Speed control
  Avoid:
- Rapid flashing
- Overwhelming density

---

## Creative Process

1. Concept / Theme
2. Sketch algorithm (paper)
3. Implement core loop
4. Add parameters
5. Refine palette + rhythm
6. Document iterations

---

## Color Strategy

Use HSL:

- Hue sweep for spectrum
- Fixed saturation/lightness for cohesion
  Try limited ranges (e.g., 200–240 for cool blues).

---

## Common Pitfalls

- Forget `restore()` → warped canvas
- Creating objects every frame → lag
- Using degrees in `rotate()`
- Unbounded randomness → messy visuals

---

## Debugging Tips

- Log positions: `console.log(x,y)`
- Profile frame time (`performance.now()`)
- Reduce count to isolate issues
- Comment out transforms temporarily

---

## Extension Ideas

- Preset system (store parameter sets)
- Export PNG (`canvas.toDataURL()`)
- Mouse reactive particles
- Simple noise function for organic motion

---

## Reflection Prompts

- Which parameter most changes mood?
- How did randomness vs rule balance evolve?
- What aesthetic principle guided palette?

---

## Assessment Focus

- Intentional parameterization
- Performance stability
- Creative coherence
- Clear documentation & iteration

---

## Next Module Preview

Module 07 — Sustainability Mini‑App:
Purpose-driven UI, localStorage, impact metrics.

---

<!-- _class: lead -->

# Create • Iterate • Reflect

Ready to build your generative piece!

---

## Quick Reference

- Animation: `requestAnimationFrame()`
- Random int: `rInt(min,max)`
- Rotate: radians
- Pause: toggle flag
- Export: `canvas.toDataURL()`

---

<!-- End Unit 6.1 Deck -->
