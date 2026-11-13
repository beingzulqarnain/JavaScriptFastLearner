# Class 07: Events in JavaScript

## 📚 Overview

In this class, we learned about **Events in JavaScript** and how to make webpages interactive.

JavaScript events allow us to perform specific actions when users interact with a webpage.

For example:

- When a user clicks a button.
- When a user double-clicks an element.
- When a user enters text into an input field.
- When a user presses a keyboard key.
- When a user focuses on an input field.

At the end of the class, we also built a mini project to practice JavaScript events.

---

## 1. What Are Events in JavaScript?

An **event** is an action or occurrence that happens in a browser, usually because of user interaction.

JavaScript can detect these events and execute code in response.

### Real-Life Analogy

Imagine a doorbell at your home.

1. Someone presses the doorbell.
2. The doorbell detects the action.
3. It produces a sound.

Similarly, in JavaScript:

1. A user clicks a button.
2. JavaScript detects the click event.
3. A function executes.

### Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript Events</title>
  </head>
  <body>
    <button onclick="alert('Button Clicked!')">Click Me</button>
  </body>
</html>
```

**Output:**

When you click the button, a popup message appears:

```text
Button Clicked!
```

---

# 2. Types of Events in JavaScript

We learned about the following eight events:

1. `onclick`
2. `oncontextmenu`
3. `ondblclick`
4. `onfocus`
5. `oninput`
6. `onchange`
7. `onkeydown`
8. `onkeyup`

Let's understand each one.

---

## 2.1 onclick Event

The `onclick` event occurs when a user clicks an HTML element.

It is commonly used with buttons, links, images, and other webpage elements.

### Example

```html
<!DOCTYPE html>
<html>
  <body>
    <button onclick="showMessage()">Click Me</button>

    <script>
      function showMessage() {
        alert("Hello! Welcome to JavaScript.");
      }
    </script>
  </body>
</html>
```

**Output:**

When the user clicks the button, a popup displays:

```text
Hello! Welcome to JavaScript.
```

### Real-Life Example

Like pressing a doorbell, clicking a button triggers an action.

**Common Uses:**

- Submit buttons.
- Login buttons.
- Navigation buttons.
- Opening popup messages.

---

## 2.2 oncontextmenu Event

The `oncontextmenu` event occurs when a user opens the context menu, usually by right-clicking an element.

### Example

```html
<!DOCTYPE html>
<html>
  <body>
    <h2 oncontextmenu="showMessage()">Right-click on this heading.</h2>

    <script>
      function showMessage() {
        alert("You right-clicked!");
      }
    </script>
  </body>
</html>
```

**Output:**

When you right-click the heading, a popup message appears.

### Preventing the Default Context Menu

We can also prevent the browser's default right-click menu.

```html
<!DOCTYPE html>
<html>
  <body>
    <h2 oncontextmenu="return false;">Right-click on this heading.</h2>
  </body>
</html>
```

**Result:**

The browser's default context menu will not appear when you right-click the heading.

**Common Uses:**

- Custom right-click menus.
- Context-based actions.
- Custom interaction menus.

---

## 2.3 ondblclick Event

The `ondblclick` event occurs when a user double-clicks an HTML element.

### Example

```html
<!DOCTYPE html>
<html>
  <body>
    <h2 ondblclick="showMessage()">Double-click on this heading.</h2>

    <script>
      function showMessage() {
        alert("You double-clicked!");
      }
    </script>
  </body>
</html>
```

**Output:**

When you double-click the heading, a popup message appears:

```text
You double-clicked!
```

### Real-Life Example

Double-clicking an icon on a computer desktop to open an application.

**Common Uses:**

- Opening items.
- Editing text.
- Interactive elements.
- Selecting or activating content.

---

## 2.4 onfocus Event

The `onfocus` event occurs when an HTML element receives focus.

For example, when a user clicks inside an input field or navigates to it using the keyboard, the element receives focus.

### Example

```html
<!DOCTYPE html>
<html>
  <body>
    <input type="text" onfocus="showMessage()" placeholder="Enter your name" />

    <script>
      function showMessage() {
        console.log("Input field is focused!");
      }
    </script>
  </body>
</html>
```

**Output:**

When you click inside the input field, the browser console displays:

```text
Input field is focused!
```

### Real-Life Example

Imagine clicking inside a search box on Google. The search box becomes active and ready to receive your text.

**Common Uses:**

- Highlighting input fields.
- Displaying helpful instructions.
- Activating form fields.
- Improving user experience.

---

## 2.5 oninput Event

The `oninput` event occurs whenever the value of an input field changes because of user interaction.

It usually fires immediately when the user types, deletes, or pastes text.

### Example

```html
<!DOCTYPE html>
<html>
  <body>
    <input type="text" oninput="showInput()" placeholder="Type something" />

    <script>
      function showInput() {
        console.log("You are typing!");
      }
    </script>
  </body>
</html>
```

**Output:**

Whenever you enter or delete a character, the browser console displays:

```text
You are typing!
You are typing!
You are typing!
```

The message appears repeatedly as the input changes.

### Example: Displaying Live Input

```html
<!DOCTYPE html>
<html>
  <body>
    <h2>Live Text Preview</h2>

    <input
      type="text"
      id="username"
      oninput="displayText()"
      placeholder="Enter your name"
    />

    <p id="result"></p>

    <script>
      function displayText() {
        let inputValue = document.getElementById("username").value;

        document.getElementById("result").innerText = inputValue;
      }
    </script>
  </body>
</html>
```

**Output:**

If you type:

```text
Zulqarnain
```

The same text appears immediately below the input field.

**Common Uses:**

- Live search.
- Character counters.
- Live text previews.
- Form validation.
- Search suggestions.

---

## 2.6 onchange Event

The `onchange` event occurs when an element's value is changed and that change is committed.

For text inputs, this commonly happens when the user changes the value and then leaves the field.

For dropdowns, it generally fires when the user selects a different option.

### Example: Text Input

```html
<!DOCTYPE html>
<html>
  <body>
    <input type="text" onchange="showMessage()" placeholder="Enter your name" />

    <script>
      function showMessage() {
        alert("Your input has changed!");
      }
    </script>
  </body>
</html>
```

**Output:**

1. Enter your name.
2. Click outside the input field.
3. If the value changed, an alert appears.

### Example: Dropdown Menu

```html
<!DOCTYPE html>
<html>
  <body>
    <h2>Select Your Country</h2>

    <select onchange="showCountry(this.value)">
      <option value="">Select a country</option>
      <option value="Pakistan">Pakistan</option>
      <option value="United Kingdom">United Kingdom</option>
      <option value="United States">United States</option>
    </select>

    <script>
      function showCountry(country) {
        alert("You selected: " + country);
      }
    </script>
  </body>
</html>
```

**Output:**

When you select Pakistan, a popup displays:

```text
You selected: Pakistan
```

**Common Uses:**

- Dropdown menus.
- Form fields.
- Country selection.
- Updating settings.
- Detecting committed input changes.

---

## 2.7 onkeydown Event

The `onkeydown` event occurs when a user presses a key on the keyboard.

It triggers when the key is pressed down.

### Example

```html
<!DOCTYPE html>
<html>
  <body>
    <input type="text" onkeydown="showMessage()" placeholder="Press any key" />

    <script>
      function showMessage() {
        console.log("A key was pressed down!");
      }
    </script>
  </body>
</html>
```

**Output:**

Whenever you press a key inside the input field, the browser console displays:

```text
A key was pressed down!
```

### Example: Detecting Which Key Was Pressed

```html
<!DOCTYPE html>
<html>
  <body>
    <input type="text" onkeydown="showKey(event)" placeholder="Press any key" />

    <script>
      function showKey(event) {
        console.log("Key pressed:", event.key);
      }
    </script>
  </body>
</html>
```

**Example Output:**

If you press the letter A:

```text
Key pressed: a
```

**Common Uses:**

- Keyboard shortcuts.
- Detecting key presses.
- Keyboard navigation.
- Interactive games.

---

## 2.8 onkeyup Event

The `onkeyup` event occurs when a user releases a key after pressing it.

### Example

```html
<!DOCTYPE html>
<html>
  <body>
    <input
      type="text"
      onkeyup="showMessage()"
      placeholder="Press and release a key"
    />

    <script>
      function showMessage() {
        console.log("A key was released!");
      }
    </script>
  </body>
</html>
```

**Output:**

When you press and release a key, the browser console displays:

```text
A key was released!
```

### Example: Displaying the Released Key

```html
<!DOCTYPE html>
<html>
  <body>
    <input type="text" onkeyup="showKey(event)" placeholder="Type something" />

    <script>
      function showKey(event) {
        console.log("Released key:", event.key);
      }
    </script>
  </body>
</html>
```

**Example Output:**

If you type and release the letter A:

```text
Released key: a
```

**Common Uses:**

- Keyboard interactions.
- Detecting released keys.
- Keyboard-based controls.
- Updating information after a key is released.

---

# 3. Difference Between oninput and onchange

Both events are used to detect changes in input values, but they behave differently.

| oninput                                                  | onchange                                                    |
| -------------------------------------------------------- | ----------------------------------------------------------- |
| Fires immediately when the value changes.                | Fires when the change is committed.                         |
| Commonly triggers with every typed or deleted character. | For text fields, commonly triggers after leaving the field. |
| Useful for live updates.                                 | Useful for committed changes.                               |
| Commonly used for live search.                           | Commonly used for dropdown selections.                      |

### Example

Suppose you enter:

```text
JavaScript
```

With `oninput`, the event can fire as you type each character.

With `onchange`, the event generally fires after you finish changing the text and leave the input field.

---

# 4. Difference Between onkeydown and onkeyup

Both events are related to keyboard interaction.

| onkeydown                           | onkeyup                            |
| ----------------------------------- | ---------------------------------- |
| Fires when a key is pressed down.   | Fires when a key is released.      |
| Happens before the key is released. | Happens after the key is released. |
| Useful for detecting key presses.   | Useful for detecting key releases. |

### Easy Example

Imagine pressing the letter A on your keyboard.

1. You press the A key → `onkeydown`.
2. You release the A key → `onkeyup`.

**Remember:**

- `keydown` = Key pressed down.
- `keyup` = Key released up.

---

# 5. Quick Revision of All Eight Events

| Event           | Meaning                              | Example                      |
| --------------- | ------------------------------------ | ---------------------------- |
| `onclick`       | When an element is clicked.          | Clicking a button.           |
| `oncontextmenu` | When the context menu is requested.  | Right-clicking an element.   |
| `ondblclick`    | When an element is double-clicked.   | Double-clicking a heading.   |
| `onfocus`       | When an element receives focus.      | Clicking inside an input.    |
| `oninput`       | When an input value changes.         | Typing text.                 |
| `onchange`      | When an input change is committed.   | Selecting a dropdown option. |
| `onkeydown`     | When a keyboard key is pressed down. | Pressing Enter.              |
| `onkeyup`       | When a keyboard key is released.     | Releasing Enter.             |

---

# 6. Mini Project

At the end of this class, we built a mini project to practice the JavaScript events we learned.

The purpose of this project was to understand how JavaScript detects user interactions and responds to them.

### Concepts Practiced

- Mouse click events.
- Right-click events.
- Double-click events.
- Input focus events.
- Live input events.
- Change events.
- Keyboard keydown events.
- Keyboard keyup events.

**Project:** Mini project completed during the class.

_Add your project name, screenshots, and source code here to document your practical work._

---

# 7. Important Notes

1. Events make webpages interactive.
2. JavaScript can respond to mouse, keyboard, and input interactions.
3. Event handlers execute JavaScript code when their associated events occur.
4. The `event` object provides information about an event.
5. `event.key` helps identify which keyboard key was pressed or released.
6. `oninput` is useful for live updates.
7. `onchange` is useful for detecting committed changes.
8. `onkeydown` detects a key being pressed.
9. `onkeyup` detects a key being released.

### A Note About Modern JavaScript

In our class, we learned event handling using HTML attributes such as:

```html
<button onclick="showMessage()">Click Me</button>
```

Modern JavaScript projects commonly use `addEventListener()` instead.

Example:

```html
<button id="myButton">Click Me</button>

<script>
  let button = document.getElementById("myButton");

  button.addEventListener("click", function () {
    alert("Button clicked!");
  });
</script>
```

Both approaches can handle events, but `addEventListener()` is generally preferred in modern applications because it separates HTML structure from JavaScript behavior and supports multiple listeners.

---

# 8. Practice Questions

### Beginner Level

1. What are events in JavaScript?
2. Why do we use events?
3. What is the purpose of the `onclick` event?
4. What happens when we use `oncontextmenu`?
5. What is the difference between `onclick` and `ondblclick`?
6. What is the purpose of the `onfocus` event?
7. What is the difference between `oninput` and `onchange`?
8. What is the difference between `onkeydown` and `onkeyup`?
9. What is the event object?
10. What does `event.key` return?

### Coding Exercises

**Exercise 1: Click Event**

Create a button that displays an alert when clicked.

**Exercise 2: Double-Click Event**

Create a heading that displays a message when double-clicked.

**Exercise 3: Right-Click Event**

Create a paragraph that detects when the user right-clicks it.

**Exercise 4: Focus Event**

Create an input field that displays a message in the console when focused.

**Exercise 5: Input Event**

Create an input field that displays the entered text immediately below it.

**Exercise 6: Change Event**

Create a dropdown menu containing three countries. Display the selected country when the user changes the selection.

**Exercise 7: Keydown Event**

Create an input field that displays the name of the key pressed.

**Exercise 8: Keyup Event**

Create an input field that displays the name of the key released.

---

## 🎯 Class Goal

By the end of Class 07, you should be able to:

- Understand JavaScript events.
- Handle mouse interactions.
- Handle keyboard interactions.
- Detect changes in input fields.
- Use event handlers in HTML.
- Build interactive webpages.
- Apply JavaScript events in small projects.

**Keep practicing!** Events are an important part of JavaScript because they allow us to build interactive websites and real-world web applications.
