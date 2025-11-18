# Tutorial: Unit 4.2 — DOM Manipulation

**Module:** 04 — JavaScript Essentials  
**Unit:** 4.2 — DOM Manipulation  
**Estimated Time:** 60–75 minutes  
**Author:** Digital Proficiency Kit Team  
**Last Updated:** 2025-11-18

---

## Overview

**What You Will Learn:**
In this tutorial, you will learn to select HTML elements, respond to user events, and dynamically modify webpage content and styles using JavaScript.

**What You Will Build:**
An interactive to-do list application with add, complete, and delete functionality—demonstrating practical DOM manipulation techniques.

**Learning Outcomes:**

- Understand what the DOM (Document Object Model) is
- Select HTML elements using querySelector and querySelectorAll
- Add event listeners to respond to user actions
- Modify element content, attributes, and styles
- Create and remove HTML elements dynamically
- Build interactive web applications

---

## Prerequisites

Before starting this tutorial, you should:

- [ ] Have completed Unit 4.1 (JavaScript Basics) or be comfortable with functions, variables, and conditionals
- [ ] Understand HTML structure and CSS basics
- [ ] Know how to use browser DevTools

**Tools Required:**

- Text editor
- Modern web browser with DevTools

---

## Concept Overview

**What is the DOM?**

The **Document Object Model (DOM)** is a programming interface for HTML documents. It represents the page structure as a tree of objects that JavaScript can access and manipulate.

**Visual Representation:**

```
document
  └── html
       ├── head
       │    ├── title
       │    └── style
       └── body
            ├── h1
            ├── p
            └── button
```

**Key DOM Concepts:**

- **Nodes:** Every element, text, attribute is a node
- **Element Selection:** Finding specific elements in the DOM tree
- **Event Handling:** Responding to user actions (clicks, typing, etc.)
- **Dynamic Updates:** Changing content without page reload

**Why DOM Manipulation Matters:**

Modern web applications feel responsive because JavaScript updates the page dynamically without requiring full page refreshes.

---

## Step-by-Step Guide

### Step 1: Set Up DOM Project

**Objective:** Create HTML structure for DOM manipulation practice.

**Instructions:**

Create `dom-manipulation.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>DOM Manipulation</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        max-width: 800px;
        margin: 50px auto;
        padding: 20px;
        background-color: #f5f5f5;
      }
      .container {
        background-color: white;
        padding: 30px;
        border-radius: 8px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
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
      button.danger {
        background-color: #e74c3c;
      }
      button.danger:hover {
        background-color: #c0392b;
      }
      #output {
        background-color: #ecf0f1;
        padding: 15px;
        margin: 15px 0;
        border-radius: 4px;
        min-height: 50px;
      }
      input {
        padding: 8px;
        border: 1px solid #ddd;
        border-radius: 4px;
        margin: 5px;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1 id="main-heading">DOM Manipulation Practice</h1>
      <p id="intro">Learn to control webpages with JavaScript!</p>

      <div id="output"></div>

      <h2>Element Selection</h2>
      <button id="select-btn">Select Element</button>
      <button id="select-all-btn">Select All Paragraphs</button>

      <h2>Content Modification</h2>
      <p class="demo-text">This text will change.</p>
      <button id="change-text-btn">Change Text</button>
      <button id="change-html-btn">Change HTML</button>

      <h2>Style Manipulation</h2>
      <div
        id="style-box"
        style="width: 200px; height: 100px; background-color: lightblue; margin: 10px;"
      >
        Style Box
      </div>
      <button id="change-color-btn">Change Color</button>
      <button id="toggle-class-btn">Toggle Class</button>

      <h2>Event Handling</h2>
      <button id="click-btn">Click Me!</button>
      <button id="double-click-btn">Double Click Me!</button>
      <input type="text" id="text-input" placeholder="Type something..." />

      <h2>Dynamic Elements</h2>
      <button id="add-element-btn">Add Element</button>
      <button id="remove-element-btn" class="danger">
        Remove Last Element
      </button>
      <div id="element-container"></div>
    </div>

    <script src="dom-script.js"></script>
  </body>
</html>
```

Create empty `dom-script.js` file.

**Expected Result:**

- Page displays with styled sections
- Buttons and input fields visible
- External JavaScript file linked

**Why This Step:**
Structured HTML provides targets for DOM manipulation practice.

**Quick Self-Check:**

- [ ] Page loads without errors
- [ ] All buttons visible
- [ ] Console shows no 404 errors

---

### Step 2: Selecting Elements

**Objective:** Learn different methods to select HTML elements.

**Instructions:**

Add to `dom-script.js`:

```javascript
// Selecting Single Elements
const heading = document.getElementById("main-heading");
console.log("Heading:", heading);

const intro = document.querySelector("#intro");
console.log("Intro paragraph:", intro);

const firstButton = document.querySelector("button");
console.log("First button:", firstButton);

// Selecting Multiple Elements
const allButtons = document.querySelectorAll("button");
console.log("All buttons:", allButtons);
console.log("Number of buttons:", allButtons.length);

const allParagraphs = document.querySelectorAll("p");
console.log("All paragraphs:", allParagraphs);

// Select Button Functionality
document.getElementById("select-btn").addEventListener("click", function () {
  const output = document.getElementById("output");
  output.innerHTML = `
        <h3>Selected Element:</h3>
        <p><strong>Heading text:</strong> ${heading.textContent}</p>
        <p><strong>Heading tag:</strong> ${heading.tagName}</p>
    `;
});

document
  .getElementById("select-all-btn")
  .addEventListener("click", function () {
    const output = document.getElementById("output");
    let html = "<h3>All Paragraphs:</h3><ul>";

    allParagraphs.forEach((paragraph, index) => {
      html += `<li>Paragraph ${index + 1}: ${paragraph.textContent}</li>`;
    });

    html += "</ul>";
    output.innerHTML = html;
  });
```

**Expected Result:**

- Console shows selected elements
- "Select Element" button displays heading info
- "Select All Paragraphs" button lists all paragraphs

**Why This Step:**
Element selection is the foundation of DOM manipulation—you must select elements before modifying them.

**Selection Methods:**

| Method               | Use Case                              | Returns                |
| -------------------- | ------------------------------------- | ---------------------- |
| `getElementById()`   | Select by ID (unique)                 | Single element or null |
| `querySelector()`    | Select first match (any CSS selector) | Single element or null |
| `querySelectorAll()` | Select all matches                    | NodeList (array-like)  |

**Important:**

- `querySelectorAll()` returns a **NodeList**, not an array (but has forEach)
- IDs use `#`, classes use `.`, tags use tag name
- `querySelector()` can use any CSS selector: `.class`, `#id`, `tag`, `[attribute]`

**Common Pitfall:**
⚠️ **Watch Out:** Trying to manipulate element before it exists in DOM.  
✅ **Tip:** Place `<script>` at end of body, or use DOMContentLoaded event.

**Quick Self-Check:**

- [ ] Console shows selected elements
- [ ] Buttons display element information
- [ ] Can select both single and multiple elements

---

### Step 3: Modifying Content

**Objective:** Change text and HTML content of elements.

**Instructions:**

Add to `dom-script.js`:

```javascript
// Change Text Content
document
  .getElementById("change-text-btn")
  .addEventListener("click", function () {
    const demoText = document.querySelector(".demo-text");
    demoText.textContent = "The text has changed!";

    const output = document.getElementById("output");
    output.textContent = "Text changed successfully!";
  });

// Change HTML Content
document
  .getElementById("change-html-btn")
  .addEventListener("click", function () {
    const demoText = document.querySelector(".demo-text");
    demoText.innerHTML = "<strong>Bold text</strong> with <em>emphasis</em>!";

    const output = document.getElementById("output");
    output.innerHTML =
      "<p style='color: green;'>✓ HTML changed successfully!</p>";
  });
```

**Expected Result:**

- "Change Text" button updates paragraph text
- "Change HTML" button adds HTML formatting
- Output area shows success messages

**Why This Step:**
Dynamic content updates create interactive experiences without page refreshes.

**textContent vs. innerHTML:**

```javascript
// textContent: Plain text only (safer, faster)
element.textContent = "Hello <strong>World</strong>";
// Displays: Hello <strong>World</strong>

// innerHTML: Can include HTML tags (powerful but XSS risk)
element.innerHTML = "Hello <strong>World</strong>";
// Displays: Hello World (World is bold)
```

**Security Note:**
⚠️ **Never use innerHTML with user input** (risk of Cross-Site Scripting attacks).  
✅ **Use textContent for user-generated content.**

**Quick Self-Check:**

- [ ] Text changes when button clicked
- [ ] HTML formatting displays correctly
- [ ] Understand textContent vs. innerHTML difference

---

### Step 4: Manipulating Styles

**Objective:** Change element styles and CSS classes dynamically.

**Instructions:**

Add to `dom-script.js`:

```javascript
// Change Inline Styles
document
  .getElementById("change-color-btn")
  .addEventListener("click", function () {
    const styleBox = document.getElementById("style-box");

    // Generate random color
    const randomColor = "#" + Math.floor(Math.random() * 16777215).toString(16);

    styleBox.style.backgroundColor = randomColor;
    styleBox.style.transform = "scale(1.1)";
    styleBox.style.transition = "all 0.3s ease";

    const output = document.getElementById("output");
    output.innerHTML = `<p>Box color changed to: ${randomColor}</p>`;
  });

// Toggle CSS Class
// First, add this CSS class to your <style> section in HTML:
// .highlighted {
//     background-color: yellow !important;
//     border: 3px solid orange;
//     font-weight: bold;
// }

document
  .getElementById("toggle-class-btn")
  .addEventListener("click", function () {
    const styleBox = document.getElementById("style-box");
    styleBox.classList.toggle("highlighted");

    const output = document.getElementById("output");
    if (styleBox.classList.contains("highlighted")) {
      output.textContent = "Class added!";
    } else {
      output.textContent = "Class removed!";
    }
  });
```

**Update HTML `<style>` section** (add this class):

```css
.highlighted {
  background-color: yellow !important;
  border: 3px solid orange;
  font-weight: bold;
}
```

**Expected Result:**

- "Change Color" button changes box color randomly
- "Toggle Class" button adds/removes highlighting

**Why This Step:**
Style manipulation creates visual feedback and dynamic user interfaces.

**classList Methods:**

```javascript
element.classList.add("class-name"); // Add class
element.classList.remove("class-name"); // Remove class
element.classList.toggle("class-name"); // Toggle (add if absent, remove if present)
element.classList.contains("class-name"); // Check if class exists
```

**Inline Styles vs. Classes:**

- **Inline styles:** Quick, specific changes (element.style.property)
- **Classes:** Preferred for multiple style changes (reusable, maintainable)

**Common Pitfall:**
⚠️ **Watch Out:** CSS property names in JavaScript use camelCase.  
✅ **CSS:** `background-color`, **JavaScript:** `backgroundColor`

**Quick Self-Check:**

- [ ] Box color changes on click
- [ ] Highlight class toggles on/off
- [ ] Understand inline styles vs. classes

---

### Step 5: Event Handling

**Objective:** Respond to different user interactions.

**Instructions:**

Add to `dom-script.js`:

```javascript
// Click Event
let clickCount = 0;
document.getElementById("click-btn").addEventListener("click", function () {
  clickCount++;
  const output = document.getElementById("output");
  output.innerHTML = `<p>Button clicked ${clickCount} time(s)!</p>`;
});

// Double Click Event
document
  .getElementById("double-click-btn")
  .addEventListener("dblclick", function () {
    alert("You double-clicked! 🎉");
  });

// Input Event (fires on every keystroke)
const textInput = document.getElementById("text-input");
textInput.addEventListener("input", function () {
  const output = document.getElementById("output");
  output.innerHTML = `
        <h3>You typed:</h3>
        <p>${textInput.value}</p>
        <p>Character count: ${textInput.value.length}</p>
    `;
});

// Keyboard Events
textInput.addEventListener("keydown", function (event) {
  if (event.key === "Enter") {
    alert(`You pressed Enter! Input value: ${textInput.value}`);
  }
});
```

**Expected Result:**

- Click button tracks number of clicks
- Double-click shows alert
- Text input displays typed content in real-time
- Enter key triggers alert

**Why This Step:**
Event handling makes webpages interactive and responsive to user actions.

**Common Event Types:**

| Event       | Trigger                        |
| ----------- | ------------------------------ |
| `click`     | Mouse click                    |
| `dblclick`  | Double click                   |
| `input`     | Input value changes            |
| `change`    | Input loses focus after change |
| `keydown`   | Key is pressed                 |
| `keyup`     | Key is released                |
| `mouseover` | Mouse enters element           |
| `mouseout`  | Mouse leaves element           |
| `submit`    | Form is submitted              |

**Event Object:**

Every event handler receives an **event object** with details:

```javascript
element.addEventListener("click", function (event) {
  console.log("Event type:", event.type);
  console.log("Target element:", event.target);
  console.log("Mouse position:", event.clientX, event.clientY);
});
```

**Common Pitfall:**
⚠️ **Watch Out:** Forgetting to prevent default behavior (e.g., form submission).  
✅ **Tip:** Use `event.preventDefault()` when needed.

**Quick Self-Check:**

- [ ] Click counter works
- [ ] Double-click triggers alert
- [ ] Input event fires on typing
- [ ] Enter key detected

---

### Step 6: Creating and Removing Elements

**Objective:** Dynamically add and remove HTML elements.

**Instructions:**

Add to `dom-script.js`:

```javascript
// Add Element
let elementCount = 0;
document
  .getElementById("add-element-btn")
  .addEventListener("click", function () {
    elementCount++;

    // Create new element
    const newElement = document.createElement("div");
    newElement.className = "dynamic-element";
    newElement.innerHTML = `
        <p><strong>Element ${elementCount}</strong></p>
        <p>Created at: ${new Date().toLocaleTimeString()}</p>
    `;

    // Style the element
    newElement.style.backgroundColor = "#e8f4f8";
    newElement.style.padding = "15px";
    newElement.style.margin = "10px 0";
    newElement.style.borderRadius = "4px";
    newElement.style.border = "1px solid #3498db";

    // Add to container
    const container = document.getElementById("element-container");
    container.appendChild(newElement);

    // Update output
    const output = document.getElementById("output");
    output.innerHTML = `<p style="color: green;">✓ Element ${elementCount} added!</p>`;
  });

// Remove Last Element
document
  .getElementById("remove-element-btn")
  .addEventListener("click", function () {
    const container = document.getElementById("element-container");
    const lastElement = container.lastElementChild;

    if (lastElement) {
      container.removeChild(lastElement);
      elementCount--;

      const output = document.getElementById("output");
      output.innerHTML = `<p style="color: red;">✗ Last element removed!</p>`;
    } else {
      const output = document.getElementById("output");
      output.innerHTML = `<p style="color: orange;">⚠ No elements to remove!</p>`;
    }
  });
```

**Expected Result:**

- "Add Element" creates new div with timestamp
- "Remove Last Element" deletes most recent addition
- Elements styled and numbered correctly

**Why This Step:**
Dynamic element creation is essential for applications like to-do lists, shopping carts, and social media feeds.

**DOM Manipulation Methods:**

```javascript
// Create
const element = document.createElement("div");

// Add content
element.textContent = "Text";
element.innerHTML = "<p>HTML</p>";

// Add attributes
element.id = "my-id";
element.className = "my-class";
element.setAttribute("data-value", "123");

// Add to DOM
parent.appendChild(element); // Add as last child
parent.insertBefore(element, ref); // Add before reference

// Remove from DOM
parent.removeChild(element);
element.remove(); // Modern way
```

**Common Pitfall:**
⚠️ **Watch Out:** Creating element but forgetting to add it to DOM.  
✅ **Tip:** Always use appendChild or insertBefore to make element visible.

**Quick Self-Check:**

- [ ] New elements appear when added
- [ ] Elements removed correctly
- [ ] Empty container shows warning message

---

### Step 7: Build Interactive To-Do List

**Objective:** Combine all DOM concepts into functional application.

**Instructions:**

Create new file `todo.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>To-Do List</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        max-width: 600px;
        margin: 50px auto;
        padding: 20px;
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        min-height: 100vh;
      }
      .container {
        background-color: white;
        padding: 30px;
        border-radius: 10px;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
      }
      h1 {
        text-align: center;
        color: #667eea;
      }
      .input-section {
        display: flex;
        gap: 10px;
        margin-bottom: 20px;
      }
      #task-input {
        flex: 1;
        padding: 12px;
        border: 2px solid #ddd;
        border-radius: 5px;
        font-size: 16px;
      }
      #add-btn {
        padding: 12px 24px;
        background-color: #667eea;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 16px;
        font-weight: bold;
      }
      #add-btn:hover {
        background-color: #5568d3;
      }
      #task-list {
        list-style: none;
        padding: 0;
      }
      .task-item {
        background-color: #f8f9fa;
        padding: 15px;
        margin-bottom: 10px;
        border-radius: 5px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        transition: all 0.3s ease;
      }
      .task-item:hover {
        background-color: #e9ecef;
        transform: translateX(5px);
      }
      .task-item.completed {
        text-decoration: line-through;
        opacity: 0.6;
        background-color: #d4edda;
      }
      .task-text {
        flex: 1;
        cursor: pointer;
      }
      .delete-btn {
        background-color: #e74c3c;
        color: white;
        border: none;
        padding: 6px 12px;
        border-radius: 4px;
        cursor: pointer;
      }
      .delete-btn:hover {
        background-color: #c0392b;
      }
      .stats {
        text-align: center;
        margin-top: 20px;
        padding: 15px;
        background-color: #f8f9fa;
        border-radius: 5px;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>📝 My To-Do List</h1>

      <div class="input-section">
        <input type="text" id="task-input" placeholder="Enter a new task..." />
        <button id="add-btn">Add Task</button>
      </div>

      <ul id="task-list"></ul>

      <div class="stats">
        <p>
          <strong>Total:</strong> <span id="total-count">0</span> |
          <strong>Completed:</strong> <span id="completed-count">0</span> |
          <strong>Remaining:</strong> <span id="remaining-count">0</span>
        </p>
      </div>
    </div>

    <script src="todo.js"></script>
  </body>
</html>
```

Create `todo.js`:

```javascript
// Select elements
const taskInput = document.getElementById("task-input");
const addBtn = document.getElementById("add-btn");
const taskList = document.getElementById("task-list");

// Counters
let totalCount = 0;
let completedCount = 0;

// Add task function
function addTask() {
  const taskText = taskInput.value.trim();

  // Validate input
  if (taskText === "") {
    alert("Please enter a task!");
    return;
  }

  // Create task item
  const taskItem = document.createElement("li");
  taskItem.className = "task-item";

  // Create task text span
  const taskSpan = document.createElement("span");
  taskSpan.className = "task-text";
  taskSpan.textContent = taskText;

  // Toggle complete on click
  taskSpan.addEventListener("click", function () {
    taskItem.classList.toggle("completed");
    updateStats();
  });

  // Create delete button
  const deleteBtn = document.createElement("button");
  deleteBtn.className = "delete-btn";
  deleteBtn.textContent = "Delete";

  // Delete task on click
  deleteBtn.addEventListener("click", function () {
    taskItem.remove();
    updateStats();
  });

  // Assemble task item
  taskItem.appendChild(taskSpan);
  taskItem.appendChild(deleteBtn);

  // Add to list
  taskList.appendChild(taskItem);

  // Clear input
  taskInput.value = "";
  taskInput.focus();

  // Update statistics
  updateStats();
}

// Update statistics
function updateStats() {
  const allTasks = document.querySelectorAll(".task-item");
  const completedTasks = document.querySelectorAll(".task-item.completed");

  totalCount = allTasks.length;
  completedCount = completedTasks.length;
  const remainingCount = totalCount - completedCount;

  document.getElementById("total-count").textContent = totalCount;
  document.getElementById("completed-count").textContent = completedCount;
  document.getElementById("remaining-count").textContent = remainingCount;
}

// Event Listeners
addBtn.addEventListener("click", addTask);

// Add task with Enter key
taskInput.addEventListener("keydown", function (event) {
  if (event.key === "Enter") {
    addTask();
  }
});

// Initial focus
taskInput.focus();
```

**Expected Result:**

- Enter task and click "Add Task" (or press Enter)
- Task appears in list
- Click task text to mark complete
- Click "Delete" to remove task
- Statistics update automatically

**Why This Step:**
To-do list demonstrates real-world application combining element selection, creation, events, and styling.

**Key Features:**

- ✅ Add tasks
- ✅ Mark complete (click task text)
- ✅ Delete tasks
- ✅ Live statistics
- ✅ Keyboard support (Enter to add)
- ✅ Input validation
- ✅ Smooth animations

**Common Pitfall:**
⚠️ **Watch Out:** Event listeners on dynamically created elements must be added when element is created.  
✅ **Tip:** Attach event listeners immediately after creating element.

**Quick Self-Check:**

- [ ] Can add tasks
- [ ] Can complete tasks
- [ ] Can delete tasks
- [ ] Statistics update correctly
- [ ] Enter key works

---

## Debugging Section

**Scenario 1: "Cannot read property of null"**

- **Possible Cause:** Trying to select element that doesn't exist
- **Solution:**
  - Check element ID/class spelling
  - Ensure script runs after HTML loads
  - Use console.log to verify element selected

**Scenario 2: Event listener doesn't work**

- **Possible Causes:**
  - Element not selected correctly
  - Event type misspelled ("clik" instead of "click")
  - Function not defined
- **Solution:**
  - Console.log element to verify selection
  - Check event type spelling
  - Ensure function exists before addEventListener

**Scenario 3: New elements don't appear**

- **Possible Cause:** Element created but not added to DOM
- **Solution:**
  - Verify appendChild or insertBefore call
  - Check parent element exists
  - Use console.log to trace execution

**Scenario 4: Styles don't apply**

- **Possible Causes:**
  - CSS property name incorrect (JavaScript uses camelCase)
  - CSS specificity conflict (inline styles vs. classes)
  - Typo in property value
- **Solution:**
  - Use DevTools Elements tab to inspect applied styles
  - Check JavaScript console for errors
  - Use !important in CSS (sparingly) to override

**General Debugging Tips:**

- **Use console.log extensively:** Log variables, function calls, event triggers
- **Inspect Elements:** DevTools shows live DOM state, styles, event listeners
- **Breakpoints:** Use DevTools debugger to pause execution
- **Check Console:** Errors show line numbers and stack traces
- **Event Listener tab:** DevTools shows all attached event listeners

---

## Consolidated Key Concepts

**1. Element Selection**

```javascript
document.getElementById("id");
document.querySelector(".class");
document.querySelectorAll("tag");
```

**2. Content Manipulation**

```javascript
element.textContent = "text";
element.innerHTML = "<p>HTML</p>";
```

**3. Style Manipulation**

```javascript
element.style.property = "value";
element.classList.add("class-name");
element.classList.toggle("class-name");
```

**4. Event Handling**

```javascript
element.addEventListener("event", function () {
  // code
});
```

**5. Creating Elements**

```javascript
const el = document.createElement("tag");
parent.appendChild(el);
```

**6. Removing Elements**

```javascript
parent.removeChild(element);
element.remove();
```

---

## Practice Variations

**Variation 1: Enhanced To-Do List**

- Add task priority (high, medium, low) with color coding
- Implement task editing (double-click to edit)
- Add "Clear Completed" button
- Save to localStorage (persist across page reloads)

**Variation 2: Interactive Quiz**

- Create multiple-choice questions
- Check answers and show score
- Highlight correct/incorrect answers
- Add timer

**Variation 3: Image Gallery**

- Display thumbnail images
- Click to view full size (modal/lightbox)
- Add previous/next navigation
- Implement slideshow

---

## Reflection Prompts

1. **How does DOM manipulation make websites more interactive?**

   - [Space for student response]

2. **When would you use textContent vs. innerHTML?**

   - [Space for student response]

3. **How could you improve the to-do list application?**
   - [Space for student response]

---

## Further Reading

**Official Documentation:**

- [MDN: Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- [MDN: Event Reference](https://developer.mozilla.org/en-US/docs/Web/Events)

**Related Tutorials:**

- Previous: Unit 4.1 — JavaScript Basics
- Next: Module 05 — Data Visualization

**Advanced Topics:**

- Event delegation for dynamic elements
- MutationObserver for DOM change detection
- Shadow DOM and Web Components
- Performance optimization for large DOM trees

---

## Accessibility Considerations

**This Tutorial Emphasized:**

- ✅ Keyboard support (Enter key to add tasks)
- ✅ Focus management (auto-focus input)
- ✅ Clear visual feedback (hover states, completed styling)

**DOM & Accessibility:**

- Always ensure keyboard navigation works
- Use ARIA attributes for dynamic content (`aria-live`, `role`)
- Announce changes to screen readers
- Maintain focus order when adding/removing elements

**Improvements for Production:**

```html
<button aria-label="Delete task">Delete</button>
<div role="alert" id="status"></div>
```

---

## Metadata

**Module:** 04 — JavaScript Essentials  
**Unit:** 4.2 — DOM Manipulation  
**Author:** Digital Proficiency Kit Team  
**Contributors:** N/A  
**License:** CC BY-SA 4.0  
**Repository:** [dpk-learning-materials](https://github.com/STEAM-C3T/dpk-learning-materials)

---

<!-- End of Unit 4.2 Tutorial -->
