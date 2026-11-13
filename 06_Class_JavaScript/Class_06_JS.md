# Class 06: Functions and Naming Conventions in JavaScript

## 📚 Overview

In this class, we will learn about JavaScript functions, built-in functions, user-defined functions, identifiers, naming conventions, and case sensitivity.

These concepts will help us write clean, readable, and organized JavaScript code.

## 📌 Topics Covered

1. What is a function?
2. Function definition and function call
3. Built-in functions in JavaScript
4. User-defined functions
5. Difference between defining and calling a function
6. Function names and identifiers
7. Naming conventions
8. Case sensitivity in JavaScript
9. Complete practical example
10. Practice questions

---

## 1. What Is a Function?

A **function** is a reusable block of code designed to perform a particular task.

### Real-Life Analogy

Imagine a coffee machine.

You press a button, and the machine prepares coffee. You don't need to explain every step each time you want coffee.

Similarly, a JavaScript function performs a task whenever you call it.

### Example

```javascript
function makeCoffee() {
  console.log("Your coffee is ready!");
}

makeCoffee();
```

**Output:**

```text
Your coffee is ready!
```

### Explanation

- `function` is the keyword used to declare a function.
- `makeCoffee` is the function's name.
- `{ }` contains the code that runs when the function is called.
- `console.log()` displays a message in the browser console.
- `makeCoffee()` calls the function.

**Remember:** A function generally runs when it is called, not merely when it is defined.

---

## 2. Function Definition and Function Call

There are two important concepts when working with functions.

### A. Function Definition

A function definition creates the function and specifies what it will do.

```javascript
function sayHello() {
  console.log("Hello, World!");
}
```

Here, we have defined a function named `sayHello`.

However, this code does not call the function.

### B. Function Call

A function call executes the function.

```javascript
sayHello();
```

**Output:**

```text
Hello, World!
```

### Complete Example

```javascript
function sayHello() {
  console.log("Hello, World!");
}

sayHello();
sayHello();
sayHello();
```

**Output:**

```text
Hello, World!
Hello, World!
Hello, World!
```

We defined the function once and called it three times.

### Key Difference

| Function Definition            | Function Call             |
| ------------------------------ | ------------------------- |
| Creates the function           | Executes the function     |
| Defines what the function does | Tells the function to run |
| Example: `function greet() {}` | Example: `greet()`        |

---

## 3. Built-in Functions in JavaScript

Built-in functions are functions provided by the programming language or its runtime environment.

In beginner JavaScript, you will also frequently use browser-provided functions and methods.

### A. `alert()`

Displays a message in a browser dialog box.

```javascript
alert("Welcome to JavaScript!");
```

You can also write:

```javascript
window.alert("Welcome to JavaScript!");
```

**Result:** A browser dialog box displays the message.

### B. `console.log()`

Displays information in the browser's developer console.

```javascript
console.log("Hello, World!");
console.log(100);
console.log(10 + 20);
```

**Output:**

```text
Hello, World!
100
30
```

**Common use:** Testing code, displaying values, and debugging programs.

### C. `document.write()`

Writes content into an HTML document.

```javascript
document.write("Welcome to JavaScript!");
```

**Result:**

The text appears on the webpage.

**Important:** Using `document.write()` after a page has loaded can replace the existing document. Use it cautiously; modern webpages usually display content by manipulating HTML elements instead.

### D. `window.print()`

Opens the browser's print dialog.

```javascript
window.print();
```

**Result:** The browser allows the user to print the page or save it as a PDF, depending on the available options.

### Comparison Table

| Function or Method | Purpose                                       |
| ------------------ | --------------------------------------------- |
| `alert()`          | Displays a dialog box                         |
| `console.log()`    | Displays information in the developer console |
| `document.write()` | Writes content into the HTML document         |
| `window.print()`   | Opens the browser's print dialog              |

**Note:** `console.log()`, `document.write()`, and `window.print()` are commonly used JavaScript methods. Some are provided by the browser rather than being core language functions.

---

## 4. User-Defined Functions

A **user-defined function** is a function that a programmer creates to perform a specific task.

### Example 1: Simple Function

```javascript
function welcome() {
  console.log("Welcome to my JavaScript class!");
}

welcome();
```

**Output:**

```text
Welcome to my JavaScript class!
```

### Example 2: Displaying Your Name

```javascript
function showName() {
  console.log("My name is Ali.");
}

showName();
```

**Output:**

```text
My name is Ali.
```

### Example 3: Performing a Calculation

```javascript
function calculateSum() {
  let a = 10;
  let b = 20;

  console.log(a + b);
}

calculateSum();
```

**Output:**

```text
30
```

### Example 4: Calling a Function Multiple Times

```javascript
function greet() {
  console.log("Hello!");
}

greet();
greet();
greet();
```

**Output:**

```text
Hello!
Hello!
Hello!
```

### Why Do We Use Functions?

Functions help us:

- Reuse code.
- Avoid unnecessary repetition.
- Organize programs into smaller parts.
- Make code easier to understand.
- Maintain and debug programs more easily.

---

## 5. Function Names and Identifiers

An **identifier** is a name used to identify something in a program, such as a variable, function, or class.

### Examples

```javascript
let firstName = "Ali";

function sayHello() {
  console.log("Hello!");
}

class StudentProfile {}
```

In this example:

- `firstName` is a variable identifier.
- `sayHello` is a function identifier.
- `StudentProfile` is a class identifier.

### Rules for Naming Identifiers

**Rule 1: Names can contain letters.**

```javascript
let username = "Ali";
```

**Rule 2: Names can contain numbers, but cannot start with a number.**

```javascript
let user1 = "Ali"; // Correct
```

Incorrect:

```javascript
let 1user = "Ali"; // SyntaxError
```

**Rule 3: Names can contain underscores.**

```javascript
let first_name = "Ali";
```

**Rule 4: Names can contain dollar signs.**

```javascript
let $price = 500;
```

**Rule 5: Names cannot contain spaces.**

Incorrect:

```javascript
let first name = "Ali";
```

Correct:

```javascript
let firstName = "Ali";
```

**Rule 6: Reserved keywords cannot be used as ordinary identifiers.**

Incorrect:

```javascript
let let = 10;
```

Correct:

```javascript
let age = 10;
```

**Rule 7: Identifiers are case-sensitive.**

```javascript
let name = "Ali";
let Name = "Ahmed";
```

These are two different variables.

---

## 6. Naming Conventions in Programming

A **naming convention** is a style or pattern used to name variables, functions, classes, and other identifiers.

Different programming languages and projects may follow different naming conventions.

### A. lowercase

All letters are written in lowercase.

```text
username
```

Example:

```javascript
let username = "Ali";
```

### B. UPPERCASE

All letters are written in uppercase.

```text
MAX_LIMIT
```

Example:

```javascript
const MAX_LIMIT = 100;
```

**Common use:** Constants that represent fixed configuration values.

Note that uppercase is a convention, not a special JavaScript rule. `const` prevents reassignment of the binding, but it does not automatically make an object or array immutable.

### C. snake_case

Words are separated by underscores.

```text
user_name
```

Example:

```javascript
let user_name = "Ali";
```

JavaScript allows `snake_case`, although `camelCase` is more common for JavaScript variables and functions.

**Common use:** Python variables and some other programming conventions.

### D. camelCase

The first word begins with a lowercase letter. Each following word begins with an uppercase letter.

```text
userName
```

Example:

```javascript
let firstName = "Ali";
let lastName = "Khan";

function calculateTotal() {
  console.log(10 + 20);
}
```

**Common use:** JavaScript variables and functions.

### E. PascalCase

Every word begins with an uppercase letter.

```text
UserName
```

Example:

```javascript
class StudentProfile {
  constructor(name) {
    this.name = name;
  }
}

let student = new StudentProfile("Ali");

console.log(student.name);
```

**Output:**

```text
Ali
```

**Common use:** JavaScript class names.

### Naming Conventions Comparison

| Naming Style | Example     | Common Use                    |
| ------------ | ----------- | ----------------------------- |
| `lowercase`  | `username`  | Simple names                  |
| `UPPERCASE`  | `MAX_LIMIT` | Fixed configuration constants |
| `snake_case` | `user_name` | Common in Python              |
| `camelCase`  | `us         |                               |
