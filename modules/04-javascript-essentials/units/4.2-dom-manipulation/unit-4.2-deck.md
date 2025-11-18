---
marp: true
theme: default
paginate: true
header: "Digital Proficiency Kit | Module 04: Unit 4.2"
footer: "STEAM-C3T | CC BY-SA 4.0"
---

# Unit 4.2: DOM Manipulation

Module 04: JavaScript Essentials
Digital Proficiency Kit

---

## Warm-Up

How do dynamic lists (like to-do apps) work? What happens when you add or remove items?

_Think, pair, share your ideas._

---

## Unit Objectives

- Manage UI state with JavaScript
- Create and remove DOM elements
- Build dynamic lists or forms
- Render UI from state

---

## Quick Check

What is "state" in a web application?

---

## State Management

Keep data in JavaScript:

```javascript
let items = ["Task 1", "Task 2"];
```

Render UI from state:

```javascript
function render() {
  // Update DOM based on items
}
```

---

## Creating Elements

```javascript
const newItem = document.createElement("li");
newItem.textContent = "New task";
list.appendChild(newItem);
```

---

## Removing Elements

```javascript
element.remove();
// or
parent.removeChild(child);
```

---

## Event Delegation

Handle events on parent for dynamic children:

```javascript
list.addEventListener("click", (e) => {
  if (e.target.matches("button")) {
    // Handle button click
  }
});
```

---

## Guided Practice

Build a simple to-do list: add items, mark complete, remove

---

## Check for Understanding

1. What's the difference between state and DOM?
2. How do you create a new element?
3. Why use event delegation?

---

## Independent Task

Create a dynamic UI component with state-driven rendering

---

## Reflection

How does state make UIs more manageable? What's challenging?

---

## Accessibility

- Manage focus when adding/removing elements
- Announce changes to screen readers
- Ensure all controls are keyboard accessible

---

## Extension

- Add filtering or search
- Save state to localStorage
- Implement undo/redo

---

## Summary & Next Steps

Today: State management, creating/removing elements, dynamic rendering

Next: Module 05 — Data Visualization

---

## Questions?

Ask now, or check the tutorial and workbook for more info.

---

# Thank You!

Next: Module 05 — Data Visualization

---

<!-- End of Unit 4.2 Deck -->
