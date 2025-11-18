# Tutorial: Unit 4.1 — JavaScript Basics

**Module:** 04 — JavaScript Essentials  
**Unit:** 4.1 — JavaScript Basics  
**Estimated Time:** 60–75 minutes  
**Author:** Digital Proficiency Kit Team  
**Last Updated:** 2025-11-18

---

## Overview

**What You Will Learn:**
In this tutorial, you will learn JavaScript fundamentals including variables, data types, operators, functions, and control structures.

**What You Will Build:**
An interactive calculator and quiz application demonstrating JavaScript basics with user input, calculations, and conditional logic.

**Learning Outcomes:**

- Declare and use variables with `let`, `const`, and `var`
- Work with different data types (strings, numbers, booleans, arrays, objects)
- Write and call functions
- Use conditional statements (`if`, `else`, `switch`)
- Implement loops (`for`, `while`)
- Handle user input and output

---

## Prerequisites

Before starting this tutorial, you should:

- [ ] Have completed Modules 02-03 or be familiar with HTML and CSS
- [ ] Understand basic programming concepts (helpful but not required)
- [ ] Know how to use browser DevTools console

**Tools Required:**

- Text editor (VS Code, Notepad++, or similar)
- Modern web browser with JavaScript console (DevTools)

---

## Concept Overview

**What is JavaScript?**
JavaScript is a programming language that adds interactivity to websites. While HTML provides structure and CSS provides style, JavaScript provides behavior.

**Where JavaScript Runs:**

- **Browser (Client-Side):** Runs in user's browser
- **Server (Node.js):** Runs on servers (not covered in this unit)

**Three Ways to Add JavaScript:**

1. **External:** Separate `.js` file (recommended)
2. **Internal:** `<script>` tag in HTML
3. **Inline:** In HTML attributes like `onclick` (avoid)

**JavaScript Execution:**
JavaScript runs line-by-line, top-to-bottom. The browser's JavaScript engine interprets and executes code.

---

## Step-by-Step Guide

### Step 1: Set Up JavaScript Environment

**Objective:** Create HTML file ready for JavaScript.

**Instructions:**

Create `javascript-basics.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>JavaScript Basics</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        max-width: 800px;
        margin: 50px auto;
        padding: 20px;
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
      .output {
        background-color: #f4f4f4;
        padding: 15px;
        margin: 15px 0;
        border-radius: 4px;
        min-height: 50px;
      }
    </style>
  </head>
  <body>
    <h1>JavaScript Basics</h1>
    <div id="output" class="output">Output will appear here</div>

    <script src="script.js"></script>
  </body>
</html>
```

Create empty `script.js` file in same folder.

**Expected Result:**

- HTML page loads with output area
- External JavaScript file linked

**Why This Step:**
External JavaScript files keep code organized and reusable.

**Quick Self-Check:**

- [ ] Page opens in browser
- [ ] Output div visible
- [ ] Console shows no 404 error for script.js

---

### Step 2: Variables and Data Types

**Objective:** Learn to declare variables and work with different data types.

**Instructions:**

Add to `script.js`:

```javascript
// Variables
let userName = "Alex"; // String
const userAge = 16; // Number
let isStudent = true; // Boolean
let hobbies = ["coding", "music"]; // Array
let user = {
  // Object
  name: "Alex",
  age: 16,
  grade: 11,
};

// Output to console
console.log("Name:", userName);
console.log("Age:", userAge);
console.log("Is student?", isStudent);
console.log("Hobbies:", hobbies);
console.log("User object:", user);

// Output to page
const output = document.getElementById("output");
output.innerHTML = `
    <h3>User Information</h3>
    <p><strong>Name:</strong> ${userName}</p>
    <p><strong>Age:</strong> ${userAge}</p>
    <p><strong>Is Student:</strong> ${isStudent}</p>
    <p><strong>Hobbies:</strong> ${hobbies.join(", ")}</p>
    <p><strong>Grade:</strong> ${user.grade}</p>
`;
```

**Expected Result:**

- Information displays on page
- Console shows variable values
- Different data types work correctly

**Why This Step:**
Variables store data. Understanding data types is fundamental to programming.

**Key Concepts:**

- **`let`:** Variable that can change
- **`const`:** Constant that cannot change
- **`var`:** Old way (avoid in modern code)
- **String:** Text in quotes ("hello" or 'hello')
- **Number:** Integers or decimals (42, 3.14)
- **Boolean:** true or false
- **Array:** List of values [1, 2, 3]
- **Object:** Key-value pairs {name: "Alex"}

**Common Pitfall:**
⚠️ **Watch Out:** Using `const` for values that need to change.  
✅ **Tip:** Use `const` by default, `let` when value changes, avoid `var`.

**Quick Self-Check:**

- [ ] Information displays on page
- [ ] Console log shows all values
- [ ] Can change `userName` value and see update

---

### Step 3: Operators and Expressions

**Objective:** Use arithmetic, comparison, and logical operators.

**Instructions:**

Add to `script.js`:

```javascript
// Arithmetic Operators
let a = 10;
let b = 3;

console.log("Addition:", a + b); // 13
console.log("Subtraction:", a - b); // 7
console.log("Multiplication:", a * b); // 30
console.log("Division:", a / b); // 3.333...
console.log("Modulus (remainder):", a % b); // 1
console.log("Exponentiation:", a ** 2); // 100

// Comparison Operators
console.log("a > b:", a > b); // true
console.log("a === b:", a === b); // false (strict equality)
console.log("a !== b:", a !== b); // true (strict inequality)

// Logical Operators
let x = true;
let y = false;

console.log("x AND y:", x && y); // false
console.log("x OR y:", x || y); // true
console.log("NOT x:", !x); // false

// String Concatenation
let firstName = "Alex";
let lastName = "Chen";
let fullName = firstName + " " + lastName;
console.log("Full name:", fullName);

// Template Literals (modern way)
let greeting = `Hello, ${firstName}! You are ${userAge} years old.`;
console.log(greeting);
```

**Expected Result:**

- Console shows all calculations
- Comparison results are booleans
- Strings concatenate correctly

**Why This Step:**
Operators are essential for calculations, comparisons, and logic.

**Important:**

- **`===`** (strict equality): Checks value AND type
- **`==`** (loose equality): Converts types (avoid)
- Always use `===` and `!==`

**Common Pitfall:**
⚠️ **Watch Out:** Using `=` (assignment) instead of `===` (comparison).  
✅ **Tip:** `=` assigns, `==` compares (but use `===`).

**Quick Self-Check:**

- [ ] Console shows correct calculations
- [ ] Boolean comparisons work
- [ ] Template literals display variables

---

### Step 4: Functions

**Objective:** Write reusable functions with parameters and return values.

**Instructions:**

Add to `script.js`:

```javascript
// Function Declaration
function greet(name) {
  return `Hello, ${name}!`;
}

// Function Call
console.log(greet("Alex"));
console.log(greet("Jordan"));

// Function with Multiple Parameters
function add(num1, num2) {
  return num1 + num2;
}

console.log("5 + 3 =", add(5, 3));

// Function Expression
const multiply = function (num1, num2) {
  return num1 * num2;
};

console.log("4 * 7 =", multiply(4, 7));

// Arrow Function (modern syntax)
const divide = (num1, num2) => {
  return num1 / num2;
};

console.log("20 / 4 =", divide(20, 4));

// Arrow Function (concise)
const square = (num) => num * num;
console.log("Square of 6:", square(6));

// Function without Return (performs action)
function displayMessage(message) {
  output.innerHTML += `<p>${message}</p>`;
}

displayMessage("Functions are powerful!");
```

**Expected Result:**

- Functions execute and return values
- Console shows function results
- Page displays messages

**Why This Step:**
Functions organize code into reusable blocks, making programs modular and maintainable.

**Function Syntax Comparison:**

```javascript
// Traditional
function name(params) {
  return value;
}

// Expression
const name = function (params) {
  return value;
};

// Arrow
const name = (params) => {
  return value;
};

// Concise arrow (one expression)
const name = (params) => value;
```

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting `return` when you need a value.  
✅ **Tip:** If function should give back a value, use `return`.

**Quick Self-Check:**

- [ ] Functions return correct values
- [ ] Can call same function multiple times
- [ ] Arrow functions work

---

### Step 5: Conditional Statements

**Objective:** Control program flow with `if`, `else`, and `switch`.

**Instructions:**

Add to `script.js`:

```javascript
// If Statement
function checkAge(age) {
  if (age >= 18) {
    return "You are an adult.";
  } else if (age >= 13) {
    return "You are a teenager.";
  } else {
    return "You are a child.";
  }
}

console.log(checkAge(20)); // Adult
console.log(checkAge(15)); // Teenager
console.log(checkAge(10)); // Child

// Switch Statement
function getDayType(day) {
  switch (day) {
    case "Monday":
    case "Tuesday":
    case "Wednesday":
    case "Thursday":
    case "Friday":
      return "Weekday";
    case "Saturday":
    case "Sunday":
      return "Weekend";
    default:
      return "Invalid day";
  }
}

console.log(getDayType("Wednesday")); // Weekday
console.log(getDayType("Saturday")); // Weekend

// Ternary Operator (shorthand if/else)
const temperature = 75;
const weather = temperature > 70 ? "Warm" : "Cool";
console.log("Weather:", weather);

// Complex Condition
function canVote(age, isCitizen) {
  if (age >= 18 && isCitizen) {
    return "You can vote!";
  } else if (age < 18) {
    return "Too young to vote.";
  } else {
    return "Must be a citizen to vote.";
  }
}

console.log(canVote(20, true)); // Can vote
console.log(canVote(16, true)); // Too young
console.log(canVote(20, false)); // Must be citizen
```

**Expected Result:**

- Conditional logic executes correctly
- Different paths taken based on conditions
- Console shows appropriate messages

**Why This Step:**
Conditionals allow programs to make decisions and respond to different situations.

**When to Use What:**

- **if/else:** Most flexible, handles complex conditions
- **switch:** Multiple exact value checks (like menu options)
- **ternary:** Simple true/false, one-line assignment

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting `break` in `switch` cases (causes fall-through).  
✅ **Tip:** Always end switch cases with `break` or `return`.

**Quick Self-Check:**

- [ ] if/else works correctly
- [ ] switch statement handles all cases
- [ ] Ternary operator returns expected value

---

### Step 6: Loops

**Objective:** Repeat actions with `for` and `while` loops.

**Instructions:**

Add to `script.js`:

```javascript
// For Loop
console.log("Counting 1 to 5:");
for (let i = 1; i <= 5; i++) {
  console.log(i);
}

// Loop through Array
const fruits = ["apple", "banana", "cherry"];
console.log("Fruits:");
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}

// For...of Loop (modern, cleaner)
console.log("Fruits (for...of):");
for (const fruit of fruits) {
  console.log(fruit);
}

// While Loop
let count = 0;
console.log("While loop counting:");
while (count < 3) {
  console.log(count);
  count++;
}

// Loop to Build HTML
let listHTML = "<h3>My Hobbies</h3><ul>";
const myHobbies = ["Coding", "Music", "Reading"];
for (const hobby of myHobbies) {
  listHTML += `<li>${hobby}</li>`;
}
listHTML += "</ul>";
output.innerHTML += listHTML;

// Array Methods (modern approach)
const numbers = [1, 2, 3, 4, 5];

// forEach: Execute function for each item
numbers.forEach((num) => {
  console.log("Number:", num);
});

// map: Transform each item
const doubled = numbers.map((num) => num * 2);
console.log("Doubled:", doubled); // [2, 4, 6, 8, 10]

// filter: Keep items that match condition
const evens = numbers.filter((num) => num % 2 === 0);
console.log("Even numbers:", evens); // [2, 4]

// reduce: Combine items into single value
const sum = numbers.reduce((total, num) => total + num, 0);
console.log("Sum:", sum); // 15
```

**Expected Result:**

- Loops execute correctly
- Arrays processed
- Page displays list of hobbies
- Console shows all iterations

**Why This Step:**
Loops automate repetitive tasks, essential for working with collections of data.

**Loop Types:**

- **`for`:** Known number of iterations
- **`for...of`:** Loop through array items
- **`while`:** Continue until condition false
- **`forEach`:** Execute function for each array item
- **`map`:** Create new array from transformation
- **`filter`:** Create new array with matching items
- **`reduce`:** Combine array into single value

**Common Pitfall:**
⚠️ **Watch Out:** Infinite loops (condition never becomes false).  
✅ **Tip:** Always ensure loop condition will eventually be false.

**Quick Self-Check:**

- [ ] Loops execute correct number of times
- [ ] Array methods work as expected
- [ ] List displays on page

---

### Step 7: Build Interactive Calculator

**Objective:** Combine all concepts into functional calculator.

**Instructions:**

Update `javascript-basics.html` body:

```html
<body>
  <h1>Interactive Calculator</h1>

  <div>
    <input type="number" id="num1" placeholder="First number" />
    <select id="operator">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">×</option>
      <option value="/">÷</option>
    </select>
    <input type="number" id="num2" placeholder="Second number" />
    <button onclick="calculate()">Calculate</button>
  </div>

  <div id="result" class="output"></div>

  <h2>Quiz</h2>
  <div>
    <p>What is 5 + 3?</p>
    <input type="number" id="quizAnswer" />
    <button onclick="checkAnswer()">Check Answer</button>
  </div>
  <div id="quizResult" class="output"></div>

  <script src="script.js"></script>
</body>
```

Update `script.js`:

```javascript
// Calculator Function
function calculate() {
  // Get values from inputs
  const num1 = parseFloat(document.getElementById("num1").value);
  const num2 = parseFloat(document.getElementById("num2").value);
  const operator = document.getElementById("operator").value;

  // Validate inputs
  if (isNaN(num1) || isNaN(num2)) {
    document.getElementById("result").innerHTML =
      "<p style='color: red;'>Please enter valid numbers!</p>";
    return;
  }

  // Perform calculation
  let result;
  switch (operator) {
    case "+":
      result = num1 + num2;
      break;
    case "-":
      result = num1 - num2;
      break;
    case "*":
      result = num1 * num2;
      break;
    case "/":
      if (num2 === 0) {
        document.getElementById("result").innerHTML =
          "<p style='color: red;'>Cannot divide by zero!</p>";
        return;
      }
      result = num1 / num2;
      break;
    default:
      result = "Invalid operator";
  }

  // Display result
  document.getElementById(
    "result"
  ).innerHTML = `<p><strong>${num1} ${operator} ${num2} = ${result}</strong></p>`;
}

// Quiz Function
function checkAnswer() {
  const userAnswer = parseInt(document.getElementById("quizAnswer").value);
  const correctAnswer = 8;
  const resultDiv = document.getElementById("quizResult");

  if (isNaN(userAnswer)) {
    resultDiv.innerHTML =
      "<p style='color: orange;'>Please enter a number!</p>";
    return;
  }

  if (userAnswer === correctAnswer) {
    resultDiv.innerHTML = "<p style='color: green;'>✓ Correct! Well done!</p>";
  } else {
    resultDiv.innerHTML = `<p style='color: red;'>✗ Incorrect. The answer is ${correctAnswer}.</p>`;
  }
}
```

**Expected Result:**

- Calculator performs operations correctly
- Input validation works
- Quiz checks answers
- Error messages display appropriately

**Why This Step:**
Brings together variables, functions, conditionals, and DOM manipulation into a real application.

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting to convert input values to numbers (`parseFloat`).  
✅ **Tip:** Input values are strings by default—use `parseFloat()` or `parseInt()`.

**Quick Self-Check:**

- [ ] Calculator computes correctly
- [ ] Division by zero handled
- [ ] Quiz validates answers
- [ ] Error messages display

---

## Debugging Section

**Scenario 1: Nothing happens when clicking button**

- **Possible Causes:**
  - Function name misspelled in `onclick`
  - JavaScript file not loaded
  - Function not defined yet (order matters)
- **Solution:**
  - Check console for errors
  - Verify function names match
  - Ensure script loads after HTML

**Scenario 2: "undefined" or "NaN" in output**

- **Possible Cause:** Variable not set or wrong data type
- **Solution:**
  - Use `console.log()` to check variable values
  - Ensure inputs converted to numbers (`parseFloat`)
  - Check for typos in variable names

**Scenario 3: Condition always executes wrong branch**

- **Possible Cause:** Using `=` instead of `===`
- **Solution:** Double-check comparison operators

**Scenario 4: Loop runs forever**

- **Possible Cause:** Counter never changes or condition never false
- **Solution:**
  - Ensure loop variable increments/decrements
  - Check loop condition will eventually be false
  - Add `console.log()` inside loop to see iterations

**General Debugging Tips:**

- **Console is your friend:** `console.log()` everywhere
- **Check DevTools Console:** Shows errors with line numbers
- **Use breakpoints:** In DevTools Sources tab
- **Read error messages carefully:** They often tell you exactly what's wrong
- **Comment out code:** Isolate problem section

---

## Consolidated Key Concepts

**1. Variables**

```javascript
let changeable = "can change";
const constant = "cannot change";
```

**2. Data Types**

- String: `"text"`
- Number: `42`
- Boolean: `true` / `false`
- Array: `[1, 2, 3]`
- Object: `{key: "value"}`

**3. Functions**

```javascript
function name(params) {
  return value;
}
const name = (params) => value;
```

**4. Conditionals**

```javascript
if (condition) {
  // code
} else {
  // code
}
```

**5. Loops**

```javascript
for (let i = 0; i < 10; i++) {
  // code
}
for (const item of array) {
  // code
}
```

**6. Operators**

- Arithmetic: `+`, `-`, `*`, `/`, `%`
- Comparison: `===`, `!==`, `>`, `<`, `>=`, `<=`
- Logical: `&&`, `||`, `!`

---

## Practice Variations

**Variation 1: Enhanced Calculator**

- Add more operations (power, square root)
- Implement calculation history
- Add "Clear" button

**Variation 2: Grade Calculator**

- Input quiz scores
- Calculate average
- Determine letter grade (A-F)

**Variation 3: Number Guessing Game**

- Generate random number 1-100
- User guesses, get "higher" or "lower" feedback
- Count number of guesses

---

## Reflection Prompts

1. **How are JavaScript functions similar to functions in math?**

   - [Space for student response]

2. **When would you use a `for` loop vs. a `while` loop?**

   - [Space for student response]

3. **Why is input validation important?**
   - [Space for student response]

---

## Further Reading

**Official Documentation:**

- [MDN: JavaScript Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
- [MDN: JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)

**Related Tutorials:**

- Previous: Module 03 — CSS Styling & Layout
- Next: Unit 4.2 — DOM Manipulation

**Interactive Learning:**

- [JavaScript.info](https://javascript.info/)
- [freeCodeCamp JavaScript](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/)

**Advanced Topics:**

- Asynchronous JavaScript (Promises, async/await)
- ES6+ features
- Object-oriented programming in JavaScript

---

## Accessibility Considerations

**This Tutorial Emphasized:**

- ✅ Meaningful button text
- ✅ Error messages that are clear
- ✅ Keyboard-accessible interactions
- ✅ Visual feedback for user actions

**JavaScript & Accessibility:**

- Don't rely solely on color for feedback
- Ensure keyboard navigation works
- Provide text alternatives for dynamic content
- Test with screen readers

**Next Steps:**

- Unit 4.2 will cover DOM manipulation and events

---

## Metadata

**Module:** 04 — JavaScript Essentials  
**Unit:** 4.1 — JavaScript Basics  
**Author:** Digital Proficiency Kit Team  
**Contributors:** N/A  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Unit 4.1 Tutorial -->
