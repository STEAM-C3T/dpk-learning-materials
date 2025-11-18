# Student Workbook: Unit 4.2 — DOM Manipulation

**Module:** 04 — JavaScript Essentials  
**Unit:** 4.2 — DOM Manipulation  
**Name:** ____________________  
**Date:** ____________________

---

## Learning Objectives

By the end of this unit, I will be able to:

- [ ] Explain what the DOM (Document Object Model) is
- [ ] Select HTML elements using getElementById, querySelector, querySelectorAll
- [ ] Add event listeners to respond to clicks, typing, and other user actions
- [ ] Modify element content using textContent and innerHTML
- [ ] Change element styles and CSS classes dynamically
- [ ] Create new HTML elements with JavaScript
- [ ] Remove elements from the page
- [ ] Build an interactive to-do list application

---

## Part 1: Key Concepts Fill-In

**DOM Basics**

1. DOM stands for: ____________ ____________ ____________

2. The DOM represents a webpage as a ____________ of objects

3. The root of the DOM tree is the ____________ object

**Element Selection**

4. To select an element by ID, use: `document.____________("id")`

5. To select the first element matching a CSS selector, use: `document.____________("selector")`

6. To select ALL elements matching a selector, use: `document.____________("selector")`

7. The method that returns multiple elements gives you a: ____________

**Content Modification**

8. To change plain text in an element, set: `element.____________`

9. To change HTML content (including tags), set: `element.____________`

10. Which is safer for user-generated content? ____________

**Events**

11. To listen for user actions, use: `element.____________("event", function)`

12. A mouse click event is called: "____________"

13. An input field changing fires an: "____________" event

14. Pressing a key fires a: "____________" event

**Element Creation**

15. To create a new element, use: `document.____________("tagName")`

16. To add an element to the page, use: `parent.____________(element)`

17. To remove an element, use: `element.____________()` or `parent.____________(element)`

---

## Part 2: Guided Practice Notes

### Step 1: Element Selection Practice

**Select elements with different methods:**

```javascript
// Select by ID:
const heading = document.getElementById("____________");

// Select first button:
const firstButton = document.querySelector("____________");

// Select all paragraphs:
const allParagraphs = document.querySelectorAll("____________");

// How many paragraphs? 
console.log(allParagraphs.____________);
```

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

**Difference between querySelector and querySelectorAll:**
_____________________________________________________________________
_____________________________________________________________________

---

### Step 2: Content Modification Practice

**Change text content:**

```javascript
const element = document.getElementById("demo");

// Plain text (safe):
element.____________ = "Hello World";

// HTML content (can include tags):
element.____________ = "<strong>Bold</strong> text";
```

**Security Question:** Why shouldn't we use innerHTML with user input?
_____________________________________________________________________
_____________________________________________________________________

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

---

### Step 3: Style Manipulation Practice

**Change styles two ways:**

```javascript
const box = document.getElementById("box");

// Method 1: Inline styles
box.style.backgroundColor = "____________";
box.style.width = "____________px";
box.style.padding = "____________px";

// Method 2: CSS classes
box.classList.____________("class-name");  // Add class
box.classList.____________("class-name");  // Remove class
box.classList.____________("class-name");  // Toggle class
```

**Which method is better for multiple style changes?** ____________

**Why?** ______________________________________________________________
_____________________________________________________________________

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

---

### Step 4: Event Handling Practice

**Add event listeners:**

```javascript
const button = document.getElementById("my-button");

// Click event:
button.addEventListener("____________", function() {
    console.log("Button clicked!");
});

// Input event:
const input = document.getElementById("text-input");
input.addEventListener("____________", function() {
    console.log("User typed:", input.value);
});

// Enter key event:
input.addEventListener("keydown", function(event) {
    if (event.key === "____________") {
        console.log("Enter pressed!");
    }
});
```

**Event object practice:**

When an event fires, JavaScript provides an **event object**. What information can we get from it?

- Event type: event.____________
- Target element: event.____________
- Key pressed: event.____________

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

---

### Step 5: Creating Elements Practice

**Build elements step-by-step:**

```javascript
// Step 1: Create element
const newDiv = document.____________("div");

// Step 2: Add content
newDiv.textContent = "____________";

// Step 3: Add class
newDiv.className = "____________";

// Step 4: Add styles
newDiv.style.backgroundColor = "____________";
newDiv.style.padding = "____________px";

// Step 5: Add to page
const container = document.getElementById("container");
container.____________(newDiv);
```

**Important:** If you forget Step 5, what happens? ____________________
_____________________________________________________________________

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

---

### Step 6: Removing Elements Practice

**Two ways to remove elements:**

```javascript
const element = document.getElementById("to-remove");

// Modern way:
element.____________();

// Traditional way:
const parent = element.parentNode;
parent.____________(element);
```

**Which method is simpler?** ____________

**What I learned:**
_____________________________________________________________________
_____________________________________________________________________

---

## Part 3: Code Snippet Collection

**Useful DOM Patterns:**

**1. Select element:**
```javascript
const element = document.getElementById("id");
const element = document.querySelector(".class");
```

**2. Change content:**
```javascript
element.textContent = "Plain text";
element.innerHTML = "<strong>HTML</strong>";
```

**3. Add event listener:**
```javascript
element.addEventListener("click", function() {
    // code
});
```

**4. Create and add element:**
```javascript
const newEl = document.createElement("div");
newEl.textContent = "Content";
parent.appendChild(newEl);
```

**5. Toggle class:**
```javascript
element.classList.toggle("class-name");
```

**6. Check if element has class:**
```javascript
if (element.classList.contains("class-name")) {
    // code
}
```

**Notes on when to use each pattern:**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

---

## Part 4: Independent Task Checklist

**Task: Build Interactive To-Do List**

**HTML Setup:**
- [ ] Create input field for task text
- [ ] Create "Add Task" button
- [ ] Create empty `<ul>` for task list
- [ ] Create stats section (total, completed, remaining)
- [ ] Add CSS styling

**JavaScript Functionality:**
- [ ] Select all necessary elements
- [ ] Create `addTask()` function
- [ ] Validate input (check not empty)
- [ ] Create new `<li>` element for task
- [ ] Add task text to element
- [ ] Create delete button for task
- [ ] Add click event to mark task complete
- [ ] Add click event to delete button
- [ ] Append task to list
- [ ] Clear input field after adding
- [ ] Create `updateStats()` function
- [ ] Count total, completed, remaining tasks
- [ ] Update stats display
- [ ] Add Enter key support

**Bonus Challenges:**
- [ ] Add task editing (double-click to edit)
- [ ] Add "Clear All" button
- [ ] Add task priority (high/medium/low) with colors
- [ ] Save tasks to localStorage

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
| **Element Selection:** I can select elements using various methods | ☐ | ☐ | ☐ | ☐ | |
| **Content Manipulation:** I can change element text and HTML | ☐ | ☐ | ☐ | ☐ | |
| **Style Manipulation:** I can modify styles and classes dynamically | ☐ | ☐ | ☐ | ☐ | |
| **Event Handling:** I can respond to clicks, input, and keyboard events | ☐ | ☐ | ☐ | ☐ | |
| **Element Creation:** I can create new elements and add to DOM | ☐ | ☐ | ☐ | ☐ | |
| **Element Removal:** I can remove elements from the page | ☐ | ☐ | ☐ | ☐ | |
| **Application Building:** I combined all concepts into working to-do list | ☐ | ☐ | ☐ | ☐ | |
| **Debugging:** I can use DevTools to inspect and debug DOM issues | ☐ | ☐ | ☐ | ☐ | |

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

**1. How does the DOM connect JavaScript to HTML?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

**2. What was the most challenging part of DOM manipulation?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

**3. How could you use DOM manipulation in a personal project?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

**4. What's the difference between selecting one element vs. all elements?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

**5. Why is event handling important for web applications?**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

---

## Part 7: Vocabulary Glossary

Define these terms in your own words:

**DOM (Document Object Model):** _____________________________________
_____________________________________________________________________

**Element:** _________________________________________________________
_____________________________________________________________________

**Event:** ___________________________________________________________
_____________________________________________________________________

**Event Listener:** ___________________________________________________
_____________________________________________________________________

**Node:** ____________________________________________________________
_____________________________________________________________________

**NodeList:** ________________________________________________________
_____________________________________________________________________

**textContent:** _____________________________________________________
_____________________________________________________________________

**innerHTML:** _______________________________________________________
_____________________________________________________________________

**appendChild:** _____________________________________________________
_____________________________________________________________________

**classList:** _______________________________________________________
_____________________________________________________________________

**querySelector:** ___________________________________________________
_____________________________________________________________________

**addEventListener:** ________________________________________________
_____________________________________________________________________

---

## Part 8: Debugging Log

**Common Errors & Solutions:**

| Error | What Caused It | How I Fixed It |
|-------|----------------|----------------|
| Example: "Cannot read property of null" | Element ID misspelled | Checked spelling, fixed ID |
| | | |
| | | |
| | | |
| | | |

**DevTools Practice:**

**Elements Tab:** Shows live DOM, applied styles, event listeners  
**Console Tab:** Shows errors, logs, warnings  
**Sources Tab:** Allows breakpoints for debugging

**How I used DevTools to debug:**
_____________________________________________________________________
_____________________________________________________________________

---

## Part 9: DOM Tree Visualization

**Draw the DOM tree for this HTML:**

```html
<body>
    <h1 id="title">My Page</h1>
    <div class="container">
        <p>Paragraph 1</p>
        <p>Paragraph 2</p>
    </div>
</body>
```

**Your DOM Tree Drawing:**

```
document
  └── 







```

**Parent-Child Relationships:**

- The parent of `<p>` is: ____________
- The children of `<div>` are: ____________ and ____________
- The sibling of the first `<p>` is: ____________

---

## Part 10: Event Flow Practice

**For this code, trace what happens:**

```javascript
const button = document.getElementById("btn");
const output = document.getElementById("output");

button.addEventListener("click", function() {
    output.textContent = "Clicked!";
});
```

**Step-by-step execution:**

1. User clicks button
2. Browser fires ____________ event
3. Event listener ____________ is called
4. Function selects ____________ element
5. Element's ____________ property is set to "Clicked!"
6. Page updates to show ____________

---

## Part 11: Extension Activities

**Activity 1: Color Picker**
- Create color swatches (divs with different colors)
- Click swatch to change page background
- Display selected color name

**Activity 2: Character Counter**
- Create textarea input
- Show live character count as user types
- Show remaining characters (max 280, like Twitter)
- Change color when limit approached

**Activity 3: Image Gallery**
- Display thumbnail images
- Click thumbnail to show large version
- Add previous/next buttons
- Implement keyboard navigation (arrow keys)

**Which extension activity did I try?** ________________________________

**What I learned:** ___________________________________________________
_____________________________________________________________________

---

## Part 12: Peer Review

**Partner's Name:** ___________________________________________________

**What I learned from reviewing their to-do list:**
_____________________________________________________________________
_____________________________________________________________________

**One creative feature they added:**
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
- [MDN: Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- [MDN: Event Reference](https://developer.mozilla.org/en-US/docs/Web/Events)

**Interactive Practice:**
- [JavaScript30](https://javascript30.com/) (30 vanilla JS projects)
- [DOM Challenges](https://www.w3schools.com/js/js_htmldom.asp)

**Related Tutorials:**
- Unit 4.2 Tutorial: DOM Manipulation (this unit)
- Next: Module 05 — Data Visualization

---

**Notes to Self:**
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________
_____________________________________________________________________

---

<!-- End of Student Workbook: Unit 4.2 -->
