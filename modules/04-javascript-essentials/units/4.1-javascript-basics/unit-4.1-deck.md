---
marp: true
theme: default
paginate: true
header: "Digital Proficiency Kit | Module 04: Unit 4.1"
footer: "STEAM-C3T | CC BY-SA 4.0"
---

# Unit 4.1: JavaScript Basics

Module 04: JavaScript Essentials
Digital Proficiency Kit

---

## Warm-Up

What happens when you click a button on a website? How does the page respond?

_Think, pair, share your ideas._

---

## Unit Objectives

- Write basic JavaScript syntax
- Select elements from the DOM
- Register event listeners
- Update content dynamically

---

## Quick Check

What's the difference between HTML, CSS, and JavaScript?

---

## JavaScript Basics

- Variables: `let`, `const`
- Functions: `function name() { }`
- Strings and numbers
- Console for testing: `console.log()`

---

## Selecting Elements

```javascript
// Select by ID
const element = document.querySelector("#myId");

// Select by class
const elements = document.querySelectorAll(".myClass");
```

---

## Event Listeners

```javascript
button.addEventListener("click", function () {
  // Do something when clicked
});
```

Common events: click, submit, keydown, input

---

## Updating Content

```javascript
// Change text
element.textContent = "New text";

// Change style
element.style.color = "blue";

// Add/remove classes
element.classList.add("active");
```

---

## Guided Practice

Create a button that changes text when clicked

---

## Check for Understanding

1. How do you select an element by ID?
2. What does `addEventListener` do?
3. How do you change an element's text?

---

## Independent Task

Add interactivity to your page using event listeners

---

## Reflection

What surprised you about JavaScript? What's still confusing?

---

## Accessibility

- Use semantic buttons
- Ensure keyboard events work (Enter/Space)
- Provide clear feedback

---

## Extension

- Try different event types
- Chain multiple actions
- Add input validation

---

## Summary & Next Steps

Today: Variables, selecting elements, events, updating DOM

Next: Unit 4.2 — DOM manipulation and state

---

## Questions?

Ask now, or check the tutorial and workbook for more info.

---

# Thank You!

Next: Unit 4.2 — DOM Manipulation

---

<!-- End of Unit 4.1 Deck -->
