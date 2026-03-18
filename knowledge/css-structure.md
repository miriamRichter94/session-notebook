# CSS Structure

- [What is CSS Structure & Why It Matters 🏗️](#what-is-css-structure--why-it-matters-️)
  - [The Problem: CSS That "Works" But Is a Mess 😰](#the-problem-css-that-works-but-is-a-mess-)
  - [What Good Structure Solves ✅](#what-good-structure-solves-)
  - [What CSS Structure Includes 📋](#what-css-structure-includes-)
  - [The Difference: Unstructured vs Structured CSS 🆚](#the-difference-unstructured-vs-structured-css-)
  - [The Shift in Thinking 🧠](#the-shift-in-thinking-)
  - [Real-World Example: Small vs Large Projects 📊](#real-world-example-small-vs-large-projects-)
  - [What You'll Learn in This Guide 📖](#what-youll-learn-in-this-guide-)
  - [Key Principle: Start Simple, Add Structure as Needed 🎯](#key-principle-start-simple-add-structure-as-needed-)
  - [What Makes This Different from Fundamentals? 🤔](#what-makes-this-different-from-fundamentals-)
  - [You're Ready 🚀](#youre-ready-)
- [File Organization Strategies 📂](#file-organization-strategies-)
  - [Strategy 1: Single File (Simple Projects) 📄](#strategy-1-single-file-simple-projects-)
  - [Strategy 2: Multiple Files (Medium Projects) 📑](#strategy-2-multiple-files-medium-projects-)
  - [Strategy 3: Component-Based (Large Projects) 🗂️](#strategy-3-component-based-large-projects-️)
  - [File Naming Conventions 📝](#file-naming-conventions-)
  - [Folder Structure Best Practices 🗂️](#folder-structure-best-practices-️)
  - [When to Split Files 🤔](#when-to-split-files-)
  - [Performance Considerations ⚡](#performance-considerations-)
  - [Summary: Which Strategy to Use? 🎯](#summary-which-strategy-to-use-)
  - [Real-World Example 💼](#real-world-example-)
- [Importing Stylesheets 📥](#importing-stylesheets-)
  - [Method 1: Multiple `<link>` Tags (HTML) 🔗](#method-1-multiple-link-tags-html-)
  - [Method 2: `@import` in CSS 📥](#method-2-import-in-css-)
  - [Nested Folders with `@import` 📂](#nested-folders-with-import-)
  - [Combining Both Methods 🔀](#combining-both-methods-)
  - [Which Method to Use? 🤔](#which-method-to-use-)
  - [Performance: `<link>` vs `@import` ⚡](#performance-link-vs-import-)
  - [Common Mistakes 🐞](#common-mistakes-)
  - [Build Tools & Production 🛠️](#build-tools--production-️)
  - [Practical Example 💼](#practical-example-)
  - [Key Takeaways 💡](#key-takeaways-)
- [The DRY Principle ♻️](#the-dry-principle-️)
  - [What is the DRY Principle? 🤔](#what-is-the-dry-principle-)
  - [Why Repetition is Bad ❌](#why-repetition-is-bad-)
  - [Technique 1: Group Selectors 🎯](#technique-1-group-selectors-)
  - [Technique 2: Extract Common Styles into Base Classes 📦](#technique-2-extract-common-styles-into-base-classes-)
  - [Technique 3: Use CSS Variables 🔧](#technique-3-use-css-variables-)
  - [Technique 4: Create Utility Classes 🛠️](#technique-4-create-utility-classes-️)
  - [Real-World Example: Buttons 🔘](#real-world-example-buttons-)
  - [Real-World Example: Spacing System 📏](#real-world-example-spacing-system-)
  - [When NOT to Use DRY 🚫](#when-not-to-use-dry-)
  - [DRY Checklist ✅](#dry-checklist-)
  - [Practical Workflow 🛠️](#practical-workflow-️)
  - [Key Takeaways 💡](#key-takeaways--1)
- [Naming Conventions 🏷️](#naming-conventions-️)
  - [The Naming Problem 😰](#the-naming-problem-)
  - [Basic Naming Rules 📏](#basic-naming-rules-)
  - [Kebab-Case: The Standard 🔤](#kebab-case-the-standard-)
  - [BEM: Block Element Modifier 🧱](#bem-block-element-modifier-)
  - [When to Use BEM vs Simple Naming 🤷](#when-to-use-bem-vs-simple-naming-)
  - [Common BEM Mistakes 🐞](#common-bem-mistakes-)
  - [Alternative: Simplified BEM](#alternative-simplified-bem)
  - [Real-World Example: Alert Component](#real-world-example-alert-component)
  - [Naming Convention Decision Guide 🎯](#naming-convention-decision-guide-)
  - [Key Takeaways 💡](#key-takeaways--2)
- [CSS Custom Properties (Variables) 🔧](#css-custom-properties-variables-)
  - [The Problem: Repeating Values 🔁](#the-problem-repeating-values-)
  - [Defining Variables 📝](#defining-variables-)
  - [Where to Define Variables: `:root` 🌳](#where-to-define-variables-root-)
  - [Using Variables 🎯](#using-variables-)
  - [Common Use Cases 💼](#common-use-cases-)
  - [Variable Scope 🔍](#variable-scope-)
  - [Fallback Values 🛟](#fallback-values-)
  - [Practical Example: Complete Color System 🎨](#practical-example-complete-color-system-)
  - [Practical Example: Dark Mode 🌓](#practical-example-dark-mode-)
  - [Organizing Variables 🗂️](#organizing-variables-️)
  - [Naming Convention for Variables 🏷️](#naming-convention-for-variables-️)
  - [Common Mistakes 🐞](#common-mistakes--1)
  - [Key Takeaways 💡](#key-takeaways--4)
- [Commenting Your CSS 💬](#commenting-your-css-)
  - [Why Comments Matter 📝](#why-comments-matter-)
  - [Comment Syntax 📐](#comment-syntax-)
  - [When to Comment 🤔](#when-to-comment-)
  - [Comment Styles for Sections 🎨](#comment-styles-for-sections-)
  - [Organizing CSS with Comments 📂](#organizing-css-with-comments-)
  - [Component Documentation 📦](#component-documentation-)
  - [When NOT to Comment 🚫](#when-not-to-comment-)
  - [Practical Examples 💼](#practical-examples-)
  - [Team Collaboration Comments 👥](#team-collaboration-comments-)
  - [Comments for Debugging 🔍](#comments-for-debugging-)
  - [Common Mistakes 🐞](#common-mistakes--2)
  - [Quick Reference: Comment Template 📋](#quick-reference-comment-template-)
  - [Key Takeaways 💡](#key-takeaways--5)
- [Custom Fonts & Web Fonts 🔤](#custom-fonts--web-fonts-)
  - [What are Web Fonts? 🤔](#what-are-web-fonts-)
  - [Why Use Web Fonts? 🎨](#why-use-web-fonts-)
  - [Method 1: Google Fonts (Easiest) 🔥](#method-1-google-fonts-easiest-)
  - [Method 2: Self-Hosted Fonts (@font-face) 📦](#method-2-self-hosted-fonts-font-face-)
  - [Font Formats & Browser Support 🌐](#font-formats--browser-support-)
  - [Performance Considerations ⚡](#performance-considerations--1)
  - [Common Mistakes 🐞](#common-mistakes--3)
  - [Google Fonts vs Self-Hosted: Which to Use? 🤔](#google-fonts-vs-self-hosted-which-to-use-)
  - [Practical Example: Complete Setup 💼](#practical-example-complete-setup-)
  - [Key Takeaways 💡](#key-takeaways--6)
- [Quick Reference 📚](#quick-reference-)
  - [File Organization Patterns](#file-organization-patterns)
  - [Importing Stylesheets](#importing-stylesheets)
  - [Naming Conventions](#naming-conventions)
  - [CSS Variables](#css-variables)
  - [Common Variable Patterns](#common-variable-patterns)
  - [Comment Formats](#comment-formats)
  - [Google Fonts Setup](#google-fonts-setup)
  - [Self-Hosted Fonts](#self-hosted-fonts)
  - [Useful Code Snippets](#useful-code-snippets)
  - [DRY Principle Patterns](#dry-principle-patterns)
  - [File Organization Decision Guide](#file-organization-decision-guide)
  - [Import Order](#import-order)
  - [Common Mistakes to Avoid 🐞](#common-mistakes-to-avoid-)
  - [Quick Checklist for New Projects ✅](#quick-checklist-for-new-projects-)
  - [Helpful Resources](#helpful-resources)

---

## **What is CSS Structure & Why It Matters 🏗️**

You've learned how to write CSS. Now it's time to learn how to **organize** CSS.

**CSS structure** refers to how you organize, name, and maintain your stylesheets. It's the difference between CSS that works and CSS that's maintainable.

---

### **The Problem: CSS That "Works" But Is a Mess 😰**

Here's a real scenario:

**Week 1:** You build a website. Your CSS file has 200 lines. Everything works great.

**Week 4:** You add more features. Your CSS file now has 800 lines. You start scrolling to find things.

**Week 8:** Your CSS file has 1500 lines. You're not sure which rules are still being used. You're afraid to delete anything because something might break.

**Week 12:** A teammate joins the project. They ask "Where should I add styles for the navigation menu?" You're not sure anymore.

**This is what happens without structure.**

---

### **What Good Structure Solves ✅**

**Good CSS structure makes your code:**

1. **Maintainable** - Easy to update and modify
2. **Scalable** - Grows cleanly as your project grows
3. **Collaborative** - Other developers can understand and contribute
4. **Debuggable** - Easy to find and fix issues
5. **Reusable** - Styles can be shared across projects

---

### **What CSS Structure Includes 📋**

**Organizing your CSS means thinking about:**

1. **File structure** - Should everything be in one file? Multiple files? How should they be organized?
2. **Import strategy** - How do you connect multiple CSS files?
3. **Naming conventions** - How do you name classes consistently?
4. **Code organization** - How do you group related styles?
5. **Variables** - How do you avoid repeating values like colors and sizes?
6. **Comments** - How do you document your CSS so others (and future you) understand it?

---

### **The Difference: Unstructured vs Structured CSS 🆚**

**Unstructured CSS (hard to maintain):**

```css
/* Everything in one file, no organization */

.btn {
  background-color: #3498db;
  color: white;
  padding: 10px 20px;
}

.header {
  background-color: #2c3e50;
}

.card {
  border: 1px solid #e0e0e0;
  padding: 20px;
}

.btn-red {
  background-color: #e74c3c;
  color: white;
  padding: 10px 20px;
}

.footer {
  background-color: #2c3e50;
}

/* 1500 more lines... */
```

**Problems:**

- No clear organization (buttons, headers, cards all mixed together)
- Repeated values (`#2c3e50` used twice, `padding: 10px 20px` repeated)
- Inconsistent naming (`.btn` vs `.btn-red`)
- Hard to find specific styles
- No documentation

---

**Structured CSS (easy to maintain):**

```css
/* Variables for reusable values */
:root {
  --color-primary: #3498db;
  --color-danger: #e74c3c;
  --color-dark: #2c3e50;
  --spacing-md: 10px 20px;
}

/* ======================
   Buttons
   ====================== */

.button {
  padding: var(--spacing-md);
  border: none;
  cursor: pointer;
}

.button--primary {
  background-color: var(--color-primary);
  color: white;
}

.button--danger {
  background-color: var(--color-danger);
  color: white;
}

/* ======================
   Layout
   ====================== */

.header,
.footer {
  background-color: var(--color-dark);
  color: white;
}

/* ======================
   Components
   ====================== */

.card {
  border: 1px solid #e0e0e0;
  padding: 20px;
}
```

**Benefits:**

- Variables eliminate repetition
- Clear sections with comments
- Consistent naming convention (BEM-style)
- Easy to find and modify specific components
- Values can be changed in one place (variables)

---

### **The Shift in Thinking 🧠**

**When you're learning CSS:**

- Focus: "How do I make this element blue?"
- Goal: Make it work

**When you're structuring CSS:**

- Focus: "How do I organize my styles so they're easy to maintain?"
- Goal: Make it scalable

**Both are important.** You need to know how to write CSS (fundamentals), and you need to know how to organize it (structure).

---

### **Real-World Example: Small vs Large Projects 📊**

**Small project (personal portfolio):**

- One CSS file (500 lines)
- Basic organization with comments
- Minimal variables

**This is fine.** Small projects don't need complex structure.

---

**Large project (e-commerce site):**

- Multiple CSS files organized by purpose
- Global variables for colors, spacing, fonts
- Consistent naming conventions across 50+ components
- Documented with comments
- Team of 5+ developers

**Structure is critical.** Without it, the project becomes unmaintainable.

---

### **What You'll Learn in This Guide 📖**

This guide covers:

1. **How to organize CSS files** - Single file vs multiple files, folder structures
2. **How to import stylesheets** - Connecting multiple CSS files
3. **The DRY principle** - Avoiding repetition in your code
4. **Naming conventions** - Consistent, predictable class names (including BEM)
5. **CSS variables** - Creating reusable values for colors, spacing, etc.
6. **Commenting strategies** - Writing helpful documentation
7. **Custom fonts** - Adding web fonts to your projects
8. **Real project structures** - Examples from actual projects

---

### **Key Principle: Start Simple, Add Structure as Needed 🎯**

**Don't over-engineer small projects.**

- Portfolio site? One CSS file is fine.
- Adding more pages? Maybe split into 2-3 files.
- Building a web app with a team? Use full structure.

**Start simple. Add structure when the project demands it.**

---

### **What Makes This Different from Fundamentals? 🤔**

**CSS Fundamentals** taught you:

- How to write CSS syntax
- What selectors, properties, and values are
- How the cascade and specificity work

**CSS Structure** teaches you:

- How to organize CSS in real projects
- How to make CSS maintainable
- How to work with CSS as part of a team
- How to scale CSS as projects grow

**Think of it this way:**

- Fundamentals = Grammar and vocabulary
- Structure = How to write a well-organized essay

Both are essential.

---

### **You're Ready 🚀**

You know how to write CSS. Now you'll learn how to write **good** CSS. Code that's clean, organized, and maintainable.

Let's get started.

---

## **File Organization Strategies 📂**

How you organize your CSS files affects how easy your project is to maintain. Let's look at different approaches and when to use each one.

---

### **Strategy 1: Single File (Simple Projects) 📄**

**When to use:**

- Small projects (1-5 pages)
- Personal portfolios
- Simple landing pages
- Learning projects

**Structure:**

```
my-project/
├── index.html
└── styles.css
```

**Example `styles.css`:**

```css
/* ======================
   Variables
   ====================== */
:root {
  --color-primary: #3498db;
  --color-dark: #2c3e50;
}

/* ======================
   Base Styles
   ====================== */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  line-height: 1.6;
}

/* ======================
   Navigation
   ====================== */
.nav {
  background-color: var(--color-dark);
}

/* ======================
   Components
   ====================== */
.button {
  background-color: var(--color-primary);
  color: white;
  padding: 10px 20px;
}

.card {
  border: 1px solid #ddd;
  padding: 20px;
}

/* ======================
   Footer
   ====================== */
.footer {
  background-color: var(--color-dark);
  color: white;
}
```

**Pros:**

- ✅ Simple to manage
- ✅ No import complexity
- ✅ Fast to set up

**Cons:**

- ❌ Gets unwieldy above ~500 lines
- ❌ Hard to find specific styles in large files
- ❌ Everything loads even if not used on the page

---

### **Strategy 2: Multiple Files (Medium Projects) 📑**

**When to use:**

- Multi-page websites (5-20 pages)
- Projects with distinct sections
- When your CSS file exceeds ~500 lines

**Structure:**

```
my-project/
├── index.html
└── css/
    ├── base.css       (reset, typography, global styles)
    ├── layout.css     (header, footer, grid, containers)
    ├── components.css (buttons, cards, forms)
    └── pages.css      (page-specific styles)
```

**How to link them:**

```html
<head>
  <link rel="stylesheet" href="css/base.css" />
  <link rel="stylesheet" href="css/layout.css" />
  <link rel="stylesheet" href="css/components.css" />
  <link rel="stylesheet" href="css/pages.css" />
</head>
```

**What goes in each file:**

**`base.css` - Foundation:**

```css
/* CSS reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Typography */
body {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  color: #333;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  margin-bottom: 1rem;
}

/* Links */
a {
  color: #3498db;
  text-decoration: none;
}
```

**`layout.css` - Page structure:**

```css
/* Header */
.header {
  background-color: #2c3e50;
  color: white;
  padding: 1rem;
}

/* Navigation */
.nav {
  display: flex;
  gap: 1rem;
}

/* Main container */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

/* Footer */
.footer {
  background-color: #2c3e50;
  color: white;
  padding: 2rem;
  text-align: center;
}
```

**`components.css` - Reusable UI elements:**

```css
/* Buttons */
.button {
  padding: 10px 20px;
  border: none;
  cursor: pointer;
}

.button--primary {
  background-color: #3498db;
  color: white;
}

/* Cards */
.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
}

/* Forms */
.input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
}
```

**`pages.css` - Page-specific styles:**

```css
/* Home page hero */
.home-hero {
  background-image: url("../images/hero.jpg");
  height: 500px;
}

/* About page team section */
.about-team {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

/* Contact page form */
.contact-form {
  max-width: 600px;
  margin: 0 auto;
}
```

**Pros:**

- ✅ Easier to find specific styles
- ✅ Better organization
- ✅ Can load only needed files per page (optional)

**Cons:**

- ❌ Multiple HTTP requests (can impact performance)
- ❌ Need to maintain multiple files

---

### **Strategy 3: Component-Based (Large Projects) 🗂️**

**When to use:**

- Large applications (20+ pages)
- Component-heavy projects
- Team projects
- When using build tools

**Structure:**

```
my-project/
├── index.html
└── css/
    ├── base/
    │   ├── reset.css
    │   ├── typography.css
    │   └── variables.css
    ├── layout/
    │   ├── header.css
    │   ├── footer.css
    │   ├── grid.css
    │   └── containers.css
    ├── components/
    │   ├── buttons.css
    │   ├── cards.css
    │   ├── forms.css
    │   ├── modals.css
    │   └── navigation.css
    ├── pages/
    │   ├── home.css
    │   ├── about.css
    │   └── contact.css
    └── main.css (imports all files)
```

**`main.css` - Master file:**

```css
/* Import base styles first */
@import "base/variables.css";
@import "base/reset.css";
@import "base/typography.css";

/* Import layout */
@import "layout/header.css";
@import "layout/footer.css";
@import "layout/grid.css";
@import "layout/containers.css";

/* Import components */
@import "components/buttons.css";
@import "components/cards.css";
@import "components/forms.css";
@import "components/modals.css";
@import "components/navigation.css";

/* Import page-specific styles */
@import "pages/home.css";
@import "pages/about.css";
@import "pages/contact.css";
```

**HTML:**

```html
<head>
  <!-- Only link the main file -->
  <link rel="stylesheet" href="css/main.css" />
</head>
```

**Example component file - `components/buttons.css`:**

```css
/* ======================
   Buttons Component
   ====================== */

.button {
  display: inline-block;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
}

.button--primary {
  background-color: var(--color-primary);
  color: white;
}

.button--primary:hover {
  background-color: var(--color-primary-dark);
}

.button--secondary {
  background-color: var(--color-secondary);
  color: white;
}

.button--large {
  padding: 15px 30px;
  font-size: 1.2rem;
}

.button--small {
  padding: 5px 10px;
  font-size: 0.875rem;
}
```

**Pros:**

- ✅ Extremely organized
- ✅ Easy to find and modify specific components
- ✅ Great for team collaboration
- ✅ Each component is self-contained

**Cons:**

- ❌ More complex setup
- ❌ Requires understanding @import
- ❌ May need build tools for production

---

### **File Naming Conventions 📝**

**Consistent naming makes files easy to find.**

**Common patterns:**

**Lowercase with hyphens (kebab-case):**

```
base.css
typography.css
button-component.css
home-page.css
```

**Descriptive names:**

```
✅ Good:
- navigation.css
- product-card.css
- contact-form.css

❌ Bad:
- styles2.css
- new.css
- temp.css
```

**Category prefixes (optional):**

```
base-reset.css
base-typography.css
component-button.css
component-card.css
page-home.css
page-about.css
```

---

### **Folder Structure Best Practices 🗂️**

**Keep it consistent:**

**Option 1: Flat structure (simple projects)**

```
css/
├── base.css
├── layout.css
├── components.css
└── pages.css
```

**Option 2: Categorized folders (medium projects)**

```
css/
├── base/
├── layout/
├── components/
└── pages/
```

**Option 3: Full organization (large projects)**

```
assets/
├── css/
│   ├── base/
│   ├── layout/
│   ├── components/
│   └── pages/
├── images/
├── fonts/
└── js/
```

---

### **When to Split Files 🤔**

**Signs you should split your CSS:**

1. **File exceeds 500-1000 lines** - Getting hard to navigate
2. **You're scrolling to find things** - Organization is lacking
3. **Multiple developers** - Need clear separation of concerns
4. **Distinct page sections** - Header, footer, components are clearly separate
5. **You're duplicating code** - Same patterns repeated across sections

**Don't split just to split.** Only add complexity when it solves a real problem.

---

### **Performance Considerations ⚡**

**Multiple `<link>` tags:**

```html
<link rel="stylesheet" href="base.css" />
<link rel="stylesheet" href="layout.css" />
<link rel="stylesheet" href="components.css" />
```

**Impact:** Multiple HTTP requests (can slow down page load)

**Solution for production:**

- Use build tools to combine files into one
- Or use `@import` in a main file (covered in next section)

**For learning/development:** Multiple files are fine. Optimize for production later.

---

### **Summary: Which Strategy to Use? 🎯**

| Project Type                     | Strategy        | File Count |
| -------------------------------- | --------------- | ---------- |
| Personal portfolio, landing page | Single file     | 1          |
| Small website (5-10 pages)       | Multiple files  | 3-5        |
| Medium website (10-20 pages)     | Multiple files  | 5-10       |
| Large application, team project  | Component-based | 10-30+     |

**Golden rule:** Use the simplest structure that keeps your project organized.

---

### **Real-World Example 💼**

**Project:** E-commerce website

**Structure:**

```
css/
├── base/
│   ├── variables.css    (colors, spacing, fonts)
│   ├── reset.css        (CSS reset)
│   └── typography.css   (font styles)
├── layout/
│   ├── header.css       (site header)
│   ├── footer.css       (site footer)
│   └── grid.css         (grid system)
├── components/
│   ├── buttons.css      (button styles)
│   ├── product-card.css (product display)
│   ├── cart.css         (shopping cart)
│   └── forms.css        (form inputs)
├── pages/
│   ├── home.css         (homepage specific)
│   ├── product.css      (product page)
│   └── checkout.css     (checkout page)
└── main.css             (imports everything)
```

**Why this works:**

- Clear separation of concerns
- Easy for team to work on different components
- Components are reusable across pages
- Easy to find and modify specific styles

---

## **Importing Stylesheets 📥**

When you have multiple CSS files, you need a way to connect them. There are two main approaches: multiple `<link>` tags in HTML, or `@import` in CSS.

Let's look at both and when to use each.

---

### **Method 1: Multiple `<link>` Tags (HTML) 🔗**

**How it works:**

Add multiple `<link>` tags in your HTML `<head>`.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>My Site</title>

    <!-- Link multiple CSS files -->
    <link rel="stylesheet" href="css/base.css" />
    <link rel="stylesheet" href="css/layout.css" />
    <link rel="stylesheet" href="css/components.css" />
    <link rel="stylesheet" href="css/pages.css" />
  </head>
  <body>
    <!-- Your content -->
  </body>
</html>
```

---

**How files are loaded:**

The browser loads all CSS files **in parallel** (at the same time), but applies them **in order** (top to bottom).

```
Browser requests:
┌─────────────┐
│  base.css   │  ← Request 1
├─────────────┤
│ layout.css  │  ← Request 2
├─────────────┤
│components.css│ ← Request 3
├─────────────┤
│ pages.css   │  ← Request 4
└─────────────┘

All requests happen simultaneously (parallel)
Styles applied in order: base → layout → components → pages
```

**Order matters:**

```html
<!-- Correct order -->
<link rel="stylesheet" href="css/base.css" />
<!-- Foundation -->
<link rel="stylesheet" href="css/layout.css" />
<!-- Structure -->
<link rel="stylesheet" href="css/components.css" /><!-- UI elements -->
<link rel="stylesheet" href="css/pages.css" />
<!-- Page-specific -->
```

**Why this order?**

1. **Base** sets defaults for everything
2. **Layout** builds on base styles
3. **Components** build on layout
4. **Pages** override components when needed

---

**Pros:**

- ✅ Simple and straightforward
- ✅ Files load in parallel (faster)
- ✅ Easy to debug (clear in HTML)
- ✅ Each HTML page can load only needed files

**Cons:**

- ❌ Multiple HTTP requests (can slow page load)
- ❌ Have to manage links in every HTML file
- ❌ Can't conditionally load based on CSS logic

---

### **Method 2: `@import` in CSS 📥**

**How it works:**

Create one main CSS file that imports other files using `@import`.

**Example:**

**File structure:**

```
css/
├── base.css
├── layout.css
├── components.css
├── pages.css
└── main.css  ← Master file
```

**`main.css`:**

```css
/* Import all CSS files */
@import "base.css";
@import "layout.css";
@import "components.css";
@import "pages.css";
```

**HTML:**

```html
<head>
  <!-- Link only the main file -->
  <link rel="stylesheet" href="css/main.css" />
</head>
```

---

**`@import` Syntax:**

<!-- prettier-ignore -->
```css
/* Basic import */
@import 'filename.css';

/* With quotes (single or double) */
@import "filename.css";

/* With url() */
@import url('filename.css');

/* Relative paths */
@import '../styles/base.css';
@import './components/button.css';

/* Absolute URL */
@import 'https://example.com/styles.css';
```

---

**Import Order Matters:**

```css
/* main.css */

/* ALWAYS import in this order */

/* 1. Variables first (other files may use them) */
@import "base/variables.css";

/* 2. Resets and base styles */
@import "base/reset.css";
@import "base/typography.css";

/* 3. Layout */
@import "layout/header.css";
@import "layout/footer.css";

/* 4. Components */
@import "components/buttons.css";
@import "components/cards.css";

/* 5. Page-specific (overrides components if needed) */
@import "pages/home.css";
@import "pages/about.css";
```

**Why this order?**

- Variables must come first (other files reference them)
- Base styles set defaults
- Components build on base
- Pages can override components

---

**How `@import` loads files:**

Unlike `<link>` tags, `@import` loads files **sequentially** (one after another).

```
Browser:
1. Loads main.css
2. Sees @import 'base.css'
3. Pauses, fetches base.css
4. Sees @import 'layout.css'
5. Pauses, fetches layout.css
6. Continues for each import...
```

**This is slower than parallel loading with `<link>` tags.**

---

**Pros:**

- ✅ One `<link>` tag in HTML
- ✅ CSS stays organized in one master file
- ✅ Easy to add/remove files (just edit main.css)
- ✅ Better for component-based organization

**Cons:**

- ❌ Loads sequentially (slower than parallel)
- ❌ Delays page rendering
- ❌ More difficult to debug (imports hidden in CSS)

---

### **Nested Folders with `@import` 📂**

When using folders, adjust paths accordingly.

**Structure:**

```
css/
├── base/
│   ├── variables.css
│   ├── reset.css
│   └── typography.css
├── components/
│   ├── buttons.css
│   └── cards.css
└── main.css
```

**`main.css`:**

```css
/* Import from folders */
@import "base/variables.css";
@import "base/reset.css";
@import "base/typography.css";

@import "components/buttons.css";
@import "components/cards.css";
```

**OR if main.css is inside css/ folder:**

```css
/* If main.css is at same level as folders */
@import "./base/variables.css";
@import "./components/buttons.css";
```

---

### **Combining Both Methods 🔀**

You can use both approaches together.

**Example:**

**HTML:**

```html
<head>
  <!-- Critical CSS loaded with link tags (parallel) -->
  <link rel="stylesheet" href="css/base.css" />
  <link rel="stylesheet" href="css/layout.css" />

  <!-- Additional CSS loaded with @import -->
  <link rel="stylesheet" href="css/components.css" />
</head>
```

**`components.css`:**

```css
/* This file imports other component files */
@import "components/buttons.css";
@import "components/cards.css";
@import "components/forms.css";
```

**When to do this:**

- Load critical CSS with `<link>` (faster)
- Group related files with `@import`

---

### **Which Method to Use? 🤔**

#### **Use Multiple `<link>` Tags When:**

- ✅ You have 3-5 CSS files
- ✅ Performance is critical
- ✅ Each HTML page needs different CSS files
- ✅ You're learning (easier to understand)

**Example use case:** Multi-page website where each page has unique styles.

```html
<!-- homepage.html -->
<link rel="stylesheet" href="css/base.css" />
<link rel="stylesheet" href="css/layout.css" />
<link rel="stylesheet" href="css/home.css" />

<!-- about.html -->
<link rel="stylesheet" href="css/base.css" />
<link rel="stylesheet" href="css/layout.css" />
<link rel="stylesheet" href="css/about.css" />
```

---

#### **Use `@import` When:**

- ✅ You have 10+ CSS files
- ✅ You want component-based organization
- ✅ You're using build tools (they optimize imports)
- ✅ You want centralized CSS management

**Example use case:** Large application with many components.

```css
/* main.css - imports everything */
@import "base/variables.css";
@import "base/reset.css";
@import "components/button.css";
@import "components/card.css";
@import "components/modal.css";
@import "components/navigation.css";
/* ... 20 more component files */
```

---

### **Performance: `<link>` vs `@import` ⚡**

**Multiple `<link>` tags:**

```
Time to load 4 files (parallel):
┌──────────┐
│ base.css │ ← 100ms
├──────────┤
│layout.css│ ← 100ms  } All at once
├──────────┤
│comp.css  │ ← 100ms
├──────────┤
│pages.css │ ← 100ms
└──────────┘
Total time: ~100ms (files load simultaneously)
```

**`@import`:**

```
Time to load 4 files (sequential):
┌──────────┐
│ base.css │ ← 100ms
└──────────┘
     ↓
┌──────────┐
│layout.css│ ← 100ms  } One after another
└──────────┘
     ↓
┌──────────┐
│comp.css  │ ← 100ms
└──────────┘
     ↓
┌──────────┐
│pages.css │ ← 100ms
└──────────┘
Total time: ~400ms (files load one by one)
```

**Winner:** `<link>` tags are faster.

---

**But...**

**In production, you should combine all CSS into one file anyway** (using build tools). So for development, use whatever method makes your code more organized.

---

### **Common Mistakes 🐞**

#### **Mistake 1: `@import` after other CSS**

```css
/* Wrong - @import must come first */
body {
  margin: 0;
}

@import "base.css"; /* Won't work! */
```

**`@import` must be at the top of the file**, before any other CSS rules.

```css
/* Correct */
@import "base.css";

body {
  margin: 0;
}
```

---

#### **Mistake 2: Wrong file paths**

```css
/* Wrong - file is in base/ folder */
@import "variables.css";

/* Correct */
@import "base/variables.css";
```

**Always check:** Where is the importing file, and where is the imported file?

---

#### **Mistake 3: Circular imports**

```css
/* file-a.css */
@import "file-b.css";

/* file-b.css */
@import "file-a.css"; /* Circular! */
```

**This creates an infinite loop.** Don't import files that import each other.

---

#### **Mistake 4: Forgetting quotes**

```css
/* Wrong */
@import base.css;

/* Correct */
@import "base.css";
```

**Quotes are required** around the filename.

---

### **Build Tools & Production 🛠️**

**In production, you should:**

1. **Combine all CSS files into one** (reduces HTTP requests)
2. **Minify CSS** (removes whitespace, reduces file size)

**Tools that do this:**

- Webpack
- Vite
- Parcel
- Gulp

**For now:** Focus on organization during development. Learn build tools later when you need them.

---

### **Practical Example 💼**

**Project:** Blog website

**Development structure:**

```
css/
├── base/
│   ├── variables.css
│   ├── reset.css
│   └── typography.css
├── layout/
│   ├── header.css
│   └── footer.css
├── components/
│   ├── post-card.css
│   ├── sidebar.css
│   └── comments.css
└── main.css
```

**`main.css`:**

```css
@import "base/variables.css";
@import "base/reset.css";
@import "base/typography.css";
@import "layout/header.css";
@import "layout/footer.css";
@import "components/post-card.css";
@import "components/sidebar.css";
@import "components/comments.css";
```

**HTML:**

```html
<link rel="stylesheet" href="css/main.css" />
```

**For production:** Build tool combines main.css and all imports into one minified file.

---

### **Key Takeaways 💡**

1. **Multiple `<link>` tags** = Fast (parallel loading), simple, good for learning
2. **`@import`** = Better organization, but slower (sequential loading)
3. **`@import` must be at the top** of the CSS file
4. **Order matters** for both methods (base → layout → components → pages)
5. **For production**, combine files into one (using build tools)
6. **For development**, use whatever keeps your code organized

**Recommendation for beginners:** Start with multiple `<link>` tags. Move to `@import` when your project has 10+ files.

---

## **The DRY Principle ♻️**

**DRY = Don't Repeat Yourself**

One of the most important principles in writing maintainable CSS: **avoid repetition**.

---

### **What is the DRY Principle? 🤔**

**The core idea:**

If you're writing the same code multiple times, you're doing it wrong. Extract the repeated code into something reusable.

**In CSS, this means:**

- Don't repeat the same property values
- Don't repeat the same style patterns
- Don't copy-paste entire rule blocks

**Why it matters:**

**Example problem:**

```css
.button-primary {
  background-color: #3498db;
  color: white;
  padding: 10px 20px;
  border-radius: 4px;
}

.button-secondary {
  background-color: #e74c3c;
  color: white;
  padding: 10px 20px;
  border-radius: 4px;
}

.button-success {
  background-color: #2ecc71;
  color: white;
  padding: 10px 20px;
  border-radius: 4px;
}
```

**Issue:** You want to change padding from `10px 20px` to `12px 24px`.

**Without DRY:** Edit 3 places (error-prone, time-consuming)

**With DRY:** Edit 1 place (fast, reliable)

---

### **Why Repetition is Bad ❌**

**1. Hard to maintain**

When you need to change something, you have to find and update every instance.

**2. Increases file size**

Repeated code makes CSS files larger (slower page loads).

**3. Inconsistency**

Easy to miss one instance when updating, leading to inconsistent styles.

**4. Harder to read**

Repetitive code is harder to scan and understand.

---

### **Technique 1: Group Selectors 🎯**

**Problem: Repeating the same styles for multiple elements**

```css
/* Repetitive - same styles written 3 times */
h1 {
  color: #2c3e50;
  font-family: Georgia, serif;
  margin-bottom: 1rem;
}

h2 {
  color: #2c3e50;
  font-family: Georgia, serif;
  margin-bottom: 1rem;
}

h3 {
  color: #2c3e50;
  font-family: Georgia, serif;
  margin-bottom: 1rem;
}
```

**DRY solution: Group selectors**

```css
/* Write once, apply to all */
h1,
h2,
h3 {
  color: #2c3e50;
  font-family: Georgia, serif;
  margin-bottom: 1rem;
}
```

**When to use:** Multiple elements need identical styles.

---

### **Technique 2: Extract Common Styles into Base Classes 📦**

**Problem: Repeating style patterns**

```css
/* Repetitive - same padding and border repeated */
.product-card {
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: white;
}

.user-card {
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: lightblue;
}

.info-card {
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: lightyellow;
}
```

**DRY solution: Extract common base class**

```css
/* Base card styles */
.card {
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
}

/* Specific variations */
.product-card {
  background-color: white;
}

.user-card {
  background-color: lightblue;
}

.info-card {
  background-color: lightyellow;
}
```

**HTML:**

```html
<div class="card product-card">Product</div>
<div class="card user-card">User</div>
<div class="card info-card">Info</div>
```

**Benefits:**

- Change padding once in `.card`, all cards update
- Less code repetition
- Clear inheritance (`.card` = base, others = variations)

---

### **Technique 3: Use CSS Variables 🔧**

**Problem: Repeating the same values**

```css
/* Repetitive - color #3498db repeated 5 times */
.header {
  background-color: #3498db;
}

.button {
  background-color: #3498db;
}

.link {
  color: #3498db;
}

.badge {
  border-color: #3498db;
}

.highlight {
  background-color: #3498db;
}
```

**DRY solution: CSS variables**

```css
/* Define once */
:root {
  --color-primary: #3498db;
}

/* Use everywhere */
.header {
  background-color: var(--color-primary);
}

.button {
  background-color: var(--color-primary);
}

.link {
  color: var(--color-primary);
}

.badge {
  border-color: var(--color-primary);
}

.highlight {
  background-color: var(--color-primary);
}
```

**Now to change the color:** Edit one line in `:root`

**We'll cover CSS variables in depth in [Section 6](#css-custom-properties-variables).**

---

### **Technique 4: Create Utility Classes 🛠️**

**Problem: Repeating common utility patterns**

```css
/* Repetitive - text centering repeated */
.header {
  text-align: center;
  /* other styles */
}

.footer {
  text-align: center;
  /* other styles */
}

.modal {
  text-align: center;
  /* other styles */
}
```

**DRY solution: Utility class**

```css
/* Create reusable utility */
.text-center {
  text-align: center;
}

/* Use where needed */
.header {
  /* other styles */
}

.footer {
  /* other styles */
}

.modal {
  /* other styles */
}
```

**HTML:**

```html
<header class="header text-center">Header</header>
<footer class="footer text-center">Footer</footer>
<div class="modal text-center">Modal</div>
```

**Common utility classes:**

```css
/* Text alignment */
.text-left {
  text-align: left;
}
.text-center {
  text-align: center;
}
.text-right {
  text-align: right;
}

/* Display */
.block {
  display: block;
}
.inline {
  display: inline;
}
.flex {
  display: flex;
}

/* Visibility */
.hidden {
  display: none;
}
.invisible {
  visibility: hidden;
}

/* Spacing (be careful not to overdo this) */
.mt-1 {
  margin-top: 1rem;
}
.mb-1 {
  margin-bottom: 1rem;
}
.p-1 {
  padding: 1rem;
}
```

**When to use:** For truly reusable, single-purpose styles.

**Warning:** Don't go overboard. Too many utility classes can make HTML messy. Use for common patterns only.

---

### **Real-World Example: Buttons 🔘**

**Before DRY (repetitive):**

```css
.btn-primary {
  display: inline-block;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  background-color: #3498db;
  color: white;
}

.btn-secondary {
  display: inline-block;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  background-color: #e74c3c;
  color: white;
}

.btn-success {
  display: inline-block;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  background-color: #2ecc71;
  color: white;
}
```

**After DRY (reusable):**

```css
/* Base button styles (shared) */
.btn {
  display: inline-block;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  color: white;
}

/* Variations (only differences) */
.btn-primary {
  background-color: #3498db;
}

.btn-secondary {
  background-color: #e74c3c;
}

.btn-success {
  background-color: #2ecc71;
}
```

**HTML:**

```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-success">Success</button>
```

**Benefits:**

- Shared styles in one place
- Easy to add new button variants
- Consistent button behavior

---

### **Real-World Example: Spacing System 📏**

**Before DRY (inconsistent):**

```css
.card {
  margin-bottom: 20px;
}

.section {
  margin-bottom: 25px;
}

.post {
  margin-bottom: 30px;
}

.comment {
  margin-bottom: 15px;
}
```

**Issue:** Spacing values are arbitrary and inconsistent.

**After DRY (systematic):**

```css
/* Define spacing scale */
:root {
  --spacing-xs: 8px;
  --spacing-sm: 16px;
  --spacing-md: 24px;
  --spacing-lg: 32px;
  --spacing-xl: 48px;
}

/* Use consistent values */
.card {
  margin-bottom: var(--spacing-sm);
}

.section {
  margin-bottom: var(--spacing-md);
}

.post {
  margin-bottom: var(--spacing-lg);
}

.comment {
  margin-bottom: var(--spacing-xs);
}
```

**Benefits:**

- Consistent spacing throughout the site
- Easy to adjust the entire spacing scale
- Clear naming (xs, sm, md, lg, xl)

---

### **When NOT to Use DRY 🚫**

**Sometimes repetition is OK.**

#### **Case 1: Styles that coincidentally match**

```css
/* These happen to have the same padding now */
.header {
  padding: 20px;
}

.footer {
  padding: 20px;
}
```

**Don't combine them just because they match right now:**

```css
/* Bad - creates coupling */
.header,
.footer {
  padding: 20px;
}
```

**Why?** Header and footer padding might need to be different in the future. Combining them creates unnecessary coupling.

**When to combine:** Only if the styles are **semantically related** and will **always change together**.

---

#### **Case 2: Over-abstracting**

```css
/* Too abstract */
.blue-bg-white-text-padded-rounded {
  background-color: blue;
  color: white;
  padding: 10px;
  border-radius: 4px;
}
```

**Problem:** This class name is too specific and won't be reusable.

**Better:** Create semantic, purpose-driven classes.

```css
.alert-info {
  background-color: blue;
  color: white;
  padding: 10px;
  border-radius: 4px;
}
```

---

### **DRY Checklist ✅**

**Before you write CSS, ask:**

1. ☐ Am I repeating the same color/spacing/font value?
   - **Use CSS variables**

2. ☐ Am I writing the same styles for multiple elements?
   - **Group selectors**

3. ☐ Am I copy-pasting rule blocks?
   - **Extract common base class**

4. ☐ Am I repeating simple utilities (text-center, hidden, etc.)?
   - **Create utility classes**

5. ☐ Will these styles always change together?
   - **Yes** → Combine them
   - **No** → Keep them separate

---

### **Practical Workflow 🛠️**

**Step 1: Write CSS normally**

Don't worry about DRY at first. Get it working.

```css
.card-one {
  padding: 20px;
  border: 1px solid #ddd;
}

.card-two {
  padding: 20px;
  border: 1px solid #ddd;
}
```

**Step 2: Spot repetition**

Notice you're repeating padding and border.

**Step 3: Refactor**

Extract common styles.

```css
.card {
  padding: 20px;
  border: 1px solid #ddd;
}
```

**Step 4: Test**

Make sure everything still works after refactoring.

---

### **Key Takeaways 💡**

1. **DRY = Don't Repeat Yourself** - Avoid writing the same code multiple times
2. **Group selectors** for shared styles across multiple elements
3. **Extract base classes** for common patterns (e.g., `.card`, `.btn`)
4. **Use CSS variables** for repeated values (colors, spacing, fonts)
5. **Create utility classes** for frequently-used single-purpose styles
6. **Don't over-abstract** - Only combine styles that are semantically related
7. **Refactor gradually** - Write first, optimize later

**The goal:** Write CSS that's easy to maintain, update, and scale.

---

## **Naming Conventions 🏷️**

Choosing good class names is harder than it looks. A naming convention gives you a consistent system for naming CSS classes.

**Why it matters:**

- **Consistency** - Everyone on the team names things the same way
- **Readability** - Class names are self-explanatory
- **Maintainability** - Easy to find and modify styles
- **Scalability** - System works as project grows

---

### **The Naming Problem 😰**

**Without a convention:**

```html
<div class="blueBox">
  <h2 class="Title">Product Name</h2>
  <p class="description_text">Description</p>
  <button class="BuyNow">Buy Now</button>
</div>
```

**Issues:**

- `blueBox` - What if you change it to red? Name is now misleading
- `Title` - Capitalized (inconsistent)
- `description_text` - Uses underscores
- `BuyNow` - CamelCase
- No consistency, hard to predict class names

---

**With a convention:**

```html
<div class="product-card">
  <h2 class="product-card__title">Product Name</h2>
  <p class="product-card__description">Description</p>
  <button class="product-card__button">Buy Now</button>
</div>
```

**Benefits:**

- Consistent naming (kebab-case)
- Semantic names (describes purpose, not appearance)
- Clear relationship between elements
- Predictable structure

---

### **Basic Naming Rules 📏**

**Before diving into conventions, follow these universal rules:**

#### **1. Use Lowercase**

<!-- prettier-ignore -->
```css
/* Good */
.button {
}
.product-card {
}

/* Bad */
.Button {
}
.PRODUCT-CARD {
}
```

---

#### **2. Use Hyphens for Multi-Word Names (Kebab-Case)**

```css
/* Good - kebab-case */
.primary-button {
}
.user-profile {
}
.navigation-menu {
}

/* Bad - camelCase */
.primaryButton {
}
.userProfile {
}

/* Bad - snake_case */
.primary_button {
}
.user_profile {
}

/* Bad - no separator */
.primarybutton {
}
```

**Why kebab-case?**

- Standard in CSS community
- Easy to read
- Works well with CSS syntax

---

#### **3. Be Descriptive and Semantic**

**Describe the purpose, not the appearance.**

```css
/* Good - semantic */
.alert-error {
}
.product-card {
}
.navigation-primary {
}

/* Bad - appearance-based */
.red-box {
}
.big-text {
}
.blue-border {
}
```

**Why?** If you change the red box to blue, the class name `.red-box` becomes misleading.

---

#### **4. Avoid Abbreviations (Unless Common)**

```css
/* Good */
.button {
}
.navigation {
}

/* Bad - unclear */
.btn {
}
.nav {
}

/* Exception - common abbreviations are OK */
.img {
} /* Everyone knows this is image */
.bg {
} /* Background is commonly shortened */
```

**But:** Be consistent. If you use `.btn`, use it everywhere (don't mix `.btn` and `.button`).

---

### **Kebab-Case: The Standard 🔤**

**Kebab-case** is the most common naming convention in CSS.

**Format:** All lowercase, words separated by hyphens

**Examples:**

```css
.header {
}
.main-content {
}
.sidebar {
}
.footer {
}
.product-card {
}
.user-profile {
}
.navigation-menu {
}
.call-to-action {
}
```

**When to use:** Always, for all CSS class names. It's the standard.

---

### **BEM: Block Element Modifier 🧱**

**BEM is a naming methodology** for creating consistent, scalable class names.

**BEM stands for:**

- **Block** - Standalone component
- **Element** - Part of a block
- **Modifier** - Variation of a block or element

---

#### **BEM Syntax**

```
.block { }
.block__element { }
.block--modifier { }
.block__element--modifier { }
```

**Breakdown:**

- `.block` - The component
- `.block__element` - Child of the block (double underscore `__`)
- `.block--modifier` - Variation of the block (double hyphen `--`)
- `.block__element--modifier` - Variation of an element

---

#### **BEM Example: Product Card**

**HTML:**

```html
<article class="product-card">
  <img class="product-card__image" src="product.jpg" alt="Product" />
  <h2 class="product-card__title">Amazing Product</h2>
  <p class="product-card__description">Product description</p>
  <button class="product-card__button product-card__button--primary">
    Buy Now
  </button>
</article>
```

**CSS:**

```css
/* Block */
.product-card {
  border: 1px solid #ddd;
  padding: 20px;
  border-radius: 8px;
}

/* Elements (parts of the block) */
.product-card__image {
  width: 100%;
  border-radius: 4px;
}

.product-card__title {
  font-size: 1.5rem;
  margin: 10px 0;
}

.product-card__description {
  color: #666;
  font-size: 0.9rem;
}

.product-card__button {
  padding: 10px 20px;
  border: none;
  cursor: pointer;
}

/* Modifier (variation) */
.product-card__button--primary {
  background-color: #3498db;
  color: white;
}
```

---

#### **Breaking Down BEM Components**

**Block = The component itself**

```css
.product-card {
}
.navigation {
}
.modal {
}
.header {
}
```

**Think:** Standalone, reusable component

---

**Element = Part of the block**

```css
.product-card__image {
}
.product-card__title {
}
.navigation__link {
}
.modal__close-button {
}
```

**Syntax:** `.block__element`

**Think:** "The image that belongs to the product card"

---

**Modifier = Variation of block or element**

```css
.product-card--featured {
}
.product-card--sale {
}
.product-card__button--small {
}
.product-card__button--large {
}
```

**Syntax:** `.block--modifier` or `.block__element--modifier`

**Think:** "A special version of this block/element"

---

#### **BEM in Practice: Navigation Menu**

**HTML:**

```html
<nav class="navigation">
  <ul class="navigation__list">
    <li class="navigation__item">
      <a href="#" class="navigation__link navigation__link--active">Home</a>
    </li>
    <li class="navigation__item">
      <a href="#" class="navigation__link">About</a>
    </li>
    <li class="navigation__item">
      <a href="#" class="navigation__link">Contact</a>
    </li>
  </ul>
</nav>
```

**CSS:**

```css
/* Block */
.navigation {
  background-color: #2c3e50;
  padding: 1rem;
}

/* Elements */
.navigation__list {
  list-style: none;
  display: flex;
  gap: 1rem;
}

.navigation__item {
  /* Individual list item styles */
}

.navigation__link {
  color: white;
  text-decoration: none;
  padding: 0.5rem 1rem;
}

/* Modifier */
.navigation__link--active {
  background-color: #3498db;
  border-radius: 4px;
}
```

---

#### **Why Use BEM? 🤔**

**Benefits:**

1. **Clear relationships** - You can see which elements belong to which block
2. **No specificity issues** - All classes have same specificity (one class)
3. **Self-documenting** - Class names tell you structure
4. **Reusable** - Blocks are standalone components
5. **Scalable** - Works for large projects with many components

**Example:**

```css
/* Without BEM - unclear relationship */
.card {
}
.title {
} /* Title of what? Card? Page? Section? */
.button {
}

/* With BEM - clear relationship */
.product-card {
}
.product-card__title {
} /* Clearly the title of the product card */
.product-card__button {
}
```

---

#### **BEM Naming Examples**

**Button component:**

```html
<button class="button button--primary button--large">Click Me</button>
```

```css
.button {
} /* Base button */
.button--primary {
} /* Primary color variation */
.button--secondary {
} /* Secondary color variation */
.button--large {
} /* Size variation */
.button--small {
} /* Size variation */
```

**Multiple modifiers can be combined:**

```html
<button class="button button--primary button--large">Large Primary</button>
<button class="button button--secondary button--small">Small Secondary</button>
```

---

**Modal component:**

```html
<div class="modal modal--open">
  <div class="modal__overlay"></div>
  <div class="modal__container">
    <button class="modal__close-button">×</button>
    <h2 class="modal__title">Modal Title</h2>
    <p class="modal__content">Modal content goes here.</p>
    <div class="modal__actions">
      <button class="modal__button modal__button--confirm">Confirm</button>
      <button class="modal__button modal__button--cancel">Cancel</button>
    </div>
  </div>
</div>
```

---

### **When to Use BEM vs Simple Naming 🤷**

#### **Use BEM When:**

- ✅ Building reusable components (cards, modals, navigation)
- ✅ Working on large projects with many components
- ✅ Working in teams (consistency is critical)
- ✅ You want clear, self-documenting class names

**Example:** E-commerce site with 50+ components

---

#### **Use Simple Naming When:**

- ✅ Small projects (personal portfolio, landing page)
- ✅ Learning CSS (BEM adds complexity)
- ✅ Quick prototypes

**Example:** Personal blog with 5 pages

```css
/* Simple naming - perfectly fine for small projects */
.header {
}
.nav {
}
.main-content {
}
.sidebar {
}
.footer {
}
.post-card {
}
```

---

### **Common BEM Mistakes 🐞**

#### **Mistake 1: Nesting elements in class names**

```css
/* Wrong - over-nesting */
.product-card__content__title {
}
.product-card__content__description {
}

/* Correct - flat structure */
.product-card__title {
}
.product-card__description {
}
```

**Rule:** Elements should reference the block directly, not other elements.

---

#### **Mistake 2: Using BEM for everything**

```html
<!-- Wrong - overkill for simple elements -->
<p class="paragraph paragraph__text">Simple text</p>

<!-- Correct - just use a class or element selector -->
<p class="description">Simple text</p>
```

**Rule:** Not every element needs BEM. Use it for components, not every single element.

---

#### **Mistake 3: Modifier without base class**

```html
<!-- Wrong - missing base class -->
<button class="button--primary">Click</button>

<!-- Correct - include both -->
<button class="button button--primary">Click</button>
```

**Rule:** Modifiers extend the base class, they don't replace it.

---

### **Alternative: Simplified BEM**

**Some developers use a simplified version:**

```css
/* Standard BEM */
.product-card__button--primary {
}

/* Simplified - single hyphen for elements */
.product-card-button--primary {
}

/* Or even simpler */
.product-card-button-primary {
}
```

**This is fine.** The important thing is **consistency**, not strict adherence to double underscores/hyphens.

---

### **Real-World Example: Alert Component**

**HTML:**

```html
<div class="alert alert--success">
  <span class="alert__icon">✓</span>
  <p class="alert__message">Your changes have been saved!</p>
  <button class="alert__close-button">×</button>
</div>

<div class="alert alert--error">
  <span class="alert__icon">✗</span>
  <p class="alert__message">An error occurred. Please try again.</p>
  <button class="alert__close-button">×</button>
</div>
```

**CSS:**

```css
/* Block */
.alert {
  padding: 15px;
  border-radius: 4px;
  display: flex;
  align-items: center;
  gap: 10px;
}

/* Modifiers */
.alert--success {
  background-color: #d4edda;
  border: 1px solid #c3e6cb;
  color: #155724;
}

.alert--error {
  background-color: #f8d7da;
  border: 1px solid #f5c6cb;
  color: #721c24;
}

/* Elements */
.alert__icon {
  font-size: 1.5rem;
  font-weight: bold;
}

.alert__message {
  flex: 1;
  margin: 0;
}

.alert__close-button {
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  opacity: 0.5;
}

.alert__close-button:hover {
  opacity: 1;
}
```

**Why this works:**

- Clear component structure (`.alert` is the block)
- Elements clearly belong to the alert (`.alert__icon`, `.alert__message`)
- Variations are obvious (`.alert--success`, `.alert--error`)
- Easy to add new alert types (`.alert--warning`, `.alert--info`)

---

### **Naming Convention Decision Guide 🎯**

| Project Type                                 | Recommendation                 |
| -------------------------------------------- | ------------------------------ |
| Personal portfolio (5 pages)                 | Simple kebab-case              |
| Small business site (10-15 pages)            | Simple kebab-case or light BEM |
| Medium site (20+ pages, multiple developers) | BEM                            |
| Large application (50+ components, team)     | BEM (strict)                   |

**Golden rule:** Start simple. Add BEM when your project demands it.

---

### **Key Takeaways 💡**

1. **Always use kebab-case** for CSS class names (lowercase, hyphens)
2. **Be semantic** - Describe purpose, not appearance
3. **BEM = Block Element Modifier** - Naming methodology for components
4. **BEM syntax:**
   - `.block` - Component
   - `.block__element` - Part of component
   - `.block--modifier` - Variation
5. **Use BEM for:** Reusable components in medium/large projects
6. **Use simple naming for:** Small projects, quick prototypes
7. **Consistency matters more than which convention** you choose

**The goal:** Predictable, maintainable class names that scale with your project.

---

## **CSS Custom Properties (Variables) 🔧**

CSS variables (officially called **Custom Properties**) let you store values and reuse them throughout your CSS.

**Think of them like this:**

Instead of writing `#3498db` 50 times, you write it once in a variable and reference it everywhere.

---

### **The Problem: Repeating Values 🔁**

**Without variables:**

```css
.header {
  background-color: #3498db;
}

.button {
  background-color: #3498db;
}

.link {
  color: #3498db;
}

.badge {
  border-color: #3498db;
}

.highlight {
  background-color: #3498db;
}
```

**Issues:**

1. **Hard to maintain** - If you want to change the color, you have to update 5 places
2. **Error-prone** - Easy to miss one instance or make a typo
3. **No context** - `#3498db` doesn't tell you what it represents

---

**With variables:**

```css
/* Define once */
:root {
  --color-primary: #3498db;
}

/* Use everywhere */
.header {
  background-color: var(--color-primary);
}

.button {
  background-color: var(--color-primary);
}

.link {
  color: var(--color-primary);
}

.badge {
  border-color: var(--color-primary);
}

.highlight {
  background-color: var(--color-primary);
}
```

**Benefits:**

1. **Easy to maintain** - Change the color once in `:root`, all instances update
2. **Self-documenting** - `--color-primary` tells you what it represents
3. **Consistent** - All instances use the exact same value

---

### **Defining Variables 📝**

**Syntax:**

```css
selector {
  --variable-name: value;
}
```

**Rules:**

1. Variable names **must start with two hyphens** `--`
2. Variable names are **case-sensitive** (`--color` ≠ `--Color`)
3. Use **kebab-case** for multi-word names (`--primary-color`, not `--primaryColor`)

---

### **Where to Define Variables: `:root` 🌳**

**The `:root` selector** represents the document root (the `<html>` element). It's the most common place to define variables because they're available everywhere.

**Example:**

```css
:root {
  --color-primary: #3498db;
  --color-secondary: #e74c3c;
  --color-dark: #2c3e50;
  --color-light: #ecf0f1;
}
```

**Why `:root`?**

- Variables defined in `:root` are **global** - accessible anywhere in your CSS
- Standard convention - other developers expect global variables in `:root`
- Easy to find - all your main variables in one place

---

### **Using Variables 🎯**

**Syntax:**

```css
property: var(--variable-name);
```

**Example:**

```css
/* Define */
:root {
  --color-primary: #3498db;
}

/* Use */
.button {
  background-color: var(--color-primary);
  border: 2px solid var(--color-primary);
}

.link {
  color: var(--color-primary);
}
```

**The `var()` function** retrieves the value of the variable.

---

### **Common Use Cases 💼**

#### **1. Colors 🎨**

**Define your color palette once:**

```css
:root {
  /* Brand colors */
  --color-primary: #3498db;
  --color-secondary: #e74c3c;
  --color-success: #2ecc71;
  --color-warning: #f39c12;
  --color-danger: #e74c3c;

  /* Neutral colors */
  --color-dark: #2c3e50;
  --color-gray: #95a5a6;
  --color-light: #ecf0f1;
  --color-white: #ffffff;

  /* Text colors */
  --text-primary: #2c3e50;
  --text-secondary: #7f8c8d;
  --text-muted: #bdc3c7;
}
```

**Use:**

```css
.button-primary {
  background-color: var(--color-primary);
  color: var(--color-white);
}

.alert-success {
  background-color: var(--color-success);
  color: var(--color-white);
}

body {
  color: var(--text-primary);
}

.caption {
  color: var(--text-muted);
}
```

---

#### **2. Spacing 📏**

**Create a consistent spacing scale:**

```css
:root {
  --spacing-xs: 4px;
  --spacing-sm: 8px;
  --spacing-md: 16px;
  --spacing-lg: 24px;
  --spacing-xl: 32px;
  --spacing-2xl: 48px;
}
```

**Use:**

```css
.card {
  padding: var(--spacing-lg);
  margin-bottom: var(--spacing-md);
}

.button {
  padding: var(--spacing-sm) var(--spacing-md);
}

.section {
  margin-bottom: var(--spacing-xl);
}
```

**Benefits:**

- Consistent spacing throughout the site
- Easy to adjust the entire scale
- Visual rhythm and hierarchy

---

#### **3. Typography 📝**

**Font families, sizes, and weights:**

```css
:root {
  /* Font families */
  --font-primary: "Helvetica Neue", Helvetica, Arial, sans-serif;
  --font-secondary: Georgia, "Times New Roman", serif;
  --font-mono: "Courier New", monospace;

  /* Font sizes */
  --font-size-xs: 0.75rem;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.25rem;
  --font-size-xl: 1.5rem;
  --font-size-2xl: 2rem;
  --font-size-3xl: 3rem;

  /* Font weights */
  --font-weight-normal: 400;
  --font-weight-medium: 500;
  --font-weight-bold: 700;

  /* Line heights */
  --line-height-tight: 1.2;
  --line-height-normal: 1.5;
  --line-height-relaxed: 1.8;
}
```

**Use:**

```css
body {
  font-family: var(--font-primary);
  font-size: var(--font-size-base);
  line-height: var(--line-height-normal);
}

h1 {
  font-family: var(--font-secondary);
  font-size: var(--font-size-3xl);
  font-weight: var(--font-weight-bold);
  line-height: var(--line-height-tight);
}

code {
  font-family: var(--font-mono);
  font-size: var(--font-size-sm);
}
```

---

#### **4. Layout Values 📐**

**Widths, heights, border radius:**

```css
:root {
  /* Container widths */
  --container-sm: 640px;
  --container-md: 768px;
  --container-lg: 1024px;
  --container-xl: 1280px;

  /* Border radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 16px;
  --radius-full: 9999px; /* For pills/circles */

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.15);
}
```

**Use:**

```css
.container {
  max-width: var(--container-lg);
  margin: 0 auto;
}

.card {
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-md);
}

.button {
  border-radius: var(--radius-sm);
}

.avatar {
  border-radius: var(--radius-full); /* Makes it circular */
}
```

---

### **Variable Scope 🔍**

Variables are **scoped** to the element they're defined in and its children.

**Example:**

```css
/* Global variables */
:root {
  --color-primary: blue;
}

/* Scoped to .dark-theme */
.dark-theme {
  --color-primary: lightblue; /* Overrides blue within .dark-theme */
  --bg-color: black;
}

/* Use */
.button {
  background-color: var(--color-primary);
}
```

**HTML:**

```html
<button class="button">I'm blue</button>

<div class="dark-theme">
  <button class="button">I'm lightblue (inside dark-theme)</button>
</div>
```

**Why this works:**

- Outside `.dark-theme`: `--color-primary` = `blue` (from `:root`)
- Inside `.dark-theme`: `--color-primary` = `lightblue` (overridden)

---

### **Fallback Values 🛟**

You can provide a **fallback value** in case the variable is undefined.

**Syntax:**

```css
property: var(--variable-name, fallback-value);
```

**Example:**

```css
.button {
  background-color: var(--color-primary, blue);
  /* If --color-primary isn't defined, use blue */
}
```

**When to use:**

- When a variable might not be defined
- As a safety net
- When creating reusable components

**Example with nested fallback:**

```css
.button {
  color: var(--button-color, var(--color-primary, black));
  /* 1. Try --button-color
     2. If not defined, try --color-primary
     3. If not defined, use black */
}
```

---

### **Practical Example: Complete Color System 🎨**

**Define a complete color system:**

```css
:root {
  /* Primary palette */
  --color-primary-light: #5dade2;
  --color-primary: #3498db;
  --color-primary-dark: #2980b9;

  /* Secondary palette */
  --color-secondary-light: #ec7063;
  --color-secondary: #e74c3c;
  --color-secondary-dark: #c0392b;

  /* Success palette */
  --color-success-light: #58d68d;
  --color-success: #2ecc71;
  --color-success-dark: #27ae60;

  /* Grays */
  --color-gray-100: #f8f9fa;
  --color-gray-200: #e9ecef;
  --color-gray-300: #dee2e6;
  --color-gray-400: #ced4da;
  --color-gray-500: #adb5bd;
  --color-gray-600: #6c757d;
  --color-gray-700: #495057;
  --color-gray-800: #343a40;
  --color-gray-900: #212529;
}
```

**Use:**

```css
.button-primary {
  background-color: var(--color-primary);
  border: 2px solid var(--color-primary-dark);
}

.button-primary:hover {
  background-color: var(--color-primary-dark);
}

.card {
  background-color: var(--color-gray-100);
  border: 1px solid var(--color-gray-300);
}

.text-muted {
  color: var(--color-gray-600);
}
```

---

### **Practical Example: Dark Mode 🌓**

Variables make theme switching incredibly powerful. Let's understand **exactly** how this works.

---

#### **The Concept: Variable Overriding 🔄**

CSS variables can be **redefined** at different levels. When you redefine a variable, it overrides the previous value **for that element and its children**.

**Key principle:** The browser uses the **closest** variable definition.

---

#### **Setting Up Dark Mode Variables**

**Step 1: Define default (light) theme in `:root`**

```css
/* Default theme - available everywhere */
:root {
  --bg-primary: #ffffff; /* White background */
  --bg-secondary: #f8f9fa; /* Light gray background */
  --text-primary: #212529; /* Dark text */
  --text-secondary: #6c757d; /* Gray text */
  --border-color: #dee2e6; /* Light border */
}
```

These are **global defaults**. Every element can access them.

---

**Step 2: Override variables for dark theme**

```css
/* Dark theme - overrides :root values when active */
.dark-mode {
  --bg-primary: #212529; /* Dark background */
  --bg-secondary: #343a40; /* Darker gray background */
  --text-primary: #f8f9fa; /* Light text */
  --text-secondary: #adb5bd; /* Light gray text */
  --border-color: #495057; /* Dark border */
}
```

**Notice:** We use the **same variable names** but with **different values**.

---

**Step 3: Use the variables in your styles**

```css
body {
  background-color: var(--bg-primary);
  color: var(--text-primary);
}

.card {
  background-color: var(--bg-secondary);
  border: 1px solid var(--border-color);
  color: var(--text-primary);
}

.caption {
  color: var(--text-secondary);
}
```

**Important:** These styles don't know (or care) whether they're in light or dark mode. They just use the variable values.

---

#### **How the Browser Decides Which Value to Use 🧠**

**Scenario 1: Light Mode (no `.dark-mode` class)**

```html
<body>
  <div class="card">
    <p>Content</p>
    <span class="caption">Caption text</span>
  </div>
</body>
```

**What happens:**

1. `body` needs `var(--bg-primary)`
2. Browser checks: Does `body` have a `--bg-primary` variable defined? **No**
3. Browser checks: Does the parent (`<html>`) have it? **No**
4. Browser checks: Does `:root` have it? **Yes!** → `#ffffff` (white)
5. **Result:** White background

**Same process for all elements:**

```
body uses var(--bg-primary)
  → Looks for --bg-primary
  → Finds it in :root
  → Uses white (#ffffff)

.card uses var(--bg-secondary)
  → Looks for --bg-secondary
  → Finds it in :root
  → Uses light gray (#f8f9fa)

.caption uses var(--text-secondary)
  → Looks for --text-secondary
  → Finds it in :root
  → Uses gray (#6c757d)
```

**Result:** Light mode appearance

---

**Scenario 2: Dark Mode (`.dark-mode` class on `<body>`)**

```html
<body class="dark-mode">
  <div class="card">
    <p>Content</p>
    <span class="caption">Caption text</span>
  </div>
</body>
```

**What happens:**

1. `body` needs `var(--bg-primary)`
2. Browser checks: Does `body` have a `--bg-primary` variable defined?
3. **Yes!** → `body` has class `.dark-mode` which defines `--bg-primary: #212529;`
4. **Result:** Dark background

**Same process for all elements:**

```
body uses var(--bg-primary)
  → Looks for --bg-primary
  → Finds it in body (from .dark-mode class)
  → Uses dark (#212529)

.card uses var(--bg-secondary)
  → Looks for --bg-secondary
  → Finds it in body (from .dark-mode class)
  → Inherits and uses dark gray (#343a40)

.caption uses var(--text-secondary)
  → Looks for --text-secondary
  → Finds it in body (from .dark-mode class)
  → Inherits and uses light gray (#adb5bd)
```

**Result:** Dark mode appearance

---

#### **The Key: Variable Inheritance & Proximity 🔑**

**Rule:** CSS variables **inherit down the DOM tree**, and **closer definitions override further ones**.

**Visual representation:**

```
Light Mode:
──────────────────────────────────────────
:root { --bg-primary: white; }
  ↓
body { background: var(--bg-primary); }
  ↓ inherits from :root
<body> → white background


Dark Mode:
──────────────────────────────────────────
:root { --bg-primary: white; }
  ↓
body.dark-mode { --bg-primary: black; } ← Overrides!
  ↓
body { background: var(--bg-primary); }
  ↓ uses .dark-mode value (closer)
<body class="dark-mode"> → black background
```

**Why `.dark-mode` wins:**

- `:root` is the furthest ancestor (document root)
- `.dark-mode` is on `body` itself (much closer)
- **Closer definitions override further ones**

---

#### **Complete Working Example 💡**

**CSS:**

```css
/* Step 1: Define light theme (default) */
:root {
  --bg-color: #ffffff;
  --text-color: #000000;
  --card-bg: #f0f0f0;
}

/* Step 2: Define dark theme (override) */
.dark-mode {
  --bg-color: #1a1a1a;
  --text-color: #ffffff;
  --card-bg: #2d2d2d;
}

/* Step 3: Use variables everywhere */
body {
  background-color: var(--bg-color);
  color: var(--text-color);
  transition:
    background-color 0.3s,
    color 0.3s; /* Smooth transition */
}

.card {
  background-color: var(--card-bg);
  padding: 20px;
  border-radius: 8px;
}
```

**HTML:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <button id="theme-toggle">Toggle Dark Mode</button>

    <div class="card">
      <h2>Card Title</h2>
      <p>Card content goes here.</p>
    </div>
  </body>
</html>
```

**JavaScript:**

```javascript
const toggleButton = document.getElementById("theme-toggle");

toggleButton.addEventListener("click", () => {
  document.body.classList.toggle("dark-mode");
});
```

---

#### **What Happens When You Click the Button 🖱️**

**Initial state (Light Mode):**

```html
<body>
  <!-- Uses :root variables -->
  <!-- Background: white, Text: black -->
</body>
```

**After first click:**

```javascript
document.body.classList.toggle("dark-mode");
```

```html
<body class="dark-mode">
  <!-- Now uses .dark-mode variables -->
  <!-- Background: dark, Text: white -->
  <!-- Browser recalculates ALL var() references -->
</body>
```

**After second click:**

```javascript
document.body.classList.toggle("dark-mode");
```

```html
<body>
  <!-- Removes .dark-mode class -->
  <!-- Back to :root variables -->
  <!-- Background: white, Text: black -->
</body>
```

**`.toggle()` means:**

- If class exists → remove it
- If class doesn't exist → add it

---

#### **Why This Approach is Powerful 💪**

**1. Change once, update everywhere**

You don't need to update individual element styles. Just toggle the class on `body`, and all variables automatically switch.

**2. Easy to add more themes**

```css
:root {
  --bg-color: white;
  --text-color: black;
}

.dark-mode {
  --bg-color: black;
  --text-color: white;
}

.high-contrast-mode {
  --bg-color: black;
  --text-color: yellow;
}

.sepia-mode {
  --bg-color: #f4ecd8;
  --text-color: #5b4636;
}
```

**3. Works with user preferences**

```javascript
// Detect user's system preference
if (window.matchMedia("(prefers-color-scheme: dark)").matches) {
  document.body.classList.add("dark-mode");
}
```

---

#### **Saving User Preference 💾**

**Save the theme choice to localStorage:**

```javascript
const toggleButton = document.getElementById("theme-toggle");

// Load saved theme on page load
if (localStorage.getItem("theme") === "dark") {
  document.body.classList.add("dark-mode");
}

// Toggle and save
toggleButton.addEventListener("click", () => {
  document.body.classList.toggle("dark-mode");

  // Save preference
  if (document.body.classList.contains("dark-mode")) {
    localStorage.setItem("theme", "dark");
  } else {
    localStorage.setItem("theme", "light");
  }
});
```

Now the theme persists across page reloads!

---

#### **Visual Summary 📊**

```
Without .dark-mode:
────────────────────────────────────────
Elements use var(--bg-primary)
  ↓
Browser finds it in :root
  ↓
Light theme colors applied


With .dark-mode on <body>:
────────────────────────────────────────
Elements use var(--bg-primary)
  ↓
Browser finds it in body.dark-mode (closer!)
  ↓
Dark theme colors applied
```

---

#### **Key Takeaways 💡**

1. **Define global defaults in `:root`** - Used when no override exists
2. **Define overrides in `.dark-mode`** - Use same variable names, different values
3. **Browser uses the closest definition** - `.dark-mode` (on body) beats `:root`
4. **All children inherit** - Card, paragraph, buttons all get dark mode automatically
5. **Toggle the class with JavaScript** - `classList.toggle('dark-mode')`
6. **Variables update instantly** - Browser recalculates all `var()` references
7. **Works for any number of themes** - Just define more override classes

**The magic:** Same variable names, different values based on class presence.

---

### **Organizing Variables 🗂️**

**Group related variables together:**

```css
:root {
  /* ========================================
     COLORS
     ======================================== */

  /* Brand */
  --color-primary: #3498db;
  --color-secondary: #e74c3c;

  /* State */
  --color-success: #2ecc71;
  --color-warning: #f39c12;
  --color-danger: #e74c3c;

  /* Neutrals */
  --color-dark: #2c3e50;
  --color-gray: #95a5a6;
  --color-light: #ecf0f1;

  /* ========================================
     SPACING
     ======================================== */

  --spacing-xs: 4px;
  --spacing-sm: 8px;
  --spacing-md: 16px;
  --spacing-lg: 24px;
  --spacing-xl: 32px;

  /* ========================================
     TYPOGRAPHY
     ======================================== */

  --font-primary: Arial, sans-serif;
  --font-secondary: Georgia, serif;

  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.25rem;
  --font-size-xl: 1.5rem;

  /* ========================================
     LAYOUT
     ======================================== */

  --container-max-width: 1200px;
  --radius-sm: 4px;
  --radius-md: 8px;
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
}
```

---

### **Naming Convention for Variables 🏷️**

**Follow a consistent pattern:**

**Format:** `--category-name-variant`

**Examples:**

```css
/* Colors */
--color-primary
--color-primary-light
--color-primary-dark

/* Spacing */
--spacing-xs
--spacing-sm
--spacing-md

/* Font */
--font-size-base
--font-weight-bold
--line-height-normal

/* Radius */
--radius-sm
--radius-md
--radius-lg
```

**Benefits:**

- Predictable names
- Easy to find related variables
- Clear hierarchy

---

### **Common Mistakes 🐞**

#### **Mistake 1: Forgetting the double hyphens**

```css
/* Wrong */
:root {
  color-primary: blue; /* Missing -- */
}

/* Correct */
:root {
  --color-primary: blue;
}
```

---

#### **Mistake 2: Using the variable without `var()`**

```css
/* Wrong */
.button {
  background-color: --color-primary; /* Missing var() */
}

/* Correct */
.button {
  background-color: var(--color-primary);
}
```

---

#### **Mistake 3: Case sensitivity**

```css
:root {
  --Color-Primary: blue; /* Capital C and P */
}

.button {
  background-color: var(--color-primary); /* lowercase - won't work! */
}
```

**Variables are case-sensitive.** Stick to lowercase kebab-case.

---

#### **Mistake 4: Defining variables in the wrong place**

```css
/* Wrong - variables only available inside .button */
.button {
  --color-primary: blue;
}

.link {
  color: var(--color-primary); /* Not defined here! */
}

/* Correct - define in :root for global access */
:root {
  --color-primary: blue;
}

.button {
  background-color: var(--color-primary);
}

.link {
  color: var(--color-primary);
}
```

---

### **Key Takeaways 💡**

1. **CSS variables** = Store and reuse values
2. **Define in `:root`** for global access
3. **Syntax:** `--variable-name: value;` to define, `var(--variable-name)` to use
4. **Common uses:** Colors, spacing, typography, layout values
5. **Fallbacks:** `var(--name, fallback)` for safety
6. **Scoped variables** can override global ones
7. **Use kebab-case** for variable names
8. **Group related variables** together (colors, spacing, typography)
9. **Make maintenance easy** - change once, update everywhere

**The goal:** Write CSS that's easy to maintain and update.

---

## **Commenting Your CSS 💬**

Comments are notes you leave in your code for yourself and other developers. The browser ignores them—they're purely for humans.

**Good comments make your CSS:**

- Easier to understand
- Easier to maintain
- Easier to navigate
- Better for collaboration

---

### **Why Comments Matter 📝**

**Without comments:**

```css
.card {
  margin-bottom: 24px;
}

.special-promo {
  margin-bottom: 48px;
}
```

**Questions:**

- Why is `.special-promo` margin different?
- Is this intentional or a mistake?
- Can I change it?

---

**With comments:**

```css
.card {
  margin-bottom: 24px;
}

/* Special promo cards need extra spacing to stand out visually */
.special-promo {
  margin-bottom: 48px;
}
```

**Now it's clear:** The extra spacing is intentional and has a purpose.

---

### **Comment Syntax 📐**

**CSS comment format:**

```css
/* This is a comment */
```

**Rules:**

- Starts with `/*`
- Ends with `*/`
- Everything between is ignored by the browser

---

**Single-line comments:**

```css
/* This is a comment */

.button {
  color: blue; /* This is also a comment */
}
```

---

**Multi-line comments:**

```css
/*
This is a multi-line comment.
You can write as much as you want.
Great for longer explanations.
*/

.card {
  padding: 20px;
}
```

---

**Comments can go anywhere:**

```css
/* Before a rule */
.button {
  /* Inside a rule */
  color: blue; /* After a property */
}
/* After a rule */
```

---

### **When to Comment 🤔**

#### **1. Explain "Why," Not "What"**

**Bad comment (states the obvious):**

```css
/* Makes the text blue */
.link {
  color: blue;
}
```

The code already says it's blue. The comment adds no value.

---

**Good comment (explains the reason):**

```css
/* Blue matches our brand color and improves link visibility */
.link {
  color: blue;
}
```

Now we understand **why** it's blue.

---

#### **2. Document Non-Obvious Decisions**

```css
/* 
  Using a fixed height instead of min-height to prevent layout shift
  when the content loads dynamically from the API
*/
.product-card {
  height: 300px;
}
```

Without this comment, someone might change `height` to `min-height` and break the layout.

---

#### **3. Explain Workarounds or Hacks**

```css
/*
  Safari has a bug with flexbox and min-height.
  This empty ::before pseudo-element fixes it.
  Bug report: https://bugs.webkit.org/show_bug.cgi?id=137730
*/
.container::before {
  content: "";
  display: block;
}
```

**Why this matters:** Future developers won't delete this thinking it's useless code.

---

#### **4. Mark Temporary or Incomplete Code**

```css
/* TODO: Replace with actual brand colors once design is finalized */
.button {
  background-color: blue;
}

/* FIXME: This breaks on mobile - needs media query */
.sidebar {
  width: 300px;
}

/* NOTE: This is a temporary solution until we implement proper theming */
.dark-mode {
  background-color: #1a1a1a;
}
```

**Common markers:**

- `TODO:` - Something that needs to be done
- `FIXME:` - Something that's broken and needs fixing
- `NOTE:` - Important information
- `HACK:` - A workaround that should be improved later

---

#### **5. Section Your CSS**

**Create visual sections for better navigation:**

```css
/* ==============================================
   COLORS
   ============================================== */

:root {
  --color-primary: #3498db;
  --color-secondary: #e74c3c;
}

/* ==============================================
   TYPOGRAPHY
   ============================================== */

body {
  font-family: Arial, sans-serif;
  font-size: 16px;
}

/* ==============================================
   LAYOUT
   ============================================== */

.container {
  max-width: 1200px;
  margin: 0 auto;
}
```

**Benefits:**

- Easy to scan and find sections
- Clear organization
- Professional appearance

---

### **Comment Styles for Sections 🎨**

**Style 1: Simple divider**

```css
/* Navigation */

.nav {
  display: flex;
}

/* Footer */

.footer {
  padding: 2rem;
}
```

---

**Style 2: Heavy divider**

```css
/* ======================
   Navigation
   ====================== */

.nav {
  display: flex;
}

/* ======================
   Footer
   ====================== */

.footer {
  padding: 2rem;
}
```

---

**Style 3: Box comment**

```css
/*
 * =====================================
 * NAVIGATION
 * =====================================
 */

.nav {
  display: flex;
}

/*
 * =====================================
 * FOOTER
 * =====================================
 */

.footer {
  padding: 2rem;
}
```

---

**Pick one style and stick with it.** Consistency matters more than which style you choose.

---

### **Organizing CSS with Comments 📂**

**Good structure with comments:**

```css
/* ==============================================
   TABLE OF CONTENTS
   ==============================================
   1. Variables
   2. Base Styles
   3. Layout
   4. Components
      4.1 Buttons
      4.2 Cards
      4.3 Forms
   5. Pages
      5.1 Home
      5.2 About
   6. Utilities
   ============================================== */

/* ==============================================
   1. VARIABLES
   ============================================== */

:root {
  --color-primary: #3498db;
  --spacing-md: 16px;
}

/* ==============================================
   2. BASE STYLES
   ============================================== */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
}

/* ==============================================
   3. LAYOUT
   ============================================== */

.container {
  max-width: 1200px;
  margin: 0 auto;
}

/* ==============================================
   4. COMPONENTS
   ============================================== */

/* 4.1 Buttons */

.button {
  padding: 10px 20px;
  border: none;
  cursor: pointer;
}

/* 4.2 Cards */

.card {
  border: 1px solid #ddd;
  padding: 20px;
}

/* 4.3 Forms */

.input {
  width: 100%;
  padding: 10px;
}
```

**Benefits:**

- Table of contents makes navigation easy
- Clear hierarchy
- Easy to find specific components

---

### **Component Documentation 📦**

**Document complex components:**

```css
/*
 * Product Card Component
 * 
 * Used on: Homepage, Shop page, Search results
 * 
 * Modifiers:
 *   .product-card--featured  - Highlighted card with larger size
 *   .product-card--sale      - Card with sale badge
 * 
 * Example:
 *   <div class="product-card">
 *     <img class="product-card__image" src="..." />
 *     <h3 class="product-card__title">Product Name</h3>
 *     <p class="product-card__price">$29.99</p>
 *   </div>
 */

.product-card {
  border: 1px solid #ddd;
  padding: 20px;
  border-radius: 8px;
}

.product-card__image {
  width: 100%;
  border-radius: 4px;
}

.product-card__title {
  font-size: 1.2rem;
  margin: 10px 0;
}

.product-card--featured {
  border: 3px solid gold;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
```

**What this documents:**

- Component purpose
- Where it's used
- Available variations
- HTML structure example

---

### **When NOT to Comment 🚫**

#### **Don't state the obvious**

```css
/* Bad - the code already says this */

/* Makes the background red */
.error {
  background-color: red;
}

/* Sets the width to 100 pixels */
.sidebar {
  width: 100px;
}
```

**These comments add no value.** The code is self-explanatory.

---

#### **Don't comment out large blocks of old code**

```css
/* Bad - clutters the file */

/*
.old-button {
  background-color: blue;
  padding: 10px;
  border: none;
}

.old-card {
  border: 1px solid gray;
  padding: 20px;
}

.old-nav {
  display: flex;
  gap: 1rem;
}
*/

/* New styles */
.button {
  background-color: green;
}
```

**Problem:** Makes the file longer and harder to read.

**Solution:** Delete old code. Use version control (Git) to retrieve it if needed.

---

#### **Don't over-comment**

```css
/* Too many comments */

/* Button styles */
.button {
  /* Padding */
  padding: 10px 20px;

  /* Border */
  border: none;

  /* Cursor */
  cursor: pointer;

  /* Background color */
  background-color: blue;

  /* Text color */
  color: white;
}
```

**This is overkill.** The code is clear without all these comments.

**Better:**

```css
.button {
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  background-color: blue;
  color: white;
}
```

No comments needed. The code is self-explanatory.

---

### **Practical Examples 💼**

#### **Example 1: Explaining Magic Numbers**

```css
/* Bad - no explanation */
.modal {
  z-index: 9999;
}

/* Good - explains the value */
.modal {
  /* z-index high enough to appear above header (z-index: 1000) 
     and dropdown menus (z-index: 100) */
  z-index: 9999;
}
```

---

#### **Example 2: Browser-Specific Fixes**

```css
/*
  Fix for IE11: Flexbox doesn't work properly with min-height.
  This forces IE11 to calculate flex item heights correctly.
*/
.flex-container {
  display: flex;
  min-height: 100vh;
}

.flex-container::before {
  content: "";
  min-height: inherit;
}
```

---

#### **Example 3: Dependency Notes**

```css
/*
  This layout depends on JavaScript to calculate dynamic heights.
  See: js/layout-calculator.js
  
  DO NOT change these values without updating the JS!
*/
.dynamic-section {
  height: 0;
  overflow: hidden;
  transition: height 0.3s ease;
}
```

---

### **Team Collaboration Comments 👥**

**When working with others, comments help communication:**

```css
/*
  IMPORTANT: Marketing team requested this specific color.
  Do not change without approval from Jane (jane@company.com)
*/
.promo-banner {
  background-color: #ff6b35;
}

/*
  TODO: Design team is creating new button styles.
  This is temporary - will be replaced in Sprint 23.
  - Alex, 2024-02-09
*/
.button-temp {
  background-color: gray;
}
```

---

### **Comments for Debugging 🔍**

**Temporarily disable CSS while debugging:**

```css
.card {
  padding: 20px;
  /* margin: 20px; */ /* Temporarily disabled to test layout */
  border: 1px solid #ddd;
}
```

**Remember:** Remove or uncomment these before committing code!

---

### **Common Mistakes 🐞**

#### **Mistake 1: Forgetting to close a comment**

```css
/* This comment is not closed
.button {
  color: blue;
}

.card {
  padding: 20px;
}
```

**Problem:** Everything after `/*` is treated as a comment. The styles won't work.

**Fix:** Always close comments with `*/`

```css
/* This comment is properly closed */
.button {
  color: blue;
}
```

---

#### **Mistake 2: Nesting comments**

```css
/* Outer comment
  /* Inner comment - THIS BREAKS */
  More text
*/
```

**Problem:** CSS doesn't support nested comments. The first `*/` closes the comment.

**Fix:** Don't nest comments.

---

#### **Mistake 3: Using // for comments**

```css
// This doesn't work in CSS
.button {
  color: blue;
}
```

**Problem:** `//` is NOT valid CSS comment syntax (it works in Sass/Less, but not CSS).

**Fix:** Always use `/* */`

```css
/* This works in CSS */
.button {
  color: blue;
}
```

---

### **Quick Reference: Comment Template 📋**

**File header comment:**

```css
/*
 * Project Name: My Awesome Site
 * File: styles.css
 * Author: Your Name
 * Last Updated: 2024-02-09
 * Description: Main stylesheet for the project
 */
```

**Section comment:**

```css
/* ==============================================
   SECTION NAME
   ============================================== */
```

**Component comment:**

```css
/*
 * Component Name
 * Description: Brief description
 * Used on: Page names
 */
```

**Inline explanation:**

```css
.class {
  property: value; /* Brief explanation why */
}
```

**TODO marker:**

```css
/* TODO: Description of what needs to be done */
```

---

### **Key Takeaways 💡**

1. **Explain "why," not "what"** - The code shows what, comments explain why
2. **Document non-obvious decisions** - Help future developers understand your choices
3. **Use section comments** to organize large CSS files
4. **Mark temporary code** with TODO, FIXME, NOTE
5. **Don't over-comment** - Self-explanatory code doesn't need comments
6. **Delete old code** - Don't comment out large blocks, use version control
7. **Comment syntax:** `/* comment */` only (not `//`)
8. **Be consistent** with comment style across your project

**The goal:** Make your CSS easy to understand and maintain for yourself and others.

---

## **Custom Fonts & Web Fonts 🔤**

System fonts (Arial, Times New Roman, etc.) are limited and generic. **Web fonts** let you use custom fonts on your website, giving you complete control over typography.

---

### **What are Web Fonts? 🤔**

**System fonts:**

- Pre-installed on users' computers
- Limited selection (Arial, Helvetica, Times New Roman, etc.)
- Load instantly (already on the system)
- Boring and overused

**Web fonts:**

- Downloaded from a server when the page loads
- Unlimited selection (thousands of fonts available)
- Small delay while downloading
- Unique and professional

---

### **Why Use Web Fonts? 🎨**

**Benefits:**

- ✅ Unique brand identity
- ✅ Better design control
- ✅ Professional appearance
- ✅ Consistent across all devices

**Example comparison:**

**With system font (Arial):**

```css
body {
  font-family: Arial, sans-serif;
}
```

→ Generic, looks like every other website

**With web font (Roboto from Google Fonts):**

```css
body {
  font-family: "Roboto", sans-serif;
}
```

→ Modern, professional, unique

---

### **Method 1: Google Fonts (Easiest) 🔥**

**Google Fonts** is a free library of web fonts that's easy to use and fast to load.

**Link:** [fonts.google.com](https://fonts.google.com)

---

#### **Step 1: Choose a Font**

1. Go to [fonts.google.com](https://fonts.google.com)
2. Browse or search for a font (e.g., "Roboto")
3. Click on the font to see details

---

#### **Step 2: Select Font Weights**

Fonts come in different weights (thicknesses).

**Common weights:**

- 300 = Light
- 400 = Regular (normal text)
- 500 = Medium
- 700 = Bold (headings)

**Select the weights you need:**

- Click "+ Select this style" for each weight

**Tip:** Only select weights you'll actually use. Each weight adds to page load time.

---

#### **Step 3: Get the Code**

Click "View selected families" (top right corner).

Google Fonts gives you two options:

---

**Option A: Link tag (recommended for beginners)**

Copy the `<link>` tag and paste it in your HTML `<head>`:

```html
<head>
  <meta charset="UTF-8" />
  <title>My Site</title>

  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
    rel="stylesheet"
  />

  <!-- Your CSS -->
  <link rel="stylesheet" href="styles.css" />
</head>
```

**What these lines do:**

- Line 1-2: Speed up the connection to Google's servers
- Line 3: Load the Roboto font (weights 400 and 700)

---

**Option B: @import (alternative method)**

Copy the `@import` code and paste it at the **very top** of your CSS file:

```css
/* Must be at the very top of your CSS file */
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

/* Rest of your CSS */
body {
  font-family: "Roboto", sans-serif;
}
```

---

#### **Step 4: Use the Font in CSS**

Google Fonts provides the CSS code. Copy and use it:

```css
body {
  font-family: "Roboto", sans-serif;
}

h1,
h2,
h3 {
  font-family: "Roboto", sans-serif;
  font-weight: 700; /* Bold weight */
}

p {
  font-family: "Roboto", sans-serif;
  font-weight: 400; /* Regular weight */
}
```

**Note:** Always include a fallback (`sans-serif`, `serif`, etc.) in case the font fails to load.

---

#### **Complete Example: Google Fonts**

**HTML:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>My Site</title>

    <!-- Google Fonts: Roboto -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
      rel="stylesheet"
    />

    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Welcome to My Site</h1>
    <p>This text uses the Roboto font from Google Fonts.</p>
  </body>
</html>
```

**CSS:**

```css
body {
  font-family: "Roboto", sans-serif;
  font-weight: 400;
}

h1 {
  font-family: "Roboto", sans-serif;
  font-weight: 700;
}
```

**Result:** Page loads with Roboto font instead of Arial.

---

#### **Using Multiple Google Fonts**

You can load multiple fonts at once.

**Example: Roboto for body text, Playfair Display for headings**

**HTML:**

```html
<link
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&family=Playfair+Display:wght@700&display=swap"
  rel="stylesheet"
/>
```

**CSS:**

```css
body {
  font-family: "Roboto", sans-serif;
}

h1,
h2,
h3 {
  font-family: "Playfair Display", serif;
  font-weight: 700;
}
```

---

### **Method 2: Self-Hosted Fonts (@font-face) 📦**

For more control, you can **host font files yourself** using `@font-face`.

**When to use:**

- You have custom brand fonts
- You want maximum control over loading
- You don't want to rely on third-party services

---

#### **Step 1: Get Font Files**

**Common font formats:**

- `.woff2` (best, modern browsers)
- `.woff` (fallback for older browsers)
- `.ttf` or `.otf` (older, larger files)

**Where to get fonts:**

- Purchase from font foundries (MyFonts, Adobe Fonts, etc.)
- Free fonts from [Google Fonts](https://fonts.google.com) (download button)
- Free fonts from [Font Squirrel](https://www.fontsquirrel.com)

---

#### **Step 2: Add Font Files to Your Project**

**Folder structure:**

```
my-project/
├── index.html
├── css/
│   └── styles.css
└── fonts/
    ├── Roboto-Regular.woff2
    ├── Roboto-Regular.woff
    ├── Roboto-Bold.woff2
    └── Roboto-Bold.woff
```

---

#### **Step 3: Use @font-face in CSS**

**Syntax:**

```css
@font-face {
  font-family: "Font Name";
  src:
    url("path/to/font.woff2") format("woff2"),
    url("path/to/font.woff") format("woff");
  font-weight: 400;
  font-style: normal;
}
```

**Complete example:**

```css
/* Define the font */
@font-face {
  font-family: "Roboto";
  src:
    url("../fonts/Roboto-Regular.woff2") format("woff2"),
    url("../fonts/Roboto-Regular.woff") format("woff");
  font-weight: 400;
  font-style: normal;
}

@font-face {
  font-family: "Roboto";
  src:
    url("../fonts/Roboto-Bold.woff2") format("woff2"),
    url("../fonts/Roboto-Bold.woff") format("woff");
  font-weight: 700;
  font-style: normal;
}

/* Use the font */
body {
  font-family: "Roboto", sans-serif;
}

h1 {
  font-family: "Roboto", sans-serif;
  font-weight: 700;
}
```

---

#### **Understanding @font-face Properties**

| Property      | Description              | Example                      |
| ------------- | ------------------------ | ---------------------------- |
| `font-family` | Name you'll use in CSS   | `'Roboto'`                   |
| `src`         | Path to font files       | `url('../fonts/font.woff2')` |
| `font-weight` | Weight of this font file | `400`, `700`                 |
| `font-style`  | Style of this font file  | `normal`, `italic`           |

**Important:** Each weight and style needs its own `@font-face` declaration.

---

#### **Multiple Weights Example**

```css
/* Regular (400) */
@font-face {
  font-family: "MyFont";
  src: url("../fonts/MyFont-Regular.woff2") format("woff2");
  font-weight: 400;
  font-style: normal;
}

/* Bold (700) */
@font-face {
  font-family: "MyFont";
  src: url("../fonts/MyFont-Bold.woff2") format("woff2");
  font-weight: 700;
  font-style: normal;
}

/* Italic (400) */
@font-face {
  font-family: "MyFont";
  src: url("../fonts/MyFont-Italic.woff2") format("woff2");
  font-weight: 400;
  font-style: italic;
}
```

**Usage:**

```css
p {
  font-family: "MyFont", sans-serif;
  font-weight: 400; /* Uses MyFont-Regular */
}

strong {
  font-family: "MyFont", sans-serif;
  font-weight: 700; /* Uses MyFont-Bold */
}

em {
  font-family: "MyFont", sans-serif;
  font-style: italic; /* Uses MyFont-Italic */
}
```

---

### **Font Formats & Browser Support 🌐**

**Modern format (use this):**

- `.woff2` - Best compression, supported by all modern browsers

**Fallback format:**

- `.woff` - Older browsers

**Legacy formats (rarely needed):**

- `.ttf` / `.otf` - Older browsers (IE9 and below)

**Recommended approach:**

```css
@font-face {
  font-family: "MyFont";
  src:
    url("../fonts/MyFont.woff2") format("woff2"),
    url("../fonts/MyFont.woff") format("woff");
  /* Browser tries woff2 first, falls back to woff if needed */
}
```

---

### **Performance Considerations ⚡**

**Fonts can slow down your page.** Here's how to optimize:

---

#### **1. Only Load Weights You Need**

**Bad (loads 6 weights):**

```html
<link
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700;900&display=swap"
  rel="stylesheet"
/>
```

**Good (loads 2 weights):**

```html
<link
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
  rel="stylesheet"
/>
```

**Each weight adds ~20-50KB to your page load.**

---

#### **2. Use `font-display` for Faster Rendering**

```css
@font-face {
  font-family: "MyFont";
  src: url("../fonts/MyFont.woff2") format("woff2");
  font-display: swap; /* Show fallback font immediately, swap when custom font loads */
}
```

**`font-display` options:**

| Value      | Behavior                                                                      |
| ---------- | ----------------------------------------------------------------------------- |
| `swap`     | Show fallback font immediately, swap to custom font when loaded (recommended) |
| `block`    | Hide text until custom font loads (can create "flash of invisible text")      |
| `fallback` | Short block period, then show fallback, swap if font loads quickly            |
| `optional` | Show fallback, only swap if font loads very quickly                           |

**Recommended:** Use `swap` for better user experience.

---

#### **3. Preconnect to Font Servers**

**When using Google Fonts:**

```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
```

**What this does:** Establishes early connection to Google's servers, speeding up font loading.

---

#### **4. Limit Number of Fonts**

**Bad (too many fonts):**

```css
body {
  font-family: "Font1", sans-serif;
}
h1 {
  font-family: "Font2", serif;
}
h2 {
  font-family: "Font3", sans-serif;
}
nav {
  font-family: "Font4", sans-serif;
}
```

**Good (2 fonts max):**

```css
body {
  font-family: "Roboto", sans-serif;
}
h1,
h2,
h3 {
  font-family: "Playfair Display", serif;
}
```

**Rule of thumb:** Use 1-2 fonts per project.

---

### **Common Mistakes 🐞**

#### **Mistake 1: Wrong file path**

```css
/* Wrong - font file is in fonts/ folder */
@font-face {
  font-family: "MyFont";
  src: url("MyFont.woff2") format("woff2");
}

/* Correct */
@font-face {
  font-family: "MyFont";
  src: url("../fonts/MyFont.woff2") format("woff2");
}
```

**Check:** Where is your CSS file relative to the font file?

---

#### **Mistake 2: Forgetting font-weight in @font-face**

```css
/* Wrong - browser doesn't know this is the bold version */
@font-face {
  font-family: "MyFont";
  src: url("../fonts/MyFont-Bold.woff2") format("woff2");
  /* Missing font-weight! */
}

/* Correct */
@font-face {
  font-family: "MyFont";
  src: url("../fonts/MyFont-Bold.woff2") format("woff2");
  font-weight: 700;
}
```

---

#### **Mistake 3: Not including fallback fonts**

```css
/* Bad - if font fails to load, browser uses default */
body {
  font-family: "Roboto";
}

/* Good - fallback to sans-serif if Roboto fails */
body {
  font-family: "Roboto", sans-serif;
}
```

---

#### **Mistake 4: Loading too many font weights**

```html
<!-- Bad - loads 9 weights (huge file size) -->
<link
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;200;300;400;500;600;700;800;900&display=swap"
  rel="stylesheet"
/>

<!-- Good - loads 2 weights you'll actually use -->
<link
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
  rel="stylesheet"
/>
```

---

#### **Mistake 5: Using the wrong font name**

```css
/* Wrong - font name doesn't match @font-face declaration */
@font-face {
  font-family: "MyCustomFont";
  src: url("../fonts/font.woff2") format("woff2");
}

body {
  font-family: "CustomFont", sans-serif; /* Wrong name! */
}

/* Correct */
body {
  font-family: "MyCustomFont", sans-serif; /* Matches @font-face */
}
```

---

### **Google Fonts vs Self-Hosted: Which to Use? 🤔**

| Factor          | Google Fonts                 | Self-Hosted (@font-face)       |
| --------------- | ---------------------------- | ------------------------------ |
| **Ease of use** | ✅ Very easy                 | ❌ More complex                |
| **Speed**       | ✅ Google's CDN is fast      | ⚠️ Depends on your hosting     |
| **Privacy**     | ❌ Loads from Google servers | ✅ No third-party requests     |
| **Control**     | ❌ Limited                   | ✅ Full control                |
| **Cost**        | ✅ Free                      | ⚠️ Some fonts require purchase |
| **Maintenance** | ✅ Google handles updates    | ❌ You handle updates          |

**For beginners:** Start with Google Fonts. It's easy and fast.

**For advanced projects:** Self-host if you need custom fonts or maximum control.

---

### **Practical Example: Complete Setup 💼**

**Using Google Fonts for a blog:**

**HTML:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>My Blog</title>

    <!-- Google Fonts: Merriweather for body, Playfair Display for headings -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Merriweather:wght@400;700&family=Playfair+Display:wght@700&display=swap"
      rel="stylesheet"
    />

    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <article>
      <h1>Article Title</h1>
      <p>Article content goes here.</p>
    </article>
  </body>
</html>
```

**CSS:**

```css
body {
  font-family: "Merriweather", serif;
  font-weight: 400;
  line-height: 1.8;
  color: #333;
}

h1,
h2,
h3 {
  font-family: "Playfair Display", serif;
  font-weight: 700;
  line-height: 1.2;
  color: #000;
}
```

**Result:** Professional typography with distinct heading and body fonts.

---

### **Key Takeaways 💡**

1. **Google Fonts is easiest** - Great for beginners, free, and fast
2. **Self-hosting gives control** - Use for custom fonts or privacy
3. **Only load weights you need** - Each weight adds to page load time
4. **Always include fallback fonts** - `font-family: 'Custom', sans-serif;`
5. **Use `font-display: swap`** - Shows text immediately while loading
6. **Limit to 1-2 fonts per project** - Too many fonts slow down your site
7. **Test font loading** - Make sure fonts actually appear

**The goal:** Beautiful typography without slowing down your website.

---

## **Quick Reference 📚**

A condensed reference for quick lookups while working with CSS structure and organization.

---

### **File Organization Patterns**

**Single file (small projects):**

```
project/
├── index.html
└── styles.css
```

**Multiple files (medium projects):**

```
project/
├── index.html
└── css/
    ├── base.css
    ├── layout.css
    ├── components.css
    └── pages.css
```

**Component-based (large projects):**

```
project/
├── index.html
└── css/
    ├── base/
    │   ├── variables.css
    │   └── reset.css
    ├── components/
    │   ├── buttons.css
    │   └── cards.css
    └── main.css
```

---

### **Importing Stylesheets**

**Multiple `<link>` tags (HTML):**

```html
<head>
  <link rel="stylesheet" href="css/base.css" />
  <link rel="stylesheet" href="css/layout.css" />
  <link rel="stylesheet" href="css/components.css" />
</head>
```

**@import (CSS):**

```css
/* Must be at top of file */
@import "base.css";
@import "layout.css";
@import "components.css";

/* Your CSS below */
```

**@import with folders:**

```css
@import "base/variables.css";
@import "base/reset.css";
@import "components/buttons.css";
```

---

### **Naming Conventions**

**Kebab-case (always use this):**

```css
.product-card {
}
.navigation-menu {
}
.user-profile {
}
```

**BEM syntax:**

```css
/* Block */
.product-card {
}

/* Element */
.product-card__title {
}
.product-card__image {
}
.product-card__button {
}

/* Modifier */
.product-card--featured {
}
.product-card__button--primary {
}
```

**HTML with BEM:**

```html
<div class="product-card product-card--featured">
  <img class="product-card__image" src="..." />
  <h3 class="product-card__title">Title</h3>
  <button class="product-card__button product-card__button--primary">
    Buy Now
  </button>
</div>
```

---

### **CSS Variables**

**Define in :root:**

```css
:root {
  --color-primary: #3498db;
  --color-secondary: #e74c3c;
  --spacing-md: 16px;
  --font-primary: Arial, sans-serif;
}
```

**Use with var():**

```css
.button {
  background-color: var(--color-primary);
  padding: var(--spacing-md);
  font-family: var(--font-primary);
}
```

**With fallback:**

```css
.button {
  background-color: var(--color-primary, blue);
}
```

**Scoped variables (override):**

```css
:root {
  --bg-color: white;
  --text-color: black;
}

.dark-mode {
  --bg-color: black;
  --text-color: white;
}
```

---

### **Common Variable Patterns**

**Colors:**

```css
:root {
  --color-primary: #3498db;
  --color-secondary: #e74c3c;
  --color-success: #2ecc71;
  --color-warning: #f39c12;
  --color-danger: #e74c3c;
  --color-dark: #2c3e50;
  --color-gray: #95a5a6;
  --color-light: #ecf0f1;
}
```

**Spacing scale:**

```css
:root {
  --spacing-xs: 4px;
  --spacing-sm: 8px;
  --spacing-md: 16px;
  --spacing-lg: 24px;
  --spacing-xl: 32px;
  --spacing-2xl: 48px;
}
```

**Typography:**

```css
:root {
  --font-primary: Arial, sans-serif;
  --font-secondary: Georgia, serif;
  --font-mono: "Courier New", monospace;

  --font-size-xs: 0.75rem;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.25rem;
  --font-size-xl: 1.5rem;
  --font-size-2xl: 2rem;
}
```

---

### **Comment Formats**

**Section divider:**

```css
/* ==============================================
   SECTION NAME
   ============================================== */
```

**Subsection:**

```css
/* Components */
```

**Inline explanation:**

```css
.element {
  property: value; /* Explains why this value is used */
}
```

**Multi-line explanation:**

```css
/*
  This is a longer explanation that spans
  multiple lines. Use for complex decisions
  or important context.
*/
```

**TODO markers:**

```css
/* TODO: Add responsive styles */
/* FIXME: This breaks on mobile */
/* NOTE: Don't change without testing */
```

**Component documentation:**

```css
/*
 * Component Name
 * 
 * Used on: Page names
 * 
 * Modifiers:
 *   .component--modifier - Description
 * 
 * Example:
 *   <div class="component">...</div>
 */
```

---

### **Google Fonts Setup**

**HTML (link method):**

```html
<head>
  <!-- Preconnect for speed -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />

  <!-- Load font -->
  <link
    href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
    rel="stylesheet"
  />
</head>
```

**CSS:**

```css
body {
  font-family: "Roboto", sans-serif;
}
```

**@import method:**

```css
/* At top of CSS file */
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

body {
  font-family: "Roboto", sans-serif;
}
```

---

### **Self-Hosted Fonts**

**@font-face syntax:**

```css
@font-face {
  font-family: "FontName";
  src:
    url("../fonts/FontName.woff2") format("woff2"),
    url("../fonts/FontName.woff") format("woff");
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}
```

**Multiple weights:**

```css
/* Regular (400) */
@font-face {
  font-family: "FontName";
  src: url("../fonts/FontName-Regular.woff2") format("woff2");
  font-weight: 400;
  font-style: normal;
}

/* Bold (700) */
@font-face {
  font-family: "FontName";
  src: url("../fonts/FontName-Bold.woff2") format("woff2");
  font-weight: 700;
  font-style: normal;
}
```

**Use:**

```css
body {
  font-family: "FontName", sans-serif;
}

strong {
  font-weight: 700; /* Uses bold font file */
}
```

---

### **Useful Code Snippets**

**CSS Reset:**

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

**Container:**

```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}
```

**Responsive image:**

```css
img {
  max-width: 100%;
  height: auto;
}
```

**Hide element:**

```css
.hidden {
  display: none;
}

.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
}
```

**Center element:**

```css
.center {
  margin: 0 auto;
}
```

**Smooth transitions:**

```css
.element {
  transition: all 0.3s ease;
}
```

---

### **DRY Principle Patterns**

**Group selectors:**

```css
h1,
h2,
h3 {
  font-family: Georgia, serif;
  color: #2c3e50;
}
```

**Base class + modifiers:**

```css
.button {
  padding: 10px 20px;
  border: none;
  cursor: pointer;
}

.button--primary {
  background-color: blue;
  color: white;
}

.button--secondary {
  background-color: gray;
  color: white;
}
```

**Use variables for repeated values:**

```css
/* Don't repeat */
.header {
  background-color: #3498db;
}
.button {
  background-color: #3498db;
}
.link {
  color: #3498db;
}

/* Do this instead */
:root {
  --color-primary: #3498db;
}

.header {
  background-color: var(--color-primary);
}
.button {
  background-color: var(--color-primary);
}
.link {
  color: var(--color-primary);
}
```

---

### **File Organization Decision Guide**

| Project Size | Strategy                  | File Count |
| ------------ | ------------------------- | ---------- |
| 1-10 pages   | Single file               | 1          |
| 10-30 pages  | Multiple files by purpose | 3-6        |
| 30+ pages    | Component-based folders   | 10-30+     |

---

### **Import Order**

**Always import in this order:**

1. Variables (first - other files use them)
2. Resets/base styles
3. Typography
4. Layout
5. Components
6. Pages (last - overrides if needed)

**Example:**

```css
@import "base/variables.css";
@import "base/reset.css";
@import "base/typography.css";
@import "layout/header.css";
@import "layout/footer.css";
@import "components/buttons.css";
@import "components/cards.css";
@import "pages/home.css";
```

---

### **Common Mistakes to Avoid 🐞**

1. ❌ Forgetting `--` prefix for variables → ✅ `--variable-name`
2. ❌ Forgetting `var()` to use variables → ✅ `var(--variable-name)`
3. ❌ @import not at top of file → ✅ @import must be first
4. ❌ Using `//` for comments → ✅ Use `/* */`
5. ❌ Forgetting fallback fonts → ✅ `'Custom', sans-serif`
6. ❌ Loading too many font weights → ✅ Only load what you need
7. ❌ Inconsistent naming → ✅ Pick one convention, stick with it
8. ❌ No section comments in large files → ✅ Use dividers

---

### **Quick Checklist for New Projects ✅**

**Before you start:**

- [ ] Decide on file structure (single file vs multiple)
- [ ] Choose naming convention (BEM or simple)
- [ ] Set up variables for colors, spacing, fonts
- [ ] Add CSS reset
- [ ] Load custom fonts if needed

**During development:**

- [ ] Use comments to organize sections
- [ ] Follow DRY principle (don't repeat values)
- [ ] Keep files focused (one purpose per file)
- [ ] Use consistent naming

**Before launch:**

- [ ] Remove unused CSS
- [ ] Remove TODO/FIXME comments
- [ ] Test font loading
- [ ] Validate CSS (W3C validator)

---

### **Helpful Resources**

**Documentation:**

- [MDN CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
- [CSS-Tricks](https://css-tricks.com)

**Fonts:**

- [Google Fonts](https://fonts.google.com)
- [Font Squirrel](https://www.fontsquirrel.com)

**Validation:**

- [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)

**BEM Naming:**

- [BEM Methodology](https://getbem.com)
