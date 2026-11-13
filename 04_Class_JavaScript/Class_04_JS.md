# 📘 Class 04: JavaScript Output, Variables, Memory, and Mathematical Operations

## 📌 Overview

In Class 04, I learned how to display output in JavaScript, store data in variables, understand how temporary data is stored in computer memory (RAM), and perform mathematical operations using JavaScript.

These concepts are essential for understanding how JavaScript programs work.

---

## 📚 Topics Covered

1. Output statements in JavaScript
2. Using `window.alert()`
3. Using `console.log()`
4. Using `document.write()`
5. Storing data in variables
6. Understanding `var`, `let`, and `const`
7. Understanding temporary data storage in RAM
8. Understanding variables and memory addresses
9. Introduction to pointers and references
10. Mathematical operations in JavaScript
11. Practice examples and exercises

---

# 1. Output Statements in JavaScript

An **output statement** is a way to display information produced by a program.

JavaScript provides several ways to display output. In this class, I learned three methods:

* `window.alert()`
* `console.log()`
* `document.write()`

Each method displays information differently.

## A. Using `window.alert()`

The `window.alert()` method displays a message in a pop-up dialog box in the browser.

### Example

```javascript
window.alert("Welcome to JavaScript!");
```

### Output

A browser dialog appears with the message:

```text
Welcome to JavaScript!
```

### Another Example

```javascript
let name = "Ali";

window.alert(name);
```

Output: A pop-up displays:

```text
Ali
```

### When Should We Use It?

Use `window.alert()` when you need to display a simple message that requires the user to dismiss the dialog before continuing to interact with the webpage.

**Remember:** `alert()` is also a shorter way to call `window.alert()` in a browser.

---

## B. Using `console.log()`

The `console.log()` method displays information in the browser's developer console.

Developers commonly use it to test code, inspect values, and find errors.

### Example 1: Display Text

```javascript
console.log("Hello, World!");
```

Output in the console:

```text
Hello, World!
```

### Example 2: Display Numbers

```javascript
console.log(100);
console.log(500);
console.log(1000);
```

Output:

```text
100
500
1000
```

### Example 3: Display a Variable

```javascript
let age = 18;

console.log(age);
```

Output:

```text
18
```

### Example 4: Display Multiple Values

```javascript
let name = "Ali";
let age = 20;

console.log(name);
console.log(age);
```

Output:

```text
Ali
20
```

### How to Open the Console

1. Open your HTML file in a browser such as Google Chrome.
2. Right-click on the webpage.
3. Select **Inspect**.
4. Open the **Console** tab.

You can see the output of your `console.log()` statements there.

---

## C. Using `document.write()`

The `document.write()` method writes content directly into an HTML document.

It can display text and HTML markup on the webpage.

### Example 1: Display Text

```javascript
document.write("Hello, World!");
```

Output on the webpage:

Hello, World!

### Example 2: Display a Number

```javascript
document.write(100);
```

Output on the webpage:

100

### Example 3: Display HTML

```javascript
document.write("<h1>Welcome to JavaScript</h1>");
document.write("<p>I am learning JavaScript.</p>");
```

Output on the webpage:

# Welcome to JavaScript

I am learning JavaScript.

### Example 4: Display a Variable

```javascript
let studentName = "Ali";

document.write(studentName);
```

Output on the webpage:

Ali

### Important Warning

`document.write()` is mainly useful for learning and simple demonstrations. When used after a page has finished loading, it can replace the entire document with new content.

For modern webpages, developers usually update the page using DOM methods such as `document.querySelector()` and `textContent` instead.

---

# 2. Difference Between the Three Output Methods

| Feature                    | `window.alert()`           | `console.log()`          | `document.write()`                 |
| -------------------------- | -------------------------- | ------------------------ | ---------------------------------- |
| Where output appears       | Pop-up dialog              | Developer console        | Webpage                            |
| Main purpose               | Display a simple message   | Debug and inspect values | Write content into the document    |
| Requires user interaction? | Yes, to dismiss the dialog | No                       | No                                 |
| Can display variables?     | Yes                        | Yes                      | Yes                                |
| Common modern use          | Simple alerts              | Testing and debugging    | Mostly demonstrations and learning |

### Easy Analogy

Imagine you are a teacher in a classroom.

* **`window.alert()`** is like making an announcement that everyone must acknowledge.
* **`console.log()`** is like writing a note in your private notebook.
* **`document.write()`** is like writing directly on the classroom board.

Each method serves a different purpose.

---

# 3. What Is a Variable in JavaScript?

A **variable** is a named identifier that allows a program to access and work with a value.

Variables can store information such as names, ages, prices, scores, and other data.

### Example

```javascript
let name = "Ali";
let age = 18;
let marks = 95;

console.log(name);
console.log(age);
console.log(marks);
```

### Output

```text
Ali
18
95
```

In this example:

* `name` is a variable that holds the string `"Ali"`.
* `age` is a variable that holds the number `18`.
* `marks` is a variable that holds the number `95`.

### Real-Life Analogy

Imagine a box with a label on it.

* The label is the variable name.
* The item inside the box represents the value.

For example:

```javascript
let color = "Blue";
```

Imagine a box labelled `color` containing the value `"Blue"`.

You can access the value using the variable name:

```javascript
console.log(color);
```

Output:

```text
Blue
```

**Important:** A variable is a programming concept, not literally a physical box in RAM.

---

# 4. How to Declare Variables in JavaScript

JavaScript provides three common variable declaration keywords:

* `var`
* `let`
* `const`

They have different rules for reassignment, redeclaration, and scope.

## A. The `var` Keyword

`var` is an older way to declare a variable.

### Example

```javascript
var name = "Ali";

console.log(name);
```

Output:

```text
Ali
```

### Changing the Value

```javascript
var age = 18;

console.log(age);

age = 20;

console.log(age);
```

Output:

```text
18
20
```

A variable declared with `var` can be reassigned.

It can also be redeclared in the same scope:

```javascript
var score = 50;
var score = 100;

console.log(score);
```

Output:

```text
100
```

**Important:** `var` is function-scoped rather than block-scoped, which can lead to unexpected behavior in larger programs.

---

## B. The `let` Keyword

`let` is used when you want to declare a variable whose value may change.

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

### Example with a Score

```javascript
let score = 50;

score = 75;

console.log(score);
```

Output:

```text
75
```

A variable declared with `let` can be reassigned, but it cannot be redeclared in the same scope.

```javascript
let marks = 80;

marks = 90; // Allowed

console.log(marks);
```

Output:

```text
90
```

`let` is block-scoped, meaning it is limited to the block in which it is declared.

---

## C. The `const` Keyword

`const` is used when you do not intend to reassign a variable after initializing it.

### Example

```javascript
const country = "Pakistan";

console.log(country);
```

Output:

```text
Pakistan
```

### What Happens If We Change It?

```javascript
const age = 18;

age = 20;
```

This causes a `TypeError` because a `const` variable cannot be reassigned.

### Important Rule

A `const` declaration must have an initial value.

Incorrect example:

```javascript
const score;
```

This causes a syntax error.

Correct example:

```javascript
const score = 100;

console.log(score);
```

Output:

```text
100
```

**Important:** `const` prevents reassignment of the variable. It does not automatically make objects or arrays immutable.

---

# 5. Difference Between `var`, `let`, and `const`

| Feature                              | `var`           | `let`                            | `const`                              |
| ------------------------------------ | --------------- | -------------------------------- | ------------------------------------ |
| Can be reassigned?                   | Yes             | Yes                              | No                                   |
| Can be redeclared in the same scope? | Yes             | No                               | No                                   |
| Scope                                | Function-scoped | Block-scoped                     | Block-scoped                         |
| Must have an initial value?          | No              | No                               | Yes                                  |
| Recommended for most new code?       | Usually no      | Yes, when reassignment is needed | Yes, when reassignment is not needed |

### Best Practice

* Use `const` by default when you do not need to reassign a variable.
* Use `let` when you need to change a variable's value.
* Generally avoid `var` in modern JavaScript unless you have a specific reason to use it.

### Example

```javascript
const name = "Ali";
let age = 18;

age = 19;

console.log(name);
console.log(age);
```

Output:

```text
Ali
19
```

The `name` variable cannot be reassigned, but `age` can.

---

# 6. How Is Data Stored in RAM?

**RAM** stands for **Random Access Memory**.

RAM is the computer's working memory. It holds data and instructions that programs need while they are running.

### Simple Explanation

When a JavaScript program runs, the JavaScript engine uses computer memory to store and work with information.

For example:

```javascript
let age = 18;
```

The JavaScript engine manages the value `18` in memory and makes it accessible through the variable `age`.

A simplified way to imagine this is:

```text
JavaScript Program
        |
        v
Variable: age
        |
        v
Value: 18
        |
        v
Memory managed by the JavaScript engine
```

This is a conceptual diagram. The actual memory layout is managed by the JavaScript engine and may be more complicated.

### Real-Life Analogy

Imagine a desk where you are doing your homework.

* **RAM** is like the desk where you keep the things you are currently using.
* **Variables** are like labels that help you identify information.
* **Values** are the information you are working with.
* **Storage, such as an SSD or hard drive,** is like a cupboard where you keep things for later.

RAM is generally temporary working memory. When a program stops, its ordinary in-memory data is not automatically saved for use the next time it runs.

If you want information to remain available after a program closes, you need to save it using an appropriate storage system, such as a file, database, or browser storage.

---

# 7. Do Variables Store Data at Memory Addresses?

You learned that variables are associated with memory addresses. This is a useful introduction to computer memory, but JavaScript needs a little more explanation.

In lower-level languages such as C, programmers can work directly with memory addresses and pointers.

JavaScript is different.

**JavaScript does not normally let you access the raw memory address of a variable or use traditional pointers directly.** The JavaScript engine manages memory internally.

Consider this example:

```javascript
let age = 18;

console.log(age);
```

Output:

```text
18
```

You use the variable name `age` to access its value. You do not need to know the physical memory address where the value is stored.

### A Simplified Memory Illustration

```text
Variable Name       Value

age                 18
score               95
name                "Ali"
```

Think of this as a simple learning model, not an exact map of RAM.

The actual storage and memory representation depend on the JavaScript engine and the type of value.

### What Is a Memory Address?

A **memory address** identifies a location in computer memory.

For example, a computer might use a hexadecimal address such as:

```text
0x7FFE1234
```

This is only an illustrative example, not the actual address of a JavaScript variable in your computer.

JavaScript normally hides these details from the programmer.

---

# 8. What Is a Pointer?

A **pointer** is a concept in programming in which a value represents or identifies a memory address.

Pointers are commonly used in languages such as C and C++.

### Simple Analogy

Imagine a house:

* The house is like a value stored somewhere.
* The street address tells you where the house is located.
* A pointer is like a note containing the house's address.

If you know the address, you can find the house.

### Are JavaScript Variables Pointers?

JavaScript does not provide traditional, directly accessible pointers like C or C++.

However, JavaScript has **object references**.

Consider this example:

```javascript
let student1 = {
    name: "Ali"
};

let student2 = student1;

student2.name = "Ahmed";

console.log(student1.name);
console.log(student2.name);
```

Output:

```text
Ahmed
Ahmed
```

### Why Did Both Values Change?

Both `student1` and `student2` refer to the same object.

The assignment:

```javascript
let student2 = student1;
```

does not create a separate copy of the object. It copies the reference to that object.

A simplified illustration:

```text
student1 ─────┐
              |
              v
        { name: "Ali" }
              ^
              |
student2 ─────┘
```

After changing the name through `student2`, the same object is updated. Therefore, reading the name through `student1` also returns `"Ahmed"`.

**Remember:** JavaScript object references are not the same as raw memory pointers that programmers can directly inspect or manipulate.

---

# 9. Introduction to Mathematical Operations in JavaScript

JavaScript can perform mathematical calculations using arithmetic operators.

These operators allow us to add, subtract, multiply, divide, and calculate remainders.

## A. Addition (`+`)

The addition operator adds numbers together.

```javascript
let a = 10;
let b = 20;

console.log(a + b);
```

Output:

```text
30
```

## B. Subtraction (`-`)

The subtraction operator subtracts one number from another.

```javascript
let a = 20;
let b = 10;

console.log(a - b);
```

Output:

```text
10
```

## C. Multiplication (`*`)

The multiplication operator multiplies numbers.

```javascript
let a = 5;
let b = 4;

console.log(a * b);
```

Output:

```text
20
```

## D. Division (`/`)

The division operator divides one number by another.

```javascript
let a = 20;
let b = 4;

console.log(a / b);
```

Output:

```text
5
```

## E. Modulus or Remainder (`%`)

The remainder operator returns the remainder after division.

```javascript
console.log(10 % 3);
```

Output:

```text
1
```

Why?

* 3 goes into 10 three times.
* `3 × 3 = 9`
* `10 − 9 = 1`

The remainder is `1`.

## F. Exponentiation (`**`)

The exponentiation operator raises a number to a power.

```javascript
console.log(2 ** 3);
```

Output:

```text
8
```

This means:

```text
2 × 2 × 2 = 8
```

## G. Increment (`++`)

The increment operator increases a variable's value by one.

```javascript
let count = 5;

count++;

console.log(count);
```

Output:

```text
6
```

## H. Decrement (`--`)

The decrement operator decreases a variable's value by one.

```javascript
let count = 5;

count--;

console.log(count);
```

Output:

```text
4
```

---

# 10. JavaScript Arithmetic Operators Summary

| Operator | Name           | Example   | Result           |
| -------- | -------------- | --------- | ---------------- |
| `+`      | Addition       | `10 + 5`  | `15`             |
| `-`      | Subtraction    | `10 - 5`  | `5`              |
| `*`      | Multiplication | `10 * 5`  | `50`             |
| `/`      | Division       | `10 / 5`  | `2`              |
| `%`      | Remainder      | `10 % 3`  | `1`              |
| `**`     | Exponentiation | `2 ** 3`  | `8`              |
| `++`     | Increment      | `count++` | Increases by `1` |
| `--`     | Decrement      | `count--` | Decreases by `1` |

### Important Note About the `+` Operator

In JavaScript, `+` can perform addition or string concatenation, depending on the values.

Example:

```javascript
console.log(10 + 20);
console.log("Hello " + "World");
console.log("Age: " + 18);
```

Output:

```text
30
Hello World
Age: 18
```

The first statement adds numbers. The other statements combine strings or combine a string with a number.

---

# 11. Storing Mathematical Results in Variables

You can store the result of a mathematical calculation in a variable.

### Example

```javascript
let number1 = 10;
let number2 = 5;

let addition = number1 + number2;
let subtraction = number1 - number2;
let multiplication = number1 * number2;
let division = number1 / number2;

console.log("Addition:", addition);
console.log("Subtraction:", subtraction);
console.log("Multiplication:", multiplication);
console.log("Division:", division);
```

### Output

```text
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2
```

### Why Is This Useful?

Suppose you are building a shopping application.

You can calculate the total price of two products:

```javascript
let product1 = 100;
let product2 = 250;

let totalPrice = product1 + product2;

console.log("Total Price:", totalPrice);
```

Output:

```text
Total Price: 350
```

This is a simple example of how JavaScript performs calculations in real-world applications.

---

# 12. Complete Practice Program

This example combines output statements, variables, and mathematical operations.

```javascript
// Store information in variables
const studentName = "Ali";
let age = 18;

let number1 = 20;
let number2 = 10;

// Display a browser alert
window.alert("Welcome to my JavaScript program!");

// Display information in the developer console
console.log("Student Name:", studentName);
console.log("Age:", age);

// Perform mathematical operations
console.log("Addition:", number1 + number2);
console.log("Subtraction:", number1 - number2);
console.log("Multiplication:", number1 * number2);
console.log("Division:", number1 / number2);
console.log("Remainder:", number1 % number2);

// Display information on the webpage
document.write("<h1>JavaScript Practice</h1>");
document.write("<p>Student Name: " + studentName + "</p>");
document.write("<p>Age: " + age + "</p>");
```

### Expected Console Output

```text
Student Name: Ali
Age: 18
Addition: 30
Subtraction: 10
Multiplication: 200
Division: 2
Remainder: 0
```

The browser also displays an alert dialog and writes the heading and student information onto the webpage.

**Note:** If you run `document.write()` after the page has already loaded, it may replace the existing document. This example is intended for learning.

---

# 13. Key Takeaways

In Class 04, I learned that:

* `window.alert()` displays a message in a browser dialog.
* `console.log()` displays information in the developer console.
* `document.write()` writes content into an HTML document.
* Variables allow programs to access and work with stored values.
* `var`, `let`, and `const` have different rules.
* `let` allows reassignment, while `const` prevents reassignment.
* RAM is the computer's working memory.
* JavaScript engines manage memory while programs execute.
* JavaScript does not normally expose the raw memory addresses of variables.
* Pointers are used directly in languages such as C and C++.
* JavaScript uses object references to access objects.
* JavaScript supports mathematical operations using arithmetic operators.
* The `+` operator can add numbers or combine strings.
* Variables can store the results of calculations.

---

# 14. Practice Questions

Try answering these questions without looking at the notes.

### Theory Questions

1. What is an output statement?
2. What is the difference between `window.alert()` and `console.log()`?
3. What does `document.write()` do?
4. What is a variable in JavaScript?
5. What is the difference between `var`, `let`, and `const`?
6. What is RAM?
7. Why is RAM called working memory?
8. What is a memory address?
9. Does JavaScript allow programmers to access raw variable memory addresses directly?
10. What is a pointer?
11. What is the difference between a pointer and a JavaScript object reference?
12. What are arithmetic operators?
13. What is the difference between `/` and `%`?
14. What does the `**` operator do?
15. What is the difference between adding two numbers and combining two strings using `+`?

### Coding Exercises

**Exercise 1:** Display your name using `console.log()`.

**Exercise 2:** Display a welcome message using `window.alert()`.

**Exercise 3:** Display your name and age on a webpage using `document.write()`.

**Exercise 4:** Declare two variables and add their values.

**Exercise 5:** Calculate the subtraction, multiplication, and division of two numbers.

**Exercise 6:** Use the `%` operator to find the remainder of `17 / 5`.

**Exercise 7:** Declare a variable with `let` and change its value.

**Exercise 8:** Declare a variable with `const` and try to reassign it. Observe the error.

**Exercise 9:** Create two variables that refer to the same object. Change one of the object's properties and observe the result.

**Exercise 10:** Create a simple shopping calculator that adds the prices of three products and displays the total.

---

## 🎯 Class Goal

My goal is to understand how JavaScript displays output, works with variables, manages data in memory, and performs mathematical calculations.

These fundamentals will help me build a strong foundation for learning more advanced JavaScript concepts.


