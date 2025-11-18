# Teacher-Annotated Workbook: Unit 6.1 — Generative Art

**Module:** 06 — Creative Web Projects  
**Unit:** 6.1 — Generative Art  
**Recommended Duration:** 90–120 minutes  
**Prerequisites:** HTML/CSS basics (Modules 1–3), JavaScript fundamentals (Module 4), Canvas/Data Viz (Module 5 recommended)

---

## Overview for Teachers

This workbook provides answer keys, teaching strategies, differentiation pathways, assessment rubric, extension ideas, troubleshooting guidance, and professional reflection prompts for Unit 6.1. Students explore _generative art_ using HTML5 Canvas: algorithmic visuals, parameterization, randomness, animation loops, and user controls.

### Core Pedagogical Goals

- Reinforce algorithmic thinking and abstraction (parameters as levers).
- Foster creative expression through code (STEAM integration: Art + Tech + Math).
- Encourage iterative design (sketch → implement → refine → reflect).
- Promote accessible & inclusive practices (motion control, contrast awareness).

### DigComp 2.2 Mapping

| Competence                                      | Connection                                            |
| ----------------------------------------------- | ----------------------------------------------------- |
| 3.1 Developing digital content                  | Students create dynamic algorithmic visuals           |
| 3.2 Integrating and re-elaborating              | Combine animation, UI, color logic                    |
| 3.4 Programming                                 | Implement loops, functions, classes (Particle)        |
| 5.2 Identifying needs & technological responses | Adjust parameters to reach aesthetic/functional goals |

---

## Part 1 Answer Key (Fill‑In)

1. **algorithmic**
2. **unique** (or _different_)
3. **parameters**
4. **emergent**
5. **rules**
6. **requestAnimationFrame**
7. **60**
8. **semi** (semi‑transparent)
9. **frame**
10. **isPaused**
11. **save**
12. **translate**
13. **rotate**
14. **radians**
15. **restore**
16. **0** and **1**
17. **floor** (in combination with scaling calculation)
18. **Hue**
19. **Hue**
20. **HSL**

### Teaching Notes

Stress difference between randomness (unpredictable variation) and noise (coherent subtle variation). Clarify angle units (radians vs degrees) early—students often try degrees.

---

## Part 2 Animation Loop Answer Key

Blanks: `ctx.fillStyle`, `drawPattern`, `animationSpeed` (or a numeric increment), `requestAnimationFrame`, `animate`.

**requestAnimationFrame:** Schedules next frame synced with browser repaint for smooth performance and efficiency.
**Frame counter purpose:** Enables time‑based animation (e.g., rotating, pulsing, oscillating).  
**Without isPaused check:** Loop continues, ignoring user intent; cannot halt motion (accessibility issue).

### Formative Check

Ask: “What changes if I double the frame increment?” Expect: faster temporal changes (oscillations accelerate).

---

## Part 3 Random Functions Answer Key

```javascript
function randomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
function randomFloat(min, max) {
  return Math.random() * (max - min) + min;
}
function randomHSL(hueMin = 0, hueMax = 360) {
  const hue = randomInt(hueMin, hueMax);
  return `hsl(${hue}, 70%, 50%)`;
}
```

Sample outputs vary—emphasize nondeterminism. HSL chosen for palette control (e.g., hue span for related colors).

---

## Part 4 Circular Arrangement Answer Key

Blanks: `2`, `cos`, `sin`. Adding `frame * 0.01` rotates ring over time (continuous motion).

### Misconception Alert

Students may treat `i / circleCount` as degrees; reinforce conversion logic for full circle (× 2π).

---

## Part 5 Transformations Answer Key

Sequence: `save`, `translate`, `rotate`, `restore`. Centering with negative half‑width/height ensures rotation about the rectangle's center.

**If restore omitted:** Subsequent drawings inherit transformed coordinate system—cascading distortions.

### Strategy

Demonstrate progressively: draw without save/restore; observe compounding rotations.

---

## Part 6 UI Controls Answer Key

Blanks: `circle-count`, `count-value`, `input`, `parseInt`.  
**parseInt:** Converts slider’s string value to integer.  
**Why input event:** Fires continuously while dragging, enabling real‑time visual feedback; `change` only fires on release.

---

## Part 7 Particle System Answer Key

Velocity ranges: `-2, 2`. Updates: `this.x += this.vx * animationSpeed; this.y += this.vy * animationSpeed;`  
Wrap for y:

```javascript
if (this.y < 0) this.y = canvas.height;
if (this.y > canvas.height) this.y = 0;
```

**Wrap concept:** Teleports particle to opposite edge (toroidal space).  
**Bounce modification:** Invert velocity and clamp position at boundary.

---

## Part 8 Pattern Usage Notes (Model)

1. Full clear: Reset composition each frame (no trails).
2. Trail: Fading persistence for motion blur aesthetics.
3. Circular position: Even angular distribution around center.
4. Size variation: Temporal pulsing linked to `frame`.
5. Gradient hue: Systematic color progression; visual rhythm.
6. Random position: Scatter distribution; base for particle initialization.

Encourage students to annotate reasons personally—metacognition enhances transfer.

---

## Part 9 Independent Task Guidance

Minimum expected features: Smooth animation, at least two parameters, pause control, commentary on concept.  
Advanced: Export PNG, preset system, layered algorithms.

### Circulation Questions

- “Which parameter most dramatically alters composition?”
- “How could you constrain randomness for more coherence?”
- “Is motion comfortable (not overwhelming)?”

---

## Part 10 Self‑Assessment Calibration

Use rubric descriptors to coach upward leveling. If student marks “4” without evidence, prompt: “Show me the code segment demonstrating advanced reuse/modularity.”

---

## Part 11 Reflection Exemplars

1. Parameters modulate structure; small numeric deltas can shift emergent symmetry.
2. Balance: Enough randomness for novelty; enough rules for recognizability.
3. Palette influences emotional tone (e.g., cool hues → calm).
4. Generative art: System defines outcome; traditional art: manual direct creation.
5. Applications: Procedural game assets, dynamic backgrounds, data‑driven visuals.

---

## Part 12 Algorithm Planning Notes

Encourage rough pencil sketches before coding; reference fosters intentionality vs trial‑and‑error only.

### Differentiation

- **Support:** Provide template with animation loop & single parameter.
- **Challenge:** Student designs composite algorithm (e.g., particles + recursive tree + noise lines).

---

## Part 13 Debugging Log Guidance

Common errors: Performance degradation with excessive object creation. Solution: initialize once, reuse arrays.

Encourage logging early (positions, calculated angles) THEN remove extraneous logs for production cleanliness.

---

## Part 14 Iteration Coaching

Require at least two documented iterations (visual + notes). Focus conversation on _decision rationales_ not just what changed.

---

## Part 15 Vocabulary Model Definitions

Provide after student attempt; avoid pre‑empting recall.

---

## Part 16 Variation Commentary

- Nature: Introduce Perlin/Simplex noise for organic movement.
- Geometric: Emphasize symmetry, tiling logic (grid loops).
- Abstract: Risk of visual clutter—teach restraint (limit simultaneous random properties).

---

## Part 17 Peer Review Protocol

Train specific, actionable feedback: “Increase contrast at larger sizes” > “Looks cool.” Provide sentence stems.

---

## Part 18 Extension Challenge Notes

- Mouse interaction: Introduce event listeners + distance calculations.
- Presets: Store parameter sets in array; loop to apply.
- Sound reactive: Map amplitude bands to parameter modulations (requires caution: complexity/time).

---

## Part 19 Algorithm Analysis Model Answers

Emergent pattern: Vertical stratification by size; hue gradient upward; drifting cloud impression. Randomness adds positional variation preventing uniform appearance. Improvement: Introduce easing movement; add slight horizontal oscillation.

Parameters to expose: Count, vertical speed, hue range, size multiplier.

---

## Assessment Rubric (Teacher)

| Criterion                       | Beginning (1)                | Developing (2)                        | Proficient (3)                          | Advanced (4)                                                    |
| ------------------------------- | ---------------------------- | ------------------------------------- | --------------------------------------- | --------------------------------------------------------------- |
| Concept & Theme                 | No clear concept             | Vague idea, limited coherence         | Clear theme guides choices              | Compelling concept; cohesive aesthetic narrative                |
| Parameterization                | No controls                  | One control; limited impact           | ≥2 meaningful controls                  | Multi‑parameter; presets/advanced UI                            |
| Algorithmic Complexity          | Simple static shapes         | Basic animation or repetition         | Combined loops + transformations        | Layered algorithms (particles + recursion + noise)              |
| Randomness Use                  | Uncontrolled, chaotic        | Some variation but inconsistent       | Balanced randomness for variety         | Sophisticated variation (controlled palettes/structured noise)  |
| Code Quality                    | Unorganized; duplication     | Some structure; minor duplication     | Functions/classes; readable             | Modular, reusable patterns; documented rationale                |
| Performance                     | Laggy / excessive operations | Occasional frame drops                | Stable at target FPS                    | Optimized (profiling/logical culling)                           |
| Accessibility (Motion/Contrast) | No pause; poor contrast      | Pause OR contrast partially addressed | Pause + safe motion + adequate contrast | Thoughtful inclusive design (adjustable speed, palette options) |
| Reflection & Documentation      | Minimal notes                | Basic description                     | Clear rationale & iteration notes       | Deep reflection + evidence of learning transfer                 |

Use rubric for formative feedback mid‑way (after initial implementation) to encourage improvement trajectory.

---

## Troubleshooting Guide

| Issue                | Cause                               | Strategy                                           |
| -------------------- | ----------------------------------- | -------------------------------------------------- |
| Stuttering animation | Too many draw calls per frame       | Reduce shape count; profile frame time             |
| Colors look muddy    | Overlapping semi‑transparent fills  | Occasional full clears or adjust alpha             |
| Sliders unresponsive | Missing `input` listener            | Replace `change` with `input`                      |
| Rotation offset      | Origin not translated before rotate | Apply `translate` then `rotate` then draw centered |
| Memory growth        | Creating arrays each frame          | Initialize once; reuse objects                     |

Encourage early performance measurement using `performance.now()`.

---

## Differentiation Strategies

| Level    | Scaffold                            | Goal                                             |
| -------- | ----------------------------------- | ------------------------------------------------ |
| Emerging | Provide starter skeleton & 1 slider | Achieve working loop + single parameter          |
| On Track | Build ring pattern + 2 sliders      | Demonstrate controlled variation                 |
| Advanced | Multi‑system composition + presets  | Integrate UI + algorithm layering + optimization |

---

## Extension Ideas

1. **Preset Manager:** Save parameter sets to array; cycle with buttons.
2. **Palette Designer:** UI to set hue range, saturation, lightness dynamically.
3. **Adaptive Speed:** Frame time feedback reduces complexity (dynamic throttling).
4. **Snapshot Timeline:** Automatic PNG snapshots every N seconds, displayed as gallery.

---

## Professional Reflection (Teacher)

- Were students able to articulate algorithmic rules clearly?
- Did accessibility (pause control) feel integrated or appended late?
- Which misconceptions appeared repeatedly (e.g., radians)?
- What evidence showed students iterated intentionally vs random tinkering?
- Next iteration: Introduce noise earlier? Provide palette design mini‑lesson?

Record reflections promptly after lesson; adjust next run.

---

## Ethical & Inclusion Notes

Generative outputs should avoid seizure triggers (rapid flashing, high‑frequency contrast changes). Reinforce optional motion control via pause and perhaps speed slider.

Encourage culturally diverse inspirations—not only Western geometric art. Invite references from students’ backgrounds (textiles, patterns, natural forms).

---

## Summary for Teachers

Students learn to treat code as an expressive medium, balancing constraint (rules) and freedom (randomness). Key success indicators: purposeful parameters, coherent visual identity, and clear reflection on algorithmic choices.

**Next Module Preview:** Module 07 — Sustainability Mini‑App (purpose‑driven application, localStorage, impact communication).

---

**Version 1.0** — 2025-11-18  
Prepared by: Automated assistant (review manually before classroom use)

<!-- End Teacher-Annotated Workbook: Unit 6.1 -->
