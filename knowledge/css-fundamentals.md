# CSS Fundamentals

- [What CSS Is & How It Works](#what-css-is--how-it-works-)
  - [How HTML, CSS, and JavaScript Work Together](#how-html-css-and-javascript-work-together-️)
  - [What "Cascading" Means](#what-cascading-means-)
  - [What "Style Sheets" Means](#what-style-sheets-means-)
  - [How Browsers Apply CSS](#how-browsers-apply-css-)
  - [CSS is About Selectors and Declarations](#css-is-about-selectors-and-declarations-)
  - [Why CSS is Separate from HTML](#why-css-is-separate-from-html-)
  - [CSS Controls Visual Properties](#css-controls-visual-properties-)
  - [What CSS Cannot Do](#what-css-cannot-do-)
- [Your First CSS File](#your-first-css-file-)
  - [Step 1: Create Your CSS File](#step-1-create-your-css-file-)
  - [Step 2: Link CSS to Your HTML](#step-2-link-css-to-your-html-)
  - [Step 3: Write Your First CSS Rule](#step-3-write-your-first-css-rule-️)
  - [Step 4: View It in Your Browser](#step-4-view-it-in-your-browser-)
  - [Step 5: Add More Styles](#step-5-add-more-styles-)
  - [Understanding What Just Happened](#understanding-what-just-happened-)
  - [The Edit-Save-Refresh Cycle](#the-edit-save-refresh-cycle-) -[Multiple Rules for the Same Element](#multiple-rules-for-the-same-element-)
  - [Why This Approach is Powerful](#why-this-approach-is-powerful-)
  - [What If My Styles Don't Show Up?](#what-if-my-styles-dont-show-up-)
- [CSS Syntax & Rules](#css-syntax--rules-)
  - [Anatomy of a CSS Rule](#anatomy-of-a-css-rule-)
  - [The Four Parts of a CSS Rule](#the-four-parts-of-a-css-rule-)
  - [Writing Your First Rule](#writing-your-first-rule-️)
  - [Multiple Declarations](#multiple-declarations-)
  - [Syntax Rules You MUST Follow & Common Mistakes](#syntax-rules-you-must-follow---common-mistakes-)
  - [How to Check for Syntax Errors](#how-to-check-for-syntax-errors-)
  - [Spacing and Formatting](#spacing-and-formatting-)
  - [Indentation Best Practice](#indentation-best-practice-)
  - [Multiple Rules in a Stylesheet](#multiple-rules-in-a-stylesheet-)
  - [Comments in CSS](#comments-in-css-)
  - [Grouping Selectors](#grouping-selectors-)
  - [Practice: Write a Complete Rule](#practice-write-a-complete-rule-)
- [Selectors: Simple to Advanced](#selectors-simple-to-advanced-)
  - [What is a Selector?](#what-is-a-selector-)
  - [Level 1: Basic Selectors](#level-1-basic-selectors-)
  - [Level 2: Combining Selectors](#level-2-combining-selectors-)
  - [Level 3: Attribute Selectors](#level-3-attribute-selectors-)
  - [Level 4: Pseudo-Classes](#level-4-pseudo-classes-)
  - [Selector Combinations in Practice](#selector-combinations-in-practice-)
  - [Selector Specificity Preview](#selector-specificity-preview-)
  - [When to Use Which Selector?](#when-to-use-which-selector-)

---

## **What CSS Is & How It Works 🎨**

CSS stands for **Cascading Style Sheets**. It's the language that controls how your HTML looks.

### **How HTML, CSS, and JavaScript Work Together 🛠️**

When building a website, each technology has a specific job:

- **HTML** = Structure and content ("This is a heading. This is a paragraph.")
- **CSS** = Appearance and layout ("Make the heading blue. Put this box on the left.")
- **JavaScript** = Behavior and interactivity ("When clicked, show a message.")

Think of building a house:

- HTML is the foundation and walls (structure)
- CSS is the paint, furniture, and decoration (style)
- JavaScript is the lights, doors, and appliances (functionality)

---

### **What "Cascading" Means 🌊**

The "Cascading" in CSS refers to how the browser decides which styles to apply when multiple rules target the same element.

**Simple example:**

```css
p {
  color: blue;
}

p {
  color: red;
}
```

Both rules target paragraphs. Which color wins? **Red**, because it comes last.

But it gets more complex when specificity and importance are involved. We'll dive into the cascade algorithm in detail later—for now, just know that "cascading" means **rules flow down and can override each other**.

---

### **What "Style Sheets" Means 📄**

A **stylesheet** is a file (usually with a `.css` extension) that contains CSS rules.

**Example stylesheet (`styles.css`):**

```css
h1 {
  color: blue;
  font-size: 2rem;
}

p {
  color: gray;
  line-height: 1.5;
}
```

This file defines styles for `h1` and `p` elements. You link it to your HTML, and the browser applies those styles.

---

### **How Browsers Apply CSS 🌐**

When you load a webpage, here's what happens:

1. **Browser reads HTML** (structure)
2. **Browser reads CSS** (styling rules)
3. **Browser combines them** (applies styles to HTML elements)
4. **Browser renders the page** (displays the styled result)

**Without CSS:**

```html
<h1>Welcome</h1>
<p>This is a paragraph.</p>
```

The browser shows plain, unstyled text—black text on white background, default font.

**With CSS:**

```css
h1 {
  color: hotpink;
  font-size: 3rem;
}

p {
  color: gray;
  font-size: 1rem;
}
```

Now the heading is giant and pink, the paragraph is gray and smaller.

---

### **CSS is About Selectors and Declarations 🎯**

Every CSS rule has two parts:

1. **Selector** - Which element(s) to style
2. **Declarations** - What styles to apply

**Example:**

```css
h1 {
  color: blue;
  font-size: 2rem;
}
```

- **Selector**: `h1` (targets all `<h1>` elements)
- **Declarations**: `color: blue;` and `font-size: 2rem;` (what to change)

We'll break down the syntax in the next section.

---

### **Why CSS is Separate from HTML 🔗**

You could technically write CSS directly in HTML like this:

```html
<h1 style="color: blue; font-size: 2rem;">Welcome</h1>
```

But this is **bad practice** for several reasons:

1. **Hard to maintain** - If you want to change the heading color, you have to edit EVERY heading in EVERY HTML file
2. **Repetitive** - You write the same styles over and over
3. **Not reusable** - Styles are tied to individual elements
4. **Messy HTML** - Your HTML becomes cluttered with style information

**The better way:**

Write styles once in a CSS file, link it to your HTML, and all elements with matching selectors get styled automatically.

```html
<!-- HTML stays clean -->
<h1>Welcome</h1>
```

```css
/* CSS stays organized */
h1 {
  color: blue;
  font-size: 2rem;
}
```

Now every `<h1>` on the page gets the same styling, and you can change it in one place.

---

### **CSS Controls Visual Properties 🎨**

CSS can style almost anything about how an element looks:

**Text styling:**

- Color
- Font size
- Font family
- Bold, italic
- Alignment

**Layout:**

- Width and height
- Spacing (margins, padding)
- Position on the page

**Decoration:**

- Borders
- Backgrounds
- Shadows
- Rounded corners

**Animation:**

- Transitions
- Movement
- Hover effects

---

### **What CSS Cannot Do ❌**

CSS is ONLY for styling. It cannot:

- Process logic (if/then statements)
- Store data
- Respond to user input beyond basic hover/focus
- Make API calls
- Calculate complex values (beyond basic math)

For those things, you need JavaScript.

---

## **Your First CSS File 🚀**

This is where we make CSS real. You're going to create a CSS file, link it to HTML, write a style rule, and see it work in your browser.

### **Step 1: Create Your CSS File 📄**

1. Open your project folder (the one with your HTML file)
2. Create a new file called `styles.css`

**File structure:**

```
my-project/
├── index.html
└── styles.css
```

**Pro tip:** 💡 Many developers organize CSS in a folder:

```
my-project/
├── index.html
└── css/
    └── styles.css
```

Both approaches work. For now, keep it simple with `styles.css` in the same folder as your HTML.

---

### **Step 2: Link CSS to Your HTML 🔗**

Open your `index.html` file and add a `<link>` tag in the `<head>` section:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My First Styled Page</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is my first styled page.</p>
  </body>
</html>
```

**What this link tag does:**

- `rel="stylesheet"` tells the browser "this is a CSS file"
- `href="styles.css"` tells the browser where to find it
- For more information read the [HTML Basics](html-basics.md)

**If your CSS is in a folder:**

```html
<link rel="stylesheet" href="css/styles.css" />
```

---

### **Step 3: Write Your First CSS Rule ✍️**

Open `styles.css` and write this:

```css
h1 {
  color: hotpink;
}
```

**Save the file.**

---

### **Step 4: View It in Your Browser 👀**

Open `index.html` in your browser (or refresh if it's already open).

**What you should see:**

Your `<h1>` is now **hotpink** instead of the default black.

🎉 **Congratulations! You just styled your first element with CSS.**

---

### **Step 5: Add More Styles 🎨**

Let's style the paragraph too. Update your `styles.css`:

```css
h1 {
  color: hotpink;
  font-size: 3rem;
}

p {
  color: gray;
  font-size: 1.2rem;
  line-height: 1.6;
}
```

**Save the file. Refresh your browser.**

**What changed:**

- The heading is now pink AND bigger
- The paragraph is gray with larger text and more space between lines

---

### **Understanding What Just Happened 💡**

When you refreshed the browser:

1. **Browser loaded `index.html`**
2. **Browser saw the `<link>` tag** and fetched `styles.css`
3. **Browser read the CSS rules:**
   - "Make all `h1` elements hotpink and 3rem"
   - "Make all `p` elements gray, 1.2rem, with 1.6 line-height"
4. **Browser applied those styles** to matching elements
5. **Browser rendered the styled page**

---

### **The Edit-Save-Refresh Cycle 🔄**

This is the workflow you'll use constantly when building websites:

1. **Edit** your CSS file
2. **Save** the file (Ctrl+S / Cmd+S)
3. **Refresh** your browser (F5 / Cmd+R)
4. **See** the changes

**Try it now:**

Change the heading color to `blue`:

```css
h1 {
  color: blue;
  font-size: 3rem;
}
```

Save → Refresh → The heading is now blue. 🔵

---

### **Multiple Rules for the Same Element ✨**

You can style the same element in multiple ways:

```css
h1 {
  color: blue;
  font-size: 3rem;
  text-align: center;
  background-color: lightgray;
  padding: 1rem;
  border-radius: 10px;
}
```

**Save and refresh.**

Now your heading is:

- Blue text
- Large font
- Centered
- On a light gray background
- With padding around it
- With rounded corners

---

### **Why This Approach is Powerful 💪**

**Before CSS (inline styles):**

```html
<h1 style="color: blue; font-size: 3rem;">Welcome</h1>
<h1 style="color: blue; font-size: 3rem;">About Us</h1>
<h1 style="color: blue; font-size: 3rem;">Contact</h1>
```

You have to repeat the same styles for every heading. If you want to change the color, you edit EVERY heading.

**With CSS:**

```html
<h1>Welcome</h1>
<h1>About Us</h1>
<h1>Contact</h1>
```

```css
h1 {
  color: blue;
  font-size: 3rem;
}
```

Change the CSS once → all headings update automatically. 🎯

---

### **What If My Styles Don't Show Up? 🐛**

**Common mistakes:**

1. **Wrong file path** in the `<link>` tag
   - Check: Is `styles.css` in the same folder as `index.html`?
   - If it's in a `css` folder, use `href="css/styles.css"`

2. **Typo in the link tag**
   - Make sure: `rel="stylesheet"` and `href="styles.css"` are correct

3. **CSS syntax error**
   - Missing semicolon: `color: blue` (missing `;`)
   - Missing curly brace: `h1 { color: blue;` (missing `}`)

4. **Wrong selector**
   - If you wrote `h2 { color: blue; }` but your HTML has `<h1>`, it won't match

5. **Browser cache**
   - Try: Hard refresh (Ctrl+Shift+R / Cmd+Shift+R)

---

### **Checking If CSS is Loaded 🔍**

**Use browser DevTools:**

1. Right-click on your page → "Inspect" (or press F12)
2. Go to the **Network** tab
3. Refresh the page
4. Look for `styles.css` in the file list

**If it's there:** CSS loaded successfully
**If it's red/missing:** Check your file path

---

### **Your Workflow Going Forward 🛠️**

Every time you build a webpage:

1. Create HTML file ✅
2. Create CSS file ✅
3. Link CSS to HTML with `<link>` tag ✅
4. Write CSS rules ✅
5. Save and refresh to see changes ✅
6. Edit → Save → Refresh → Repeat ✅

Get comfortable with this cycle. It's how CSS development works.

---

## **CSS Syntax & Rules 📝**

Every CSS file is made up of **rules**. A rule tells the browser which elements to style and how to style them.

### **Anatomy of a CSS Rule 🔍**

Here's a complete CSS rule:

```css
h1 {
  color: blue;
  font-size: 2rem;
}
```

**Breaking it down:**

```
┌─ Selector (which element to style)
│
h1 {
  color: blue;        ← Declaration (property + value)
  font-size: 2rem;    ← Another declaration
}
└─ Closing curly brace
```

---

### **The Four Parts of a CSS Rule 🧩**

| Part            | Description               | Example                        |
| --------------- | ------------------------- | ------------------------------ |
| **Selector**    | Which element(s) to style | `h1`, `.button`, `#header`     |
| **Property**    | What aspect to style      | `color`, `font-size`, `margin` |
| **Value**       | How to style it           | `blue`, `2rem`, `10px`         |
| **Declaration** | Property + Value together | `color: blue;`                 |

**Complete rule structure:**

```css
selector {
  property: value;
  property: value;
}
```

---

### **Writing Your First Rule ✍️**

**Step-by-step:**

1. **Start with the selector:**

```css
p
```

2. **Add opening curly brace:**

```css
p {
```

3. **Write a declaration (property: value;):**

```css
p {
  color: gray;
```

4. **Add closing curly brace:**

```css
p {
  color: gray;
}
```

5. **Done!** This rule makes all paragraphs gray.

---

### **Multiple Declarations 📋**

You can style multiple properties in one rule:

```css
h1 {
  color: hotpink;
  font-size: 3rem;
  text-align: center;
  background-color: black;
  padding: 1rem;
}
```

**Each declaration:**

- Starts with a property name
- Followed by a colon `:`
- Followed by the value
- Ends with a semicolon `;`

---

### **Syntax Rules You MUST Follow 🚨 & Common Mistakes 🐞**

Follow these rules to write valid CSS. We'll show each rule with correct and incorrect examples.

#### **1. Always use a colon between property and value**

✅ **Correct:**

```css
color: blue;
```

❌ **Wrong:**

```css
color = blue;  /* Using equals sign doesn't work */
color blue;    /* Missing colon */
```

---

#### **2. Always end declarations with a semicolon**

✅ **Correct:**

```css
color: blue;
font-size: 2rem;
```

❌ **Wrong:**

```css
color: blue
font-size: 2rem
```

When you forget the semicolon, the browser may ignore the next declaration.

**Pro tip:** 💡 Even the last declaration should have a semicolon. It prevents errors when you add more properties later.

---

#### **3. Wrap declarations in curly braces**

✅ **Correct:**

```css
h1 {
  color: blue;
}
```

❌ **Wrong:**

```css
h1
  color: blue;
```

---

#### **4. Property names must be lowercase**

✅ **Correct:**

```css
color: blue;
font-size: 2rem;
```

<!-- prettier-ignore -->
❌ **Wrong:**

```css
color: blue; /* Capitalized */
font-size: 2rem; /* All caps */
```

---

#### **5. Watch out for typos in property names**

CSS property names are standardized. If you misspell them, the browser **silently ignores** them—no error message.

❌ **Common typos:**

```css
colour: blue; /* British spelling doesn't work */
fontsize: 2rem; /* Missing hyphen */
text-allign: center; /* Misspelled */
margn: 10px; /* Missing letter */
```

✅ **Correct spellings:**

```css
color: blue;
font-size: 2rem;
text-align: center;
margin: 10px;
```

You're absolutely right. We're saying the same thing twice.

**"How to Check for Syntax Errors"** already explains:

- Use your editor
- Use DevTools
- Use the validator

Then **"CSS is Forgiving"** just repeats "CSS doesn't show errors, here's what to check."

---

**Better approach:**

Delete the "CSS is Forgiving" section and add that key insight as an intro to "How to Check for Syntax Errors":

---

### **How to Check for Syntax Errors 🔍**

**Important:** CSS doesn't throw obvious errors like other languages. If you make a mistake, CSS silently ignores it—no error message, no warning. This makes debugging tricky, so you need to actively check for problems.

**1. Use your code editor:**

- VS Code highlights syntax errors
- Look for red squiggly lines

**2. Use browser DevTools:**

- Right-click → Inspect → Elements tab
- Click on an element
- Check the Styles panel
- Invalid properties will be crossed out

**3. Validate your CSS:**

- Use the [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
- Paste your CSS or upload your file
- It will show all errors and warnings

**What to check when styles don't work:**

1. Is my selector correct?
2. Is my property name spelled right?
3. Is my value valid for that property?

---

### **Spacing and Formatting 📐**

CSS doesn't care about whitespace, but humans do. Here are common formatting styles:

**Expanded format (most readable):**

```css
h1 {
  color: blue;
  font-size: 2rem;
  text-align: center;
}
```

**Compressed format (harder to read):**

<!-- prettier-ignore -->
```css
h1{color:blue;font-size:2rem;}
```

**Both work, but expanded format is standard.** It's easier to read and edit.

---

### **Indentation Best Practice 📏**

Always indent declarations inside the curly braces:

✅ **Good (indented):**

```css
h1 {
  color: blue;
  font-size: 2rem;
}
```

❌ **Bad (not indented):**

<!-- prettier-ignore -->
```css
h1 {
color: blue;
font-size: 2rem;
}
```

**Standard indentation:** 2 spaces (most common) or 4 spaces

---

### **Multiple Rules in a Stylesheet 📄**

A CSS file contains multiple rules:

```css
h1 {
  color: blue;
  font-size: 3rem;
}

p {
  color: gray;
  line-height: 1.6;
}

a {
  color: hotpink;
  text-decoration: none;
}
```

**Best practice:** Leave a blank line between rules for readability.

---

### **Comments in CSS 💬**

Use comments to explain your code or leave notes:

**Syntax:**

```css
/* This is a comment */
```

**Example:**

```css
/* Main heading styles */
h1 {
  color: blue;
  font-size: 3rem;
}

/* Paragraph styles */
p {
  color: gray; /* Gray text for readability */
  line-height: 1.6;
}

/*
This is a multi-line comment.
You can write as much as you want.
Useful for longer explanations.
*/
```

**Comments are ignored by the browser** — they're only for you and other developers.

---

#### **When to Use Comments 📝**

**Good uses:**

- Explaining why you made a styling decision
- Organizing sections of your stylesheet
- Temporarily disabling a rule while testing

**Example:**

```css
/* Header Section */
header {
  background-color: black;
  color: white;
}

/* Navigation Menu */
nav {
  display: flex;
  /* padding: 1rem; */ /* Temporarily disabled for testing */
}
```

**Don't overdo it:** If your code is clear, you don't need comments for every single line.

---

### **Grouping Selectors 🎯**

If multiple elements should have the same styles, group them with commas:

**Without grouping (repetitive):**

```css
h1 {
  color: blue;
}

h2 {
  color: blue;
}

h3 {
  color: blue;
}
```

**With grouping (efficient):**

```css
h1,
h2,
h3 {
  color: blue;
}
```

**Another example:**

```css
p,
li,
span {
  font-size: 1rem;
  line-height: 1.5;
}
```

This makes all paragraphs, list items, and spans use the same font size and line height.

---

### **Practice: Write a Complete Rule 🧪**

Try writing this rule from scratch:

**Goal:** Style all `<a>` elements with:

- Color: hotpink
- No underline
- Bold text

**Answer:**

```css
a {
  color: hotpink;
  text-decoration: none;
  font-weight: bold;
}
```

---

## **Selectors: Simple to Advanced 🎯**

Selectors are how you tell CSS which elements to style. Let's build your selector knowledge from the simplest to the most powerful.

### **What is a Selector? 🤔**

A selector is the part of a CSS rule that targets elements.

```css
h1 {
  color: blue;
}
```

`h1` is the selector. It says "find all `<h1>` elements and apply these styles."

---

### **Level 1: Basic Selectors 🟢**

These are the foundation. Master these first.

#### **Type Selector (Element Selector)**

**What it does:** Selects all elements of a specific type.

**Syntax:** Just the element name (no symbols)

**Examples:**

```css
p {
  color: gray;
}

h1 {
  font-size: 3rem;
}

a {
  color: hotpink;
}
```

**What gets styled:**

- `p` targets ALL `<p>` elements
- `h1` targets ALL `<h1>` elements
- `a` targets ALL `<a>` elements

**When to use:** When you want every instance of an element to look the same.

---

#### **Class Selector**

**What it does:** Selects all elements with a specific class.

**Syntax:** `.classname` (starts with a dot)

**HTML:**

```html
<p class="highlight">This paragraph is highlighted.</p>
<p>This paragraph is not.</p>
<div class="highlight">This div is also highlighted.</div>
```

**CSS:**

```css
.highlight {
  background-color: yellow;
}
```

**What gets styled:** Both the `<p>` and `<div>` with `class="highlight"`

**Key points:**

- Classes are reusable—multiple elements can have the same class
- An element can have multiple classes: `<p class="highlight important">`
- Class names are case-sensitive: `.Highlight` ≠ `.highlight`

**When to use:** When you want to style specific elements, not all elements of a type.

---

#### **ID Selector**

**What it does:** Selects ONE element with a specific ID.

**Syntax:** `#idname` (starts with a hash)

**HTML:**

```html
<header id="main-header">Site Header</header>
```

**CSS:**

```css
#main-header {
  background-color: black;
  color: white;
}
```

**Key points:**

- IDs must be unique—only ONE element per page can have a specific ID
- ID selectors have very high specificity (we'll cover this later)

**⚠️ Important:** In modern web development, **avoid using ID selectors for styling**. Use classes instead.

**Why?**

- IDs are typically reserved for JavaScript functionality
- ID selectors are hard to override due to high specificity
- Classes are more flexible and reusable

**When to use IDs:** For JavaScript hooks, anchor links, or form labels—NOT for styling.

---

#### **Universal Selector**

**What it does:** Selects ALL elements.

**Syntax:** `*`

**Example:**

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

This applies to every single element on the page.

**When to use:**

- CSS resets (like removing default margins/padding)
- Setting `box-sizing: border-box` globally

**⚠️ Warning:** Don't use `*` for general styling—it's slow and usually overkill.

---

### **Level 2: Combining Selectors 🟡**

Now we combine basic selectors to target elements more precisely.

#### **Grouping Selectors (Comma)**

**What it does:** Applies the same styles to multiple selectors.

**Syntax:** `selector1, selector2, selector3`

**Example:**

```css
h1,
h2,
h3 {
  color: blue;
  font-family: Arial, sans-serif;
}
```

All headings (`h1`, `h2`, `h3`) get the same color and font.

**When to use:** When multiple elements need identical styles (DRY principle—Don't Repeat Yourself).

---

#### **Descendant Combinator (Space)**

**What it does:** Selects elements that are descendants (children, grandchildren, etc.) of another element.

**Syntax:** `parent child` (separated by a space)

**HTML:**

```html
<article>
  <p>I get styled.</p>
  <div>
    <p>I also get styled (I'm a grandchild).</p>
  </div>
</article>

<p>I don't get styled (not inside article).</p>
```

**CSS:**

```css
article p {
  color: gray;
}
```

This styles ALL `<p>` elements inside `<article>`, no matter how deeply nested.

**When to use:** When you want to style elements only within a specific container.

---

#### **Direct Child Combinator (>)**

**What it does:** Selects only DIRECT children (not grandchildren).

**Syntax:** `parent > child`

**HTML:**

```html
<article>
  <p>I get styled (direct child).</p>
  <div>
    <p>I DON'T get styled (grandchild).</p>
  </div>
</article>
```

**CSS:**

```css
article > p {
  color: gray;
}
```

Only the first `<p>` (direct child of `<article>`) gets styled.

**Descendant vs Direct Child:**

| Combinator    | Selects                                  | Example                                      |
| ------------- | ---------------------------------------- | -------------------------------------------- |
| `article p`   | All `<p>` inside `<article>` (any depth) | Children, grandchildren, great-grandchildren |
| `article > p` | Only direct children of `<article>`      | Just children                                |

---

### **Level 3: Attribute Selectors 🟠**

Select elements based on their attributes.

#### **Basic Attribute Selector**

**Syntax:** `[attribute]`

**Example:**

```css
[type] {
  border: 1px solid gray;
}
```

**HTML:**

```html
<input type="text" />
<!-- Gets styled -->
<input type="email" />
<!-- Gets styled -->
<input />
<!-- NOT styled (no type attribute) -->
```

Selects all elements that have a `type` attribute, regardless of its value.

---

#### **Attribute Value Selector**

**Syntax:** `[attribute="value"]`

**Example:**

```css
[type="text"] {
  border: 2px solid blue;
}
```

**HTML:**

```html
<input type="text" />
<!-- Gets styled -->
<input type="email" />
<!-- NOT styled -->
```

Selects only elements where `type` exactly equals `"text"`.

---

#### **Practical Use Case**

```css
/* Style password inputs differently */
input[type="password"] {
  border-color: red;
  background-color: lightyellow;
}

/* Style email inputs */
input[type="email"] {
  border-color: blue;
}
```

**When to use:** When you need to target specific form inputs or elements with specific attributes.

---

### **Level 4: Pseudo-Classes 🔵**

Pseudo-classes select elements in a specific **state**.

**Syntax:** `selector:pseudo-class`

#### **`:hover` - Mouse Hover State**

**Example:**

```css
a:hover {
  color: hotpink;
  text-decoration: underline;
}
```

The link changes color and gets underlined when you hover over it with your mouse.

---

#### **`:focus` - Keyboard/Click Focus State**

**Example:**

```css
input:focus {
  border: 2px solid blue;
  outline: none;
}
```

When you click into an input field or tab to it with your keyboard, the border turns blue.

**When to use:** For interactive elements like links, buttons, and form inputs.

---

#### **Other Common Pseudo-Classes**

| Pseudo-Class     | Selects                      | Example                                 |
| ---------------- | ---------------------------- | --------------------------------------- |
| `:active`        | Element being clicked        | `button:active { background: gray; }`   |
| `:visited`       | Links that have been clicked | `a:visited { color: purple; }`          |
| `:first-child`   | First child of its parent    | `li:first-child { font-weight: bold; }` |
| `:last-child`    | Last child of its parent     | `li:last-child { border: none; }`       |
| `:nth-child(n)`  | Specific child by position   | `li:nth-child(2) { color: red; }`       |
| `:not(selector)` | Elements that DON'T match    | `p:not(.highlight) { color: gray; }`    |

**Full list:** [MDN Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

---

#### **Pseudo-Classes vs Pseudo-Elements ⚠️**

**This is important:**

| Type               | Syntax            | Purpose                          | Example                                 |
| ------------------ | ----------------- | -------------------------------- | --------------------------------------- |
| **Pseudo-class**   | Single colon `:`  | Selects elements in a **state**  | `:hover`, `:focus`, `:first-child`      |
| **Pseudo-element** | Double colon `::` | Selects a **part** of an element | `::before`, `::after`, `::first-letter` |

**Pseudo-class example:**

```css
a:hover {
  color: hotpink; /* Change link color on hover */
}
```

**Pseudo-element example:**

```css
p::first-letter {
  font-size: 2rem; /* Make first letter bigger */
}
```

**Remember:** One colon = state, two colons = part of element.

---

### **Selector Combinations in Practice 🎯**

Real-world examples combining what we've learned:

#### **Example 1: Style only links inside navigation**

```css
nav a {
  color: white;
  text-decoration: none;
}

nav a:hover {
  color: hotpink;
}
```

#### **Example 2: Style the first paragraph differently**

```css
article p:first-child {
  font-size: 1.2rem;
  font-weight: bold;
}
```

#### **Example 3: Style specific input types**

```css
input[type="text"],
input[type="email"] {
  border: 1px solid gray;
  padding: 0.5rem;
}

input[type="text"]:focus,
input[type="email"]:focus {
  border-color: blue;
}
```

---

### **Selector Specificity Preview 🔍**

When multiple selectors target the same element, which one wins?

**Quick hierarchy (from weakest to strongest):**

1. Type selectors: `p`
2. Class selectors: `.highlight`
3. ID selectors: `#header`

**Example:**

```css
p {
  color: gray;
} /* Specificity: 0-0-1 */
.highlight {
  color: yellow;
} /* Specificity: 0-1-0 */
#special {
  color: red;
} /* Specificity: 1-0-0 */
```

```html
<p class="highlight" id="special">What color am I?</p>
```

**Answer:** Red (ID selector wins).

We'll dive deep into specificity in the next section.

---

### **When to Use Which Selector? 🤷**

| Selector                    | Use When                                         |
| --------------------------- | ------------------------------------------------ |
| Type (`p`, `h1`)            | Styling ALL instances of an element              |
| Class (`.button`)           | Styling specific elements, reusable styles       |
| ID (`#header`)              | JavaScript hooks or anchor links—NOT for styling |
| Attribute (`[type="text"]`) | Targeting specific form inputs or attributes     |
| Pseudo-class (`:hover`)     | Styling interactive states                       |
| Combinators (`nav a`)       | Targeting elements within specific containers    |
