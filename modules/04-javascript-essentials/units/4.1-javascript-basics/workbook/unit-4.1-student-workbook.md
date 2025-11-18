# Student Workbook: Unit 4.1 — JavaScript Basics

**Module:** 04 — JavaScript Essentials  
**Unit:** 4.1 — JavaScript Basics  
**Name:** ____________________  
**Date:** ____________________

---

## Learning Objectives

By the end of this unit, I will be able to:

- [ ] Declare variables using `let`, `const`, and understand when to use each
- [ ] Work with different data types (strings, numbers, booleans, arrays, objects)
- [ ] Use arithmetic, comparison, and logical operators
- [ ] Write and call functions with parameters and return values
- [ ] Implement conditional statements (`if/else`, `switch`)
- [ ] Create loops to repeat actions (`for`, `while`, array methods)
- [ ] Build an interactive calculator combining all concepts
- [ ] Debug JavaScript using console.log and browser DevTools

---

## Part 1: Key Concepts Fill-In

**Variables and Data Types**

1. To declare a variable that can change, use: ____________

2. To declare a constant that cannot change, use: ____________

3. Text values are called: ____________ and are wrapped in ____________

4. True/false values are called: ____________

5. A list of values is called an: ____________ and uses ____________ brackets

6. A collection of key-value pairs is called an: ____________ and uses ____________ braces

**Operators**

7. The operator for addition is: ____________

8. The operator for strict equality is: ____________ (not `==`)

9. The logical AND operator is: ____________

10. The modulus (remainder) operator is: ____________

**Functions**

11. A reusable block of code is called a: ____________

12. To give back a value from a function, use the ____________ keyword

13. Modern arrow function syntax: `const add = (a, b) => ____________;`

**Control Flow**

14. To make decisions in code, use an ____________ statement

15. For multiple exact value checks, use a ____________ statement

16. A loop with a known number of iterations uses: ____________ loop

17. To loop through array items, use: ____________ loop

---

## Part 2: Guided Practice Notes

### Step 1: Variables Setup

**Variable Declaration Practice:**

```javascript
// Declare a variable for your name:
let myName = "____________________";

// Declare a constant for your birth year:
const birthYear = ____________;

// Declare an array of your favorite colors (at least 3):
let favoriteColors = [____________, ____________, ____________];

// Declare an object representing yourself:
let me = {
    name: "____________________",
    age: ____________,
    school: "____________________"
};
```

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

### Step 2: Operators Practice

**Calculate and record results:**

```javascript
let x = 15;
let y = 4;
```

- `x + y` = ____________
- `x - y` = ____________
- `x * y` = ____________
- `x / y` = ____________
- `x % y` = ____________ (reminder: modulus gives remainder)
- `x > y` = ____________ (true or false?)
- `x === y` = ____________ (true or false?)

**String Concatenation:**

```javascript
let firstName = "____________________";
let lastName = "____________________";
let fullName = firstName + " " + lastName;
// fullName = ____________________
```

**Template Literal:**

```javascript
let age = ____________;
let message = `I am ${age} years old`;
// message = ____________________
```

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

### Step 3: Functions Practice

**Function that greets a person:**

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}

// Call the function with your name:
greet("____________________"); 
// Result: ____________________
```

**Function that adds two numbers:**

```javascript
function add(a, b) {
    return ____________; // What goes here?
}

add(10, 5); // Result: ____________
```

**Arrow function that squares a number:**

```javascript
const square = num => ____________; // What goes here?

square(7); // Result: ____________
```

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

### Step 4: Conditionals Practice

**Age category function:**

```javascript
function checkAge(age) {
    if (age >= 18) {
        return "____________"; // Adult
    } else if (age >= 13) {
        return "____________"; // Teenager
    } else {
        return "____________"; // Child
    }
}

checkAge(16); // Result: ____________
checkAge(20); // Result: ____________
checkAge(10); // Result: ____________
```

**Switch statement for grades:**

```javascript
function getLetterGrade(score) {
    switch(true) {
        case score >= 90:
            return "____________"; // A
        case score >= 80:
            return "____________"; // B
        case score >= 70:
            return "____________"; // C
        case score >= 60:
            return "____________"; // D
        default:
            return "____________"; // F
    }
}

getLetterGrade(85); // Result: ____________
```

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

### Step 5: Loops Practice

**For loop counting:**

```javascript
// Count from 1 to 5:
for (let i = ____; i <= ____; i++) {
    console.log(i);
}
```

**Loop through array:**

```javascript
const fruits = ["apple", "banana", "cherry"];

// Traditional for loop:
for (let i = 0; i < fruits.____; i++) {
    console.log(fruits[____]);
}

// Modern for...of loop:
for (const fruit of ____________) {
    console.log(fruit);
}
```

**Array methods:**

```javascript
const numbers = [2, 4, 6, 8, 10];

// Double each number:
const doubled = numbers.map(num => ____________);
// Result: ____________________

// Filter even numbers:
const evens = numbers.filter(num => num % 2 === ____);
// Result: ____________________

// Sum all numbers:
const sum = numbers.reduce((total, num) => total + ____, 0);
// Result: ____________
```

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

---

## Part 3: Code Snippet Collection

**Useful JavaScript Patterns:**

**1. Get user input:**
```javascript
const userInput = document.getElementById("inputId").value;
```

**2. Convert string to number:**
```javascript
const number = parseFloat(userInput);
const integer = parseInt(userInput);
```

**3. Check if value is a number:**
```javascript
if (isNaN(value)) {
    // Not a number
}
```

**4. Display output to page:**
```javascript
document.getElementById("outputId").innerHTML = "Your message";
```

**5. Template literal with variables:**
```javascript
const message = `Value is ${variable}`;
```

**6. Function with default parameter:**
```javascript
function greet(name = "Guest") {
    return `Hello, ${name}!`;
}
```

**Notes on when to use each pattern:**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

---

## Part 4: Independent Task Checklist

**Task: Build Interactive Calculator**

- [ ] Create HTML file with two number inputs
- [ ] Add operator selector (dropdown)
- [ ] Add "Calculate" button
- [ ] Create output div for result
- [ ] Write `calculate()` function
- [ ] Get values from inputs using `getElementById`
- [ ] Convert input strings to numbers using `parseFloat`
- [ ] Validate inputs (check if numbers)
- [ ] Use switch statement for operation selection
- [ ] Handle division by zero error
- [ ] Display result in output div
- [ ] Test all operations (+, -, *, /)
- [ ] Add styling to make it look good
- [ ] Add quiz section with answer checking

**Bonus Challenges:**
- [ ] Add more operations (power, square root)
- [ ] Create calculation history
- [ ] Add "Clear" button
- [ ] Style error messages differently

**My Progress Notes:**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

**Challenges I faced:**
_____________________________________________________________________
_____________________________________________________________________

**How I solved them:**
_____________________________________________________________________
_____________________________________________________________________

---

## Part 5: Self-Assessment Rubric

Rate yourself on each criterion (1 = Beginning, 2 = Developing, 3 = Proficient, 4 = Advanced):

| Criterion | 1 | 2 | 3 | 4 | Evidence |
|-----------|---|---|---|---|----------|
| **Variables & Data Types:** I can declare variables with appropriate keywords and work with different data types | ☐ | ☐ | ☐ | ☐ | |
| **Operators:** I can use arithmetic, comparison, and logical operators correctly | ☐ | ☐ | ☐ | ☐ | |
| **Functions:** I can write functions with parameters and return values | ☐ | ☐ | ☐ | ☐ | |
| **Conditionals:** I can use if/else and switch statements to control flow | ☐ | ☐ | ☐ | ☐ | |
| **Loops:** I can create loops and use array methods to repeat actions | ☐ | ☐ | ☐ | ☐ | |
| **Input Validation:** I check user input and handle errors appropriately | ☐ | ☐ | ☐ | ☐ | |
| **Debugging:** I use console.log and DevTools to find and fix errors | ☐ | ☐ | ☐ | ☐ | |
| **Code Organization:** My code is well-structured with clear function names | ☐ | ☐ | ☐ | ☐ | |

**Overall Self-Assessment:**

What I did well:
_____________________________________________________________________
_____________________________________________________________________

What I need to improve:
_____________________________________________________________________
_____________________________________________________________________

Questions I still have:
_____________________________________________________________________
_____________________________________________________________________

---

## Part 6: Reflection

**1. How does JavaScript differ from HTML and CSS?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

**2. What was the most challenging concept in this unit?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

**3. How could you use JavaScript in a real-world project?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

**4. What surprised you about programming in JavaScript?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

**5. What would you like to learn next about JavaScript?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

---

## Part 7: Vocabulary Glossary

Define these terms in your own words:

**Variable:** _________________________________________________________
_____________________________________________________________________

**Function:** _________________________________________________________
_____________________________________________________________________

**Parameter:** ________________________________________________________
_____________________________________________________________________

**Return Value:** _____________________________________________________
_____________________________________________________________________

**Conditional:** ______________________________________________________
_____________________________________________________________________

**Loop:** ____________________________________________________________
_____________________________________________________________________

**Array:** ___________________________________________________________
_____________________________________________________________________

**Object:** __________________________________________________________
_____________________________________________________________________

**Boolean:** _________________________________________________________
_____________________________________________________________________

**Operator:** ________________________________________________________
_____________________________________________________________________

**Template Literal:** _________________________________________________
_____________________________________________________________________

**Arrow Function:** ___________________________________________________
_____________________________________________________________________

---

## Part 8: Debugging Log

**Common Errors & Solutions:**

| Error | What Caused It | How I Fixed It |
|-------|----------------|----------------|
| Example: "undefined" in output | Forgot to convert input to number | Used `parseFloat()` |
| | | |
| | | |
| | | |
| | | |

**Console.log() Practice:**

When I want to check a variable value, I write:
```javascript
console.log("____________", variableName);
```

When I want to check if code reaches a certain point:
```javascript
console.log("____________");
```

---

## Part 9: Extension Activities

**Activity 1: Temperature Converter**
- Create inputs for Celsius and Fahrenheit
- Convert between temperature scales
- Formula: F = C × 9/5 + 32

**Activity 2: Grade Calculator**
- Input multiple quiz scores
- Calculate average
- Determine letter grade
- Display results

**Activity 3: Simple To-Do List**
- Input task name
- Add to array
- Display list on page
- (Hint: Use loops to display items)

**Which extension activity did I try?** ________________________________

**What I learned:** ___________________________________________________
_____________________________________________________________________

---

## Part 10: Peer Review

**Partner's Name:** ___________________________________________________

**What I learned from reviewing their code:**
_____________________________________________________________________
_____________________________________________________________________

**One thing they did really well:**
_____________________________________________________________________
_____________________________________________________________________

**One suggestion for improvement:**
_____________________________________________________________________
_____________________________________________________________________

**Partner's feedback for me:**
_____________________________________________________________________
_____________________________________________________________________

---

## Teacher Feedback Section

**Strengths:**
_____________________________________________________________________
_____________________________________________________________________

**Areas for Growth:**
_____________________________________________________________________
_____________________________________________________________________

**Next Steps:**
_____________________________________________________________________
_____________________________________________________________________

**Grade/Mark:** ____________  
**Teacher Signature:** ____________________ **Date:** ____________

---

## Resources & Links

**Official Documentation:**
- [MDN JavaScript Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
- [JavaScript.info](https://javascript.info/)

**Interactive Practice:**
- [freeCodeCamp JavaScript](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/)
- [Codecademy JavaScript](https://www.codecademy.com/learn/introduction-to-javascript)

**Related Tutorials:**
- Unit 4.1 Tutorial: JavaScript Basics (this unit)
- Unit 4.2 Preview: DOM Manipulation

---

**Notes to Self:**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

---

<!-- End of Student Workbook: Unit 4.1 -->
