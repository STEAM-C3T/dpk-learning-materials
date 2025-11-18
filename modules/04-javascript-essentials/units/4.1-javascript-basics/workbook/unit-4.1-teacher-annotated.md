# Teacher-Annotated Workbook: Unit 4.1 — JavaScript Basics

**Module:** 04 — JavaScript Essentials  
**Unit:** 4.1 — JavaScript Basics  
**Purpose:** Teaching guide with answer keys, strategies, and assessment support  
**Last Updated:** 2025-11-18

---

## Teaching Notes

**Estimated Time:** 60–75 minutes (may extend to 90 minutes with extensions)

**Preparation:**

- [ ] Ensure all students have text editors installed
- [ ] Verify browser DevTools functionality on student computers
- [ ] Prepare example files on shared drive or repository
- [ ] Test code examples before class
- [ ] Have console screenshots ready for demonstration

**Learning Progression:**

1. **Introduction (10 min):** What is JavaScript? Demo interactive website
2. **Variables & Types (12-15 min):** Declare variables, explore data types
3. **Operators (8-10 min):** Arithmetic, comparison, logical operations
4. **Functions (12-15 min):** Write reusable code blocks
5. **Conditionals (10-12 min):** Make decisions with if/else, switch
6. **Loops (10-12 min):** Repeat actions, process arrays
7. **Calculator Project (15-20 min):** Apply all concepts
8. **Reflection (5 min):** Self-assessment and discussion

**Key Teaching Points:**

- JavaScript is **different** from HTML/CSS: it's programming, not markup/styling
- Emphasize **console.log()** as primary debugging tool
- Students will make syntax errors—normalize this as part of learning
- Use **live coding** to demonstrate concepts
- Encourage **experimentation** in browser console

---

## Part 1: Key Concepts Answer Key

**Variables and Data Types**

1. `let`
2. `const`
3. strings, quotes (`"` or `'`)
4. booleans
5. array, square `[]`
6. object, curly `{}`

**Operators**

7. `+`
8. `===`
9. `&&`
10. `%`

**Functions**

11. function
12. return
13. `a + b` (or any expression)

**Control Flow**

14. if (or if/else)
15. switch
16. for
17. for...of (or forEach)

**Teaching Tip:** Have students create a "cheat sheet" with these syntax patterns for reference during coding.

---

## Part 2: Guided Practice Teaching Tips

### Step 1: Variables Setup (12-15 min)

**Teaching Strategy:**

- **Start with analogy:** Variables are like labeled boxes that store information
- **Live code** variable declarations in console
- **Show errors:** Try changing a `const` to demonstrate immutability
- **Type checking:** Use `typeof` operator to show data types

**Example Demonstration:**

```javascript
// In browser console
let age = 16;
console.log(age);           // 16
console.log(typeof age);    // "number"

age = 17;                   // Works (let)
console.log(age);           // 17

const birthYear = 2008;
birthYear = 2009;           // ERROR! (const cannot change)
```

**Expected Student Answers:**

```javascript
let myName = "Student Name";
const birthYear = 2008; // (or their actual birth year)
let favoriteColors = ["blue", "green", "red"];
let me = {
    name: "Student Name",
    age: 16,
    school: "School Name"
};
```

**Common Student Errors:**

- Forgetting quotes around strings
- Using `var` instead of `let`/`const`
- Trying to change a `const`
- Missing commas in arrays/objects

**Differentiation:**

- **Scaffold:** Provide template with blanks to fill in
- **Challenge:** Have students create nested objects (e.g., object with array property)

**Formative Check:** "Show me a variable that can change and one that cannot."

---

### Step 2: Operators Practice (8-10 min)

**Teaching Strategy:**

- **Calculator comparison:** Relate operators to calculator buttons
- **Demonstrate === vs ==:** Show type coercion issues with `==`
- **Modulus confusion:** Explain remainder with clock analogy (13 % 12 = 1 o'clock)

**Expected Results:**

- `x + y` = **19**
- `x - y` = **11**
- `x * y` = **60**
- `x / y` = **3.75**
- `x % y` = **3** (remainder when 15 ÷ 4)
- `x > y` = **true**
- `x === y` = **false**

**Template Literal Example:**

```javascript
let age = 16;
let message = `I am ${age} years old`;
// message = "I am 16 years old"
```

**Teaching Tip:** Emphasize backticks (`` ` ``) for template literals, not quotes.

**Common Pitfall:**

⚠️ **Student uses `=` in condition:**
```javascript
if (x = 5) { ... }  // WRONG: assigns 5 to x
if (x === 5) { ... } // CORRECT: compares
```

**Quick Activity:** "Calculate your age in days using JavaScript operators."

---

### Step 3: Functions Practice (12-15 min)

**Teaching Strategy:**

- **Function analogy:** Like a recipe—inputs (ingredients), process (steps), output (dish)
- **Live demonstration:** Write function, call it multiple times with different arguments
- **Return vs. log:** Clarify difference between `return` and `console.log()`

**Expected Answers:**

```javascript
greet("Student Name"); 
// Result: "Hello, Student Name!"

function add(a, b) {
    return a + b; // Correct answer
}
add(10, 5); // Result: 15

const square = num => num * num; // Correct answer
square(7); // Result: 49
```

**Common Student Errors:**

- Forgetting `return` statement
- Calling function without parentheses: `greet` vs. `greet()`
- Not understanding parameters vs. arguments

**Teaching Tip:** Use "parameter" for definition, "argument" for actual value passed.

```javascript
function greet(name) { // name is parameter
    return `Hello, ${name}!`;
}
greet("Alex"); // "Alex" is argument
```

**Differentiation:**

- **Struggling:** Start with no-parameter functions
- **Advanced:** Introduce default parameters, rest parameters

**Formative Check:** "Write a function that takes your name and age and returns a greeting."

---

### Step 4: Conditionals Practice (10-12 min)

**Teaching Strategy:**

- **Decision tree visual:** Draw flowchart showing if/else paths
- **Real-world examples:** "If it's raining, bring umbrella, else leave it home"
- **Switch for menus:** Show when switch is cleaner than multiple if/else

**Expected Answers:**

```javascript
checkAge(16); // Result: "Teenager"
checkAge(20); // Result: "Adult"
checkAge(10); // Result: "Child"

function getLetterGrade(score) {
    switch(true) {
        case score >= 90:
            return "A";
        case score >= 80:
            return "B";
        case score >= 70:
            return "C";
        case score >= 60:
            return "D";
        default:
            return "F";
    }
}
getLetterGrade(85); // Result: "B"
```

**Common Student Errors:**

- Using assignment `=` instead of comparison `===`
- Forgetting `break` in switch (causes fall-through)
- Logical errors in condition order (checking >= 70 before >= 90)

**Teaching Tip:** Always test **edge cases**: exactly 18, exactly 13, etc.

**Quick Activity:** "Write a function that determines if a number is positive, negative, or zero."

---

### Step 5: Loops Practice (10-12 min)

**Teaching Strategy:**

- **Repetition analogy:** Like doing homework problems 1-10
- **Live code:** Start with simple counting, then array iteration
- **Array methods:** Introduce as "modern" approach to loops

**Expected Answers:**

```javascript
// Count from 1 to 5:
for (let i = 1; i <= 5; i++) {
    console.log(i);
}

// Loop through array:
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}

for (const fruit of fruits) {
    console.log(fruit);
}

// Array methods:
const doubled = numbers.map(num => num * 2);
// Result: [4, 8, 12, 16, 20]

const evens = numbers.filter(num => num % 2 === 0);
// Result: [2, 4, 6, 8, 10] (all are even)

const sum = numbers.reduce((total, num) => total + num, 0);
// Result: 30
```

**Common Student Errors:**

- Off-by-one errors: `i <= length` vs. `i < length`
- Infinite loops from never-changing condition
- Confusing `i` (index) with `array[i]` (value)

**Warning Sign:** If student browser freezes, likely infinite loop. Teach **Ctrl+Shift+Esc** (Windows) or **Cmd+Option+Esc** (Mac) to force quit browser.

**Teaching Tip:** Draw table showing loop variable changes:

| Iteration | i | i < 5? | Action |
|-----------|---|--------|--------|
| 1         | 0 | true   | Run    |
| 2         | 1 | true   | Run    |
| ...       | ..| ...    | ...    |
| 6         | 5 | false  | Stop   |

**Formative Check:** "Write a loop that prints even numbers from 2 to 10."

---

## Part 3: Code Snippets Teaching Notes

**When to Introduce Each Pattern:**

1. **Get user input:** Introduce in calculator project
2. **Convert to number:** Critical before any math operations
3. **Check if number:** Use `isNaN()` for input validation
4. **Display output:** Alternative to console.log for user-facing output
5. **Template literal:** Modern, cleaner than concatenation
6. **Default parameter:** Advanced, introduce if time permits

**Demonstration Idea:**

Show the problem that each pattern solves:

```javascript
// Problem: Input is string
const input = "5";
const result = input + 3; // "53" (string concatenation, not addition!)

// Solution: Convert to number
const number = parseFloat(input);
const result = number + 3; // 8 (correct!)
```

---

## Part 4: Independent Task Assessment

**Task: Build Interactive Calculator**

**Assessment Criteria:**

| Criterion | Emerging (1-2) | Proficient (3) | Advanced (4) | Points |
|-----------|----------------|----------------|--------------|--------|
| **Functionality** | Calculator performs some operations | All operations work correctly | Handles errors, validates input | __/4 |
| **Code Quality** | Some working code, many errors | Clean, organized code | Well-commented, follows best practices | __/4 |
| **Input Validation** | No validation | Checks for valid numbers | Handles all edge cases (division by zero, empty input) | __/4 |
| **User Experience** | Basic functionality | Clear interface, good feedback | Styled, intuitive, excellent error messages | __/4 |

**Total:** __/16

**What "Good" Looks Like:**

- All four operations (+, -, ×, ÷) work correctly
- Error message for invalid input
- Division by zero prevented
- Clear, styled output
- Code uses appropriate variable declarations (`const`, `let`)
- Functions are well-named
- Comments explain logic

**Scaffolding for Struggling Students:**

1. Provide HTML template with all elements already created
2. Give step-by-step function outline with comments:
   ```javascript
   function calculate() {
       // 1. Get values from inputs
       
       // 2. Convert to numbers
       
       // 3. Check if valid
       
       // 4. Perform operation
       
       // 5. Display result
   }
   ```
3. Pair program with stronger student
4. Break into mini-tasks: "First, just get the addition working"

**Extension for Advanced Students:**

- Add square root, power operations
- Implement calculation history (array of past results)
- Create keyboard shortcuts (Enter to calculate)
- Build scientific calculator with trigonometric functions

---

## Part 5: Self-Assessment Rubric Grading Guide

**How to Use Student Self-Assessments:**

1. Students complete rubric honestly
2. Teacher reviews and compares with own assessment
3. Discuss discrepancies (self-assessment too high/low)
4. Use as formative feedback, not summative grade

**Red Flags:**

- Student rates all 4s but code doesn't work → Overconfidence, needs recalibration
- Student rates all 1s but code is excellent → Underconfidence, needs encouragement
- Student leaves evidence column blank → Doesn't understand how to self-assess

**Teaching Response:**

- **Overconfident:** Show specific examples where code fails, ask "How could we improve this?"
- **Underconfident:** Highlight what IS working, celebrate small wins
- **Uncertain:** Model self-assessment: "I'd rate myself 3 on functions because I can write them, but I'm still learning arrow functions"

---

## Part 6: Reflection Expected Responses

**1. How does JavaScript differ from HTML and CSS?**

**Strong Answer:** "HTML is structure (what content), CSS is style (how it looks), JavaScript is behavior (what it does). JavaScript is programming—it has logic, variables, and can respond to user actions."

**Weak Answer:** "JavaScript makes things work."

**Teaching Tip:** Use analogy: HTML = skeleton, CSS = skin/clothes, JavaScript = muscles/brain.

---

**2. What was the most challenging concept?**

**Common Responses:**

- "Functions and return values" → Very common, abstract concept
- "Loops" → Off-by-one errors, iteration logic
- "Syntax" → Semicolons, brackets, quotes
- "Debugging" → Finding errors

**Teaching Response:** Normalize difficulty, provide additional resources, offer office hours.

---

**3. How could you use JavaScript in a real-world project?**

**Strong Answers:**

- "Make a quiz website for studying"
- "Create a game"
- "Build a tip calculator app"
- "Interactive survey or form"

**Teaching Tip:** Share examples of real student projects from previous years.

---

**4. What surprised you about programming?**

**Common Surprises:**

- "How specific you have to be" → Syntax precision
- "How powerful it is" → Small code, big results
- "How hard debugging is" → Finding errors
- "How creative you can be" → Many solutions to one problem

---

**5. What would you like to learn next?**

**Use this to inform Unit 4.2 and beyond:**

- "More interactive features" → Perfect, that's Unit 4.2 (DOM manipulation)
- "Games" → Extension projects
- "Mobile apps" → Possible advanced topic
- "Animations" → CSS animations + JavaScript

---

## Part 7: Vocabulary Assessment

**Check for Understanding:**

| Term | Minimum Acceptable Definition |
|------|------------------------------|
| **Variable** | Container/storage for data |
| **Function** | Reusable block of code |
| **Parameter** | Input to a function |
| **Return Value** | Output from a function |
| **Conditional** | Decision-making code (if/else) |
| **Loop** | Code that repeats |
| **Array** | List of values |
| **Object** | Collection of key-value pairs |
| **Boolean** | True or false value |
| **Operator** | Symbol for operation (+, -, ===, etc.) |
| **Template Literal** | String with embedded variables using backticks |
| **Arrow Function** | Modern function syntax with => |

**Red Flag:** If student can't define basic terms (variable, function), they likely need review before moving forward.

---

## Part 8: Debugging Log Teaching Notes

**Use This Section:**

- During class when students encounter errors
- As documentation of problem-solving process
- To identify common errors across class

**Common Errors Table (Expand as Needed):**

| Error | Cause | Fix | Prevention |
|-------|-------|-----|------------|
| `undefined` | Variable not set or wrong name | Check spelling, initialization | Use console.log to check values |
| `NaN` | Math on non-number | Use parseFloat/parseInt | Validate input before calculation |
| `Uncaught ReferenceError` | Variable/function doesn't exist | Check name spelling, scope | Declare before use |
| `Unexpected token` | Syntax error (missing bracket, quote) | Check matching pairs | Use editor with syntax highlighting |
| `Cannot read property of undefined` | Accessing property of non-existent object | Check if object exists first | Use optional chaining (?.) |
| Nothing happens on click | Function name mismatch or not defined | Check onclick matches function name | Use addEventListener instead |

**Teaching Moment:** When error occurs, **don't immediately fix it**. Ask class:
1. "What does this error message tell us?"
2. "Where should we look?"
3. "How can we test our fix?"

---

## Part 9: Extension Activities Teaching Notes

**Purpose:** Differentiation for fast finishers and enrichment.

### Activity 1: Temperature Converter

**Learning Goal:** Apply formula in code, bidirectional conversion

**Scaffolding:**
```javascript
function celsiusToFahrenheit(c) {
    return c * 9/5 + 32;
}

function fahrenheitToCelsius(f) {
    return (f - 32) * 5/9;
}
```

**Challenge:** Add Kelvin conversion.

---

### Activity 2: Grade Calculator

**Learning Goal:** Arrays, loops, average calculation

**Scaffolding:**
```javascript
function calculateAverage(scores) {
    let sum = 0;
    for (const score of scores) {
        sum += score;
    }
    return sum / scores.length;
}

// Or modern way:
const calculateAverage = scores => 
    scores.reduce((sum, score) => sum + score, 0) / scores.length;
```

---

### Activity 3: Simple To-Do List

**Learning Goal:** Arrays, DOM manipulation (preview of Unit 4.2)

**Note:** This bridges to next unit. May be better as homework.

---

## Part 10: Peer Review Facilitation

**How to Run Peer Review:**

1. **Pair students** (mix skill levels when possible)
2. **Set clear expectations:**
   - Be kind and constructive
   - Find one strength, one improvement
   - Ask questions if you don't understand code
3. **Provide sentence starters:**
   - "I like how you..."
   - "One thing that confused me was..."
   - "Have you considered...?"
4. **Circulate** and listen to conversations
5. **Debrief:** What did you learn from reviewing someone else's code?

**Benefits:**

- Improves code reading skills
- Normalizes different approaches
- Builds communication skills
- Often helps reviewer understand concepts better

---

## Differentiation Strategies

**For English Language Learners (ELL):**

- Provide vocabulary list with translations
- Use visual diagrams for concepts (flowcharts for conditionals, loops)
- Allow use of comments in native language
- Pair with bilingual buddy
- Provide code templates with detailed comments

**For Students with IEPs:**

- **Extended time:** Allow 90 minutes instead of 60-75
- **Reduce output:** Focus on 2-3 core concepts instead of all
- **Provide code templates:** Fill-in-the-blank rather than write from scratch
- **Assistive technology:** Screen readers, speech-to-text for comments
- **Chunking:** Break calculator project into 4 mini-milestones

**For Gifted/Advanced Students:**

- **Open-ended challenges:** "Make the calculator do something we haven't discussed"
- **Optimization:** "Can you solve this with fewer lines of code?"
- **Teaching role:** Pair with struggling student as tutor
- **Extension projects:** Scientific calculator, game, animation
- **Research:** Explore ES6+ features (destructuring, spread operator)

**For Students with Visual Impairments:**

- Ensure screen reader compatibility
- Use high-contrast code editor themes
- Provide text-based feedback (console.log) rather than visual-only
- Test with keyboard-only navigation

---

## Formative Assessment Checkpoints

**Throughout Lesson:**

1. **After Variables (Step 1):** "Quick check: Declare a constant for pi (3.14159)"
2. **After Operators (Step 2):** "Calculate: What is 17 % 5?"
3. **After Functions (Step 3):** "Write a function that doubles a number"
4. **After Conditionals (Step 4):** "What does this code output: `console.log(5 > 3 ? 'yes' : 'no')`?"
5. **After Loops (Step 5):** "Write a loop that counts down from 10 to 1"

**Expected Results:**

1. `const pi = 3.14159;`
2. `2` (remainder)
3. `function double(n) { return n * 2; }` or `const double = n => n * 2;`
4. `'yes'`
5. `for (let i = 10; i >= 1; i--) { console.log(i); }`

**If Many Students Struggle:** Re-teach concept with different approach before moving on.

---

## Common Misconceptions & How to Address

**Misconception 1: "JavaScript and Java are the same"**

**Reality:** Completely different languages.

**Teaching Response:** "Despite the name, JavaScript and Java are as different as 'car' and 'carpet.'"

---

**Misconception 2: "Variables are permanent"**

**Reality:** Variables exist only while program runs, lost on refresh.

**Teaching Response:** Demonstrate by refreshing page, show variables are gone. Introduce localStorage (preview of future topic).

---

**Misconception 3: "Functions run automatically"**

**Reality:** Functions must be called to execute.

**Teaching Response:**
```javascript
function greet() { console.log("Hello"); }
// Nothing happens yet...

greet(); // NOW it runs
```

---

**Misconception 4: "console.log() is the same as return"**

**Reality:** console.log() displays, return gives back value.

**Teaching Response:**
```javascript
function add(a, b) {
    console.log(a + b); // Shows in console
    // No return—function gives back nothing (undefined)
}

let result = add(5, 3); // result is undefined

function addCorrect(a, b) {
    return a + b; // Gives back value
}

let resultCorrect = addCorrect(5, 3); // result is 8
```

---

## Assessment Rubric (Summative)

**Calculator Project Rubric:**

| Criterion | Weight | Emerging (1-2) | Proficient (3) | Advanced (4) | Score |
|-----------|--------|----------------|----------------|--------------|-------|
| **Functionality** | 30% | Some operations work | All basic operations work | All operations + error handling | __/4 |
| **Code Quality** | 25% | Code works but messy | Clean, organized code | Well-commented, best practices | __/4 |
| **Variables & Data Types** | 15% | Uses variables inconsistently | Uses const/let appropriately | Chooses correct data types | __/4 |
| **Functions** | 15% | Functions have errors | Functions work correctly | Reusable, well-named functions | __/4 |
| **Validation & Errors** | 10% | No error handling | Checks for valid numbers | Comprehensive error messages | __/4 |
| **User Experience** | 5% | Minimal interface | Clear, functional UI | Polished, intuitive design | __/4 |

**Total: __/24 points**

**Grade Conversion:**
- 22-24: A (90-100%)
- 19-21: B (80-89%)
- 16-18: C (70-79%)
- 13-15: D (60-69%)
- 0-12: F (<60%)

---

## Lesson Closure & Next Steps

**Lesson Closure (5 min):**

1. **Gallery walk:** Students leave calculator open, walk around to see others' work
2. **Share-out:** 2-3 students demo their calculator
3. **Key takeaways:** "What's one thing you learned today?"
4. **Preview Unit 4.2:** "Next time: Make webpages respond to clicks, input, mouse movement—true interactivity!"

**Homework:**

- Complete calculator if unfinished
- Try one extension activity
- Read ahead: What is the DOM? (prepare for Unit 4.2)

**For Next Lesson (Unit 4.2):**

- Students should have solid grasp of variables, functions, conditionals
- If many struggled today, consider review day before Unit 4.2
- Unit 4.2 builds directly on these concepts

---

## Teacher Reflection Questions

**After Teaching This Unit:**

1. **What went well?**
2. **What would I change next time?**
3. **Which students need additional support?**
4. **Which students are ready for advanced challenges?**
5. **Were time estimates accurate?**
6. **What resources were most helpful?**
7. **What additional examples should I create?**

---

## Resources for Teachers

**Professional Development:**

- [JavaScript for Educators (freeCodeCamp)](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/)
- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [JavaScript.info](https://javascript.info/)

**Classroom Management:**

- **Prevent "Help Vampires":** Require students to try 3 things before asking (Check console, re-read instructions, ask peer)
- **Debugging Protocol:** 1) What did you expect? 2) What actually happened? 3) What have you tried?
- **Code Review Norms:** Establish respectful feedback culture

**Demo & Live Coding Tips:**

- **Go slow:** Students need time to type along
- **Make intentional errors:** Show debugging process
- **Use large font:** 18pt+ for projector
- **Explain as you type:** Verbalize thought process
- **Save examples:** Share working code afterward

---

## Troubleshooting Guide

**"Script doesn't load"**

- Check script tag placement (end of body)
- Verify file path is correct
- Check for typos in filename
- Use browser Network tab to see 404 errors

**"Nothing happens when I click button"**

- Check function name matches onclick attribute
- Verify function is defined before being called
- Look for JavaScript errors in console

**"Calculator shows NaN"**

- Input values not converted to numbers
- Missing `parseFloat()` or `parseInt()`
- Check if input is empty

**"Page freezes"**

- Likely infinite loop
- Force quit browser
- Check loop condition and increment

**"Code works on my computer but not students'"**

- Browser compatibility (use modern browsers)
- JavaScript disabled in browser settings
- File path issues (case sensitivity on some systems)

---

## Appendix: Live Demonstration Ideas

**Demo 1: Console Math**

Open browser console and do live calculations:
```javascript
5 + 3
"Hello" + " " + "World"
Math.sqrt(16)
Math.random()
```

**Impact:** Shows JavaScript is a calculator on steroids.

---

**Demo 2: Variable Mystery**

```javascript
let x = 10;
let y = x;
x = 20;
console.log(y); // Still 10! Why?
```

**Teaching Point:** Variables hold values, not references (for primitives).

---

**Demo 3: Broken Calculator**

Show calculator with intentional bugs:
- No parseFloat → string concatenation
- No error handling → crashes on bad input
- Missing return → undefined

Then **fix each bug live**, showing thought process.

---

## Digital Competence Mapping (DigComp 2.2)

**This Unit Addresses:**

- **3.1 Developing Digital Content:** Writing code to create interactive content
- **3.2 Integrating and Re-elaborating:** Combining HTML, CSS, JavaScript
- **5.2 Identifying Needs and Technological Responses:** Choosing appropriate programming constructs
- **5.3 Creatively Using Technologies:** Solving problems with code
- **5.4 Identifying Digital Competence Gaps:** Self-assessment, reflection on learning

---

**End of Teacher-Annotated Workbook: Unit 4.1 — JavaScript Basics**
