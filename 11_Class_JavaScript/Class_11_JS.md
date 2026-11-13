# Class 11: Document Object Model (DOM) in JavaScript

## Topics Covered

1. Introduction to DOM
2. How DOM Works
3. DOM Tree Structure
4. DOM Selectors
5. `document.getElementById()`
6. DOM Properties
7. `innerHTML` Property
8. `style` Property
9. Practical Examples
10. Practice Questions

---

# 1. What is DOM?

DOM stands for **Document Object Model**.

The DOM is a programming interface that allows JavaScript to access, manipulate, and update HTML documents.

In simple words:

**DOM allows us to manipulate HTML elements using JavaScript.**

For example, we can use JavaScript to:

- Change HTML content.
- Change text inside an element.
- Change CSS styles.
- Add or remove HTML elements.
- Change element attributes.
- Respond to user interactions.

### Example

Consider the following HTML:

```html
<h1>Hello World</h1>
<p>Welcome to JavaScript</p>
```

Using JavaScript and the DOM, we can change the heading:

```javascript
document.getElementById("heading").innerHTML = "Hello JavaScript";
```

To make this work, the heading needs an ID:

```html
<h1 id="heading">Hello World</h1>
```

**Result:**

Before JavaScript:

```text
Hello World
```

After JavaScript:

```text
Hello JavaScript
```

JavaScript accesses the HTML element through the DOM and changes its content.

---

# 2. How Does DOM Work?

When a browser loads an HTML document, it creates a DOM representation of that document.

JavaScript can then interact with this representation to access and manipulate HTML elements.

### Simple Working Process

1. The browser loads the HTML document.
2. The browser creates the DOM.
3. JavaScript selects an HTML element.
4. JavaScript accesses the element's properties.
5. JavaScript changes the content or appearance of the element.

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Example</title>
</head>
<body>

    <h1 id="heading">Hello World</h1>

    <script>
        document.getElementById("heading").innerHTML = "Hello JavaScript";
    </script>

</body>
</html>
```

**Output:**

```text
Hello JavaScript
```

---

# 3. DOM Tree Structure

The DOM represents an HTML document as a tree of objects called nodes.

Each HTML element becomes an element node in the DOM tree.

### Example HTML

```html
<html>
    <body>
        <h1>Hello World</h1>
        <p>Welcome to JavaScript</p>
    </body>
</html>
```

### DOM Tree

```text
Document
   |
   └── html
        |
        └── body
             |
             ├── h1
             |    |
             |    └── "Hello World"
             |
             └── p
                  |
                  └── "Welcome to JavaScript"
```

### Understanding the Structure

| Node | Explanation |
|---|---|
| Document | Represents the complete HTML document |
| html | Root HTML element |
| body | Contains the visible page content |
| h1 | Heading element |
| p | Paragraph element |
| Text Node | Contains the text inside an element |

**Remember:** The DOM is not simply the HTML source code. It is the browser's object-based representation of the document.

---

# 4. DOM Selectors

A DOM selector is used to select or access an HTML element so that JavaScript can manipulate it.

There are different methods for selecting HTML elements.

In this class, we learned:

`document.getElementById()`

### 4.1 document.getElementById()

The `getElementById()` method is used to select an HTML element using its unique ID.

### Syntax

```javascript
document.getElementById("elementId");
```

### Example

```html
<h1 id="heading">Hello World</h1>

<script>
    let element = document.getElementById("heading");

    console.log(element);
</script>
```

**Explanation:**

- `document` represents the HTML document.
- `getElementById()` selects an element using its ID.
- `"heading"` is the ID of the HTML element.
- `element` stores the selected HTML element.

### Important Points

- Every ID should be unique within an HTML document.
- The ID is written inside quotation marks.
- JavaScript returns the matching HTML element.
- If no matching ID exists, the method returns `null`.

---

# 5. DOM Properties

After selecting an HTML element, we can use its properties to access or manipulate its content and appearance.

In this class, we learned two important properties:

1. `innerHTML`
2. `style`

## 5.1 innerHTML Property

The `innerHTML` property is used to get or change the HTML content inside an HTML element.

In simple words, it allows JavaScript to read or modify what is inside an HTML element.

### Syntax

```javascript
document.getElementById("elementId").innerHTML = "New Content";
```

### Example 1: Changing HTML Content

```html
<h1 id="heading">Hello World</h1>

<script>
    document.getElementById("heading").innerHTML = "Hello JavaScript";
</script>
```

**Output:**

```text
Hello JavaScript
```

**Explanation:**

- `getElementById("heading")` selects the heading.
- `.innerHTML` accesses its content.
- `= "Hello JavaScript"` replaces the existing content.

### Example 2: Getting HTML Content

We can also use `innerHTML` to retrieve the content of an element.

```html
<h1 id="heading">Learning JavaScript</h1>

<script>
    let result = document.getElementById("heading").innerHTML;

    console.log(result);
</script>
```

**Output:**

```text
Learning JavaScript
```

### Example 3: Adding HTML Content

The `innerHTML` property can also insert HTML markup.

```html
<div id="container"></div>

<script>
    document.getElementById("container").innerHTML = "<h1>Hello World</h1>";
</script>
```

**Output:**

A heading displaying:

```text
Hello World
```

**Important:** `innerHTML` can interpret HTML tags. Use `textContent` when you only want to insert or retrieve plain text.

---

## 5.2 style Property

The `style` property is used to apply CSS styles to an HTML element through JavaScript.

In simple words:

**The `style` property allows JavaScript to change the appearance of HTML elements.**

We can use it to change:

- Text color.
- Background color.
- Font size.
- Font family.
- Width and height.
- Border.
- Display properties.

### Syntax

```javascript
document.getElementById("elementId").style.property = "value";
```

### Example 1: Changing Text Color

```html
<h1 id="heading">Hello World</h1>

<script>
    document.getElementById("heading").style.color = "red";
</script>
```

**Result:**

The heading text becomes red.

### Example 2: Changing Background Color

```html
<p id="paragraph">Welcome to JavaScript</p>

<script>
    document.getElementById("paragraph").style.backgroundColor = "yellow";
</script>
```

**Result:**

The paragraph receives a yellow background.

### Example 3: Changing Font Size

```html
<h1 id="heading">JavaScript DOM</h1>

<script>
    document.getElementById("heading").style.fontSize = "40px";
</script>
```

**Result:**

The heading's font size becomes 40 pixels.

### Example 4: Applying Multiple CSS Properties

We can apply multiple styles to the same HTML element.

```html
<h1 id="heading">Hello JavaScript</h1>

<script>
    let element = document.getElementById("heading");

    element.style.color = "blue";
    element.style.backgroundColor = "lightgray";
    element.style.fontSize = "35px";
    element.style.textAlign = "center";
</script>
```

**Result:**

- Text color becomes blue.
- Background becomes light gray.
- Font size becomes 35 pixels.
- Text becomes centered.

### Important: CSS Properties in JavaScript

When using the `style` property, CSS property names with hyphens are generally written in camelCase.

| CSS Property | JavaScript Style Property |
|---|---|
| `background-color` | `backgroundColor` |
| `font-size` | `fontSize` |
| `font-family` | `fontFamily` |
| `text-align` | `textAlign` |
| `border-radius` | `borderRadius` |
| `margin-top` | `marginTop` |
| `padding-left` | `paddingLeft` |

For example:

```javascript
element.style.backgroundColor = "red";
```

Not:

```javascript
element.style.background-color = "red";
```

---

# 6. Difference Between innerHTML and style

Both properties are used to manipulate HTML elements, but they perform different tasks.

| Property | Purpose | Example |
|---|---|---|
| `innerHTML` | Changes or retrieves HTML content | `element.innerHTML = "Hello"` |
| `style` | Changes CSS styles | `element.style.color = "red"` |

**Remember:**

- `innerHTML` is used for content manipulation.
- `style` is used for CSS styling.

---

# 7. Complete Practical Example

Let's combine everything we learned in this class.

### HTML and JavaScript

```html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript DOM Practice</title>
</head>
<body>

    <h1 id="heading">Hello World</h1>

    <p id="paragraph">Welcome to JavaScript DOM.</p>

    <button onclick="changeContent()">Change Content</button>

    <script>

        function changeContent() {

            // Selecting the heading
            let heading = document.getElementById("heading");

            // Changing HTML content
            heading.innerHTML = "Hello JavaScript";

            // Applying CSS styles
            heading.style.color = "blue";
            heading.style.backgroundColor = "lightgray";
            heading.style.fontSize = "40px";

            // Selecting the paragraph
            let paragraph = document.getElementById("paragraph");

            // Changing paragraph content
            paragraph.innerHTML = "I am learning DOM manipulation!";

            // Changing paragraph color
            paragraph.style.color = "green";

        }

    </script>

</body>
</html>
```

### What Happens?

Before clicking the button:

- Heading displays `Hello World`.
- Paragraph displays `Welcome to JavaScript DOM.`

After clicking the button:

- Heading changes to `Hello JavaScript`.
- Heading color becomes blue.
- Heading background becomes light gray.
- Heading font size becomes 40 pixels.
- Paragraph content changes.
- Paragraph color becomes green.

This example demonstrates how JavaScript can select HTML elements and manipulate their content and appearance using the DOM.

---

# 8. Quick Revision

| Topic | Definition |
|---|---|
| DOM | Document Object Model |
| `document` | Represents the HTML document |
| Selector | Used to select HTML elements |
| `getElementById()` | Selects an element using its ID |
| Property | Used to access or modify an element's information or behavior |
| `innerHTML` | Gets or changes HTML content inside an element |
| `style` | Gets or changes inline CSS styles |
| `null` | Returned when `getElementById()` cannot find the requested ID |

---

# 9. Practice Questions

### Conceptual Questions

1. What is DOM in JavaScript?
2. What is the purpose of DOM?
3. How does the browser create the DOM?
4. What is a DOM tree?
5. What is a DOM selector?
6. What is `document.getElementById()`?
7. Why should an ID be unique?
8. What happens if JavaScript cannot find an element by its ID?
9. What is the purpose of the `innerHTML` property?
10. What is the purpose of the `style` property?
11. What is the difference between `innerHTML` and `style`?
12. Why do we use `backgroundColor` instead of `background-color` in JavaScript?

### Practical Tasks

**Task 1: Select an Element**

Create an HTML heading with the ID `heading` and select it using `document.getElementById()`.

**Task 2: Change Content**

Create a paragraph and change its text using the `innerHTML` property.

**Task 3: Change Text Color**

Create a heading and change its text color to red using the `style` property.

**Task 4: Change Background**

Create a paragraph and apply a yellow background using JavaScript.

**Task 5: Apply Multiple Styles**

Create a heading and use JavaScript to change its:

- Text color.
- Background color.
- Font size.
- Text alignment.

**Task 6: Build a Small DOM Project**

Create a webpage containing:

- One heading.
- One paragraph.
- One button.

When the user clicks the button:

1. Change the heading text.
2. Change the paragraph text.
3. Change the heading color.
4. Change the paragraph background color.

---

## Class 11 Summary

In this class, I learned about the Document Object Model (DOM) and how JavaScript can manipulate HTML documents.

The main concepts covered were:

- DOM (Document Object Model).
- DOM Tree Structure.
- DOM Selectors.
- `document.getElementById()`.
- `innerHTML` for content manipulation.
- `style` for applying CSS.
- Changing HTML content and appearance using JavaScript.

**Class 11 Completed!**