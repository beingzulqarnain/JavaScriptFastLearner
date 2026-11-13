# Class 12: Practical DOM Manipulation Using JavaScript

## Topics Covered

1. Introduction to DOM Manipulation
2. Selecting HTML Elements
3. Arrow Functions
4. Passing HTML Elements Using `this`
5. Changing CSS Styles Using JavaScript
6. Changing Font Properties
7. Styling Buttons Dynamically
8. Changing Images Using the `src` Property
9. Complete Practical Project
10. Practice Questions

---

# 1. Introduction to DOM Manipulation

DOM stands for **Document Object Model**.

DOM manipulation means accessing and modifying HTML elements through JavaScript.

Using DOM manipulation, we can:

- Change text and HTML content.
- Change text color.
- Change background color.
- Change font size and font family.
- Modify button styles.
- Change images.
- Modify HTML element properties.

In this class, we learned how to manipulate multiple HTML elements using JavaScript.

---

# 2. Selecting HTML Elements

Before changing an HTML element, we first need to select it.

JavaScript provides the following method:

### `document.getElementById()`

The `getElementById()` method selects an HTML element using its unique ID.

### Syntax

```javascript
document.getElementById("elementId");
```

### Example

```html
<h1 id="title">Codethread</h1>

<script>
  const title = document.getElementById("title");
</script>
```

**Explanation:**

- `document` represents the HTML document.
- `getElementById()` selects an element using its ID.
- `"title"` is the ID of the heading.
- `const title` stores the selected HTML element.

Now we can manipulate the heading using the `title` variable.

---

# 3. Using Arrow Functions

An Arrow Function is a shorter way to write a function in JavaScript.

It uses the `=>` symbol instead of the traditional `function` keyword.

### Regular Function

```javascript
function hello() {
  console.log("Hello JavaScript");
}

hello();
```

### Arrow Function

```javascript
const hello = () => {
  console.log("Hello JavaScript");
};

hello();
```

Both functions perform the same task.

### Arrow Function with a Parameter

```javascript
const hello = (name) => {
  console.log("Hello " + name);
};

hello("Zulqarnain");
```

**Output:**

```text
Hello Zulqarnain
```

In our Class 12 project, we used an Arrow Function to handle the button click.

```javascript
const tryme = (btn) => {
  console.log(btn);
};
```

Here:

- `tryme` is the function name.
- `btn` is the parameter.
- `=>` defines the Arrow Function.
- The `btn` parameter receives the HTML element passed to the function.

---

# 4. Passing an HTML Element Using `this`

The `this` keyword can be used inside an HTML event attribute to refer to the element that triggered the event.

### Example

```html
<button onclick="tryme(this)">Submit</button>

<script>
  const tryme = (btn) => {
    console.log(btn);
  };
</script>
```

**Explanation:**

1. The user clicks the Submit button.
2. `this` refers to the clicked button element.
3. `this` passes the button element to the `tryme()` function.
4. The `btn` parameter receives the button element.
5. We can now access and manipulate the button using `btn`.

For example:

```javascript
const tryme = (btn) => {
  btn.style.backgroundColor = "black";
  btn.style.color = "white";
};
```

The button's background becomes black, and its text becomes white.

---

# 5. Changing CSS Styles Using JavaScript

JavaScript allows us to change CSS styles dynamically through the `style` property.

### Syntax

```javascript
element.style.property = "value";
```

For example:

```javascript
const title = document.getElementById("title");

title.style.color = "red";
title.style.fontSize = "50px";
```

**Result:**

- Text color changes to red.
- Font size changes to 50 pixels.

---

# 6. Manipulating Heading Properties

In our project, we selected the heading using `document.getElementById()` and changed its CSS properties.

### HTML

```html
<h1 id="title">Codethread</h1>
```

### JavaScript

```javascript
const title = document.getElementById("title");

title.style.color = "red";
title.style.fontWeight = "normal";
title.style.fontSize = "50px";
```

### Explanation

| Property     | Purpose                | Value    |
| ------------ | ---------------------- | -------- |
| `color`      | Changes text color     | `red`    |
| `fontWeight` | Changes text thickness | `normal` |
| `fontSize`   | Changes text size      | `50px`   |

**Important:** CSS property names containing hyphens are generally written in camelCase in JavaScript.

For example:

| CSS                | JavaScript        |
| ------------------ | ----------------- |
| `font-size`        | `fontSize`        |
| `font-weight`      | `fontWeight`      |
| `background-color` | `backgroundColor` |
| `font-family`      | `fontFamily`      |
| `border-radius`    | `borderRadius`    |

---

# 7. Manipulating Paragraph Properties

We can also select a paragraph and change its CSS properties.

### HTML

```html
<p id="desc">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
```

### JavaScript

```javascript
const desc = document.getElementById("desc");

desc.style.color = "green";
desc.style.fontWeight = "normal";
desc.style.fontSize = "24px";
desc.style.fontFamily = "sans-serif";
```

### Explanation

| Property     | Purpose                | Value        |
| ------------ | ---------------------- | ------------ |
| `color`      | Changes text color     | `green`      |
| `fontWeight` | Changes text thickness | `normal`     |
| `fontSize`   | Changes text size      | `24px`       |
| `fontFamily` | Changes font family    | `sans-serif` |

**Note:** The correct spelling is `sans-serif`, not `san-serif`.

---

# 8. Styling Buttons Dynamically

We can also manipulate button properties using JavaScript.

In our project, we passed the clicked button to the function using `this`.

### HTML

```html
<button id="btn" onclick="tryme(this)">Submit</button>
```

### JavaScript

```javascript
const tryme = (btn) => {
  btn.style.color = "white";
  btn.style.width = "180px";
  btn.style.backgroundColor = "black";
  btn.style.border = "none";
  btn.style.borderRadius = "24px";
  btn.style.padding = "15px 20px";
  btn.style.cursor = "pointer";
  btn.style.fontSize = "24px";
  btn.style.fontFamily = "sans-serif";
  btn.style.fontWeight = "bold";
};
```

### Explanation of Button Properties

| Property          | Purpose                       | Value        |
| ----------------- | ----------------------------- | ------------ |
| `color`           | Changes button text color     | `white`      |
| `width`           | Sets button width             | `180px`      |
| `backgroundColor` | Changes background color      | `black`      |
| `border`          | Removes the border            | `none`       |
| `borderRadius`    | Makes button corners rounded  | `24px`       |
| `padding`         | Adds space inside the button  | `15px 20px`  |
| `cursor`          | Changes mouse cursor on hover | `pointer`    |
| `fontSize`        | Changes text size             | `24px`       |
| `fontFamily`      | Changes font family           | `sans-serif` |
| `fontWeight`      | Changes text thickness        | `bold`       |

**Important:** The `btn` parameter refers to the actual HTML button element because we passed `this` when calling the function.

---

# 9. Changing Images Using JavaScript

We can change an image dynamically using the `src` property.

The `src` property specifies the path of an image displayed by an HTML `<img>` element.

### HTML

```html
<img id="images" src="images/image 1.jpg" alt="flower" />
```

### JavaScript

```javascript
const images = document.getElementById("images");

images.src = "images/image 2.jpg";
```

**Explanation:**

- `getElementById("images")` selects the image element.
- `images` stores the selected element.
- `images.src` accesses the image source.
- Assigning a new path changes the displayed image.

### Before Changing

```html
<img src="images/image 1.jpg" alt="flower" />
```

### After Changing

```javascript
images.src = "images/image 2.jpg";
```

The browser displays the second image instead of the first one.

**Important:** Make sure the new image path is correct and the image file exists in the specified folder.

---

# 10. Complete Practical Project

Now let's combine all the concepts from Class 12 into one complete HTML project.

### Project: DOM Manipulation Using JavaScript

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <title>Class 12 - DOM JavaScript</title>
  </head>

  <body>
    <!-- Heading -->
    <h1 id="title">Codethread</h1>

    <!-- Description -->
    <p id="desc">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Soluta quia,
      distinctio sunt quos enim velit magnam molestiae tempore assumenda
      accusamus, repellat minus?
    </p>

    <!-- Image -->
    <img id="images" src="images/image 1.jpg" alt="Flower" />

    <br /><br /><br />

    <!-- Button -->
    <button id="btn" onclick="tryme(this)">Submit</button>

    <script>
      // Main Function
      const tryme = (btn) => {
        // 1. Code for Title
        const title = document.getElementById("title");

        title.style.color = "red";
        title.style.fontWeight = "normal";
        title.style.fontSize = "50px";

        // 2. Code for Description
        const desc = document.getElementById("desc");

        desc.style.color = "green";
        desc.style.fontWeight = "normal";
        desc.style.fontSize = "24px";
        desc.style.fontFamily = "sans-serif";

        // 3. Code for Button
        btn.style.color = "white";
        btn.style.width = "180px";
        btn.style.backgroundColor = "black";
        btn.style.border = "none";
        btn.style.borderRadius = "24px";
        btn.style.padding = "15px 20px";
        btn.style.cursor = "pointer";
        btn.style.fontSize = "24px";
        btn.style.fontFamily = "sans-serif";
        btn.style.fontWeight = "bold";

        // 4. Code for Image
        const images = document.getElementById("images");

        images.src = "images/image 2.jpg";
      };
    </script>
  </body>
</html>
```

---

# 11. Understanding the Complete Project

Let's understand what happens when the user clicks the Submit button.

### Step 1: Button Click

The user clicks the Submit button.

```html
<button onclick="tryme(this)">Submit</button>
```

The `onclick` event calls the `tryme()` function and passes the clicked button using `this`.

### Step 2: Function Execution

```javascript
const tryme = (btn) => {
  // Code executes here
};
```

The `btn` parameter receives the clicked button element.

### Step 3: Heading Manipulation

```javascript
const title = document.getElementById("title");

title.style.color = "red";
title.style.fontSize = "50px";
```

The heading changes its color and font size.

### Step 4: Paragraph Manipulation

```javascript
const desc = document.getElementById("desc");

desc.style.color = "green";
desc.style.fontSize = "24px";
```

The paragraph changes its color and font size.

### Step 5: Button Manipulation

```javascript
btn.style.backgroundColor = "black";
btn.style.color = "white";
```

The button's background becomes black, and its text becomes white.

### Step 6: Image Manipulation

```javascript
const images = document.getElementById("images");

images.src = "images/image 2.jpg";
```

The displayed image changes from the first image to the second image.

---

# 12. Important Concepts to Remember

| Concept                     | Explanation                                                    |
| --------------------------- | -------------------------------------------------------------- |
| DOM                         | Document Object Model                                          |
| `document.getElementById()` | Selects an HTML element using its ID                           |
| Arrow Function              | A shorter way to write a function                              |
| `this`                      | Refers to the clicked HTML element in our inline event example |
| `btn`                       | Parameter that receives the HTML button element                |
| `style`                     | Used to access and change inline CSS styles                    |
| `innerHTML`                 | Used to get or change HTML content                             |
| `src`                       | Used to access or change an image source                       |
| `onclick`                   | Event triggered when an element is clicked                     |
| `const`                     | Declares a block-scoped variable that cannot be reassigned     |

---

# 13. Practice Questions

## Conceptual Questions

1. What is DOM manipulation?
2. What is the purpose of `document.getElementById()`?
3. What is an Arrow Function?
4. What does the `this` keyword represent in our button example?
5. Why do we pass `this` to the `tryme()` function?
6. What is the purpose of the `style` property?
7. How can we change the font size of an HTML element?
8. How can we change the background color of a button?
9. What is the purpose of the `src` property?
10. How can we change an image using JavaScript?

## Practical Tasks

### Task 1: Heading Styling

Create an HTML heading with the ID `title`.

When a button is clicked:

- Change the heading color to blue.
- Change the font size to 40px.
- Change the font weight to bold.

### Task 2: Paragraph Styling

Create a paragraph with the ID `description`.

When a button is clicked:

- Change its text color to green.
- Change its font size to 20px.
- Change its font family to sans-serif.

### Task 3: Button Styling

Create a button and use `this` to pass the clicked button to a JavaScript function.

Change:

- Background color.
- Text color.
- Border radius.
- Padding.
- Font size.

### Task 4: Image Changing

Create an image element with the ID `myImage`.

When a button is clicked, change its image source from `image1.jpg` to `image2.jpg`.

### Task 5: Complete DOM Project

Create a webpage containing:

- A heading.
- A paragraph.
- An image.
- A button.

When the button is clicked, change the heading, paragraph, button styles, and image.

---

# Class 12 Summary

In this class, I learned how to manipulate multiple HTML elements using JavaScript.

The main concepts covered were:

- Selecting HTML elements using `document.getElementById()`.
- Using Arrow Functions.
- Passing HTML elements using `this`.
- Applying CSS through the `style` property.
- Changing heading and paragraph styles.
- Dynamically styling buttons.
- Changing images using the `src` property.

**Class 12 Completed!**
