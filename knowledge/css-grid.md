# CSS Grid

- [What is Grid & Why It Exists 🎯](#what-is-grid--why-it-exists-)
  - [The Problem Grid Solves 🔧](#the-problem-grid-solves-)
  - [What "Two-Dimensional" Means 📐](#what-two-dimensional-means-)
  - [How Grid Actually Works (The Basic Concept) 🧠](#how-grid-actually-works-the-basic-concept-)
  - [Grid vs Flexbox: When to Use Which 🆚](#grid-vs-flexbox-when-to-use-which-)
  - [Your First Grid Example 🚀](#your-first-grid-example-)
  - [Summary 📋](#summary-)
- [Grid Container vs Grid Items 🔗](#grid-container-vs-grid-items-)
  - [What is a Grid Container? 📦](#what-is-a-grid-container-)
  - [What is a Grid Item? 🎁](#what-is-a-grid-item-)
  - [Direct Children Only! ⚠️](#direct-children-only-️)
  - [Container Properties vs Item Properties 🎯](#container-properties-vs-item-properties-)
  - [Common Mistakes 🐞](#common-mistakes-)
  - [Nested Grid Containers 🪆](#nested-grid-containers-)
  - [Quick Reference: Which Property Goes Where? 📋](#quick-reference-which-property-goes-where-)
  - [Summary 📋](#summary--1)
- [Grid Lines, Tracks, and Cells 📏](#grid-lines-tracks-and-cells-)
  - [The Four Core Concepts 🎯](#the-four-core-concepts-)
  - [Grid Lines 📍](#grid-lines-)
  - [Grid Tracks 🛤️](#grid-tracks-️)
  - [Grid Cells 📦](#grid-cells-)
  - [Grid Areas 🗺️](#grid-areas-)
  - [Putting It All Together 🧩](#putting-it-all-together-)
  - [How Items Use Lines to Position Themselves 🎯](#how-items-use-lines-to-position-themselves-)
  - [Explicit vs Implicit Grids 🔍](#explicit-vs-implicit-grids-)
  - [Common Terminology Mistakes 🐞](#common-terminology-mistakes-)
  - [Visual Summary 📊](#visual-summary-)
  - [Summary 📋](#summary--2)
- [Defining the Grid Structure 📐](#defining-the-grid-structure-)
  - [`grid-template-columns` and `grid-template-rows`](#grid-template-columns-and-grid-template-rows)
  - [The `fr` Unit 📏](#the-fr-unit-)
  - [The `repeat()` Function 🔄](#the-repeat-function-)
  - [`gap` — Space Between Cells](#gap--space-between-cells)
  - [Putting It All Together](#putting-it-all-together)
  - [Common Mistakes 🐞](#common-mistakes--1)
  - [Summary 📋](#summary--3)
- [Positioning Grid Items 📍](#positioning-grid-items-)
  - [How Item Positioning Works](#how-item-positioning-works)
  - [`grid-column` and `grid-row`](#grid-column-and-grid-row)
  - [The `span` Keyword](#the-span-keyword)
  - [Negative Line Numbers](#negative-line-numbers)
  - [`grid-area` — The Combined Shorthand](#grid-area--the-combined-shorthand)
  - [Automatic Placement for Unpositioned Items](#automatic-placement-for-unpositioned-items)
  - [Common Mistakes 🐞](#common-mistakes--2)
  - [Summary 📋](#summary--4)
- [Grid Template Areas 🗺️](#grid-template-areas-)
  - [How It Works](#how-it-works)
  - [Step 1 — Defining Areas on the Container](#step-1--defining-areas-on-the-container)
  - [Step 2 — Assigning Items to Areas](#step-2--assigning-items-to-areas)
  - [Empty Cells — The `.` Placeholder](#empty-cells--the--placeholder)
  - [The Rules for Valid Areas](#the-rules-for-valid-areas)
  - [Template Areas vs Line Numbers — Which to Use?](#template-areas-vs-line-numbers--which-to-use)
  - [Common Mistakes 🐞](#common-mistakes--3)
  - [Summary 📋](#summary--5)
- [Alignment and Distribution 🎯](#alignment-and-distribution-)
  - [Part 1 — Distributing Tracks Within the Container](#part-1--distributing-tracks-within-the-container)
  - [Part 2 — Aligning Items Within Their Cells](#part-2--aligning-items-within-their-cells)
  - [Putting It All Together](#putting-it-all-together--1)
  - [Quick Reference — Which Property Does What?](#quick-reference--which-property-does-what)
  - [Common Mistakes 🐞](#common-mistakes--4)
  - [Summary 📋](#summary--6)
- [Common Use Cases & Patterns 🎨](#common-use-cases--patterns-)
  - [Pattern 1: Classic Page Layout](#pattern-1-classic-page-layout)
  - [Pattern 2: Card Grid](#pattern-2-card-grid)
  - [Pattern 3: Featured Item Grid](#pattern-3-featured-item-grid)
  - [Pattern 4: Holy Grail Layout](#pattern-4-holy-grail-layout)
  - [Pattern 5: Dashboard Layout](#pattern-5-dashboard-layout)
  - [Pattern 6: Centered Content](#pattern-6-centered-content)
- [Quick Reference 📚](#quick-reference-)
  - [Container Properties](#container-properties)
  - [Item Properties](#item-properties)
  - [Key Syntax](#key-syntax)
  - [The `fr` Unit](#the-fr-unit)
  - [Line Numbers](#line-numbers)
  - [Alignment Values](#alignment-values)
  - [Which Property Do I Need? 🌳](#which-property-do-i-need-)
  - [Common Mistakes Checklist ✅](#common-mistakes-checklist-)

---

## **What is Grid & Why It Exists 🎯**

CSS Grid (officially "CSS Grid Layout") is a layout system designed to arrange elements in **two dimensions** - both rows AND columns at the same time. It gives you precise control over complex layouts that would be difficult or impossible with other CSS techniques.

**Think of it like this:**

Imagine you're designing a newspaper layout. You need:

- A masthead across the top
- Multiple columns of articles
- Sidebar ads of different sizes
- Photos that span multiple columns
- A footer at the bottom

Before Grid, creating this layout required complicated calculations, nested elements, and hacky workarounds. With Grid, you define the structure once, and elements snap into place.

That's CSS Grid - a layout system where you design the structure first, then place items into it.

---

### **The Problem Grid Solves 🔧**

Before Grid existed (pre-2017), creating complex two-dimensional layouts was **painful**.

**Common layout challenges:**

- Creating a page with header, sidebar, content, and footer
- Building a gallery with items of different sizes
- Making a dashboard with panels that span multiple rows and columns
- Aligning items both horizontally AND vertically at the same time

**The old way (using floats, positioning, and flexbox):**

```css
/* Just to create a basic sidebar + content layout... */
.sidebar {
  float: left;
  width: 250px;
}

.content {
  margin-left: 270px; /* 250px + 20px gap */
}

/* Had to clear floats */
.container::after {
  content: "";
  display: table;
  clear: both;
}

/* And this breaks if sidebar is taller than content! */
```

This required:

- Manual width calculations
- Clearing floats
- Nested containers for alignment
- Media queries to rearrange on mobile
- Lots of trial and error

---

**The Grid way:**

```css
.container {
  display: grid;
  grid-template-columns: 250px 1fr;
  gap: 20px;
}

/* Done. Sidebar and content automatically arrange themselves. */
```

**What Grid does automatically:**

- Creates columns and rows
- Places items in cells
- Handles gaps between items
- Aligns items within cells
- Adapts to different screen sizes

---

### **What "Two-Dimensional" Means 📐**

Grid is called a **two-dimensional** layout system because it controls **both rows AND columns simultaneously**.

**Example structure:**

```
┌────────────────────────────────┐
│  Header (spans all columns)    │ ← Row 1
├──────────┬─────────────────────┤
│ Sidebar  │  Main Content       │ ← Row 2
│          │                     │
├──────────┴─────────────────────┤
│  Footer (spans all columns)    │ ← Row 3
└────────────────────────────────┘
   ↑             ↑
Column 1      Column 2
```

With Grid, you can:

- Define how many rows and columns exist
- Control the size of each row and column
- Place items anywhere in the grid (not just in order)
- Make items span multiple rows or columns
- Align items within their grid cells

**Key difference from Flexbox:**

- **Flexbox** = one-dimensional (row OR column, items flow in a line)
- **Grid** = two-dimensional (rows AND columns, items placed in cells)

---

### **How Grid Actually Works (The Basic Concept) 🧠**

Grid uses a **parent-child relationship** similar to Flexbox:

1. **The parent (grid container)** defines the structure - how many rows/columns, their sizes
2. **The children (grid items)** get placed into the grid cells

**HTML structure:**

```html
<div class="grid-container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</div>
```

**CSS:**

```css
.grid-container {
  display: grid; /* Activates Grid */
  grid-template-columns: 200px 200px; /* 2 columns, 200px each */
  grid-template-rows: 100px 100px; /* 2 rows, 100px each */
  gap: 10px; /* Space between cells */
}
```

**What just happened:**

- `.grid-container` is the **grid container** (the parent)
- The four `.item` divs are **grid items** (the children)
- Setting `display: grid` activates the grid layout
- We defined a 2x2 grid (2 columns, 2 rows)
- Items automatically flow into the grid cells

**Default behavior:**

```
┌──────────┬──────────┐
│    1     │    2     │ ← Row 1
├──────────┼──────────┤
│    3     │    4     │ ← Row 2
└──────────┴──────────┘
 Column 1   Column 2
```

Items fill the grid from left to right, top to bottom, one item per cell.

---

### **Grid vs Flexbox: When to Use Which 🆚**

**Use Grid when you need:**

✅ **Two-dimensional layouts** - control over both rows AND columns
✅ **Precise placement** - items in specific grid positions
✅ **Overlapping items** - elements that occupy the same cells
✅ **Complex page layouts** - header, sidebar, content, footer structures
✅ **Layout-first design** - you define the structure, items fill it

**Common Grid use cases:**

- Page layouts (header, sidebar, content, footer)
- Photo galleries with items of different sizes
- Dashboards with panels
- Magazine-style layouts
- Card grids where some cards span multiple rows/columns

---

**Use Flexbox when you need:**

✅ **One-dimensional layouts** - items in a single row or column
✅ **Content-first design** - layout adapts to content size
✅ **Dynamic spacing** - distributing items with space-between, space-around
✅ **Component-level layouts** - navigation bars, button groups, form fields
✅ **Items that wrap** - cards that flow to new lines

**Common Flexbox use cases:**

- Navigation bars
- Button groups
- Form layouts
- Media objects (image + text)
- Centering content

---

**The relationship between Grid and Flexbox:**

They're **complementary**, not competing. Modern layouts often use both:

- **Grid** for overall page structure
- **Flexbox** for components within grid items

**Example:**

```css
/* Grid for page layout */
.page {
  display: grid;
  grid-template-columns: 250px 1fr;
  grid-template-rows: auto 1fr auto;
}

/* Flexbox for navigation within header */
.header nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

---

### **Your First Grid Example 🚀**

Let's create a simple grid to see it in action:

**HTML:**

```html
<div class="gallery">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</div>
```

**CSS:**

```css
.gallery {
  display: grid;
  grid-template-columns: 200px 200px 200px; /* 3 columns */
  grid-template-rows: 150px 150px; /* 2 rows */
  gap: 20px;
  background-color: #f0f0f0;
  padding: 20px;
}

.item {
  background-color: #3498db;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2rem;
  border-radius: 8px;
}
```

**Result:**

```
┌──────────────────────────────┐ ← Container (with padding)
│                              │
│  ┌────┐    ┌────┐    ┌────┐  │
│  │ 1  │    │ 2  │    │ 3  │  │ ← Row 1
│  └────┘    └────┘    └────┘  │
│     ↕ 20px gap               │
│  ┌────┐    ┌────┐    ┌────┐  │
│  │ 4  │    │ 5  │    │ 6  │  │ ← Row 2
│  └────┘    └────┘    └────┘  │
│         ↔ 20px gap           │
└──────────────────────────────┘
```

**What Grid did:**

- Created a 3x2 grid (3 columns, 2 rows)
- Placed items automatically from left to right, top to bottom
- Added 20px gaps between cells
- Made all cells exactly 200px × 150px

---

### **Summary 📋**

**CSS Grid is:**

- A two-dimensional layout system
- Designed for complex layouts with rows AND columns
- Layout-first (you define structure, items fill it)
- Perfect for page-level layouts

**Key differences from Flexbox:**

| Aspect              | Grid                                           | Flexbox                                                    |
| ------------------- | ---------------------------------------------- | ---------------------------------------------------------- |
| **Dimensions**      | Two-dimensional (rows AND columns)             | One-dimensional (row OR column)                            |
| **Design approach** | Layout-first (define structure, items fill it) | Content-first (content determines layout)                  |
| **Best for**        | Page layouts, complex grids, Dashboards        | Component layouts, single-direction flows, Navigation bars |
| **Control**         | Precise placement in rows AND columns          | Distribution along one axis                                |

**Use both together:**

- Grid for overall structure
- Flexbox for components within grid items

**Next up:** We'll dive into the container-item relationship and understand which properties go where.

---

## **Grid Container vs Grid Items 🔗**

Just like Flexbox, Grid has **two separate sets of properties** that control **two different things**:

1. **Container properties** (applied to the parent) - define the grid structure
2. **Item properties** (applied to the children) - control individual item placement

These properties **cannot be mixed**. Container properties only work on containers. Item properties only work on items.

**Think of it like this:**

Imagine you're organizing a parking lot:

- **The parking lot owner (container)** decides how many rows and columns of spaces exist, how wide each space is, and the spacing between them
- **The drivers (items)** decide which specific spaces to park in, whether to take up multiple spaces (like a truck), or where to position their car within their space

The owner controls the lot structure. Drivers control their individual parking. They don't cross roles.

That's exactly how Grid works.

---

### **What is a Grid Container? 📦**

A **grid container** is any element that has `display: grid` applied to it.

```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

```css
.container {
  display: grid; /* This makes .container a grid container */
}
```

**What happens:**

- `.container` becomes a grid container
- All **direct children** automatically become grid items
- The container can now use container properties
- The items can now use item properties

---

### **What is a Grid Item? 🎁**

A **grid item** is any **direct child** of a grid container.

```html
<div class="container">
  <div class="item">I'm a grid item</div>
  <div class="item">I'm also a grid item</div>
  <p>I'm a grid item too!</p>
  <span>And me!</span>
</div>
```

```css
.container {
  display: grid;
}
```

**Important:** ALL direct children become grid items automatically. It doesn't matter if they're `<div>`, `<p>`, `<span>`, or anything else.

---

### **Direct Children Only! ⚠️**

This is crucial: **Only DIRECT children become grid items**.

```html
<div class="container">
  <div class="item">
    I'm a grid item ✅
    <p>I'm NOT a grid item ❌ (I'm a grandchild)</p>
  </div>
  <div class="item">I'm a grid item ✅</div>
</div>
```

**Why this matters:**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}
```

The `gap` creates space between the two `.item` divs, but it does NOT affect the `<p>` inside the first item, because that `<p>` is not a direct child of `.container`.

**Visual representation:**

```
Container (grid container)
├─ Item 1 (grid item) ✅
│  └─ Paragraph (NOT a grid item) ❌
└─ Item 2 (grid item) ✅
```

---

### **Container Properties vs Item Properties 🎯**

Here's the complete breakdown of which properties go where.

#### **Container Properties (Parent)**

These go on the element with `display: grid`:

```css
.container {
  display: grid; /* Activates grid */

  /* Define grid structure */
  grid-template-columns: 200px 1fr; /* Column sizes */
  grid-template-rows: 100px auto; /* Row sizes */
  grid-template-areas: "..."; /* Named areas */

  /* Spacing */
  gap: 20px; /* Space between cells */
  row-gap: 10px; /* Vertical spacing */
  column-gap: 20px; /* Horizontal spacing */

  /* Align the grid within container */
  justify-content: center; /* Horizontal alignment of grid */
  align-content: center; /* Vertical alignment of grid */
  place-content: center; /* Shorthand for both */

  /* Align items within their cells */
  justify-items: start; /* Horizontal alignment of items */
  align-items: start; /* Vertical alignment of items */
  place-items: start; /* Shorthand for both */
}
```

**What these control:**

- How many rows and columns exist
- The size of each row and column
- Spacing between cells
- How the grid aligns within the container
- Default alignment for all items within their cells

---

#### **Item Properties (Children)**

These go on the direct children of the grid container:

```css
.item {
  /* Placement */
  grid-column-start: 1; /* Starting column line */
  grid-column-end: 3; /* Ending column line */
  grid-column: 1 / 3; /* Shorthand */

  grid-row-start: 1; /* Starting row line */
  grid-row-end: 2; /* Ending row line */
  grid-row: 1 / 2; /* Shorthand */

  grid-area: 1 / 1 / 2 / 3; /* Shorthand for all four */
  grid-area: header; /* Or named area */

  /* Individual alignment */
  justify-self: end; /* Horizontal alignment within cell */
  align-self: center; /* Vertical alignment within cell */
  place-self: center; /* Shorthand for both */
}
```

**What these control:**

- Which grid cells the item occupies
- How many cells the item spans
- The item's alignment within its cell (overriding container defaults)

---

### **Why the Separation? 🤔**

**Container properties** answer the question: "What does the grid structure look like?"

- How many columns and rows?
- How big is each column and row?
- How much space between cells?
- Where is the grid positioned in the container?

**Item properties** answer the question: "Where should THIS specific item be placed in the grid?"

- Which cells should this item occupy?
- Should this item span multiple cells?
- How should this item align within its cell?

---

### **Common Mistakes 🐞**

#### **Mistake 1: Putting container properties on items**

```css
/* ❌ Wrong */
.item {
  grid-template-columns: 1fr 1fr; /* This does nothing! */
  gap: 20px; /* This does nothing! */
}
```

**Why it fails:** These are container properties. Items can't use them.

**Fix:**

```css
/* ✅ Correct */
.container {
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}
```

---

#### **Mistake 2: Putting item properties on containers**

```css
/* ❌ Wrong */
.container {
  grid-column: 1 / 3; /* This does nothing! */
  grid-row: 1 / 2; /* This does nothing! */
}
```

**Why it fails:** These are item properties. Containers can't use them.

**Fix:**

```css
/* ✅ Correct */
.item {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}
```

---

#### **Mistake 3: Forgetting `display: grid`**

```css
/* ❌ Wrong */
.container {
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  /* Missing display: grid! */
}
```

**Why it fails:** Without `display: grid`, the container isn't a grid container, so grid properties are ignored.

**Fix:**

```css
/* ✅ Correct */
.container {
  display: grid; /* Must be present */
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}
```

---

#### **Mistake 4: Expecting grandchildren to be grid items**

```html
<div class="container">
  <div class="item">
    <p class="text">Hello</p>
  </div>
</div>
```

```css
.container {
  display: grid;
  gap: 20px; /* Only affects .item, NOT .text */
}
```

**Why it fails:** `gap` only affects direct children (`.item`), not grandchildren (`.text`).

**If you need .text to be a grid item:**

```css
.item {
  display: grid; /* Make .item a grid container too */
  gap: 10px; /* Now affects .text */
}
```

Now you have **nested grid containers**:

- `.container` is a grid container with `.item` as its grid item
- `.item` is ALSO a grid container with `.text` as its grid item

This is completely valid and very common!

---

### **Nested Grid Containers 🪆**

An element can be BOTH a grid item AND a grid container at the same time.

```html
<div class="outer-grid">
  <div class="inner-grid">
    <div class="item">A</div>
    <div class="item">B</div>
  </div>
  <div class="inner-grid">
    <div class="item">C</div>
    <div class="item">D</div>
  </div>
</div>
```

```css
/* Outer grid */
.outer-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

/* Inner grids are BOTH grid items AND grid containers */
.inner-grid {
  /* CONTAINER properties - controls its children (A, B, C, D) */
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;

  /* ITEM properties - controls itself within .outer-grid */
  grid-column: span 1; /* Takes up 1 column in outer grid */
  justify-self: stretch; /* Stretches within its grid cell */
}

/* Items */
.item {
  padding: 1rem;
  background-color: #3498db;
  color: white;
}
```

**Understanding the dual role:**

`.inner-grid` can use BOTH sets of properties because it's both a container AND an item:

- As a **container**: Uses `display: grid`, `grid-template-columns`, `gap` to arrange its children (A, B, C, D)
- As an **item**: Could use `grid-column`, `grid-row` to control how it behaves inside `.outer-grid`

Think of it like this: The element looks "up" to its parent (`.outer-grid`) and acts as an item. Then it looks "down" to its children (`.item` elements) and acts as a container.

**What's happening:**

1. `.outer-grid` is a grid container
2. `.inner-grid` elements are grid items inside `.outer-grid`
3. BUT `.inner-grid` is ALSO a grid container for its own children
4. `.item` elements are grid items inside `.inner-grid`

**Result:**

```
┌────────────────────────────────────┐ ← Outer grid
│  ┌──────────────┐ ┌──────────────┐ │
│  │ ┌───┐ ┌───┐  │ │ ┌───┐ ┌───┐  │ │
│  │ │ A │ │ B │  │ │ │ C │ │ D │  │← Inner grids
│  │ └───┘ └───┘  │ │ └───┘ └───┘  │ │
│  └──────────────┘ └──────────────┘ │
└────────────────────────────────────┘
```

This creates a nested layout where:

- Outer grid arranges inner grids side by side
- Each inner grid arranges its items in two columns

---

### **Quick Reference: Which Property Goes Where? 📋**

**Container Properties (on parent):**

- `display: grid`
- `grid-template-columns`
- `grid-template-rows`
- `grid-template-areas`
- `gap` / `row-gap` / `column-gap`
- `justify-content` / `align-content` / `place-content`
- `justify-items` / `align-items` / `place-items`

**Item Properties (on children):**

- `grid-column-start` / `grid-column-end` / `grid-column`
- `grid-row-start` / `grid-row-end` / `grid-row`
- `grid-area`
- `justify-self` / `align-self` / `place-self`

**Remember:** If you're not sure, ask yourself: "Am I defining the grid structure (container) or placing an individual item within that grid (item)?"

---

### **Summary 📋**

**Container (parent):**

- Has `display: grid`
- Defines the grid structure (columns, rows, gaps)
- Controls overall grid alignment
- Sets default alignment for all items

**Items (direct children):**

- Automatically become grid items when parent has `display: grid`
- Control their own placement in the grid
- Can span multiple cells
- Can override default alignment

**Key rules:**

1. Container properties only work on containers
2. Item properties only work on items
3. Only direct children become grid items
4. An element can be both a container AND an item (nested grids)

**Remember:** Container = "What does the grid look like?" / Item = "Where should I be placed in that grid?"

---

## **Grid Lines, Tracks, and Cells 📏**

Before we start building grids, you need to understand the **terminology**. Grid uses specific terms to describe its structure, and knowing these terms is essential for understanding how positioning works.

**Think of it like this:**

If you're learning chess, you need to know what "ranks" (horizontal rows), "files" (vertical columns), and "squares" are before you can understand how pieces move. Same with Grid. You need to know what "grid lines," "tracks," and "cells" are before you can build layouts.

---

### **The Four Core Concepts 🎯**

Grid structure has four key terms:

1. **Grid Lines** - The dividing lines that make up the structure
2. **Grid Tracks** - The rows and columns between the lines
3. **Grid Cells** - Individual spaces where items can be placed
4. **Grid Areas** - Groups of one or more cells

Let's break down each one.

---

### **Grid Lines 📍**

**Grid lines** are the horizontal and vertical lines that divide the grid. They're **numbered** starting from 1.

**Key insight:** Grid lines are what you use to position items. When you say `grid-column: 1 / 3`, you're saying "start at line 1, end at line 3."

**Visual example:**

```
           Column Lines →
        1    2    3    4
      1 ┌────┬────┬────┐
Row     │    │    │    │
Lines 2 ├────┼────┼────┤
 ↓      │    │    │    │
      3 └────┴────┴────┘


```

**Understanding the numbering:**

- A grid with **3 columns** has **4 column lines** (one before each column, plus one at the end)
- A grid with **2 rows** has **3 row lines** (one before each row, plus one at the end)

**The formula:** `number of tracks + 1 = number of lines`

---

#### **Positive and Negative Line Numbers**

Grid lines can be counted from **both directions**:

- **Positive numbers:** Count from the start (left/top)
- **Negative numbers:** Count from the end (right/bottom)

**Visual example with a 4-column grid:**

```
        Positive →
    1    2    3    4    5
    ┌────┬────┬────┬────┐
    │    │    │    │    │
    └────┴────┴────┴────┘
    -5  -4   -3   -2   -1
        ← Negative
```

**Why negative numbers are useful:**

```css
/* Span from first line to last line */
.item {
  grid-column: 1 / -1; /* From start to end */
}
```

This works regardless of how many columns you have. `-1` always means "the last line."

---

### **Grid Tracks 🛤️**

**Grid tracks** are the **rows and columns themselves**. Each track is the space between two parallel grid lines.

- **Column tracks** - entire vertical columns (top to bottom)
- **Row tracks** - entire horizontal rows (left to right)

**Visual example:**

```
    ┌────┬────┬────┐
    │    │    │    │ ← Row track 1 (entire horizontal strip)
    ├────┼────┼────┤
    │    │    │    │ ← Row track 2 (entire horizontal strip)
    └────┴────┴────┘
      ↑    ↑    ↑
     Col  Col  Col    ← Column tracks (entire vertical strips)
      1    2    3
```

**This grid has:**

- **3 column tracks** (3 vertical columns)
- **2 row tracks** (2 horizontal rows)

**Key insight:** When you define `grid-template-columns: 200px 300px 100px`, you're creating **three column tracks** with those widths.

---

### **Grid Cells 📦**

**Grid cells** are the **individual boxes** where a row track and column track intersect.

**Visual example with a 3×2 grid (3 columns, 2 rows):**

```
    ┌────┬────┬────┐
    │ 1  │ 2  │ 3  │ ← Row track 1 contains 3 cells
    ├────┼────┼────┤
    │ 4  │ 5  │ 6  │ ← Row track 2 contains 3 cells
    └────┴────┴────┘
      ↑    ↑    ↑
   Column tracks contain 2 cells each
```

**This grid has:**

- **3 column tracks**
- **2 row tracks**
- **6 individual cells** (3 columns × 2 rows)

**Important:** By default, each grid item occupies **one cell**, but items can span multiple cells.

---

### **Grid Areas 🗺️**

**Grid areas** are rectangular groups of one or more cells. An item can span multiple cells to create an area.

**Visual example:**

```
    ┌─────────────┬──────┐
    │      A      │  B   │ ← Area A spans 2 columns
    ├──────┬──────┴──────┤
    │  C   │      D      │ ← Area D spans 2 columns
    └──────┴─────────────┘
```

- **Area A:** 2 columns × 1 row = 2 cells
- **Area B:** 1 column × 1 row = 1 cell
- **Area C:** 1 column × 1 row = 1 cell
- **Area D:** 1 column × 1 row = 2 cell

**Important:** Areas must be **rectangular**. You can't create L-shaped or T-shaped areas.

---

### **Putting It All Together 🧩**

Let's see how all these concepts work together in a complete example:

```css
.container {
  display: grid;
  grid-template-columns: 100px 200px 100px;
  grid-template-rows: 80px 120px;
}
```

**What this creates:**

```
    Column Lines: 1     2      3     4
                  ↓     ↓      ↓     ↓
    Row Line 1 →  ┌─────┬──────┬─────┐
                  │  A  │  B   │  C  │ ← Row Track 1 (80px)
    Row Line 2 →  ├─────┼──────┼─────┤
                  │  D  │  E   │  F  │ ← Row Track 2 (120px)
    Row Line 3 →  └─────┴──────┴─────┘
                   100px  200px  100px
                   ← Column Tracks →
```

**Breaking it down:**

- **4 column lines** (for 3 column tracks)
- **3 row lines** (for 2 row tracks)
- **3 column tracks:** 100px, 200px, 100px
- **2 row tracks:** 80px, 120px
- **6 cells:** A, B, C, D, E, F

---

### **How Items Use Lines to Position Themselves 🎯**

When you position an item, you specify which **grid lines** it should start and end at.

**Example:**

```html
<div class="container">
  <div class="item">Item</div>
  <!-- Other items could go here -->
</div>
```

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
  grid-template-rows: 80px 80px;
  gap: 10px;
}

.item {
  grid-column: 1 / 3; /* Column lines 1 to 3 */
  grid-row: 1 / 2; /* Row lines 1 to 2 */
}
```

**Fixed visual:**

```
    1     2     3     4
  1 ┌─────┬─────┬─────┐
    │   Item    │     │ ← Item: spans columns 1-3, row 1-2 only
  2 ├───────────┼─────┤
    │     │     │     │ ← Empty cells (no item here)
  3 └─────┴─────┴─────┘
```

The item occupies:

- **Columns:** From line 1 to line 3 (2 column tracks)
- **Rows:** From line 1 to line 2 (1 row track)
- **Total area:** 2 cells

---

### **Explicit vs Implicit Grids 🔍**

There are two types of grids:

#### **Explicit Grid**

The grid you **explicitly define** with `grid-template-columns` and `grid-template-rows`.

```css
.container {
  display: grid;
  grid-template-columns: 200px 200px; /* 2 columns explicitly defined */
  grid-template-rows: 100px; /* 1 row explicitly defined */
}
```

**Result:** A 2×1 grid (2 columns, 1 row).

---

#### **Implicit Grid**

Rows or columns **automatically created** when you have more items than cells in the explicit grid.

```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <!-- This needs a 2nd row! -->
  <div>4</div>
</div>
```

```css
.container {
  display: grid;
  grid-template-columns: 200px 200px; /* 2 columns */
  grid-template-rows: 100px; /* Only 1 row defined */
  /* Items 3 and 4 will create an implicit 2nd row */
}
```

**Result:**

```
┌──────┬──────┐
│  1   │  2   │ ← Explicit row (100px)
├──────┼──────┤
│  3   │  4   │ ← Implicit row (auto height)
└──────┴──────┘
```

**Controlling implicit row/column size:**

```css
.container {
  grid-auto-rows: 80px; /* Implicit rows will be 80px */
  grid-auto-columns: 150px; /* Implicit columns will be 150px */
}
```

---

### **Common Terminology Mistakes 🐞**

#### **Mistake 1: Confusing "3 columns" with "3 lines"**

```css
.container {
  grid-template-columns: 1fr 1fr 1fr;
}
```

**Wrong:** "This creates 3 grid lines"
**Right:** "This creates 3 column **tracks** (and 4 column **lines**)"

---

#### **Mistake 2: Thinking cells = tracks**

- **Tracks:** Rows or columns
- **Cells:** Individual spaces (intersections of row and column tracks)

A 3×2 grid has:

- 3 **column tracks**
- 2 **row tracks**
- 6 **cells** (3 × 2)

---

#### **Mistake 3: Confusing line numbers when positioning**

```css
.item {
  grid-column: 2 / 3; /* This is ONE column track */
}
```

**From line 2 to line 3** = **1 column track** (not 2!)

Remember: You're specifying **lines**, not **tracks**.

---

### **Visual Summary 📊**

Here's everything in one diagram:

```
        Grid Lines (numbered)
    1    2    3    4    5    6
  1 ┌────┬────┬────┬────┬────┐
    │ 1  │ 2  │ 3  │ 4  │ 5  │ ← Row Track 1
  2 ├────┼────┼────┼────┼────┤   (Grid Cells numbered)
    │ 6  │ 7  │ 8  │ 9  │ 10 │ ← Row Track 2
  3 └────┴────┴────┴────┴────┘
      ↑    ↑    ↑    ↑    ↑
       Column Tracks 1-5
```

- **Grid Lines:** The numbered borders (1-5 horizontally, 1-2 vertically)
- **Grid Tracks:** The spaces between lines (5 columns, 2 rows)
- **Grid Cells:** Individual spaces (numbered 1-10)
- **Grid Areas:** Groups of cells (e.g., cells 1-2 could form one area)

---

### **Summary 📋**

**Grid Lines:**

- The dividing lines that make up the grid
- Numbered from 1 (also negative from -1)
- Used to position items

**Grid Tracks:**

- Rows (horizontal) and columns (vertical)
- The spaces between grid lines
- Defined with `grid-template-columns` and `grid-template-rows`

**Grid Cells:**

- Individual spaces where items can be placed
- Formed by the intersection of row and column tracks
- Total cells = columns × rows

**Grid Areas:**

- Rectangular groups of cells
- Items can span multiple cells to create areas

**Remember:**

- `number of tracks + 1 = number of lines`
- Lines are what you reference when positioning
- Cells are where items actually live

---

## **Defining the Grid Structure 📐**

Now that you understand what grid lines, tracks, and cells are, it's time to actually _build_ the grid. This is where you tell the browser how many columns and rows your grid has, how big they are, and how much space sits between them.

All of this happens on the **container**. Remember, the container defines the structure, items live inside it.

---

### **`grid-template-columns` and `grid-template-rows`**

These two properties are how you define the grid's structure. Each space-separated value you write creates one track, and the value itself determines the size of that track.

```css
.container {
  display: grid;
  grid-template-columns: 200px 200px 200px;
}
```

**What's actually happening:** The browser reads each value left to right. Three values = three column tracks. The grid now has three columns, each 200px wide.

```
┌──────────────┬──────────────┬──────────────┐
│   200px      │   200px      │   200px      │
└──────────────┴──────────────┴──────────────┘
```

`grid-template-rows` works identically, just for horizontal tracks:

```css
.container {
  display: grid;
  grid-template-columns: 200px 200px 200px;
  grid-template-rows: 100px 150px;
}
```

This gives you a 3×2 grid — three columns, two rows — where the first row is 100px tall and the second is 150px tall.

```
       200px         200px         200px
┌──────────────┬──────────────┬──────────────┐
│                                            │ 100px
├──────────────┼──────────────┼──────────────┤
└──────────────┴──────────────┴──────────────┘150px
```

**Think of it like this:**

Imagine designing a photo gallery on paper. You draw vertical lines to create columns, horizontal lines to create rows. `grid-template-columns` is where you draw the vertical lines and decide how wide each column is. `grid-template-rows` is where you draw the horizontal lines and decide how tall each row is. Every value is one line.

---

#### **What Happens Without `grid-template-rows`?**

You might notice that in a lot of grid examples, `grid-template-rows` is skipped entirely. That's because rows are **optional to define explicitly**.

If you only define columns, the browser creates rows automatically as your items overflow into new rows. These auto-created rows size themselves to fit their content. They expand to be as tall as the tallest item in that row.

```css
.container {
  display: grid;
  grid-template-columns: 200px 200px 200px;
  /* No grid-template-rows */
}
```

Six items → two rows created automatically, each as tall as their content needs.

You'll only typically define `grid-template-rows` when you need rows to be a specific fixed height, or when you're building a layout where row sizing matters precisely.

---

### **The `fr` Unit 📏**

Pixel values are rigid. A `200px` column stays `200px` no matter how wide or narrow the browser window gets. That's fine for fixed layouts, but the web needs to adapt to different screen sizes.

The `fr` unit (short for **fraction**) solves this. Instead of defining a fixed size, you're defining a _proportion_ of the available space.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
```

**What's actually happening:**

The browser looks at the total available width of the container, then counts up all the fraction units. Three `1fr` values = 3 fractions total. The available space gets divided into 3 equal parts, and each column gets 1 of those parts.

If the container is 900px wide:

- Total fractions: 3
- Each fraction: 900 ÷ 3 = 300px
- Each column: 300px

If the container resizes to 600px:

- Total fractions: 3
- Each fraction: 600 ÷ 3 = 200px
- Each column: 200px automatically

The columns adapt. No math needed from you.

---

**Fractions don't have to be equal:**

```css
.container {
  display: grid;
  grid-template-columns: 2fr 1fr;
}
```

Total fractions: 3. The first column gets 2 parts, the second gets 1. So in a 900px container:

- First column: 900 ÷ 3 × 2 = **600px**
- Second column: 900 ÷ 3 × 1 = **300px**

```
┌──────────────────────────┬─────────────┐
│       600px (2fr)        │  300px (1fr)│
└──────────────────────────┴─────────────┘
```

The first column is always exactly twice the width of the second, regardless of container size.

---

**Mixing `fr` with fixed units:**

This is where `fr` becomes especially powerful:

```css
.container {
  display: grid;
  grid-template-columns: 250px 1fr 1fr;
}
```

**What's actually happening:** Fixed values are claimed _first_. The browser sets aside 250px for the first column, then takes what's left and splits it proportionally between the `fr` columns.

In a 900px container:

1. Browser reserves 250px for column 1
2. Remaining space: 900 - 250 = **650px**
3. That 650px gets split into 2 equal parts
4. Columns 2 and 3: **325px each**

```
┌──────────┬────────────────┬────────────────┐
│  250px   │    325px (1fr) │    325px (1fr) │
└──────────┴────────────────┴────────────────┘
```

This pattern is extremely common for sidebar layouts — fixed sidebar, flexible main content:

```css
.layout {
  display: grid;
  grid-template-columns: 300px 1fr; /* Fixed sidebar, flexible content */
}
```

---

### **The `repeat()` Function 🔄**

Writing `1fr 1fr 1fr 1fr 1fr` for five equal columns gets tedious fast. The `repeat()` function is a shorthand:

```css
/* These are identical */
grid-template-columns: 1fr 1fr 1fr;
grid-template-columns: repeat(3, 1fr);
```

`repeat(count, size)` — repeat this track size (size) this many times (count).

```css
/* 4 equal columns */
grid-template-columns: repeat(4, 1fr);

/* 3 columns of 200px each */
grid-template-columns: repeat(3, 200px);

/* Mix of fixed and repeated */
grid-template-columns: 250px repeat(3, 1fr);
```

That last one gives you a 250px fixed column followed by three equal flexible columns.

---

### **`gap` — Space Between Cells**

`gap` adds space between your grid tracks. Not around the outside of the grid — only _between_ tracks.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 20px;
}
```

```
┌──────┐ 20px ┌──────┐ 20px ┌──────┐
│      │      │      │      │      │
└──────┘      └──────┘      └──────┘
```

**What's actually happening:** The 20px gap is subtracted from the available space _before_ the `fr` units are calculated. So in a 900px container with `gap: 20px` and `grid-template-columns: repeat(3, 1fr)`:

1. Two gaps of 20px each = 40px reserved
2. Remaining space: 900 - 40 = 860px
3. Each `1fr` column: 860 ÷ 3 ≈ **286px**

The `fr` unit already accounts for `gap` automatically. You don't have to do any manual math.

---

**Setting row and column gaps separately:**

```css
gap: 20px; /* Same gap for rows and columns */
gap: 10px 30px; /* row-gap | column-gap */
row-gap: 10px; /* Row gaps only */
column-gap: 30px; /* Column gaps only */
```

> **Worth knowing:** `gap` never adds space before the first track or after the last one. It only lives _between_ tracks. If you want outer spacing, use `padding` on the container.

---

### **Putting It All Together**

Here's a realistic example combining everything from this section:

```css
.dashboard {
  display: grid;
  grid-template-columns: 250px repeat(3, 1fr);
  grid-template-rows: 80px 1fr 60px;
  gap: 16px;
  padding: 16px;
  height: 100vh;
}
```

**What this creates:**

- **4 columns:** 250px fixed sidebar + 3 flexible equal columns
- **3 rows:** 80px header, flexible middle, 60px footer
- **16px gaps** between all tracks
- **16px padding** around the outside of the grid

```
     250px       1fr      1fr      1fr
┌─────────────┬───────┬───────┬───────┐
│             │       │       │       │  80px
├─────────────┼───────┼───────┼───────┤
│             │       │       │       │
│             │       │       │       │  1fr
│             │       │       │       │
│             │       │       │       │
├─────────────┼───────┼───────┼───────┤
│             │       │       │       │  60px
└─────────────┴───────┴───────┴───────┘
```

---

### **Common Mistakes 🐞**

**Mistake 1: Confusing the number of values with the number of lines**

```css
grid-template-columns: 1fr 1fr 1fr; /* 3 values */
```

This creates **3 column tracks** and **4 column lines** — not 3 lines. Each value is a track, and tracks are bounded by lines. Don't mix these up when you get to positioning.

---

**Mistake 2: Thinking `fr` is a percentage**

```css
/* These are NOT the same */
grid-template-columns: 1fr 1fr; /* Each gets 50% of available space */
grid-template-columns: 50% 50%; /* Each gets 50% of container width */
```

With `fr`, the browser calculates available space _after_ gaps and fixed columns are accounted for. With percentages, it uses the full container width, which means `50% + 50%` plus a gap overflows the container.

**Stick to `fr` for flexible columns. It's smarter than percentages.**

---

**Mistake 3: Expecting `gap` to add outer padding**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px; /* Only between items, NOT around them */
}
```

If you want spacing around the outside of your grid, add `padding` to the container:

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  padding: 20px; /* ✅ Outer spacing */
}
```

---

**Mistake 4: Forgetting that `fr` units divide what's left, not the whole container**

```css
.container {
  display: grid;
  grid-template-columns: 400px 1fr 1fr;
  gap: 20px;
  width: 900px;
}
```

The two `1fr` columns do **not** each get 450px. The browser first reserves 400px for column 1, plus 40px for the two gaps, leaving 460px. Each `1fr` column gets 230px.

---

#### **Summary 📋**

**`grid-template-columns` / `grid-template-rows`:**

- Each space-separated value creates one track
- The value determines the track's size
- Rows are optional to define — the browser creates them automatically if you don't

**The `fr` unit:**

- Divides _available_ space proportionally
- Fixed values and gaps are claimed first, `fr` splits what remains
- More flexible and smarter than percentages for grid layouts

**`repeat()`:**

- Shorthand for repeated track patterns
- `repeat(3, 1fr)` = `1fr 1fr 1fr`

**`gap`:**

- Adds space _between_ tracks only — not around the outside
- Supports separate row and column gaps
- `fr` units automatically account for gap space

**The mental model:** You're drawing the grid on paper before any content arrives. Define how many columns, how wide. Define rows if you need specific heights. Add gaps between cells. Items will fill the structure you've defined.

---

## **Positioning Grid Items 📍**

So far, you've learned how to define the grid structure on the container. But by default, items just flow into the grid automatically. Left to right, top to bottom, one item per cell. That's useful, but it's not the full power of Grid.

This section is about taking manual control. You're going to tell specific items exactly where to sit, how many cells to stretch across, and use the grid lines you learned about earlier to do it precisely.

> **Remember:** Positioning properties go on the **items**, not the container. The container defines the grid. The items decide where they live in it.

---

### **How Item Positioning Works**

When you position a grid item manually, you're telling the browser which grid lines that item should start and end at, for both columns and rows.

Think back to Section 3. A 3-column grid has 4 column lines, numbered 1 through 4. When you say "start at line 1, end at line 3," the item occupies the space between those two lines, which is 2 column tracks.

```
Column lines:  1        2        3        4
               ┌────────┬────────┬────────┐
               │   1    │   2    │   3    │
               └────────┴────────┴────────┘
```

If an item goes from line 1 to line 3, it spans columns 1 and 2. You're not specifying column _numbers_ you're specifying _line_ numbers.

---

### **`grid-column` and `grid-row`**

These are the two core positioning properties. They go on the item itself.

```css
.item {
  grid-column: 1 / 3; /* Start at column line 1, end at column line 3 */
  grid-row: 1 / 2; /* Start at row line 1, end at row line 2 */
}
```

The syntax is `start line / end line`. The `/` separates where the item begins from where it ends.

**What's actually happening:** You're drawing a box on the grid using line numbers. `grid-column: 1 / 3` says "my left edge is at column line 1, my right edge is at column line 3." That's a span of 2 column tracks.

---

**Visual example:**

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(3, 100px);
  gap: 8px;
}

.item-a {
  grid-column: 1 / 3; /* Spans 2 columns */
  grid-row: 1 / 2; /* Sits in row 1 */
}

.item-b {
  grid-column: 3 / 4; /* Single column */
  grid-row: 1 / 3; /* Spans 2 rows */
}
```

```
Col lines: 1        2        3        4
           ┌─────────────────┬────────┐  ← Row line 1
           │     item-a      │        │
           │   (col 1 → 3)   │ item-b │
           ├────────┬────────┤(col3→4)│  ← Row line 2
           │        │        │row 1→3 │
           ├────────┼────────┼────────┤  ← Row line 3
           │        │        │        │
           └────────┴────────┴────────┘  ← Row line 4
```

`item-a` stretches across two columns in the first row. `item-b` stretches across two rows in the third column. The remaining cells are filled by other items following the normal auto-placement flow.

---

#### **The Longhand Properties**

`grid-column` and `grid-row` are each shorthands for two separate properties:

```css
/* These are identical */
grid-column: 1 / 3;

grid-column-start: 1;
grid-column-end: 3;
```

```css
/* These are identical */
grid-row: 1 / 2;

grid-row-start: 1;
grid-row-end: 2;
```

You'll mostly use the shorthand because it's cleaner. But the longhand versions exist and you may see them in code.

---

### **The `span` Keyword**

Instead of specifying an end line, you can tell the browser how many tracks the item should span using the `span` keyword.

```css
/* These are identical in a 3-column grid */
grid-column: 1 / 3;
grid-column: 1 / span 2; /* Start at line 1, span 2 tracks */
```

**What's actually happening:** `span` is counting tracks, not lines. `span 2` means "take up 2 column tracks from wherever you start."

```css
.item {
  grid-column: 2 / span 2; /* Start at line 2, take up 2 columns */
  grid-row: 1 / span 3; /* Start at row line 1, take up 3 rows */
}
```

**Think of it like this:** `span` is like telling someone "start here, then take up this many seats." You don't have to count to the end line yourself the browser does it.

`span` is especially useful when you don't know exactly how many columns your grid has, or when you want an item to always take up the same number of tracks regardless of where it starts.

---

### **Negative Line Numbers**

Grid lines can be counted from **both ends**. Positive numbers count from the start (left/top), negative numbers count from the end (right/bottom).

```
Positive →
    1        2        3        4
    ┌────────┬────────┬────────┐
    │        │        │        │
    └────────┴────────┴────────┘
   -4       -3       -2       -1
                              ← Negative
```

In a 3-column grid:

- Column line 1 = column line -4
- Column line 2 = column line -3
- Column line 3 = column line -2
- Column line 4 = column line -1

**The most useful negative value is `-1`** — it always means the very last line, regardless of how many columns or rows you have.

```css
.item {
  grid-column: 1 / -1; /* Stretch from first line to last line */
}
```

This makes an item span the **entire width of the grid**. If you later change the number of columns, this item still stretches all the way across. You don't have to update the CSS.

```
    1       2        3        4
    ┌─────────────────────────┐
    │   grid-column: 1 / -1   │  ← Full width regardless of column count
    └─────────────────────────┘
```

**What's actually happening:** Negative indexes give you a way to position relative to the _end_ of the grid rather than the start. This is particularly powerful when the grid size might change. Either because you update it in CSS later, or because you're generating grid columns dynamically.

---

### **`grid-area` — The Combined Shorthand**

`grid-area` is the full shorthand that combines all four positioning values into one property.

```css
.item {
  grid-area: 1 / 1 / 3 / 4;
}
```

The order is: `row-start / column-start / row-end / column-end`.

**Think of it like coordinates:** You're defining the four edges of the box in one line — where it starts vertically, where it starts horizontally, where it ends vertically, where it ends horizontally.

```css
/* These are identical */
.item {
  grid-row: 1 / 3;
  grid-column: 1 / 4;
}

.item {
  grid-area: 1 / 1 / 3 / 4;
}
```

`grid-area` is compact, but the order can be unintuitive at first (especially because it's row values first, then column — not the x/y order you might expect). Use whichever feels clearer to you.

> **Note:** `grid-area` also has a completely different use when working with named template areas — we'll cover that in the next section.

---

### **Automatic Placement for Unpositioned Items**

When you manually position some items but not others, the browser's auto-placement algorithm fills in the rest. Unpositioned items flow into whatever cells aren't occupied by manually placed items.

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 8px;
}

.featured {
  grid-column: 1 / 3; /* Manually placed */
}

/* All other items placed automatically */
```

```
┌──────────────────┬────────┐
│    .featured     │ item 2 │  ← item 2 auto-fills next available cell
│   (col 1 → 3)    │        │
├────────┬─────────┴────────┤
│ item 3 │ item 4  │ item 5 │  ← remaining items continue auto-placing
└────────┴─────────┴────────┘
```

The browser is smart enough to work around your manually placed items and fill in the gaps with everything else.

---

### **Common Mistakes 🐞**

#### **Mistake 1: Confusing track numbers with line numbers**

```css
/* You have a 3-column grid */
.item {
  grid-column: 1 / 3; /* This spans 2 columns, NOT 3 */
}
```

`1 / 3` means from line 1 to line 3 — that's 2 tracks, not 3. If you want to span all 3 columns, you need `1 / 4` (or `1 / -1`).

**Remember:** In a 3-column grid, the last column line is line **4**, not line 3.

---

#### **Mistake 2: Putting positioning properties on the container**

```css
/* ❌ Wrong */
.container {
  grid-column: 1 / 3;
}

/* ✅ Correct */
.item {
  grid-column: 1 / 3;
}
```

`grid-column` and `grid-row` are **item properties**. They do nothing on the container.

---

#### **Mistake 3: Overlapping items accidentally**

```css
.item-a {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}

.item-b {
  grid-column: 2 / 4; /* ❌ Overlaps with item-a in column 2 */
  grid-row: 1 / 2;
}
```

Grid won't warn you about overlaps — both items will just sit on top of each other. If content looks broken or hidden, check whether your grid items are accidentally sharing cells.

---

#### **Mistake 4: Mixing up the `grid-area` order**

```css
grid-area: row-start / column-start / row-end / column-end;
```

It's **row first, then column** — the opposite of the x/y convention most people expect. `grid-area: 1 / 2 / 3 / 4` starts at row 1, column 2, ends at row 3, column 4.

---

### **Summary 📋**

**`grid-column` and `grid-row`:**

- Set on items, not the container
- Syntax is `start line / end line`
- Line numbers come from the grid's column and row lines
- Longhand versions: `grid-column-start`, `grid-column-end`, `grid-row-start`, `grid-row-end`

**`span`:**

- Use instead of an end line: `grid-column: 2 / span 3`
- Counts tracks, not lines
- Useful when you don't want to calculate the end line manually

**Negative indexes:**

- Count from the end of the grid
- `-1` always refers to the last line
- `grid-column: 1 / -1` always spans the full width of the grid

**`grid-area`:**

- Combines all four values: `row-start / column-start / row-end / column-end`
- Order is row first, then column — easy to mix up
- Also used for named areas (covered next section)

**Remember:** Lines are what you reference. Tracks are what items occupy. Span counts tracks. Negative numbers count from the end.

---

## **Grid Template Areas 🗺️**

In the last section, you positioned items using line numbers — `grid-column: 1 / 3`, `grid-row: 2 / 4`. That works well, but for complex layouts it can get hard to read. Looking at a bunch of line numbers, it's not immediately obvious what the layout actually looks like.

Grid template areas are a completely different approach to the same problem. Instead of coordinates, you draw the layout directly in your CSS using names. The result is CSS that looks remarkably like the layout it describes.

---

### **How It Works**

Grid template areas work in two steps:

1. On the **container**, you draw a map of your layout using area names
2. On each **item**, you assign it to one of those named areas

---

### **Step 1 — Defining Areas on the Container**

The `grid-template-areas` property goes on the container. Each string you write represents one row, and each word inside that string represents one cell.

```css
.container {
  display: grid;
  grid-template-columns: 250px 1fr;
  grid-template-rows: 80px 1fr 60px;
  grid-template-areas:
    "header  header"
    "sidebar content"
    "footer  footer";
}
```

**What's actually happening:** You're writing a visual map of your grid. Each row of the layout is one quoted string. Each word inside that string is the name for that cell. Words that repeat across adjacent cells tell the browser those cells belong to one combined area.

Reading it out loud: row 1 is all header, row 2 is sidebar on the left and content on the right, row 3 is all footer. That's exactly what the layout will look like.

```
    250px          1fr
┌─────────────────────────────┐
│           header            │ 80px
├──────────┬──────────────────┤
│ sidebar  │     content      │ 1fr
├──────────┴──────────────────┤
│           footer            │ 60px
└─────────────────────────────┘
```

Notice how the CSS and the diagram look structurally the same. That's the point.

---

### **Step 2 — Assigning Items to Areas**

Once the areas are defined on the container, you assign each item to its area using `grid-area` — this time with a name instead of line numbers:

```css
.header {
  grid-area: header;
}
.sidebar {
  grid-area: sidebar;
}
.content {
  grid-area: content;
}
.footer {
  grid-area: footer;
}
```

That's it. The browser handles all the positioning automatically based on the map you drew. No line numbers needed.

**Full example:**

```html
<div class="container">
  <header class="header">Header</header>
  <aside class="sidebar">Sidebar</aside>
  <main class="content">Content</main>
  <footer class="footer">Footer</footer>
</div>
```

```css
.container {
  display: grid;
  grid-template-columns: 250px 1fr;
  grid-template-rows: 80px 1fr 60px;
  gap: 16px;
  grid-template-areas:
    "header  header"
    "sidebar content"
    "footer  footer";
}

.header {
  grid-area: header;
}
.sidebar {
  grid-area: sidebar;
}
.content {
  grid-area: content;
}
.footer {
  grid-area: footer;
}
```

The HTML order doesn't matter here. You could write the footer before the header in your HTML and the layout would still look correct, because the grid map controls where everything appears — not source order.

---

### **Empty Cells — The `.` Placeholder**

What if you want a cell to be intentionally empty? You use a `.` (dot) as a placeholder:

```css
grid-template-areas:
  "header header header"
  ".      content ."
  "footer footer footer";
```

The dots tell the browser "leave this cell empty." The content area sits in the middle column, with empty cells on either side.

```
┌───────┬───────┬───────┐
│          header       │
├───────┬───────┬───────┤
│ empty │content│ empty │
├───────┴───────┴───────┤
│          footer       │
└───────────────────────┘
```

You can use multiple dots for readability — `...` counts as a single empty cell just like `.`. The number of dots doesn't change the behavior, it just helps with visual alignment in your code.

---

### **The Rules for Valid Areas**

Grid template areas have one strict rule:

**Areas must be rectangular.** You cannot create L-shaped, T-shaped, or any other non-rectangular area.

```css
/* ❌ Invalid — "content" is L-shaped */
grid-template-areas:
  "header  content"
  "content content"
  "sidebar footer";
```

```css
/* ✅ Valid — all areas are rectangular */
grid-template-areas:
  "header  header"
  "sidebar content"
  "footer  footer";
```

The browser will simply ignore an invalid `grid-template-areas` declaration if the areas aren't geometrically possible. Your layout will break silently with no error, so it's worth double-checking your map visually.

---

### **Template Areas vs Line Numbers — Which to Use?**

Both approaches position items on the same grid. They're not different features — they're different syntaxes for the same thing. You can even mix them in the same grid if you want.

**Use template areas when:**

- You're building a named page-level layout (header, sidebar, content, footer)
- You want your CSS to be readable at a glance
- You're working with a layout that might change — renaming and redrawing is easier than recalculating line numbers

**Use line numbers when:**

- You're positioning individual items precisely within a component
- Items span irregular amounts of the grid
- You need the flexibility of `span` or negative indexes

For whole-page layouts, template areas win on readability. For fine-grained item control, line numbers are more precise. In practice, you'll use both.

---

### **Common Mistakes 🐞**

#### **Mistake 1: Creating non-rectangular areas**

```css
/* ❌ "content" is L-shaped */
grid-template-areas:
  "header  content"
  "content content"
  "sidebar footer";
```

"content" appears in column 2 row 1, then column 1 row 2, and column 2 row 2. That's an L-shape — not a rectangle. The browser will discard the whole declaration.

The fix is to make sure every area forms a clean rectangle:

```css
/* ✅ Valid — all areas are rectangular */
grid-template-areas:
  "header  header"
  "sidebar content"
  "footer  footer";
```

Always visualise your map before writing it. If you can't draw it as clean rectangles, it won't work.

---

#### **Mistake 2: Mismatched cell counts between rows**

```css
/* ❌ Row 1 has 2 cells, row 2 has 3 */
grid-template-areas:
  "header header"
  "sidebar content footer";
```

Every row in `grid-template-areas` must have the same number of cells as your grid has columns. If your grid has 3 columns, every row in the map needs 3 names (or dots).

---

#### **Mistake 3: Forgetting to assign items to areas**

```css
.container {
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
}

/* ❌ No grid-area assigned — item auto-places instead */
.header {
  background: navy;
}
```

Defining the areas on the container does nothing on its own. Each item still needs its `grid-area` assignment, otherwise it just falls into auto-placement and ignores your map entirely.

---

#### **Mistake 4: Using the wrong name**

```css
.container {
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
}

/* ❌ Typo — "head" doesn't match "header" */
.header {
  grid-area: head;
}
```

Area names are case-sensitive and must match exactly. A typo means the item won't be placed in the named area — it'll auto-place instead. If an item isn't where you expect it, check that the name matches perfectly.

---

### **Summary 📋**

**`grid-template-areas`:**

- Defined on the container
- Each quoted string = one row
- Each word = one cell's area name
- Repeated adjacent names = one combined area
- Use `.` for intentionally empty cells

**`grid-area` (with a name):**

- Defined on the item
- Assigns the item to a named area from the container's map
- Name must match exactly

**The rules:**

- All areas must be rectangular — no L or T shapes
- Every row must have the same number of cells
- HTML source order doesn't affect placement — the map does

**When to use it:**

- Page-level layouts where readability matters
- Layouts that are likely to change — redrawing the map is easier than recalculating line numbers

**Remember:** You're drawing the layout directly in CSS. If your `grid-template-areas` code looks like the layout you want, you've done it right.

---

## **Alignment and Distribution 🎯**

So far, items just stretch to fill their cells by default, and the grid itself sits at the top-left of its container. But Grid gives you precise control over both of these things — and understanding which one you're controlling is the key to this entire section.

There are two completely separate alignment concepts in Grid:

1. **Distributing the tracks** — where the columns and rows sit _within the grid container_ when they don't fill it completely. This only happens with fixed-size tracks like `px`. If you use `fr` units, they consume all available space and there's nothing left to distribute.
2. **Aligning items within their cells** — where each item sits _inside the cell it occupies_

These are independent of each other. You can change one without affecting the other, and they use different properties. Getting these two concepts confused is the most common source of alignment problems in Grid.

**Think of it like this:**

Imagine a parking lot (the container) with marked parking bays arranged in rows and columns (the tracks). The bays don't fill the entire lot, so there's unused tarmac around them.

- **Distributing tracks** = deciding where in the lot those rows and columns of bays are positioned (all pushed to one side, spread across the whole lot, centered in the middle)
- **Aligning items within cells** = deciding where each car sits within its individual bay (pulled forward, pushed back, centered)

Moving the rows of bays around the lot is a completely separate decision from how each car parks within its bay. Grid handles both.

---

### **Part 1 — Distributing Tracks Within the Container**

This only becomes relevant when your tracks don't fill the entire grid container. If you define columns in fixed pixels or specific sizes that add up to less than the container width, there's leftover space. These properties decide what happens with that space.

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px; /* 300px total */
  width: 600px; /* But container is 600px */
  /* 300px of leftover space — what happens to it? */
}
```

> **Worth knowing:** If you use `fr` units, they consume all available space automatically. So there's never leftover space and these properties have no visible effect. This situation typically arises with fixed or percentage-based column definitions.

---

#### **`justify-content` — Distributing Columns Horizontally**

`justify-content` controls how the column tracks are distributed along the horizontal axis within the container.

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
  width: 600px;
  justify-content: center;
}
```

**Common values:**

`start` — tracks sit at the left edge (default):

```
┌──────┬──────┬──────┬────────────────────┐
│  1   │  2   │  3   │   leftover space   │
└──────┴──────┴──────┴────────────────────┘
```

`end` — tracks sit at the right edge:

```
┌────────────────────┬──────┬──────┬──────┐
│   leftover space   │  1   │  2   │  3   │
└────────────────────┴──────┴──────┴──────┘
```

`center` — tracks sit in the middle:

```
┌──────────┬──────┬──────┬──────┬──────────┐
│  space   │  1   │  2   │  3   │  space   │
└──────────┴──────┴──────┴──────┴──────────┘
```

`space-between` — first and last tracks at the edges, space distributed between:

```
┌──────┬────────────┬──────┬────────────┬──────┐
│  1   │   space    │  2   │   space    │  3   │
└──────┴────────────┴──────┴────────────┴──────┘
```

`space-around` — equal space around each track:

```
┌───┬──────┬──────┬──────┬──────┬──────┬───┐
│ s │  1   │  s   │  2   │  s   │  3   │ s │
└───┴──────┴──────┴──────┴──────┴──────┴───┘
```

`space-evenly` — equal space between all tracks and edges:

```
┌────┬──────┬────┬──────┬────┬──────┬────┐
│ s  │  1   │ s  │  2   │ s  │  3   │ s  │
└────┴──────┴────┴──────┴────┴──────┴────┘
```

---

#### **`align-content` — Distributing Rows Vertically**

`align-content` does the same thing as `justify-content`, but on the vertical axis — controlling how row tracks are distributed within the container when there's leftover vertical space.

```css
.container {
  display: grid;
  grid-template-rows: 80px 80px;
  height: 400px; /* More than the rows need */
  align-content: center;
}
```

**Common values:**

`start` — rows sit at the top edge (default):

```
┌──────────────────────┐
│  ┌────────────────┐  │
│  │    row 1       │  │
│  ├────────────────┤  │
│  │    row 2       │  │
│  └────────────────┘  │
│                      │
│   leftover space     │
└──────────────────────┘
```

`end` — rows sit at the bottom edge:

```
┌──────────────────────┐
│                      │
│   leftover space     │
│  ┌────────────────┐  │
│  │    row 1       │  │
│  ├────────────────┤  │
│  │    row 2       │  │
│  └────────────────┘  │
└──────────────────────┘
```

`center` — rows sit in the middle:

```
┌──────────────────────┐
│     space above      │
│  ┌────────────────┐  │
│  │    row 1       │  │
│  ├────────────────┤  │
│  │    row 2       │  │
│  └────────────────┘  │
│     space below      │
└──────────────────────┘
```

`space-between` — first and last rows at the edges, space distributed between:

```
┌──────────────────────┐
│  ┌────────────────┐  │
│  │    row 1       │  │
│  └────────────────┘  │
│                      │
│      space           │
│                      │
│  ┌────────────────┐  │
│  │    row 2       │  │
│  └────────────────┘  │
└──────────────────────┘
```

The values `space-around` and `space-evenly` follow the same logic as `justify-content` — just applied vertically.

---

#### **`place-content` — Shorthand for Both**

`place-content` sets both `align-content` and `justify-content` in one declaration:

```css
place-content: center; /* Both axes centered */
place-content: start space-between; /* align-content | justify-content */
```

If you provide one value, it applies to both axes. If you provide two, the first is `align-content` (vertical) and the second is `justify-content` (horizontal).

**Visual example — `place-content: center`:**

```
┌─────────────────────────────────────────┐
│                                         │
│        ┌──────┬──────┬──────┐           │
│        │  1   │  2   │  3   │           │
│        ├──────┼──────┼──────┤           │
│        │  4   │  5   │  6   │           │
│        └──────┴──────┴──────┘           │
│                                         │
└─────────────────────────────────────────┘
```

The entire group of tracks is centered both horizontally and vertically within the container.

**Visual example — `place-content: start space-between`:**

```
┌─────────────────────────────────────────┐
│  ┌──────┐          ┌──────┐             │
│  │  1   │          │  2   │             │  ← rows at top (start)
│  ├──────┤          ├──────┤             │    columns spread (space-between)
│  │  3   │          │  4   │             │
│  └──────┘          └──────┘             │
│                                         │
└─────────────────────────────────────────┘
```

---

### **Part 2 — Aligning Items Within Their Cells**

Now for the second concept. Regardless of where the tracks are positioned within the container, each item sits inside a cell. By default, items **stretch** to fill their entire cell — both horizontally and vertically. These properties let you change that.

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 200px);
  grid-template-rows: repeat(2, 150px);
  /* Items stretch to fill 200px × 150px cells by default */
}
```

---

#### **`justify-items` — Aligning Items Horizontally Within Cells**

`justify-items` controls where items sit horizontally inside their cells. Set it on the container and it applies to all items.

```css
.container {
  justify-items: center;
}
```

**Common values:**

`stretch` — item fills the full cell width (default):

```
┌──────────────────────┐
│  ┌────────────────┐  │
│  │      item      │  │
│  └────────────────┘  │
└──────────────────────┘
```

`start` — item sits at the left edge of its cell:

```
┌──────────────────────┐
│  ┌──────┐            │
│  │ item │            │
│  └──────┘            │
└──────────────────────┘
```

`end` — item sits at the right edge:

```
┌──────────────────────┐
│            ┌──────┐  │
│            │ item │  │
│            └──────┘  │
└──────────────────────┘
```

`center` — item sits in the middle:

```
┌──────────────────────┐
│       ┌──────┐       │
│       │ item │       │
│       └──────┘       │
└──────────────────────┘
```

---

#### **`align-items` — Aligning Items Vertically Within Cells**

`align-items` controls where items sit vertically inside their cells. Set it on the container and it applies to all items.

```css
.container {
  align-items: center;
}
```

**Common values:**

`stretch` — item fills the full cell height (default):

```
┌──────────────────────┐
│  ┌────────────────┐  │
│  │                │  │
│  │      item      │  │
│  └────────────────┘  │
└──────────────────────┘
```

`start` — item sits at the top edge of its cell:

```
┌──────────────────────┐
│  ┌────────────────┐  │
│  │      item      │  │
│  └────────────────┘  │
│                      │
└──────────────────────┘
```

`end` — item sits at the bottom edge:

```
┌──────────────────────┐
│                      │
│  ┌────────────────┐  │
│  │      item      │  │
│  └────────────────┘  │
└──────────────────────┘
```

`center` — item sits in the middle:

```
┌──────────────────────┐
│                      │
│  ┌────────────────┐  │
│  │      item      │  │
│  └────────────────┘  │
│                      │
└──────────────────────┘
```

---

#### **`place-items` — Shorthand for Both**

`place-items` sets both `align-items` and `justify-items` in one declaration:

```css
place-items: center; /* Both axes centered */
place-items: start end; /* align-items | justify-items */
```

If you provide one value it applies to both axes. If you provide two, the first is `align-items` (vertical) and the second is `justify-items` (horizontal).

**Visual example — `place-items: center`:**

```
┌──────────────────────┐ ┌──────────────────────┐ ┌──────────────────────┐
│                      │ │                      │ │                      │
│       ┌──────┐       │ │       ┌──────┐       │ │       ┌──────┐       │
│       │  1   │       │ │       │  2   │       │ │       │  3   │       │
│       └──────┘       │ │       └──────┘       │ │       └──────┘       │
│                      │ │                      │ │                      │
└──────────────────────┘ └──────────────────────┘ └──────────────────────┘
```

Every item is centered both horizontally and vertically within its own cell.

**Visual example — `place-items: start end`:**

```
┌──────────────────────┐ ┌──────────────────────┐ ┌──────────────────────┐
│            ┌──────┐  │ │            ┌──────┐  │ │            ┌──────┐  │
│            │  1   │  │ │            │  2   │  │ │            │  3   │  │
│            └──────┘  │ │            └──────┘  │ │            └──────┘  │
│                      │ │                      │ │                      │
│                      │ │                      │ │                      │
└──────────────────────┘ └──────────────────────┘ └──────────────────────┘
```

Items sit at the top (`start` vertically) and the right edge (`end` horizontally) of each cell.

---

#### **Overriding Alignment on Individual Items**

`justify-items` and `align-items` set the default for _all_ items. If you need one specific item to align differently, you can override it directly on that item using `justify-self` and `align-self`:

```css
.container {
  justify-items: start; /* All items start-aligned */
}

.special-item {
  justify-self: end; /* This one item overrides to end */
  align-self: center; /* And centers itself vertically */
}
```

`place-self` is the shorthand combining both:

```css
.special-item {
  place-self: center end; /* align-self | justify-self */
}
```

---

### **Putting It All Together**

Here's a diagram showing both concepts working simultaneously:

```
Container (800px wide, 500px tall)
grid-template-columns: repeat(3, 150px) — only 450px of columns
justify-content: center    ← tracks centered in container
align-items: center        ← items centered within their cells

┌──────────────────────────────────────────────┐
│                                              │
│        ┌──────┬──────┬──────┐                │
│        │      │      │      │                │    ← tracks centered
│        │ item │ item │ item │  ← items       │    horizontally
│        │      │      │      │    centered    │
│        └──────┴──────┴──────┘    in cells    │
│                                              │
└──────────────────────────────────────────────┘
```

`justify-content` moved the group of tracks. `align-items` moved the items within each cell. Two separate things, both happening at the same time.

---

### **Quick Reference — Which Property Does What?**

| Property          | Goes on   | Controls                             | Axis       |
| ----------------- | --------- | ------------------------------------ | ---------- |
| `justify-content` | Container | Track distribution in container      | Horizontal |
| `align-content`   | Container | Track distribution in container      | Vertical   |
| `place-content`   | Container | Both of the above                    | Both       |
| `justify-items`   | Container | Item position within cell            | Horizontal |
| `align-items`     | Container | Item position within cell            | Vertical   |
| `place-items`     | Container | Both of the above                    | Both       |
| `justify-self`    | Item      | Item position within cell (override) | Horizontal |
| `align-self`      | Item      | Item position within cell (override) | Vertical   |
| `place-self`      | Item      | Both of the above                    | Both       |

---

### **Common Mistakes 🐞**

#### **Mistake 1: Using `justify-content` when `fr` units are in use**

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  justify-content: center; /* Has no effect */
}
```

`fr` units consume all available space. There's nothing left to distribute. `justify-content` only works when your tracks have leftover space to play with. Switch to fixed sizes if you need track distribution.

---

#### **Mistake 2: Confusing track distribution with item alignment**

```css
/* You want items centered in their cells */
.container {
  justify-content: center; /* ❌ This moves the tracks, not the items */
}

/* ✅ This is what you actually want */
.container {
  justify-items: center;
}
```

If items aren't where you expect them, ask yourself: am I trying to move the tracks, or move the items within their cells? That determines which property to reach for.

---

#### **Mistake 3: Forgetting `align-content` needs a defined height**

```css
.container {
  display: grid;
  grid-template-rows: 80px 80px;
  align-content: center; /* Has no effect */
  /* No height defined — container shrinks to fit rows */
}
```

If the container has no explicit height, it shrinks to exactly fit the rows — no leftover vertical space, nothing to distribute. Add a `height` or `min-height` for `align-content` to have any visible effect.

---

### **Summary 📋**

**Two separate concepts:**

- `content` properties — distribute tracks within the container (only relevant when tracks don't fill the container)
- `items` properties — align items within their cells (always relevant)

**The properties:**

- `justify-*` — horizontal axis
- `align-*` — vertical axis
- `place-*` — shorthand for both (align first, justify second)

**Scope:**

- Container properties (`justify-content`, `align-content`, `justify-items`, `align-items`) apply to all items
- Item properties (`justify-self`, `align-self`) override the container default for individual items

**The question to ask when alignment isn't working:** "Am I trying to move the tracks or the items within their cells?" The answer tells you exactly which property to use.

---

## **Common Use Cases & Patterns 🎨**

Now that you know how Grid works, let's look at real layouts you'll actually build. These patterns come up constantly in web development. Learn to recognise them and you'll reach for the right Grid approach instinctively.

---

### **Pattern 1: Classic Page Layout**

The most common layout on the web — header, sidebar, main content, and footer. This is where `grid-template-areas` shines.

```html
<div class="page">
  <header class="header">Header</header>
  <aside class="sidebar">Sidebar</aside>
  <main class="content">Content</main>
  <footer class="footer">Footer</footer>
</div>
```

```css
.page {
  display: grid;
  grid-template-columns: 250px 1fr;
  grid-template-rows: 80px 1fr 60px;
  grid-template-areas:
    "header  header"
    "sidebar content"
    "footer  footer";
  gap: 16px;
  min-height: 100vh;
}

.header {
  grid-area: header;
}
.sidebar {
  grid-area: sidebar;
}
.content {
  grid-area: content;
}
.footer {
  grid-area: footer;
}
```

```
    250px          1fr
┌─────────────────────────────┐
│           header            │  80px
├──────────┬──────────────────┤
│ sidebar  │     content      │  1fr
├──────────┴──────────────────┤
│           footer            │  60px
└─────────────────────────────┘
```

---

### **Pattern 2: Card Grid**

A responsive grid of cards where each card is the same size. This is one of the most common UI patterns on the web.

```html
<div class="card-grid">
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
  <div class="card">Card 4</div>
  <div class="card">Card 5</div>
  <div class="card">Card 6</div>
</div>
```

```css
.card-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}
```

```
┌──────────┬──────────┬──────────┐
│  Card 1  │  Card 2  │  Card 3  │
├──────────┼──────────┼──────────┤
│  Card 4  │  Card 5  │  Card 6  │
└──────────┴──────────┴──────────┘
```

Items auto-place left to right, top to bottom. No manual positioning needed. Grid handles it all.

---

### **Pattern 3: Featured Item Grid**

A card grid where one item is promoted and spans multiple cells. Common in news sites, dashboards, and portfolio layouts.

```html
<div class="grid">
  <div class="card featured">Featured</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
  <div class="card">Card 4</div>
  <div class="card">Card 5</div>
  <div class="card">Card 6</div>
</div>
```

```css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}

.featured {
  grid-column: 1 / 3; /* Spans 2 columns */
  grid-row: 1 / 3; /* Spans 2 rows */
}
```

```
┌──────────────────┬─────────┐
│                  │  Card 2 │
│    Featured      ├─────────┤
│                  │  Card 3 │
├─────────┬────────┼─────────┤
│ Card 4  │ Card 5 │  Card 6 │
└─────────┴────────┴─────────┘
```

The featured item takes up the prime real estate. Remaining cards auto-place into whatever cells are left.

---

### **Pattern 4: Holy Grail Layout**

The "holy grail" is a classic web layout with a full-width header and footer, and three columns in betweenc (left sidebar, main content, right sidebar).

```html
<div class="holy-grail">
  <header class="header">Header</header>
  <aside class="left">Left Sidebar</aside>
  <main class="content">Content</main>
  <aside class="right">Right Sidebar</aside>
  <footer class="footer">Footer</footer>
</div>
```

```css
.holy-grail {
  display: grid;
  grid-template-columns: 200px 1fr 200px;
  grid-template-rows: auto 1fr auto;
  grid-template-areas:
    "header  header  header"
    "left    content right"
    "footer  footer  footer";
  min-height: 100vh;
  gap: 16px;
}

.header {
  grid-area: header;
}
.left {
  grid-area: left;
}
.content {
  grid-area: content;
}
.right {
  grid-area: right;
}
.footer {
  grid-area: footer;
}
```

```
    200px       1fr       200px
┌──────────────────────────────────┐
│             header               │
├──────────┬──────────┬────────────┤
│   left   │ content  │   right    │
│ sidebar  │          │  sidebar   │
├──────────┴──────────┴────────────┤
│             footer               │
└──────────────────────────────────┘
```

This layout was notoriously difficult to build before Grid existed. Now it's a handful of lines.

---

### **Pattern 5: Dashboard Layout**

A dashboard with panels of different sizes — some spanning multiple columns or rows.

```html
<div class="dashboard">
  <div class="panel stats">Stats</div>
  <div class="panel chart">Chart</div>
  <div class="panel activity">Activity</div>
  <div class="panel table">Table</div>
</div>
```

```css
.dashboard {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: 150px 300px;
  gap: 16px;
}

.stats {
  grid-column: 1 / 3;
} /* Spans 2 columns */
.chart {
  grid-column: 3 / 5;
} /* Spans 2 columns */
.activity {
  grid-column: 1 / 2;
  grid-row: 2;
}
.table {
  grid-column: 2 / 5;
  grid-row: 2;
} /* Spans 3 columns */
```

```
     1fr      1fr      1fr      1fr
┌──────────────────┬──────────────────┐
│      stats       │      chart       │ 150px
├────────┬─────────┴──────────────────┤
│activity│           table            │ 300px
│        |                            │
└────────┴────────────────────────────┘
```

---

### **Pattern 6: Centered Content**

Perfectly centering content both horizontally and vertically. Useful for landing pages, login screens, or empty states.

```html
<div class="centered-layout">
  <div class="content">I'm perfectly centered</div>
</div>
```

```css
.centered-layout {
  display: grid;
  place-items: center;
  min-height: 100vh;
}
```

```
┌─────────────────────────────────┐
│                                 │
│                                 │
│      ┌───────────────────┐      │
│      │ I'm perfectly     │      │
│      │ centered          │      │
│      └───────────────────┘      │
│                                 │
│                                 │
└─────────────────────────────────┘
```

Two lines of CSS. That's it. `place-items: center` handles both axes simultaneously.

---

## **Quick Reference 📚**

---

### **Container Properties**

| Property                | What It Does                                  |
| ----------------------- | --------------------------------------------- |
| `display: grid`         | Activates Grid on the container               |
| `grid-template-columns` | Defines column track sizes                    |
| `grid-template-rows`    | Defines row track sizes                       |
| `grid-template-areas`   | Defines named area map                        |
| `gap`                   | Space between all tracks                      |
| `row-gap`               | Space between row tracks only                 |
| `column-gap`            | Space between column tracks only              |
| `justify-content`       | Distributes columns horizontally in container |
| `align-content`         | Distributes rows vertically in container      |
| `place-content`         | Shorthand for both of the above               |
| `justify-items`         | Aligns all items horizontally within cells    |
| `align-items`           | Aligns all items vertically within cells      |
| `place-items`           | Shorthand for both of the above               |

---

### **Item Properties**

| Property            | What It Does                                        |
| ------------------- | --------------------------------------------------- |
| `grid-column`       | Sets start / end column lines                       |
| `grid-column-start` | Sets start column line                              |
| `grid-column-end`   | Sets end column line                                |
| `grid-row`          | Sets start / end row lines                          |
| `grid-row-start`    | Sets start row line                                 |
| `grid-row-end`      | Sets end row line                                   |
| `grid-area`         | Shorthand for all four lines, or assigns named area |
| `justify-self`      | Overrides horizontal alignment within cell          |
| `align-self`        | Overrides vertical alignment within cell            |
| `place-self`        | Shorthand for both of the above                     |

---

### **Key Syntax**

```css
/* Defining columns */
grid-template-columns: 200px 1fr 1fr;
grid-template-columns: repeat(3, 1fr);
grid-template-columns: 250px repeat(3, 1fr);

/* Positioning items */
grid-column: 1 / 3; /* Line 1 to line 3 */
grid-column: 1 / span 2; /* Start at line 1, span 2 tracks */
grid-column: 1 / -1; /* First line to last line */

/* Named areas */
grid-template-areas:
  "header header"
  "sidebar content"
  "footer footer";
grid-area: header; /* Assign item to named area */

/* Alignment shorthands */
place-content: center; /* align-content | justify-content */
place-items: center; /* align-items | justify-items */
place-self: center; /* align-self | justify-self */
```

---

### **The `fr` Unit**

| Situation       | What Happens                                                     |
| --------------- | ---------------------------------------------------------------- |
| `1fr 1fr 1fr`   | Available space split into 3 equal parts                         |
| `2fr 1fr`       | Available space split into 3 parts — first gets 2, second gets 1 |
| `200px 1fr`     | 200px reserved first, remaining space goes to `1fr`              |
| `fr` with `gap` | Gap space is subtracted before `fr` is calculated                |

---

### **Line Numbers**

| Grid Size         | Column Lines                          | Row Lines                      |
| ----------------- | ------------------------------------- | ------------------------------ |
| 3 columns, 2 rows | 1, 2, 3, 4 (or -4, -3, -2, -1)        | 1, 2, 3 (or -3, -2, -1)        |
| 4 columns, 3 rows | 1, 2, 3, 4, 5 (or -5, -4, -3, -2, -1) | 1, 2, 3, 4 (or -4, -3, -2, -1) |

**Formula:** `number of tracks + 1 = number of lines`

**`-1` always = the last line**, regardless of how many columns or rows you have.

---

### **Alignment Values**

| Value           | Effect                                                            |
| --------------- | ----------------------------------------------------------------- |
| `stretch`       | Fills the full cell (default for `justify-items` / `align-items`) |
| `start`         | Sits at the start edge of cell or container                       |
| `end`           | Sits at the end edge of cell or container                         |
| `center`        | Sits in the middle                                                |
| `space-between` | First and last at edges, space distributed between                |
| `space-around`  | Equal space around each track                                     |
| `space-evenly`  | Equal space between all tracks and edges                          |

---

### **Which Property Do I Need? 🌳**

```
Am I positioning an item on the grid?
    → grid-column / grid-row / grid-area

Am I distributing tracks within the container?
    → justify-content (horizontal)
    → align-content (vertical)
    → place-content (both)

Am I aligning items within their cells?
    → justify-items / align-items / place-items (all items)
    → justify-self / align-self / place-self (one specific item)
```

---

### **Common Mistakes Checklist ✅**

- ☐ `display: grid` missing on container
- ☐ Positioning properties (`grid-column`, `grid-row`) placed on container instead of item
- ☐ Container properties (`grid-template-columns`, `gap`) placed on item instead of container
- ☐ Confusing track count with line count — 3 columns = 4 lines
- ☐ Using `justify-content` with `fr` units — `fr` leaves no space to distribute
- ☐ `align-content` not working — container has no explicit height
- ☐ `grid-template-areas` not working — area names don't match `grid-area` values exactly
- ☐ `grid-template-areas` ignored — areas are not rectangular
- ☐ Sticky not sticking — wrong section, that's CSS Positioning 😄
