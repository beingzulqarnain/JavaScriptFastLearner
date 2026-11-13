# Class 08: Variable Scope, Parameters and Arguments in JavaScript

## 📚 Overview

In this class, we learned about variable scope and how to pass information to JavaScript functions.

The topics covered are:

1. Variable Scope
2. Global Scope
3. Local Scope
4. Difference between Global and Local Variables
5. Scope with `var`, `let`, and `const`
6. Function Parameters
7. Function Arguments
8. Difference between Parameters and Arguments

---

# 1. What Is Variable Scope?

**Variable Scope** refers to the area of a program where a variable can be accessed or used.

In simple words, scope tells us where a variable is available.

### Real-Life Analogy

Imagine a school with different classrooms.

- A school notice board is available to everyone in the school.
- A notebook inside one classroom is available only to people who can access that classroom.

Similarly, in JavaScript:

- A global variable can be accessed from different parts of the program where it is in scope.
- A local variable can only be accessed within its particular scope.

---

# 2. Global Scope

A variable declared outside a function or block can have global scope, depending on how and where it is declared.

A global variable can generally be accessed from different functions within the same scope.

### Example

```javascript
var x = 5; // Global variable

function demo() {
  alert("Hello Events");
  alert(x);
}

function test() {
  alert(x);
}

demo();
test();
```

### Output

When `demo()` is called:

```text
Hello Events
5
```

When `test()` is called:

```text
5
```

### Explanation

1. We declare a variable named `x` outside both functions.
2. Its value is `5`.
3. The `demo()` function can access the global variable `x`.
4. The `test()` function can also access the global variable `x`.
5. Both functions can use the same global variable.

**Important:** In your original example, `demo()` only displays `"Hello Events"`. We added `alert(x)` to demonstrate that it can also access the global variable.

### Another Example

```javascript
let username = "Zulqarnain";

function showName() {
  console.log(username);
}

function displayName() {
  console.log(username);
}

showName();
displayName();
```

**Output:**

```text
Zulqarnain
Zulqarnain
```

Both functions can access the global variable `username`.

---

# 3. Local Scope

A variable declared inside a function has local scope when declared with `var`, `let`, or `const`.

This means the variable can only be accessed within that function.

### Example

```javascript
function demo() {
  var x = 10;

  alert(x);
}

demo();
```

**Output:**

```text
10
```

### Explanation

1. We create a function named `demo()`.
2. Inside the function, we declare a variable named `x`.
3. Its value is `10`.
4. We display its value using `alert(x)`.
5. The variable `x` is available inside the function.

### Trying to Access a Local Variable Outside the Function

```javascript
function demo() {
  var x = 10;

  alert(x);
}

demo();

alert(x);
```

**Result:**

The first alert displays:

```text
10
```

The second alert produces a `ReferenceError` because `x` is not available outside the function.

**Remember:** A local variable declared inside a function cannot normally be accessed from outside that function.

---

# 4. Difference Between Global and Local Variables

| Global Variable                                                     | Local Variable                                                      |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Declared outside a function or block, depending on its declaration. | Can be declared inside a function or block.                         |
| Can be accessed from different functions where it is in scope.      | Function-local variables are accessible only within their function. |
| Usually available throughout its enclosing scope.                   | Available only within its local scope.                              |
| Example: `var x = 5;` outside a function.                           | Example: `var x = 10;` inside a function.                           |

---

# 5. Global and Local Variables Together

Let's understand both types in one example.

```javascript
var x = 100; // Global variable

function demo() {
  var y = 50; // Local variable

  console.log("Global variable:", x);
  console.log("Local variable:", y);
}

demo();

console.log("Global variable:", x);
```

**Output:**

```text
Global variable: 100
Local variable: 50
Global variable: 100
```

### Explanation

- `x` is declared outside the function, so it can be accessed inside and outside the function.
- `y` is declared inside the function, so it can only be accessed inside `demo()`.
- When we try to access `y` outside `demo()`, JavaScript produces a `ReferenceError`.

---

# 6. Variable Scope with var, let, and const

JavaScript has three commonly used variable declaration keywords:

- `var`
- `let`
- `const`

They have different scoping rules.

### A. var

The `var` keyword is function-scoped.

```javascript
function demo() {
  var age = 25;

  console.log(age);
}

demo();
```

**Output:**

```text
25
```

### B. let

The `let` keyword is block-scoped.

```javascript
if (true) {
  let age = 25;

  console.log(age);
}
```

**Output:**

```text
25
```

But accessing `age` outside the block causes a `ReferenceError`.

### C. const

The `const` keyword is also block-scoped.

```javascript
if (true) {
  const country = "Pakistan";

  console.log(country);
}
```

**Output:**

```text
Pakistan
```

The variable `country` cannot be accessed outside the block.

### Important Comparison

| Keyword | Scope          |
| ------- | -------------- |
| `var`   | Function scope |
| `let`   | Block scope    |
| `const` | Block scope    |

**Note:** A block is a section of code enclosed in curly braces `{ }`, such as an `if` statement or a loop.

---

# 7. What Are Parameters and Arguments in JavaScript?

Parameters and arguments are used when working with functions.

They allow us to pass information into a function so that it can perform different tasks using different values.

### Real-Life Analogy

Imagine you visit a restaurant and order a pizza.

You tell the restaurant:

- Pizza size: Large
- Flavor: Chicken
- Quantity: 2

The restaurant uses the information you provide to prepare your order.

Similarly, a JavaScript function can receive information and use it to perform a task.

---

## 7.1 What Are Parameters?

**Parameters** are variables listed inside the parentheses of a function definition.

They act as placeholders that receive values when the function is called.

### Example

```javascript
function greet(name) {
  console.log("Hello " + name);
}
```

In this example:

- `function` is the keyword.
- `greet` is the function name.
- `name` is the parameter.
- The parameter receives a value when the function is called.

**Remember:** Parameters are defined when we create a function.

---

## 7.2 What Are Arguments?

**Arguments** are the actual values that we pass to a function when calling it.

### Example

```javascript
function greet(name) {
  console.log("Hello " + name);
}

greet("Zulqarnain");
```

**Output:**

```text
Hello Zulqarnain
```

### Explanation

- `name` is the parameter.
- `"Zulqarnain"` is the argument.
- When the function is called, the argument is passed to the parameter.
- The function uses that value to display the message.

---

## 7.3 Difference Between Parameters and Arguments

| Parameters                                  | Arguments                                     |
| ------------------------------------------- | --------------------------------------------- |
| Variables written in a function definition. | Actual values passed when calling a function. |
| Act as placeholders.                        | Provide data to the function.                 |
| Defined when creating the function.         | Supplied when calling the function.           |
| Example: `name`                             | Example: `"Ali"`                              |

### Easy Way to Remember

```javascript
function greet(name) {
  // name = Parameter
  console.log("Hello " + name);
}

greet("Ali"); // "Ali" = Argument
```

**Parameter = Placeholder**

**Argument = Actual Value**

---

# 8. Examples of Parameters and Arguments

## Example 1: Passing a Name

```javascript
function showName(name) {
  console.log("My name is " + name);
}

showName("Ali");
```

**Output:**

```text
My name is Ali
```

Here:

- `name` is the parameter.
- `"Ali"` is the argument.

## Example 2: Passing Two Arguments

```javascript
function addNumbers(a, b) {
  console.log(a + b);
}

addNumbers(10, 20);
```

**Output:**

```text
30
```

Here:

- `a` and `b` are parameters.
- `10` and `20` are arguments.

### Explanation

1. We define a function named `addNumbers`.
2. We create two parameters: `a` and `b`.
3. We call the function with two arguments: `10` and `20`.
4. JavaScript assigns `10` to `a` and `20` to `b`.
5. The function adds both values.
6. The result is `30`.

## Example 3: Passing Different Arguments

```javascript
function greet(name) {
  console.log("Hello " + name);
}

greet("Ali");
greet("Ahmed");
greet("Zulqarnain");
```

**Output:**

```text
Hello Ali
Hello Ahmed
Hello Zulqarnain
```

We defined the function once but called it three times with different arguments.

This makes functions reusable.

## Example 4: Multiplication

```javascript
function multiplyNumbers(a, b) {
  console.log(a * b);
}

multiplyNumbers(5, 4);
```

**Output:**

```text
20
```

## Example 5: Passing Three Arguments

```javascript
function studentInfo(name, age, country) {
  console.log("Name: " + name);
  console.log("Age: " + age);
  console.log("Country: " + country);
}

studentInfo("Ali", 25, "Pakistan");
```

**Output:**

```text
Name: Ali
Age: 25
Country: Pakistan
```

### Explanation

| Parameter | Argument     |
| --------- | ------------ |
| `name`    | `"Ali"`      |
| `age`     | `25`         |
| `country` | `"Pakistan"` |

Each argument is assigned to its corresponding parameter based on its position.

---

# 9. Parameters and Arguments with Variables

We can also pass variables as arguments instead of directly passing values.

### Example

```javascript
let firstNumber = 10;
let secondNumber = 20;

function calculateSum(a, b) {
  console.log(a + b);
}

calculateSum(firstNumber, secondNumber);
```

**Output:**

```text
30
```

### Explanation

- `firstNumber` contains `10`.
- `secondNumber` contains `20`.
- Both variables are passed as arguments.
- The parameters `a` and `b` receive their values.
- The function calculates their sum.

---

# 10. Important Notes

1. Scope determines where a variable can be accessed.
2. Global variables can be accessed from different functions within their available scope.
3. Variables declared inside functions have local function scope.
4. `var` is function-scoped.
5. `let` and `const` are block-scoped.
6. Parameters are variables listed in a function definition.
7. Arguments are actual values passed when calling a function.
8. A function can have multiple parameters and arguments.
9. Arguments are assigned to parameters according to their position.
10. Functions become reusable when we pass different arguments.

---

# 11. Practice Questions

## Beginner Level

1. What is variable scope in JavaScript?
2. What is a global variable?
3. What is a local variable?
4. What is the difference between global and local scope?
5. Can a function access a global variable?
6. Can we access a function-local variable outside that function?
7. What is the difference between `var`, `let`, and `const` scope?
8. What are parameters in JavaScript?
9. What are arguments in JavaScript?
10. What is the difference between parameters and arguments?

## Coding Exercises

### Exercise 1: Global Variable

Create a global variable named `name` and access it inside two different functions.

### Exercise 2: Local Variable

Create a function named `showAge()` and declare a local variable named `age` inside it.

### Exercise 3: Global and Local Together

Create:

- One global variable named `x`.
- One local variable named `y`.

Display both variables inside a function.

### Exercise 4: Find the Error

What will happen when you run this code?

```javascript
function demo() {
  let message = "Hello JavaScript";
}

demo();

console.log(message);
```

Explain why.

### Exercise 5: Understand Scope

Predict the output:

```javascript
var x = 10;

function test() {
  var y = 20;

  console.log(x);
  console.log(y);
}

test();

console.log(x);
```

### Exercise 6: Create a Function with One Parameter

Create a function named `showName()` that accepts a name and displays it in the console.

### Exercise 7: Create a Function with Two Parameters

Create a function named `addNumbers()` that accepts two numbers and displays their sum.

### Exercise 8: Student Information

Create a function named `studentInfo()` that accepts three parameters:

- Name
- Age
- Country

Pass three arguments when calling the function and display the student's information.

### Exercise 9: Predict the Output

```javascript
function calculate(a, b) {
  console.log(a + b);
}

calculate(15, 25);
calculate(50, 50);
```

What will be the output?

---

## 🎯 Class Goal

By the end of Class 08, you should be able to:

- Understand variable scope.
- Explain global scope.
- Explain local scope.
- Identify global and local variables.
- Understand the scope differences between `var`, `let`, and `const`.
- Understand function parameters.
- Understand function arguments.
- Differentiate between parameters and arguments.
- Pass values into functions.
- Create reusable functions using parameters and arguments.

**Keep practicing!** Understanding variable scope, parameters, and arguments is essential for writing organized, reusable, and maintainable JavaScript programs.
