# 📘 Class 03: Introduction to JavaScript

## 📌 Overview

In Class 03, I learned how to connect JavaScript with HTML, display output using `window.alert()` and `console.log()`, and understand the basic building blocks of JavaScript, including data types, keywords, reserved words, and variables.

These concepts are important for building a strong foundation in JavaScript programming.

---

## 📚 Topics Covered

1. Adding JavaScript to HTML using the `<script>` tag
2. Displaying output with `window.alert()`
3. Displaying output with `console.log()`
4. Understanding JavaScript numbers
5. Understanding strings and characters
6. Understanding keywords and reserved words
7. Declaring variables with `var`, `let`, and `const`
8. Practicing JavaScript with simple examples

---

## 1. How to Add JavaScript to HTML

JavaScript can be added to an HTML document using the `<script>` tag.

The `<script>` tag tells the browser that the content inside it contains JavaScript code.

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First JavaScript Program</title>
</head>
<body>

    <h1>Welcome to JavaScript</h1>

    <script>
        console.log("Hello, World!");
    </script>

</body>
</html>
```

### Output

The webpage displays:

```text
Welcome to JavaScript
```

The browser's developer console displays:

```text
Hello, World!
```

**Remember:** HTML creates the structure of a webpage, CSS styles it, and JavaScript adds behavior and interactivity.

---

## 2. What Is the `<script>` Tag?

The `<script>` tag is an HTML element used to include or connect JavaScript code to a webpage.

### Example

```html
<script>
    console.log("I am learning JavaScript!");
</script>
```

The JavaScript code inside the tag runs when the browser processes it.

### Two Ways to Add JavaScript

**Method 1: Internal JavaScript**

Write JavaScript directly inside the HTML file.

```html
<script>
    console.log("Internal JavaScript");
</script>
```

**Method 2: External JavaScript**

Write JavaScript in a separate `.js` file and connect it to HTML.

**index.html**

```html
<!DOCTYPE html>
<html>
<head>
    <title>External JavaScript</title>
</head>
<body>

    <h1>Learning External JavaScript</h1>

    <script src="script.js"></script>
</body>
</html>
```

**script.js**

```javascript
console.log("External JavaScript is working!");
```

### Output in the browser console

```text
External JavaScript is working!
```

If both files are in the same folder, the example works without needing a different file path.

---

## 3. How to Display Output in JavaScript

JavaScript provides different ways to display information or check program results.

Two beginner-friendly methods are:

* `window.alert()`
* `console.log()`

### A. Using `window.alert()`

`window.alert()` displays a message in a pop-up dialog box in the browser.

### Example

```javascript
window.alert("Welcome to JavaScript!");
```

### Output

A pop-up dialog appears with the message:

```text
Welcome to JavaScript!
```

You can also write:

```javascript
alert("Hello, World!");
```

In a browser, `alert()` is a shorter way to call `window.alert()`.

**When to use it:** Use an alert when you want to show a simple message to the user.

**Important:** An alert temporarily interrupts interaction with the webpage until the user dismisses it.

### B. Using `console.log()`

`console.log()` displays information in the browser's developer console.

It is especially useful for testing code and understanding what a program is doing.

### Example 1: Display a message

```javascript
console.log("Hello, World!");
```

Output:

```text
Hello, World!
```

### Example 2: Display a number

```javascript
console.log(100);
```

Output:

```text
100
```

### Example 3: Display a calculation

```javascript
console.log(10 + 20);
```

Output:

```text
30
```

### Example 4: Display multiple messages

```javascript
console.log("My name is Ali.");
console.log("I am learning JavaScript.");
console.log("JavaScript is interesting!");
```

Output:

```text
My name is Ali.
I am learning JavaScript.
JavaScript is interesting!
```

### How to Open the Browser Console

1. Open your HTML file in Google Chrome.
2. Right-click anywhere on the webpage.
3. Select **Inspect**.
4. Open the **Console** tab.

You can see the output of your `console.log()` statements there.

---

## 4. Difference Between `window.alert()` and `console.log()`

| Feature              | `window.alert()`                        | `console.log()`                               |
| -------------------- | --------------------------------------- | --------------------------------------------- |
| Purpose              | Displays a pop-up message               | Displays information in the developer console |
| Where output appears | Browser dialog box                      | Developer console                             |
| User interaction     | Requires the user to dismiss the dialog | Does not require user interaction             |
| Common use           | Showing simple messages                 | Debugging and testing code                    |
| Example              | `window.alert("Hello");`                | `console.log("Hello");`                       |

### Easy Analogy

Imagine that your computer is a classroom.

* **`window.alert()`** is like a teacher stopping the lesson to make an announcement to everyone.
* **`console.log()`** is like the teacher writing a note in a private notebook to check their work.

---

## 5. What Are Data Types in JavaScript?

A **data type** tells JavaScript what kind of value a piece of data represents.

For example, a value might be a number, text, or a true/false value.

JavaScript has several built-in data types. In this class, I learned about numbers, strings, and characters.

---

## 6. Numbers in JavaScript

The **Number** data type is used to represent numerical values.

Numbers can be used for calculations, counting, prices, measurements, and many other tasks.

### Examples

```javascript
console.log(10);
console.log(100);
console.log(3.14);
console.log(-25);
```

### Output

```text
10
100
3.14
-25
```

### Performing Calculations

```javascript
console.log(10 + 5);
console.log(10 - 5);
console.log(10 * 5);
console.log(10 / 5);
```

### Output

```text
15
5
50
2
```

### Common Arithmetic Operators

| Operator | Name           | Example  | Result |
| -------- | -------------- | -------- | ------ |
| `+`      | Addition       | `10 + 5` | `15`   |
| `-`      | Subtraction    | `10 - 5` | `5`    |
| `*`      | Multiplication | `10 * 5` | `50`   |
| `/`      | Division       | `10 / 5` | `2`    |
| `%`      | Remainder      | `10 % 3` | `1`    |

### Real-Life Analogy

Imagine you have 10 apples and buy 5 more.

```javascript
console.log(10 + 5);
```

Output:

```text
15
```

JavaScript calculates the total number of apples.

---

## 7. Strings in JavaScript

A **string** is a sequence of text characters.

Strings are used to represent names, messages, sentences, addresses, and other text.

In JavaScript, strings can be written using:

* Single quotes `' '`
* Double quotes `" "`
* Backticks `` ` ` ``

### Example 1: Single Quotes

```javascript
console.log('Hello');
```

Output:

```text
Hello
```

### Example 2: Double Quotes

```javascript
console.log("JavaScript is easy to learn.");
```

Output:

```text
JavaScript is easy to learn.
```

### Example 3: Backticks

```javascript
console.log(`I am learning JavaScript.`);
```

Output:

```text
I am learning JavaScript.
```

### Example 4: A String Containing a Name

```javascript
console.log("My name is Ali.");
```

Output:

```text
My name is Ali.
```

### Important Rule

Text must be placed inside quotation marks to be treated as a string literal.

```javascript
console.log("Hello"); // String
console.log(100);     // Number
```

The first statement displays text, while the second displays a number.

**Remember:** A number written inside quotation marks is a string, not a Number value.

```javascript
console.log(25);
console.log("25");
```

Both may appear as `25` in the console, but they have different data types.

---

## 8. Characters in JavaScript

A **character** is a single letter, digit, punctuation mark, or symbol.

Examples include:

* `A`
* `b`
* `7`
* `@`
* `!`

Some programming languages have a separate character data type. **JavaScript does not have a separate `char` data type.**

In JavaScript, a single character is represented as a string of length one.

### Example

```javascript
console.log("A");
console.log("7");
console.log("@");
```

Output:

```text
A
7
@
```

These values are all strings in JavaScript.

### Checking the Length of a String

```javascript
console.log("A".length);
console.log("Hello".length);
```

Output:

```text
1
5
```

The `.length` property tells us how many UTF-16 code units a string contains. For simple examples such as `"A"` and `"Hello"`, this matches the number of characters.

### Remember

* `"A"` is a string containing one character.
* `"Hello"` is a string containing five basic English letters.
* JavaScript uses the `string` type for both.

---

## 9. What Are Keywords in JavaScript?

**Keywords** are special words that JavaScript uses for particular purposes in its syntax.

They help JavaScript understand how code should work.

### Examples of JavaScript Keywords

```javascript
let
const
var
if
else
for
while
function
return
class
new
this
try
catch
```

These words have special meanings in JavaScript.

### Example Using `if` and `else`

```javascript
let age = 18;

if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are not an adult yet.");
}
```

Output:

```text
You are an adult.
```

In this example:

* `let` declares a variable.
* `if` checks a condition.
* `else` provides an alternative when the condition is false.

### Important Note

Some words in the list, such as `let`, `const`, and `var`, are technically classified as keywords or context-dependent reserved identifiers depending on the word and its use. The important beginner lesson is that they have special roles in JavaScript and should be used according to the language's rules.

---

## 10. What Are Reserved Words in JavaScript?

**Reserved words** are words that JavaScript keeps for its syntax or future language features. They cannot be used freely as ordinary variable or function names in the contexts where they are reserved.

### Examples

Some reserved words include:

```text
class
return
if
else
for
while
new
try
catch
```

The exact restrictions depend on the word and the context.

### Incorrect Example

```javascript
let if = 10;
```

This causes a syntax error because `if` is reserved for JavaScript syntax.

### Correct Example

```javascript
let score = 10;

console.log(score);
```

Output:

```text
10
```

Here, `score` is a valid variable name.

### Another Incorrect Example

```javascript
let return = 5;
```

This is invalid because `return` has a special role in JavaScript.

### Remember

**Do not use JavaScript keywords or reserved words as ordinary variable names.**

Also, not every word that looks important is reserved. For example, `name`, `score`, and `student` can be used as variable names.

---

## 11. What Are Variables in JavaScript?

A **variable** is a named place used to store a value that a program can access.

Variables allow us to save and reuse information, such as a person's name, age, or score.

JavaScript provides three commonly taught variable declaration keywords:

* `var`
* `let`
* `const`

### Example

```javascript
let studentName = "Ali";
let age = 18;

console.log(studentName);
console.log(age);
```

Output:

```text
Ali
18
```

Here:

* `studentName` stores the string `"Ali"`.
* `age` stores the number `18`.

### Real-Life Analogy

Imagine a labelled box.

* The label is the variable name.
* The item inside the box is the value.

For example:

```javascript
let color = "Blue";
```

Think of a box labelled `color` that contains the value `"Blue"`.

---

## 12. The `var` Keyword

`var` is an older way to declare variables in JavaScript.

Variables declared with `var` can be reassigned and redeclared within the same scope.

### Example

```javascript
var name = "Ali";

console.log(name);

name = "Ahmed";

console.log(name);
```

Output:

```text
Ali
Ahmed
```

The value changes from `"Ali"` to `"Ahmed"`.

### Redeclaring a `var` Variable

```javascript
var age = 18;
var age = 20;

console.log(age);
```

Output:

```text
20
```

Redeclaring a `var` variable in the same scope is allowed.

### Important Note

`var` is function-scoped rather than block-scoped. This can lead to unexpected behavior in larger programs, so modern JavaScript generally favors `let` and `const`.

---

## 13. The `let` Keyword

`let` is used to declare a variable whose value may change later.

A `let` variable can be reassigned, but it cannot be redeclared in the same scope.

### Example

```javascript
let age = 18;

console.log(age);

age = 21;

console.log(age);
```

Output:

```text
18
21
```

The value changes from `18` to `21`.

### Incorrect Example

```javascript
let score = 50;
let score = 100;
```

This causes a syntax error because `score` is declared twice in the same scope using `let`.

### Correct Example

```javascript
let score = 50;

score = 100;

console.log(score);
```

Output:

```text
100
```

### Important Note

`let` is block-scoped. This means a variable declared inside a block, such as an `if` statement or a pair of curly braces, is limited to that block.

---

## 14. The `const` Keyword

`const` is used to declare a variable that cannot be reassigned after initialization.

A `const` declaration must include an initial value.

### Example

```javascript
const country = "Pakistan";

console.log(country);
```

Output:

```text
Pakistan
```

### Incorrect Example

```javascript
const age = 18;

age = 20;
```

This causes a `TypeError` because a `const` variable cannot be reassigned.

### Another Incorrect Example

```javascript
const score;
```

This causes a syntax error because a `const` declaration must be initialized.

### Important Note About Objects and Arrays

`const` prevents reassignment of the variable, but it does not automatically make an object or array immutable.

For example:

```javascript
const student = {
    name: "Ali"
};

student.name = "Ahmed";

console.log(student.name);
```

Output:

```text
Ahmed
```

The object's property can change, even though the variable `student` cannot be reassigned to a different object.

---

## 15. Difference Between `var`, `let`, and `const`

| Feature                              | `var`                     | `let`                            | `const`                              |
| ------------------------------------ | ------------------------- | -------------------------------- | ------------------------------------ |
| Can be reassigned?                   | Yes                       | Yes                              | No                                   |
| Can be redeclared in the same scope? | Yes                       | No                               | No                                   |
| Scope                                | Function-scoped           | Block-scoped                     | Block-scoped                         |
| Must have an initial value?          | No                        | No                               | Yes                                  |
| Recommended for modern code?         | Usually avoid in new code | Yes, when reassignment is needed | Yes, when reassignment is not needed |

### Easy Way to Remember

* **`var`**: The older way to declare a variable.
* **`let`**: Use it when the variable's value needs to change.
* **`const`**: Use it when you do not intend to reassign the variable.

### Example

```javascript
var city = "Peshawar";
let age = 18;
const country = "Pakistan";

age = 19;
city = "Islamabad";

console.log(city);
console.log(age);
console.log(country);
```

Output:

```text
Islamabad
19
Pakistan
```

The values of `city` and `age` can be reassigned. The variable `country` cannot be reassigned.

### Best Practice

In modern JavaScript:

1. Prefer `const` by default.
2. Use `let` when you need to reassign a variable.
3. Avoid `var` in most new code unless you have a specific reason to use it.

---

## 16. Complete Practice Example

The following program combines the concepts learned in this class.

```javascript
// Display a message using alert
window.alert("Welcome to my JavaScript practice!");

// Store a string
const studentName = "Ali";

// Store a number
let age = 18;

// Store a single character as a string
const grade = "A";

// Display values in the console
console.log("Student Name:", studentName);
console.log("Age:", age);
console.log("Grade:", grade);

// Update the age
age = 19;

console.log("Updated Age:", age);

// Perform a calculation
console.log("Age next year:", age + 1);
```

### Expected Console Output

```text
Student Name: Ali
Age: 18
Grade: A
Updated Age: 19
Age next year: 20
```

A browser alert also appears with the welcome message.

### What This Example Teaches

* `window.alert()` displays a browser dialog.
* `console.log()` displays information in the developer console.
* `"Ali"` is a string.
* `18` and `19` are numbers.
* `"A"` is a string containing one character.
* `const` declares variables that cannot be reassigned.
* `let` declares a variable whose value can be reassigned.
* `age + 1` performs a calculation.

---

## 17. Key Takeaways

In Class 03, I learned that:

* JavaScript can be added to HTML using the `<script>` tag.
* JavaScript can be written inside HTML or in a separate `.js` file.
* `window.alert()` displays a pop-up dialog in the browser.
* `console.log()` displays output in the developer console.
* Numbers represent numerical values and can be used for calculations.
* Strings represent text and are written inside quotation marks.
* JavaScript does not have a separate `char` data type; a single character is represented as a string.
* Keywords have special roles in JavaScript syntax.
* Reserved words cannot be used freely as ordinary identifiers in contexts where they are reserved.
* Variables store values that programs can access and use.
* `var`, `let`, and `const` have different rules.
* `let` allows reassignment.
* `const` does not allow reassignment.
* In modern JavaScript, `const` and `let` are generally preferred over `var`.

---

## 18. Practice Questions

Try to answer these questions without looking at the notes.

1. What is JavaScript?
2. What is the purpose of the `<script>` tag?
3. What is the difference between internal and external JavaScript?
4. What does `window.alert()` do?
5. Where can you see the output of `console.log()`?
6. What is a data type?
7. What is the difference between a number and a string?
8. Is `"A"` a separate character data type in JavaScript?
9. What are keywords in JavaScript?
10. Why should reserved words not be used as variable names?
11. What is a variable?
12. What is the difference between `var` and `let`?
13. What is the difference between `let` and `const`?
14. Can you reassign a variable declared with `const`?
15. Why is `const` often preferred in modern JavaScript?

### Coding Practice

**Task 1:** Display your name using `console.log()`.

**Task 2:** Display a welcome message using `window.alert()`.

**Task 3:** Create a variable called `age` and store your age in it.

**Task 4:** Create a string variable called `city` and store the name of your city.

**Task 5:** Store a single letter in a variable called `grade`.

**Task 6:** Declare a variable using `let`, then change its value.

**Task 7:** Declare a variable using `const` and try to reassign it. Observe the error.

**Task 8:** Write a program that displays the result of `25 + 15` using `console.log()`.

---

## 🎯 Class Goal

My goal is to understand the fundamentals of JavaScript and build a strong foundation before moving on to more advanced concepts.

**Status:** Class 03 — In Progress 🚀
