# Class 09: Arrow Functions, `this` Keyword and HTML Element Properties

## Topics Covered

1. Arrow Functions
2. The `this` Keyword
3. Passing HTML Elements to JavaScript Functions
4. The `innerHTML` Property
5. The `name` Property
6. The `value` Property

---

# 1. Arrow Functions in JavaScript

An **Arrow Function** is a shorter way of writing a function in JavaScript. It was introduced in ES6 (ECMAScript 2015).

Arrow functions use the arrow symbol `=>` instead of the traditional `function` keyword.

### 1.1 Regular Function

A regular function is declared using the `function` keyword.

```javascript
function greet() {
  console.log("Hello, World!");
}

greet();
```

**Output:**

```text
Hello, World!
```

### 1.2 Arrow Function

The same function can be written using arrow function syntax.

```javascript
const greet = () => {
  console.log("Hello, World!");
};

greet();
```

**Output:**

```text
Hello, World!
```

Both functions perform the same task, but the arrow function has shorter syntax.

### 1.3 Arrow Function with Parameters

Arrow functions can also accept parameters.

```javascript
const greet = (name) => {
  console.log("Hello " + name);
};

greet("Zulqarnain");
```

**Output:**

```text
Hello Zulqarnain
```

Here:

- `name` is a parameter.
- `"Zulqarnain"` is an argument.
- The function uses the argument to display a greeting.

### 1.4 Arrow Function with a Single Parameter

If an arrow function has only one parameter, parentheses are optional.

```javascript
const greet = (name) => {
  console.log("Hello " + name);
};

greet("Ali");
```

**Output:**

```text
Hello Ali
```

### 1.5 Arrow Function with an Implicit Return

If the function contains only one expression, we can remove the curly braces `{}` and the `return` keyword.

```javascript
const add = (a, b) => a + b;

console.log(add(10, 20));
```

**Output:**

```text
30
```

### Arrow Function Syntax

```javascript
const functionName = (parameters) => {
  // Statements
};
```

**Important Points:**

- Arrow functions use the `=>` symbol.
- They provide shorter function syntax.
- They can accept parameters and return values.
- Arrow functions do not have their own `this` binding. They inherit `this` from their surrounding scope.

---

# 2. The `this` Keyword in JavaScript

The `this` keyword refers to an object.

Its value depends on the context in which it is used and how a function is called.

Think of `this` as a way of referring to the current object.

### 2.1 Using `this` Inside an Object

```javascript
const student = {
  name: "Zulqarnain",
  age: 26,

  showInfo: function () {
    console.log(this.name);
    console.log(this.age);
  },
};

student.showInfo();
```

**Output:**

```text
Zulqarnain
26
```

**Explanation:**

- `this.name` accesses the `name` property of the `student` object.
- `this.age` accesses the `age` property of the `student` object.
- Here, `this` refers to the object that calls the method.

### 2.2 Using `this` in an HTML Event

We can use `this` in an HTML event to refer to the HTML element that triggered the event.

**Example:**

```html
<button name="myButton" onclick="hello(this)">Click Me</button>

<script>
  function hello(btn) {
    console.log(btn.name);
  }
</script>
```

**Output:**

```text
myButton
```

**Explanation:**

1. The user clicks the button.
2. `this` refers to the clicked button element.
3. `this` is passed to the `hello()` function.
4. The `btn` parameter receives the button element.
5. `btn.name` accesses the button's name.

**Remember:** In this example, `this` represents the HTML button element.

---

# 3. Passing HTML Elements to JavaScript Functions

JavaScript allows us to pass an HTML element to a function.

We can use `this` to pass the element that triggers an event.

### Syntax

```html
<button onclick="hello(this)">Click Me</button>
```

In the example:

- `onclick` is an HTML event attribute.
- `this` refers to the clicked HTML element.
- `hello(this)` passes that element to the JavaScript function.
- `btn` receives the element as a parameter.

### Example

```html
<button onclick="hello(this)">Submit</button>

<script>
  function hello(btn) {
    console.log(btn);
  }
</script>
```

**Result:**

When the button is clicked, the browser console displays the button element.

We can then access its properties using the `btn` parameter.

---

# 4. The `innerHTML` Property

The `innerHTML` property is used to get or change the HTML content inside an HTML element.

In simple words, it allows JavaScript to read or modify what is written inside an HTML element.

### 4.1 Getting HTML Content Using `innerHTML`

```html
<button onclick="hello(this)">Click Me</button>

<script>
  function hello(btn) {
    console.log(btn.innerHTML);
  }
</script>
```

**Output:**

```text
Click Me
```

**Explanation:**

- `this` passes the clicked button to the function.
- `btn` receives the button element.
- `btn.innerHTML` retrieves the content inside the button.

### 4.2 Changing HTML Content Using `innerHTML`

```html
<button onclick="hello(this)">Click Me</button>

<script>
  function hello(btn) {
    btn.innerHTML = "Button Clicked!";
  }
</script>
```

**Result:**

Before clicking:

```text
Click Me
```

After clicking:

```text
Button Clicked!
```

JavaScript changes the button's content when the user clicks it.

**Important:** `innerHTML` can read and insert HTML markup. When displaying plain text, prefer `textContent` because it does not interpret the text as HTML.

---

# 5. The `name` Property

The `name` property is used to access the name of an HTML element that supports the `name` attribute.

### Example

```html
<button name="submitButton" onclick="hello(this)">Submit</button>

<script>
  function hello(btn) {
    console.log(btn.name);
  }
</script>
```

**Output:**

```text
submitButton
```

**Explanation:**

- `name="submitButton"` assigns a name to the button.
- `this` passes the button element to the function.
- `btn.name` retrieves the button's name.

---

# 6. The `value` Property

The `value` property is commonly used to get or change the current value of form elements, such as input fields and buttons.

### 6.1 Getting an Input Value

```html
<input type="text" value="Hello JavaScript" oninput="showValue(this)" />

<script>
  function showValue(btn) {
    console.log(btn.value);
  }
</script>
```

**Output:**

```text
Hello JavaScript
```

When the user types into the input field, the current value is displayed in the console.

**Explanation:**

- `this` passes the input element.
- `btn` receives the input element.
- `btn.value` retrieves its current value.

### 6.2 Getting a Button Value

```html
<input type="button" value="Click Me" onclick="hello(this)" />

<script>
  function hello(btn) {
    console.log(btn.value);
  }
</script>
```

**Output:**

```text
Click Me
```

Here, `btn.value` retrieves the button's value.

---

# 7. Difference Between `innerHTML`, `name`, and `value`

These three properties are used to access different information from HTML elements.

| Property    | Purpose                                            | Example         |
| ----------- | -------------------------------------------------- | --------------- |
| `innerHTML` | Gets or changes the HTML content inside an element | `btn.innerHTML` |
| `name`      | Gets the element's name                            | `btn.name`      |
| `value`     | Gets or changes the value of a form element        | `btn.value`     |

### Complete Example

```html
<button name="myButton" value="Click Me" onclick="hello(this)">
  Submit Button
</button>

<script>
  function hello(btn) {
    console.log(btn.name);
    console.log(btn.innerHTML);
    console.log(btn.value);
  }
</script>
```

**Output:**

```text
myButton
Submit Button
Click Me
```

---

# 8. Quick Revision

| Concept        | Explanation                                                  |
| -------------- | ------------------------------------------------------------ |
| Arrow Function | A shorter way to write a JavaScript function                 |
| `=>`           | Symbol used to create an arrow function                      |
| `this`         | Refers to an object or HTML element depending on its context |
| `onclick`      | Event triggered when an element is clicked                   |
| `innerHTML`    | Gets or changes the HTML content inside an element           |
| `name`         | Accesses the name of an HTML element                         |
| `value`        | Gets or changes the value of a form element                  |
| `btn`          | A parameter receiving the HTML element passed through `this` |

---

# 9. Practice Questions

### Conceptual Questions

1. What is an Arrow Function in JavaScript?
2. Which symbol is used to create an Arrow Function?
3. What is the difference between a regular function and an Arrow Function?
4. What is the purpose of the `this` keyword?
5. What does `this` refer to when used in an HTML button's `onclick` event?
6. What is the purpose of `innerHTML`?
7. What is the difference between `innerHTML` and `value`?
8. What is the purpose of the `name` property?
9. How can we pass an HTML element to a JavaScript function?
10. What is the difference between parameters and arguments?

### Practical Tasks

1. Create an arrow function that displays your name in the console.
2. Create an arrow function that adds two numbers.
3. Create an HTML button and display its name when clicked.
4. Create a button that changes its text using `innerHTML`.
5. Create an input field and display its current value in the console.
6. Create a button with `name`, `value`, and text content. Display all three properties when clicked.

---

## Class 09 Summary

In this class, I learned how to:

- Write functions using Arrow Function syntax.
- Understand the `this` keyword.
- Pass HTML elements to JavaScript functions.
- Retrieve and change HTML content using `innerHTML`.
- Access HTML element names using `name`.
- Retrieve form element values using `value`.

**Class 09 Completed!**
