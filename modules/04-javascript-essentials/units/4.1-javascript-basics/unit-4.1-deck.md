---
marp: true
theme: default
paginate: true
header: "Digital Proficiency Kit | Module 04: Unit 4.1"
footer: "STEAM-C3T | CC BY-SA 4.0"
---

# Unit 4.1: JavaScript Basics and a First Interaction

Module 04: JavaScript Essentials

---

## Warm-Up

Predict the result of `12 + 3 * 2`. What happens if you change one value?

---

## Learning Outcomes

- Store and update simple values with `const` and `let`.
- Use arithmetic operators and simple comparisons.
- Write and call a function that returns a value.
- Use `if`/`else` to respond to an invalid calculation.
- Connect a form event to a function and display feedback.

---

## Values and Variables

```js
const price = 12;
let quantity = 3;
quantity = quantity + 1;
console.log(price * quantity);
```

Use `const` when a binding will not be reassigned and `let` when it will.

---

## Functions

```js
function add(first, second) {
  return first + second;
}

console.log(add(12, 3));
```

The parameters are inputs. `return` sends a value back to the caller.

---

## Conditions

```js
if (second === 0) {
  console.log("Cannot divide by zero");
} else {
  console.log(first / second);
}
```

Ask: Which part runs when the second number is zero?

---

## First Interaction

```js
form.addEventListener("submit", (event) => {
  event.preventDefault();
  result.textContent = add(first, second);
});
```

The event handler connects the form to the function. `textContent` updates the visible result safely.

---

## Guided Practice

Open the calculator example. Trace the values from the inputs into the calculation function and then into the result message.

---

## Independent Task

Build a two-number calculator with labeled inputs, one calculation function, a submit event listener, and a helpful message for missing values or division by zero.

---

## Check for Understanding

1. What is the difference between `const` and `let`?
2. What does a function return?
3. Why does the form handler call `preventDefault()`?
4. Which element displays the result?

---

## Accessibility and Safe Output

- Give every input a visible label.
- Use a form and submit button so keyboard users can operate the calculator.
- Put result feedback in a polite live region.
- Use `textContent`; do not build output with `innerHTML`.

---

## Optional Extensions

- Try arrays, objects, or a loop after the core calculator works.
- Add one operation or another validation rule.

These extensions are not prerequisites for Unit 4.2.

---

## Next Step

Unit 4.2 uses events and functions to manage a list stored in an array and render the visible items from state.
