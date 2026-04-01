# CSS Flexbox

- [What is Flexbox & Why It Exists 📦](#what-is-flexbox--why-it-exists-)
  - [The Problem Flexbox Solves 🔧](#the-problem-flexbox-solves-)
  - [What "One-Dimensional" Means 🎯](#what-one-dimensional-means-)
  - [How Flexbox Actually Works (The Basic Concept) 🧠](#how-flexbox-actually-works-the-basic-concept-)
  - [When to Use Flexbox 📋](#when-to-use-flexbox-)
  - [When NOT to Use Flexbox ⚠️](#when-not-to-use-flexbox-️)
  - [Flexbox vs Other Layout Methods 🆚](#flexbox-vs-other-layout-methods-)
  - [The Two Core Concepts You Need to Understand 🎯](#the-two-core-concepts-you-need-to-understand-)
  - [Your First Flexbox Example 🚀](#your-first-flexbox-example-)
  - [Summary 📋](#summary-)
- [The Container-Item Relationship 🔗](#the-container-item-relationship-)
  - [What is a Flex Container? 📦](#what-is-a-flex-container-)
  - [What is a Flex Item? 🎁](#what-is-a-flex-item-)
  - [Direct Children Only! ⚠️](#direct-children-only-️)
  - [Container Properties vs Item Properties 🎯](#container-properties-vs-item-properties-)
  - [Common Mistakes 🐞](#common-mistakes-)
  - [Visual Example: Container vs Item Properties 👀](#visual-example-container-vs-item-properties-)
  - [Nested Flex Containers 🪆](#nested-flex-containers-)
  - [Quick Reference: Which Property Goes Where? 📋](#quick-reference-which-property-goes-where-)
  - [Testing Your Understanding 🧪](#testing-your-understanding-)
  - [Summary 📋](#summary--1)
- [Main Axis vs Cross Axis 🧭](#main-axis-vs-cross-axis-)
  - [Default Axes (flex-direction: row) 📏](#default-axes-flex-direction-row-)
  - [How flex-direction Changes the Axes 🔄](#how-flex-direction-changes-the-axes-)
  - [Why Axes Matter: Property Mapping 🎯](#why-axes-matter-property-mapping-)
  - [Visual Example: Same Code, Different Directions 👀](#visual-example-same-code-different-directions-)
  - [Practical Example: Navigation Bar vs Sidebar 🧭](#practical-example-navigation-bar-vs-sidebar-)
  - [Common Mistakes 🐞](#common-mistakes--1)
  - [Quick Reference: Axes and Properties 📋](#quick-reference-axes-and-properties-)
  - [Testing Your Understanding 🧪](#testing-your-understanding--1)
  - [Summary 📋](#summary--2)
- [Flex Container Properties 🎛️](#flex-container-properties-️)
  - [display: flex 🔑](#display-flex-)
  - [flex-direction 🧭](#flex-direction-)
  - [justify-content 📏](#justify-content-)
  - [align-items 📐](#align-items-)
  - [gap 📏](#gap-)
  - [flex-wrap 🌯](#flex-wrap-)
  - [align-content 📦](#align-content-)
  - [Combining Container Properties 🎨](#combining-container-properties-)
  - [Summary 📋](#summary--3)
- [Flex Item Properties 🎁](#flex-item-properties-)
  - [flex-grow 📈](#flex-grow-)
  - [flex-shrink 📉](#flex-shrink-)
  - [flex-basis 📏](#flex-basis-)
  - [flex (Shorthand) ⚡](#flex-shorthand-)
  - [align-self 🎯](#align-self-)
  - [order 🔢](#order-)
  - [Combining Item Properties 🎨](#combining-item-properties-)
  - [Summary 📋](#summary--4)
- [Common Use Cases & Patterns 🎨](#common-use-cases--patterns-)
  - [Pattern 1: Horizontal Navigation Bar 🧭](#pattern-1-horizontal-navigation-bar-)
  - [Pattern 2: Centered Modal Dialog 🪟](#pattern-2-centered-modal-dialog-)
  - [Pattern 3: Equal-Height Card Grid 📇](#pattern-3-equal-height-card-grid-)
  - [Pattern 4: Sidebar + Content Layout 📄](#pattern-4-sidebar--content-layout-)
  - [Pattern 5: Sticky Footer ⬇️](#pattern-5-sticky-footer-️)
  - [Pattern 6: Form Layout with Labels and Inputs 📝](#pattern-6-form-layout-with-labels-and-inputs-)
  - [Pattern 7: Media Object (Image + Text) 🖼️](#pattern-7-media-object-image--text-️)
  - [Pattern 8: Button Group 🔘](#pattern-8-button-group-)
  - [Pattern 9: Holy Grail Layout 🏛️](#pattern-9-holy-grail-layout-️)
  - [Summary 📋](#summary--5)
- [Quick Reference 📚](#quick-reference-)
  - [Container Properties (Parent) 📦](#container-properties-parent-)
  - [Item Properties (Children) 🎁](#item-properties-children-)
  - [Axis Reference 🧭](#axis-reference-)
  - [Common flex Shorthand Values ⚡](#common-flex-shorthand-values-)
  - [Troubleshooting Checklist ✅](#troubleshooting-checklist-)
  - [Browser Support 🌐](#browser-support-)
  - [Flexbox vs Grid Quick Comparison 🆚](#flexbox-vs-grid-quick-comparison-)
  - [Performance Tips ⚡](#performance-tips-)
  - [Helpful Resources 🔗](#helpful-resources-)

## **What is Flexbox & Why It Exists 📦**

Flexbox (short for "Flexible Box Layout") is a CSS layout system designed to arrange elements in **one dimension** - either in a row or a column. It gives you powerful control over how items are distributed, aligned, and sized within a container.

**Think of it like this:**

Imagine you're organizing books on a shelf. Without flexbox, you'd have to carefully measure each book, calculate spacing, and position them manually. With flexbox, you tell the shelf: "Space these books evenly" or "Push them all to the right" or "Make them all the same height," and the shelf figures out the math for you.

That's flexbox - it handles the tedious layout calculations automatically.

---

### **The Problem Flexbox Solves 🔧**

Before flexbox existed (pre-2012), creating flexible, responsive layouts in CSS was **painful**.

**Common layout challenges that were hard to solve:**

- Centering something vertically? Required hacky workarounds
- Making elements share available space equally? Lots of manual math
- Creating a navigation bar where items space themselves evenly? Frustrating
- Building a layout that adapts to different screen sizes? Complex media queries and floats

**The old way (using floats and positioning):**

```css
/* Just to center three items horizontally with equal spacing... */
.container {
  width: 100%;
}

.item {
  float: left;
  width: 30%;
  margin-right: 5%;
}

.item:last-child {
  margin-right: 0;
}

/* And this breaks if items have different heights! */
```

This required:

- Manual width calculations
- Clearing floats
- Dealing with collapsing containers
- Lots of trial and error

---

**The flexbox way:**

```css
.container {
  display: flex;
  gap: 20px;
}

/* Done. Items distribute automatically. */
```

**What flexbox does automatically:**

- Items line up horizontally (or vertically)
- Available space gets distributed
- Items can grow or shrink to fit
- Alignment happens naturally
- Everything adapts to content size

---

### **What "One-Dimensional" Means 🎯**

Flexbox is called a **one-dimensional** layout system because it handles layout in **one direction at a time** - either:

- **Horizontally** (in a row) → ←
- **Vertically** (in a column) ↕️

**Example:**

```
Row layout (horizontal):
[Item 1] [Item 2] [Item 3] [Item 4]

Column layout (vertical):
[Item 1]
[Item 2]
[Item 3]
[Item 4]
```

You can only control distribution along **one main axis** at a time. You choose whether that axis is horizontal (row) or vertical (column) with the `flex-direction` property.

**Important distinction:**

- **Flexbox** = one-dimensional (row OR column)
- **CSS Grid** = two-dimensional (rows AND columns simultaneously)

This doesn't mean flexbox is worse - it's just designed for different problems. Flexbox excels at distributing items along a single line, while Grid excels at creating complex two-dimensional layouts.

---

### **How Flexbox Actually Works (The Basic Concept) 🧠**

Flexbox uses a **parent-child relationship** where:

1. **The parent (flex container)** controls the layout
2. **The children (flex items)** get positioned automatically

**HTML structure:**

```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

**CSS:**

```css
.container {
  display: flex; /* Makes this a flex container */
}

/* Now all direct children (.item) become flex items */
/* They automatically line up horizontally */
```

**What just happened:**

- `.container` is the **flex container** (the parent)
- The three `.item` divs are **flex items** (the children)
- Setting `display: flex` on the container activates flexbox
- All direct children become flex items automatically

**The default behavior:**

When you add `display: flex` to a container, the browser automatically:

1. Lines up all children horizontally (in a row)
2. Stretches them to the same height
3. Fits them all in one line (shrinking them if needed)
4. Aligns them to the start of the container

---

### **When to Use Flexbox 📋**

**Use flexbox when you need to:**

✅ Arrange items in a **single row** or **single column**
✅ Distribute space between items evenly
✅ Center items (horizontally or vertically)
✅ Create navigation bars
✅ Build card layouts that adapt to content
✅ Make items grow to fill available space
✅ Align items along one axis
✅ Create responsive components that stack on mobile

**Common use cases:**

- Navigation menus
- Header layouts (logo on left, menu on right)
- Card grids (that wrap to multiple rows)
- Footer layouts
- Button groups
- Form layouts
- Media objects (image + text side by side)

---

### **When NOT to Use Flexbox ⚠️**

**Don't use flexbox when you need:**

❌ Complex two-dimensional layouts (use CSS Grid instead)
❌ Precise control over both rows AND columns simultaneously
❌ Full-page layouts with sidebar, header, footer, and content areas

**Example where Grid is better:**

```
┌─────────────────────────┐
│       Header            │
├──────────┬──────────────┤
│ Sidebar  │   Content    │
│          │              │
├──────────┴──────────────┤
│       Footer            │
└─────────────────────────┘
```

This layout has both rows (header/middle/footer) and columns (sidebar/content) at the same time. **Grid handles this naturally, flexbox would be awkward.**

But for individual components within this layout (like the header content or navigation), flexbox is perfect!

---

### **Flexbox vs Other Layout Methods 🆚**

| Layout Method   | Best For                                   | Example                                  |
| --------------- | ------------------------------------------ | ---------------------------------------- |
| **Flexbox**     | One-dimensional layouts (row OR column)    | Navigation bars, card layouts, centering |
| **CSS Grid**    | Two-dimensional layouts (rows AND columns) | Full page layouts, complex grids         |
| **Positioning** | Precise placement, overlapping elements    | Modals, tooltips, badges                 |

**Modern approach:** Use Grid for overall page structure, use Flexbox for components within that structure.

---

### **The Two Core Concepts You Need to Understand 🎯**

Before we dive into properties, understand these two fundamental concepts:

#### **1. Container vs Items**

Flexbox has TWO types of elements with DIFFERENT properties:

- **Flex container** (the parent) - controls overall layout
- **Flex items** (the children) - controls individual item behavior

```css
/* Container properties (applied to parent) */
.container {
  display: flex;
  justify-content: center; /* container property */
  gap: 20px; /* container property */
}

/* Item properties (applied to children) */
.item {
  flex-grow: 1; /* item property */
  align-self: end; /* item property */
}
```

**Important:** You can't use container properties on items, or vice versa. They're separate systems.

---

#### **2. Main Axis vs Cross Axis**

Flexbox uses two axes:

- **Main axis** = the primary direction (horizontal by default)
- **Cross axis** = the perpendicular direction (vertical by default)

```
Main axis (horizontal) →
┌────────────────────────────┐
│                            │  ↕ Cross axis (vertical)
│  [Item] [Item] [Item]      │
│                            │
└────────────────────────────┘
```

**Why this matters:**

- `justify-content` controls spacing along the **main axis**
- `align-items` controls positioning along the **cross axis**

When you change `flex-direction` from row to column, **the axes swap**:

```
flex-direction: column

        ↕ Main axis (vertical)
┌──────────────┐
│   [Item]     │
│   [Item]  ←→ │ Cross axis (horizontal)
│   [Item]     │
└──────────────┘
```

We'll explore this in detail in the next section.

---

### **Your First Flexbox Example 🚀**

Let's see flexbox in action with a simple example:

**HTML:**

```html
<div class="nav">
  <div class="nav-item">Home</div>
  <div class="nav-item">About</div>
  <div class="nav-item">Services</div>
  <div class="nav-item">Contact</div>
</div>
```

**Without flexbox (default block behavior):**

```css
.nav {
  background-color: #333;
  padding: 1rem;
}

.nav-item {
  background-color: #666;
  padding: 0.5rem 1rem;
  color: white;
}
```

**Result:**

```
┌────────────────┐
│ Home           │
├────────────────┤
│ About          │
├────────────────┤
│ Services       │
├────────────────┤
│ Contact        │
└────────────────┘
```

Items stack vertically (block elements default behavior).

---

**With flexbox:**

```css
.nav {
  display: flex; /* ✨ The magic line */
  background-color: #333;
  padding: 1rem;
  gap: 1rem;
}

.nav-item {
  background-color: #666;
  padding: 0.5rem 1rem;
  color: white;
}
```

**Result:**

```
┌─────────────────────────────────────┐
│ [Home] [About] [Services] [Contact] │
└─────────────────────────────────────┘
```

Items line up horizontally automatically! Just by adding `display: flex` to the parent.

**What flexbox did:**

- Changed layout direction from vertical (default) to horizontal
- Distributed items along the main axis (horizontal)
- Added spacing between items with `gap`
- Made all items the same height automatically

---

### **Summary 📋**

**Flexbox is:**

- A one-dimensional layout system
- Designed to distribute space and align items
- Applied to a **container** (parent) to control its **items** (children)
- Perfect for navigation bars, card layouts, and component-level layouts

**Key concepts:**

- **Container** = parent element with `display: flex`
- **Items** = direct children of the container
- **Main axis** = primary direction (horizontal by default)
- **Cross axis** = perpendicular direction (vertical by default)

**When to use flexbox:**

- Single-direction layouts (row or column)
- Distributing space between elements
- Centering items
- Responsive component layouts

**Next up:** We'll dive deep into the container-item relationship and understand exactly which properties go where.

---

## **The Container-Item Relationship 🔗**

This is the **most important concept** in flexbox. If you understand this, everything else makes sense. If you don't, flexbox will feel confusing and unpredictable.

**The core principle:**

Flexbox has **two separate sets of properties** that control **two different things**:

1. **Container properties** (applied to the parent) - control the overall layout
2. **Item properties** (applied to the children) - control individual item behavior

These properties **cannot be mixed**. Container properties only work on containers. Item properties only work on items.

**Think of it like this:**

Imagine you're organizing a classroom:

- **The teacher (container)** controls where students sit, how rows are arranged, spacing between desks
- **The students (items)** can raise their hand, adjust their own chair height, or move to a different position in line

The teacher controls the room. Students control themselves. They don't cross roles.

That's exactly how flexbox works.

---

### **What is a Flex Container? 📦**

A **flex container** is any element that has `display: flex` applied to it.

```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

```css
.container {
  display: flex; /* This makes .container a flex container */
}
```

**What happens:**

- `.container` becomes a flex container
- All **direct children** automatically become flex items
- The container can now use container properties
- The items can now use item properties

---

### **What is a Flex Item? 🎁**

A **flex item** is any **direct child** of a flex container.

```html
<div class="container">
  <div class="item">I'm a flex item</div>
  <div class="item">I'm also a flex item</div>
  <p>I'm a flex item too!</p>
  <span>And me!</span>
</div>
```

```css
.container {
  display: flex;
}
```

**Important:** ALL direct children become flex items automatically. It doesn't matter if they're `<div>`, `<p>`, `<span>`, or anything else.

---

### **Direct Children Only! ⚠️**

This is crucial: **Only DIRECT children become flex items**.

```html
<div class="container">
  <div class="item">
    I'm a flex item ✅
    <p>I'm NOT a flex item ❌ (I'm a grandchild)</p>
  </div>
  <div class="item">I'm a flex item ✅</div>
</div>
```

**Why this matters:**

```css
.container {
  display: flex;
  gap: 20px; /* Affects direct children only */
}
```

The `gap` creates space between the two `.item` divs, but it does NOT affect the `<p>` inside the first item, because that `<p>` is not a direct child of `.container`.

**Visual representation:**

```
Container (flex container)
├─ Item 1 (flex item) ✅
│  └─ Paragraph (NOT a flex item) ❌
└─ Item 2 (flex item) ✅
```

---

### **Container Properties vs Item Properties 🎯**

Here's the complete breakdown of which properties go where:

#### **Container Properties (Parent)**

These go on the element with `display: flex`:

```css
.container {
  display: flex; /* Activates flexbox */

  /* Main axis control */
  flex-direction: row; /* row, column, row-reverse, column-reverse */
  justify-content: center; /* flex-start, flex-end, center, space-between, space-around, space-evenly */

  /* Cross axis control */
  align-items: center; /* flex-start, flex-end, center, stretch, baseline */

  /* Wrapping */
  flex-wrap: wrap; /* nowrap, wrap, wrap-reverse */

  /* Multi-line alignment */
  align-content: center; /* flex-start, flex-end, center, space-between, space-around, stretch */

  /* Spacing */
  gap: 20px; /* Spacing between items */
}
```

**What these control:**

- The direction items flow
- How items are distributed along the main axis
- How items align on the cross axis
- Whether items wrap to new lines
- Spacing between items

---

#### **Item Properties (Children)**

These go on the direct children of the flex container:

```css
.item {
  /* Flexibility */
  flex-grow: 1; /* How much item grows to fill space (default: 0) */
  flex-shrink: 1; /* How much item shrinks when space is tight (default: 1) */
  flex-basis: auto; /* Base size before growing/shrinking (default: auto) */

  /* Shorthand */
  flex: 1; /* Shorthand for grow, shrink, basis */

  /* Individual alignment */
  align-self: center; /* Overrides align-items for this specific item */

  /* Visual order */
  order: 2; /* Changes visual order (default: 0) */
}
```

**What these control:**

- How an individual item grows or shrinks
- An item's base size
- An item's alignment (overriding the container's default)
- An item's visual position in the sequence

---

### **Why the Separation? 🤔**

**Container properties** answer the question: "How should I arrange ALL the items?"

- Where do items flow? (direction)
- How should space be distributed? (justify-content)
- How should items align? (align-items)

**Item properties** answer the question: "How should THIS specific item behave?"

- Should this item grow bigger than others? (flex-grow)
- Should this item shrink less than others? (flex-shrink)
- Should this item align differently? (align-self)
- Should this item appear in a different order? (order)

---

### **Common Mistakes 🐞**

#### **Mistake 1: Putting container properties on items**

```css
/* ❌ Wrong */
.item {
  justify-content: center; /* This does nothing! */
  gap: 20px; /* This does nothing! */
}
```

**Why it fails:** These are container properties. Items can't use them.

**Fix:**

```css
/* ✅ Correct */
.container {
  justify-content: center;
  gap: 20px;
}
```

---

#### **Mistake 2: Putting item properties on containers**

```css
/* ❌ Wrong */
.container {
  flex-grow: 1; /* This does nothing! */
  align-self: end; /* This does nothing! */
}
```

**Why it fails:** These are item properties. Containers can't use them.

**Fix:**

```css
/* ✅ Correct */
.item {
  flex-grow: 1;
  align-self: end;
}
```

---

#### **Mistake 3: Forgetting `display: flex`**

```css
/* ❌ Wrong */
.container {
  justify-content: center;
  gap: 20px;
  /* Missing display: flex! */
}
```

**Why it fails:** Without `display: flex`, the container isn't a flex container, so flex properties are ignored.

**Fix:**

```css
/* ✅ Correct */
.container {
  display: flex; /* Must be present */
  justify-content: center;
  gap: 20px;
}
```

---

#### **Mistake 4: Expecting grandchildren to be flex items**

```html
<div class="container">
  <div class="item">
    <p class="text">Hello</p>
  </div>
</div>
```

```css
.container {
  display: flex;
  gap: 20px; /* Only affects .item, NOT .text */
}
```

**Why it fails:** `gap` only affects direct children (`.item`), not grandchildren (`.text`).

**If you need .text to be a flex item:**

```css
.item {
  display: flex; /* Make .item a flex container too */
  gap: 10px; /* Now affects .text */
}
```

Now you have **nested flex containers**:

- `.container` is a flex container with `.item` as its flex item
- `.item` is ALSO a flex container with `.text` as its flex item

This is completely valid and very common!

---

### **Visual Example: Container vs Item Properties 👀**

Let's see both sets of properties working together:

```html
<div class="navigation">
  <div class="nav-item">Home</div>
  <div class="nav-item">About</div>
  <div class="nav-item special">Services</div>
  <div class="nav-item">Contact</div>
</div>
```

```css
/* Container properties */
.navigation {
  display: flex;
  justify-content: space-between; /* Distribute items with space between */
  align-items: center; /* Vertically center all items */
  gap: 1rem; /* Space between items */
  background-color: #333;
  padding: 1rem;
}

/* Item properties (all items) */
.nav-item {
  flex-grow: 1; /* All items grow equally to fill space */
  padding: 0.5rem 1rem;
  background-color: #666;
  color: white;
  text-align: center;
}

/* Item properties (specific item) */
.special {
  flex-grow: 2; /* This item grows twice as much */
  align-self: stretch; /* This item stretches vertically */
  background-color: #e74c3c;
}
```

**What happens:**

```
┌────────────────────────────────────────────────┐
│ [Home] [About] [Services (bigger)] [Contact]  │
└────────────────────────────────────────────────┘
```

**Container controls:**

- Items are spaced evenly (`space-between`)
- Items are centered vertically (`align-items: center`)
- 1rem gap between items

**Items control:**

- All items grow to fill space (`flex-grow: 1`)
- The "Services" item grows twice as much (`flex-grow: 2`)
- The "Services" item has different alignment (`align-self: stretch`)

---

### **Nested Flex Containers 🪆**

An element can be BOTH a flex container AND a flex item at the same time.

```html
<div class="outer-container">
  <div class="inner-container">
    <div class="item">A</div>
    <div class="item">B</div>
  </div>
  <div class="inner-container">
    <div class="item">C</div>
    <div class="item">D</div>
  </div>
</div>
```

```css
/* Outer container */
.outer-container {
  display: flex;
  flex-direction: column; /* Stack inner containers vertically */
  gap: 20px;
}

/* Inner container is BOTH flex item AND flex container */
.inner-container {
  display: flex; /* Flex container for items inside */
  gap: 10px; /* Container property */
  flex-grow: 1; /* Item property (in relation to outer-container) */
}

/* Items */
.item {
  flex-grow: 1;
  padding: 1rem;
  background-color: #3498db;
}
```

**Understanding the dual role:**

`.inner-container` can use BOTH sets of properties because it's both a container AND an item:

- As a **container**: Uses `display: flex`, `gap` to arrange its children (A, B, C, D) inside it
- As an **item**: Uses `flex-grow` to control how it behaves inside `.outer-container`

Think of it like this: The element looks "up" to its parent (`.outer-container`) and acts as an item using item properties. Then it looks "down" to its children (`.item` elements) and acts as a container using container properties.

**What's happening:**

1. `.outer-container` is a flex container
2. `.inner-container` elements are flex items inside `.outer-container`
3. BUT `.inner-container` is ALSO a flex container for its own children
4. `.item` elements are flex items inside `.inner-container`

**Result:**

```
┌─────────────────────┐ ← Outer container
│  ┌───────────────┐  │
│  │  [A] [B]      │  │ ← Inner container 1
│  └───────────────┘  │
│                     │
│  ┌───────────────┐  │
│  │  [C] [D]      │  │ ← Inner container 2
│  └───────────────┘  │
└─────────────────────┘
```

This creates a nested layout where:

- Outer container stacks inner containers vertically
- Each inner container arranges its items horizontally

---

### **Quick Reference: Which Property Goes Where? 📋**

**Container Properties (on parent):**

- `display: flex`
- `flex-direction`
- `justify-content`
- `align-items`
- `flex-wrap`
- `align-content`
- `gap`

**Item Properties (on children):**

- `flex-grow`
- `flex-shrink`
- `flex-basis`
- `flex` (shorthand)
- `align-self`
- `order`

**Remember:** If you're not sure, ask yourself: "Am I controlling the overall layout (container) or individual item behavior (item)?"

---

### **Testing Your Understanding 🧪**

**Question 1:** Why doesn't this work?

```css
.item {
  justify-content: center;
}
```

**Answer:** `justify-content` is a container property. It only works on flex containers, not flex items.

---

**Question 2:** Why doesn't this work?

```css
.container {
  display: flex;
  flex-grow: 1;
}
```

**Answer:** `flex-grow` is an item property. It only works on flex items, not flex containers.

---

**Question 3:** Will `gap` affect the `<span>`?

```html
<div class="container">
  <div class="item">
    <span>Text</span>
  </div>
</div>
```

```css
.container {
  display: flex;
  gap: 20px;
}
```

**Answer:** No. `gap` only affects direct children of the flex container. The `<span>` is a grandchild, not a direct child.

---

### **Summary 📋**

**Container (parent):**

- Has `display: flex`
- Controls overall layout direction, distribution, and alignment
- Uses properties like `justify-content`, `align-items`, `gap`

**Items (direct children):**

- Automatically become flex items when parent has `display: flex`
- Control their own growth, shrinkage, and individual alignment
- Use properties like `flex-grow`, `flex-shrink`, `align-self`

**Key rules:**

1. Container properties only work on containers
2. Item properties only work on items
3. Only direct children become flex items
4. An element can be both a container AND an item (nested flexbox)

**Remember:** Container = "How should I arrange ALL items?" / Item = "How should I behave individually?"

---

## **Main Axis vs Cross Axis 🧭**

This is the second fundamental concept you need to master. Every flexbox property you use relates to either the **main axis** or the **cross axis**. Understanding these axes is the key to predicting how flexbox will behave.

**The golden rule:**

Flexbox always has **two axes**:

- **Main axis** = the primary direction items flow
- **Cross axis** = the perpendicular direction (90° from main axis)

These axes determine which properties control which direction.

---

### **Default Axes (flex-direction: row) 📏**

By default (when you first add `display: flex`), the axes are:

- **Main axis** = horizontal (left to right →)
- **Cross axis** = vertical (top to bottom ↓)

**Visual representation:**

```
                Main axis →
        ┌────────────────────────────┐
        │                            │
    ↕   │  [Item] [Item] [Item]      │
Cross   │                            │
axis    │                            │
        └────────────────────────────┘
```

**What this means:**

Items line up **horizontally** (along the main axis) by default.

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex;
  /* flex-direction: row is the default */
}
```

**Result:**

```
[1] [2] [3]
```

Items flow horizontally because the main axis is horizontal.

---

### **How flex-direction Changes the Axes 🔄**

Here's where it gets interesting: **`flex-direction` changes which axis is "main" and which is "cross"**.

The main axis is **always** the direction items flow.

#### **flex-direction: row (default)**

```css
.container {
  display: flex;
  flex-direction: row;
}
```

- **Main axis:** Horizontal →
- **Cross axis:** Vertical ↓
- **Items flow:** Left to right

```
        Main axis →
    ┌──────────────────┐
↕   │ [1] [2] [3]      │
Cross axis             │
    └──────────────────┘
```

---

#### **flex-direction: column**

```css
.container {
  display: flex;
  flex-direction: column;
}
```

- **Main axis:** Vertical ↓
- **Cross axis:** Horizontal →
- **Items flow:** Top to bottom

```
        ← Cross axis →
        ┌──────────┐
        │  [1]     │  ↕
        │  [2]     │  Main
        │  [3]     │  axis
        └──────────┘
```

**Notice:** The axes **swapped**! Now main is vertical, cross is horizontal.

---

#### **flex-direction: row-reverse**

```css
.container {
  display: flex;
  flex-direction: row-reverse;
}
```

- **Main axis:** Horizontal ← (reversed!)
- **Cross axis:** Vertical ↓
- **Items flow:** Right to left

```
        ← Main axis
    ┌──────────────────┐
↕   │      [3] [2] [1] │
Cross axis             │
    └──────────────────┘
```

Items still flow horizontally (main axis is still horizontal), but they start from the right and go left.

---

#### **flex-direction: column-reverse**

```css
.container {
  display: flex;
  flex-direction: column-reverse;
}
```

- **Main axis:** Vertical ↑ (reversed!)
- **Cross axis:** Horizontal →
- **Items flow:** Bottom to top

```
        ← Cross axis →
        ┌──────────┐
        │  [3]     │  ↕
        │  [2]     │  Main
        │  [1]     │  axis
        └──────────┘
```

Items flow vertically (main axis is vertical), but they start from the bottom and go up.

---

### **Why Axes Matter: Property Mapping 🎯**

Here's the critical part: **Different properties control different axes.**

#### **Main Axis Properties**

These properties control how items are distributed **along the main axis**:

- `justify-content` - distributes items along main axis
- `flex-direction` - sets the direction of the main axis

#### **Cross Axis Properties**

These properties control how items are aligned **along the cross axis**:

- `align-items` - aligns all items on cross axis
- `align-self` - aligns a single item on cross axis
- `align-content` - aligns rows/columns when wrapping (multi-line only)

**The mental model:**

- **justify-\*** = main axis
- **align-\*** = cross axis

---

### **Visual Example: Same Code, Different Directions 👀**

Let's see how the same `justify-content` and `align-items` values behave differently when you change `flex-direction`.

**Example code:**

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex;
  justify-content: center; /* Main axis */
  align-items: center; /* Cross axis */
  height: 200px;
  border: 2px solid #333;
}

.item {
  width: 60px;
  height: 60px;
  background-color: #3498db;
}
```

---

#### **With flex-direction: row**

```css
.container {
  flex-direction: row; /* Main = horizontal, Cross = vertical */
  justify-content: center; /* Centers horizontally (main axis) */
  align-items: center; /* Centers vertically (cross axis) */
}
```

**Result:**

```
┌───────────────────────┐
│                       │
│      [1] [2] [3]      │ ← Items centered horizontally AND vertically
│                       │
└───────────────────────┘
```

- `justify-content: center` centers items **horizontally** (main axis)
- `align-items: center` centers items **vertically** (cross axis)

---

#### **With flex-direction: column**

```css
.container {
  flex-direction: column; /* Main = vertical, Cross = horizontal */
  justify-content: center; /* Centers vertically (main axis) */
  align-items: center; /* Centers horizontally (cross axis) */
}
```

**Result:**

```
┌───────────────────────┐
│          [1]          │
│          [2]          │ ← Items centered vertically AND horizontally
│          [3]          │
└───────────────────────┘
```

- `justify-content: center` centers items **vertically** (main axis)
- `align-items: center` centers items **horizontally** (cross axis)

**Notice:** Same properties, same values, but they control **different directions** because the axes swapped!

---

### **Practical Example: Navigation Bar vs Sidebar 🧭**

Let's see how understanding axes helps you build different layouts.

#### **Horizontal Navigation (Row)**

```html
<nav class="navbar">
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Services</a>
  <a href="#">Contact</a>
</nav>
```

```css
.navbar {
  display: flex;
  flex-direction: row; /* Main = horizontal */
  justify-content: space-between; /* Spread items horizontally */
  align-items: center; /* Center items vertically */
  height: 60px;
  background-color: #2c3e50;
  padding: 0 2rem;
}

.navbar a {
  color: white;
  text-decoration: none;
}
```

**Result:**

```
┌─────────────────────────────────────┐
│ Home    About    Services    Contact│ ← Items spread horizontally
└─────────────────────────────────────┘
```

- Main axis = horizontal → `justify-content` spreads items left to right
- Cross axis = vertical → `align-items` centers items top to bottom

---

#### **Vertical Sidebar (Column)**

```html
<aside class="sidebar">
  <a href="#">Dashboard</a>
  <a href="#">Profile</a>
  <a href="#">Settings</a>
  <a href="#">Logout</a>
</aside>
```

```css
.sidebar {
  display: flex;
  flex-direction: column; /* Main = vertical */
  justify-content: flex-start; /* Items start at top */
  align-items: stretch; /* Items fill width */
  width: 200px;
  height: 100vh;
  background-color: #34495e;
  padding: 1rem;
  gap: 0.5rem;
}

.sidebar a {
  color: white;
  text-decoration: none;
  padding: 0.75rem;
  background-color: #2c3e50;
  border-radius: 4px;
}
```

**Result:**

```
┌───────────────┐
│ Dashboard     │
│ Profile       │
│ Settings      │
│ Logout        │
│               │
│               │
└───────────────┘
```

- Main axis = vertical → `justify-content` positions items top to bottom
- Cross axis = horizontal → `align-items` stretches items left to right

---

### **Common Mistakes 🐞**

#### **Mistake 1: Confusing which property controls which direction**

```css
/* ❌ Wrong mental model */
.container {
  display: flex;
  flex-direction: column;
  justify-content: center; /* "I want items centered horizontally" */
}
```

**Problem:** With `flex-direction: column`, main axis is **vertical**, so `justify-content` controls **vertical** distribution, not horizontal.

**If you want horizontal centering with column direction:**

```css
/* ✅ Correct */
.container {
  display: flex;
  flex-direction: column;
  align-items: center; /* Horizontal centering (cross axis) */
}
```

---

#### **Mistake 2: Forgetting axes swap with flex-direction**

```css
/* ❌ Doesn't work as expected */
.container {
  display: flex;
  flex-direction: row; /* Horizontal main axis */
  align-items: space-between; /* Trying to spread items */
}
```

**Problem:** `align-items` is for the **cross axis**. You can't use `space-between` with `align-items`. That value only works with `justify-content` (main axis).

**Correct:**

```css
/* ✅ Correct */
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between; /* Spreads items on main axis */
}
```

---

#### **Mistake 3: Not accounting for axis swap in responsive design**

```css
/* Works on desktop */
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

/* Breaks on mobile */
@media (max-width: 768px) {
  .container {
    flex-direction: column;
    /* Still using justify-content: space-between */
    /* Now this spreads items VERTICALLY, which might not be what you want */
  }
}
```

**Better approach:**

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
    align-items: stretch; /* Items fill width */
    gap: 1rem; /* Spacing between items */
  }
}
```

---

### **Quick Reference: Axes and Properties 📋**

| flex-direction   | Main Axis    | Cross Axis   | justify-content controls | align-items controls |
| ---------------- | ------------ | ------------ | ------------------------ | -------------------- |
| `row`            | Horizontal → | Vertical ↓   | Horizontal spacing       | Vertical alignment   |
| `row-reverse`    | Horizontal ← | Vertical ↓   | Horizontal spacing       | Vertical alignment   |
| `column`         | Vertical ↓   | Horizontal → | Vertical spacing         | Horizontal alignment |
| `column-reverse` | Vertical ↑   | Horizontal → | Vertical spacing         | Horizontal alignment |

**Memory trick:**

- **justify-content** = main axis = direction items **flow**
- **align-items** = cross axis = direction **perpendicular** to flow

---

### **Testing Your Understanding 🧪**

**Question 1:** With `flex-direction: row`, which property centers items vertically?

```css
.container {
  display: flex;
  flex-direction: row;
  /* Which property? */
}
```

**Answer:** `align-items: center` - because vertical is the cross axis when main axis is horizontal (row).

---

**Question 2:** With `flex-direction: column`, which property spreads items from top to bottom?

```css
.container {
  display: flex;
  flex-direction: column;
  /* Which property? */
}
```

**Answer:** `justify-content: space-between` - because vertical is the main axis when using column direction.

---

**Question 3:** Why doesn't this center items horizontally?

```css
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
```

**Answer:** Because `justify-content` controls the main axis, which is **vertical** when using `flex-direction: column`. To center horizontally (cross axis), use `align-items: center`.

---

### **Summary 📋**

**Main Axis:**

- The direction items flow
- Controlled by `flex-direction`
- Properties: `justify-content`, `flex-direction`

**Cross Axis:**

- Perpendicular to main axis
- Always 90° from the flow direction
- Properties: `align-items`, `align-self`, `align-content`

**Key insight:**

When `flex-direction` changes, the axes swap roles. What was horizontal becomes vertical and vice versa. The properties (`justify-content`, `align-items`) don't change, but what they control does.

**Remember:** justify = main axis, align = cross axis. Always.

---

## **Flex Container Properties 🎛️**

These are the properties you apply to the **parent element** (the flex container) to control how all the items are laid out. Remember: these only work when `display: flex` is set on the container.

We'll cover each property in detail with examples and all available values.

---

### **display: flex 🔑**

This is the **activation switch** for flexbox. Without this, none of the other flex properties work.

```css
.container {
  display: flex; /* Turns on flexbox */
}
```

**What it does:**

- Makes the element a flex container
- All direct children become flex items
- Enables all flex properties
- Changes layout behavior from block/inline to flex

**Alternative value:**

```css
.container {
  display: inline-flex; /* Flex container that behaves like inline element */
}
```

**Difference:**

- `display: flex` - Container behaves like a **block element** (takes full width)
- `display: inline-flex` - Container behaves like an **inline element** (only as wide as its content)

**When to use inline-flex:**

```html
<p>
  Some text <span class="inline-container">with flex items</span> in the middle.
</p>
```

```css
.inline-container {
  display: inline-flex; /* Flows with text */
  gap: 5px;
}
```

The flex container stays inline with the surrounding text instead of breaking to a new line.

**Most of the time, you'll use `display: flex`, not `inline-flex`.**

---

### **flex-direction 🧭**

Controls the **main axis direction** - which way items flow.

**Syntax:**

```css
.container {
  display: flex;
  flex-direction: row | row-reverse | column | column-reverse;
}
```

We covered the concept in Section 3. Here's the complete breakdown:

---

#### **flex-direction: row (default)**

```css
.container {
  display: flex;
  flex-direction: row;
}
```

**What it does:**

- Items flow **horizontally** from left to right
- Main axis: horizontal →
- Cross axis: vertical ↓

**Visual:**

```
[1] [2] [3] [4]
```

**Use case:** Navigation bars, horizontal button groups, card layouts.

---

#### **flex-direction: row-reverse**

```css
.container {
  display: flex;
  flex-direction: row-reverse;
}
```

**What it does:**

- Items flow **horizontally** from right to left
- Main axis: horizontal ← (reversed)
- Cross axis: vertical ↓

**Visual:**

```
[4] [3] [2] [1]
```

**Use case:** RTL (right-to-left) language layouts, reversing visual order without changing HTML.

---

#### **flex-direction: column**

```css
.container {
  display: flex;
  flex-direction: column;
}
```

**What it does:**

- Items flow **vertically** from top to bottom
- Main axis: vertical ↓
- Cross axis: horizontal →

**Visual:**

```
[1]
[2]
[3]
[4]
```

**Use case:** Sidebars, vertical navigation, stacking cards on mobile.

---

#### **flex-direction: column-reverse**

```css
.container {
  display: flex;
  flex-direction: column-reverse;
}
```

**What it does:**

- Items flow **vertically** from bottom to top
- Main axis: vertical ↑ (reversed)
- Cross axis: horizontal →

**Visual:**

```
[4]
[3]
[2]
[1]
```

**Use case:** Chat interfaces where new messages appear at bottom but list starts from bottom, footer elements that should visually reverse.

---

### **justify-content 📏**

Controls how items are **distributed along the main axis** (the direction they flow).

**Syntax:**

```css
.container {
  display: flex;
  justify-content: flex-start | flex-end | center | space-between | space-around
    | space-evenly;
}
```

This is one of the most-used flex properties. Let's see each value:

---

#### **justify-content: flex-start (default)**

```css
.container {
  display: flex;
  justify-content: flex-start;
}
```

**What it does:** Items pack at the **start** of the main axis.

**Visual (row):**

```
┌────────────────────────┐
│[1][2][3]               │ ← Items at start, extra space at end
└────────────────────────┘
```

**Visual (column):**

```
┌──────┐
│ [1]  │ ← Items at top
│ [2]  │
│ [3]  │
│      │
│      │ ← Extra space at bottom
└──────┘
```

---

#### **justify-content: flex-end**

```css
.container {
  display: flex;
  justify-content: flex-end;
}
```

**What it does:** Items pack at the **end** of the main axis.

**Visual (row):**

```
┌────────────────────────┐
│               [1][2][3]│ ← Items at end, extra space at start
└────────────────────────┘
```

**Visual (column):**

```
┌──────┐
│      │ ← Extra space at top
│      │
│ [1]  │
│ [2]  │ ← Items at bottom
│ [3]  │
└──────┘
```

---

#### **justify-content: center**

```css
.container {
  display: flex;
  justify-content: center;
}
```

**What it does:** Items pack in the **center** of the main axis.

**Visual (row):**

```
┌─────────────────────┐
│      [1][2][3]      │ ← Items centered, equal space on sides
└─────────────────────┘
```

**Visual (column):**

```
┌──────┐
│      │
│ [1]  │ ← Items centered vertically
│ [2]  │
│ [3]  │
│      │
└──────┘
```

**Use case:** Centering navigation items, centering cards in a container.

---

#### **justify-content: space-between**

```css
.container {
  display: flex;
  justify-content: space-between;
}
```

**What it does:**

- First item at the start
- Last item at the end
- **Equal space BETWEEN items** (no space at edges)

**Visual (row):**

```
┌─────────────────────┐
│[1]      [2]      [3]│ ← Equal gaps between, no gap at edges
└─────────────────────┘
```

**Visual (column):**

```
┌──────┐
│ [1]  │ ← First at top
│      │
│ [2]  │ ← Equal spacing
│      │
│ [3]  │ ← Last at bottom
└──────┘
```

**Use case:** Navigation with logo on left, links on right. Spreading items across full width.

---

#### **justify-content: space-around**

```css
.container {
  display: flex;
  justify-content: space-around;
}
```

**What it does:**

- Equal space **around** each item
- Space at edges is **half** the space between items

**Visual (row):**

```
┌─────────────────────┐
│  [1]    [2]    [3]  │ ← Space around each item
└─────────────────────┘
  ↑      ↑           ↑
  half   full      half
  space  space     space
```

Think of each item having equal margin on both sides. Where margins touch (between items), they add up to double. At edges, there's only one margin, so half the space.

**Visual (column):**

```
┌──────┐
│      │ ← Half space
│ [1]  │
│      │ ← Full space
│      │
│ [2]  │
│      │ ← Full space
│      │
│ [3]  │
│      │ ← Half space
└──────┘
```

---

#### **justify-content: space-evenly**

```css
.container {
  display: flex;
  justify-content: space-evenly;
}
```

**What it does:**

- **Equal space everywhere** (between items AND at edges)

**Visual (row):**

```
┌─────────────────────┐
│   [1]   [2]   [3]   │ ← All gaps equal
└─────────────────────┘
   ↑     ↑     ↑     ↑
  equal equal equal equal
  space space space space
```

**Visual (column):**

```
┌──────┐
│      │ ← Equal space
│ [1]  │
│      │ ← Equal space
│ [2]  │
│      │ ← Equal space
│ [3]  │
│      │ ← Equal space
└──────┘
```

**Difference from space-around:**

- `space-around`: edges have half the space
- `space-evenly`: edges have full space (same as between items)

---

### **align-items 📐**

Controls how items are **aligned along the cross axis** (perpendicular to the main axis).

**Syntax:**

```css
.container {
  display: flex;
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```

---

#### **align-items: stretch (default)**

```css
.container {
  display: flex;
  align-items: stretch;
}
```

**What it does:** Items **stretch to fill the container** along the cross axis.

**Visual (row - cross axis is vertical):**

```
┌──────────────────┐
│┌────┐┌────┐┌────┐│ ← Items stretch to container height
││ 1  ││ 2  ││ 3  ││
││    ││    ││    ││
│└────┘└────┘└────┘│
└──────────────────┘
```

All items are the same height, regardless of their content.

**Visual (column - cross axis is horizontal):**

```
┌────────────────┐
│ ┌────────────┐ │ ← Items stretch to container width
│ │     1      │ │
│ └────────────┘ │
│ ┌────────────┐ │
│ │     2      │ │
│ └────────────┘ │
│ ┌────────────┐ │
│ │     3      │ │
│ └────────────┘ │
└────────────────┘
```

**Important:** If items have a fixed height (with `flex-direction: row`) or fixed width (with `flex-direction: column`), they won't stretch. Stretch only works when size on the cross axis is `auto`.

---

#### **align-items: flex-start**

```css
.container {
  display: flex;
  align-items: flex-start;
}
```

**What it does:** Items align at the **start** of the cross axis.

**Visual (row):**

```
┌────────────────────────┐
│┌──┐┌────┐┌──┐          │ ← Items aligned to top
││1 ││ 2  ││3 │          │
│└──┘│    │└──┘          │
│    └────┘              │
└────────────────────────┘
```

Items with different heights align their **tops**.

**Visual (column):**

```
┌────────────────┐
│┌──┐            │ ← Items aligned to left
││1 │            │
│└──┘            │
│┌────┐          │
││ 2  │          │
│└────┘          │
│┌──┐            │
││3 │            │
│└──┘            │
└────────────────┘
```

---

#### **align-items: flex-end**

```css
.container {
  display: flex;
  align-items: flex-end;
}
```

**What it does:** Items align at the **end** of the cross axis.

**Visual (row):**

```
┌────────────────────────┐
│    ┌────┐              │
│┌──┐│    │┌──┐          │ ← Items aligned to bottom
││1 ││ 2  ││3 │          │
│└──┘└────┘└──┘          │
└────────────────────────┘
```

Items with different heights align their **bottoms**.

**Visual (column):**

```
┌────────────────┐
│            ┌──┐│ ← Items aligned to right
│            │1 ││
│            └──┘│
│          ┌────┐│
│          │ 2  ││
│          └────┘│
│            ┌──┐│
│            │3 ││
│            └──┘│
└────────────────┘
```

---

#### **align-items: center**

```css
.container {
  display: flex;
  align-items: center;
}
```

**What it does:** Items align in the **center** of the cross axis.

**Visual (row):**

```
┌────────────────────────┐
|                        |
│    ┌────┐              │
│┌──┐│    │┌──┐          │ ← Items centered vertically
││1 ││ 2  ││3 │          │
│└──┘└────┘└──┘          │
|                        |
└────────────────────────┘
```

**Visual (column):**

```
┌────────────────┐
│      ┌──┐      │ ← Items centered horizontally
│      │1 │      │
│      └──┘      │
│    ┌────┐      │
│    │ 2  │      │
│    └────┘      │
│      ┌──┐      │
│      │3 │      │
│      └──┘      │
└────────────────┘
```

**Use case:** Vertically centering items in a horizontal layout (very common for navigation bars).

---

#### **align-items: baseline**

```css
.container {
  display: flex;
  align-items: baseline;
}
```

**What it does:** Items align along their **text baseline** (the invisible line text sits on).

**Visual:**

```
┌────────────────────────────┐
│       ┌──────┐             │
│┌────┐ │      │ ┌─────┐     │
││text│ │ text │ │text │     │ ← Text baselines aligned
│└────┘ └──────┘ |     |     │
|                └─────┘     |
└────────────────────────────┘
         ↑
    All text sits on
    the same baseline
```

**Use case:** When you have items with different font sizes or padding but want their text to line up.

**Example:**

```html
<div class="container">
  <div class="small">Small</div>
  <div class="large">Large</div>
  <div class="small">Small</div>
</div>
```

```css
.container {
  display: flex;
  align-items: baseline;
}

.small {
  font-size: 1rem;
}

.large {
  font-size: 3rem;
}
```

The text "Small", "Large", "Small" all sit on the same baseline, even though font sizes differ.

---

### **gap 📏**

Controls **spacing between flex items** (not at the edges).

**Syntax:**

```css
.container {
  display: flex;
  gap: 20px; /* Single value = both row and column gap */
}
```

**Or separate values:**

```css
.container {
  display: flex;
  gap: 20px 40px; /* row-gap column-gap */
}
```

**What it does:**

- Adds consistent spacing between items
- Does NOT add space at container edges
- Replaces the need for margins on items

**Visual:**

```
Without gap:
[1][2][3][4]

With gap: 20px:
[1]  [2]  [3]  [4]
    ↑    ↑    ↑
   20px 20px 20px
```

**Why gap is better than margins:**

**Old way (using margins):**

```css
.item {
  margin-right: 20px;
}

.item:last-child {
  margin-right: 0; /* Remove margin from last item */
}
```

**New way (using gap):**

```css
.container {
  display: flex;
  gap: 20px;
}
```

Much cleaner! No need to remove margin from the last item.

---

**Separate row and column gaps:**

```css
.container {
  display: flex;
  flex-wrap: wrap; /* Items can wrap to multiple rows */
  gap: 20px 40px; /* 20px between rows, 40px between columns */
}
```

**Visual:**

```
[1]      [2]      [3]
  ↕ 20px
[4]      [5]      [6]
  ↔ 40px
```

**Use case:** Card grids, navigation items, any layout where you need consistent spacing.

---

### **flex-wrap 🌯**

Controls whether items **wrap to new lines** when they don't fit.

**Syntax:**

```css
.container {
  display: flex;
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

---

#### **flex-wrap: nowrap (default)**

```css
.container {
  display: flex;
  flex-wrap: nowrap;
}
```

**What it does:**

- All items stay on **one line**
- Items **shrink** to fit if necessary
- Can cause overflow if items have minimum widths

**Visual:**

```
Container width: 400px
Item width: 150px each (total 600px)

┌────────────────┐
│[1][2][3][4]    │ ← Items shrunk to fit
└────────────────┘
```

Items are compressed to fit the container.

---

#### **flex-wrap: wrap**

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

**What it does:**

- Items that don't fit **wrap to the next line**
- Creates a multi-line flex container
- Items maintain their natural size

**Visual:**

```
Container width: 400px
Item width: 150px each

┌─────────┐
│[1] [2]  │ ← First row
│[3] [4]  │ ← Second row (wrapped)
└─────────┘
```

**Use case:** Responsive card grids, tag clouds, any layout that should adapt to screen size.

**Example:**

```html
<div class="cards">
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
  <div class="card">Card 4</div>
  <div class="card">Card 5</div>
</div>
```

```css
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.card {
  width: 300px;
  min-width: 250px; /* Cards won't shrink below this */
}
```

**Result on wide screen:**

```
[Card 1] [Card 2] [Card 3]
[Card 4] [Card 5]
```

**Result on narrow screen:**

```
[Card 1]
[Card 2]
[Card 3]
[Card 4]
[Card 5]
```

The layout adapts automatically!

---

#### **flex-wrap: wrap-reverse**

```css
.container {
  display: flex;
  flex-wrap: wrap-reverse;
}
```

**What it does:**

- Items wrap to new lines
- But new lines are added **above** instead of below

**Visual:**

```
┌─────────┐
│[3] [4]  │ ← Second row (appears first visually)
│[1] [2]  │ ← First row (appears second)
└─────────┘
```

**Use case:** Rarely used. Maybe for chat interfaces where new messages appear at bottom but you want earlier messages to appear higher up.

---

### **align-content 📦**

Controls spacing between **rows or columns** when items wrap to multiple lines.

**Important:** This property **only works when `flex-wrap: wrap` is enabled** and items actually wrap to multiple lines.

**Syntax:**

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: stretch | flex-start | flex-end | center | space-between |
    space-around | space-evenly;
}
```

**Think of it as `justify-content` but for the cross axis when you have multiple lines.**

---

#### **align-content: stretch (default)**

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: stretch;
}
```

**What it does:** Rows stretch to fill the container's cross-axis space.

**Visual:**

```
┌────────────────┐
│┌──┐┌──┐        │
││1 ││2 │        │ ← Row 1 (takes half container height)
│└──┘└──┘        │
├────────────────┤ ← Rows divided equally
│┌──┐┌──┐        │
││3 ││4 │        │ ← Row 2 (takes half container height)
│└──┘└──┘        │
└────────────────┘
```

---

#### **align-content: flex-start**

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: flex-start;
}
```

**What it does:** Rows pack at the start of the cross axis.

**Visual:**

```
┌────────────────┐
│[1] [2]         │ ← Rows at top
│[3] [4]         │
│                │
│                │ ← Extra space at bottom
└────────────────┘
```

---

#### **align-content: center**

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: center;
}
```

**What it does:** Rows centered on the cross axis.

**Visual:**

```
┌────────────────┐
│                │
│[1] [2]         │ ← Rows centered
│[3] [4]         │
│                │
└────────────────┘
```

---

#### **align-content: space-between**

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: space-between;
}
```

**What it does:** Equal space between rows, no space at edges.

**Visual:**

```
┌────────────────┐
│[1] [2]         │ ← First row at top
│                │ ← Space between
│[3] [4]         │ ← Second row at bottom
└────────────────┘
```

---

**When to use align-content vs align-items:**

- **align-items:** Aligns items within a **single row** on the cross axis
- **align-content:** Distributes **multiple rows** along the cross axis

If you only have one row (no wrapping), `align-content` does nothing. Use `align-items`.

---

### **Combining Container Properties 🎨**

Let's see how these properties work together:

**Example: Responsive Card Grid**

```html
<div class="grid">
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
  <div class="card">Card 4</div>
  <div class="card">Card 5</div>
  <div class="card">Card 6</div>
</div>
```

```css
.grid {
  display: flex;
  flex-direction: row; /* Horizontal flow */
  flex-wrap: wrap; /* Wrap to multiple rows */
  justify-content: space-between; /* Spread items */
  align-items: stretch; /* Equal height cards */
  gap: 20px; /* Space between cards */
}

.card {
  flex: 1 1 300px; /* Grow, shrink, base 300px */
  min-width: 250px; /* Don't shrink below this */
  padding: 1.5rem;
  background-color: #3498db;
  color: white;
  border-radius: 8px;
}
```

**What this creates:**

- Cards line up horizontally
- Wrap to new rows when screen is narrow
- Equal spacing between cards
- All cards in a row have the same height
- Responsive: adapts from 1 column on mobile to 3+ columns on desktop

---

### **Summary 📋**

**Container properties:**

| Property          | Controls                           | Common Values                                             |
| ----------------- | ---------------------------------- | --------------------------------------------------------- |
| `display`         | Activates flexbox                  | `flex`, `inline-flex`                                     |
| `flex-direction`  | Main axis direction                | `row`, `column`, `row-reverse`, `column-reverse`          |
| `justify-content` | Main axis distribution             | `flex-start`, `center`, `space-between`, `space-evenly`   |
| `align-items`     | Cross axis alignment               | `stretch`, `center`, `flex-start`, `flex-end`, `baseline` |
| `flex-wrap`       | Wrapping behavior                  | `nowrap`, `wrap`, `wrap-reverse`                          |
| `align-content`   | Multi-line spacing (requires wrap) | `stretch`, `center`, `space-between`                      |
| `gap`             | Spacing between items              | Any length value (px, rem, em)                            |

**Remember:**

- `justify-content` = main axis
- `align-items` = cross axis (single line)
- `align-content` = cross axis (multiple lines, requires wrap)
- `gap` replaces item margins for cleaner code

---

## **Flex Item Properties 🎁**

These properties are applied to **individual flex items** (the children), not the container. They control how a specific item behaves within the flex container.

**Remember:** These properties only work on elements that are **direct children** of a flex container.

---

### **flex-grow 📈**

Controls how much an item **grows** relative to other items when there's **extra space** available.

**Syntax:**

```css
.item {
  flex-grow: 0; /* default - doesn't grow */
}
```

**What it does:**

- When there's leftover space in the container, `flex-grow` determines how much of that space each item gets
- It's a **proportion**, not a fixed size
- Default is `0` (items don't grow)

---

#### **How flex-grow Works**

Think of `flex-grow` as "appetite for space."

**Example with three items:**

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

**Scenario 1: No growth (default)**

```css
.container {
  display: flex;
  width: 600px;
}

.item {
  width: 100px;
  flex-grow: 0; /* default */
}
```

**Result:**

```
Container: 600px
Items: 100px each = 300px total
Extra space: 300px (unused)

┌────────────────────────────────┐
│[ 1  ][ 2  ][ 3  ]              │ ← 300px empty space
└────────────────────────────────┘
```

Items stay at their base size. Extra space is not used.

---

**Scenario 2: All items grow equally**

```css
.item {
  width: 100px;
  flex-grow: 1; /* All items have same grow factor */
}
```

**Result:**

```
Container: 600px
Items base: 100px each = 300px
Extra space: 300px
Grow factor: 1 for each (3 total)

Each item gets: 300px ÷ 3 = 100px extra

Final sizes: 200px each (100px base + 100px extra)

┌───────────────────────────┐
│[   1   ][   2   ][   3   ]│ ← Items fill space equally
└───────────────────────────┘
```

All items grow equally to fill the container.

---

**Scenario 3: Different grow factors**

```css
.item {
  width: 100px;
}

.item:nth-child(1) {
  flex-grow: 1;
}
.item:nth-child(2) {
  flex-grow: 2;
} /* Grows twice as much */
.item:nth-child(3) {
  flex-grow: 1;
}
```

**Result:**

```
Container: 600px
Items base: 100px each = 300px
Extra space: 300px
Total grow factor: 1 + 2 + 1 = 4

Item 1 gets: (1/4) × 300px = 75px extra → 175px total
Item 2 gets: (2/4) × 300px = 150px extra → 250px total
Item 3 gets: (1/4) × 300px = 75px extra → 175px total

┌──────────────────────────┐
│[  1  ][    2     ][  3  ]│ ← Item 2 is bigger
└──────────────────────────┘
```

Item 2 grows twice as much as items 1 and 3.

---

#### **Common flex-grow Values**

```css
flex-grow: 0; /* Default - doesn't grow */
flex-grow: 1; /* Grows to fill space equally with other items */
flex-grow: 2; /* Grows twice as much as items with flex-grow: 1 */
```

**Use case:**

```html
<div class="navbar">
  <div class="logo">Logo</div>
  <div class="spacer"></div>
  <nav class="menu">Menu items</nav>
</div>
```

```css
.navbar {
  display: flex;
}

.logo {
  flex-grow: 0; /* Fixed size */
}

.spacer {
  flex-grow: 1; /* Takes all extra space */
}

.menu {
  flex-grow: 0; /* Fixed size */
}
```

**Result:**

```
┌────────────────────────────────┐
│[Logo]          [Menu items]    │ ← Spacer pushes menu to right
└────────────────────────────────┘
```

The spacer grows to fill all available space, pushing the menu to the right.

---

### **flex-shrink 📉**

Controls how much an item **shrinks** relative to other items when there's **not enough space**.

**Syntax:**

```css
.item {
  flex-shrink: 1; /* default - can shrink */
}
```

**What it does:**

- When items are too big for the container, `flex-shrink` determines how much each item shrinks
- It's a **proportion**, like `flex-grow`
- Default is `1` (items can shrink)

---

#### **How flex-shrink Works**

Think of `flex-shrink` as "willingness to get smaller."

**Example:**

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

**Scenario 1: All items shrink equally (default)**

```css
.container {
  display: flex;
  width: 400px;
}

.item {
  width: 200px;
  flex-shrink: 1; /* default */
}
```

**Result:**

```
Container: 400px
Items want: 200px each = 600px total
Overflow: 200px (need to shrink)

Each item shrinks equally: 200px - 66.67px ≈ 133px

┌───────────────────┐
│[ 1  ][ 2  ][ 3  ] │ ← Items shrunk to fit
└───────────────────┘
```

All items shrink equally to fit the container.

---

**Scenario 2: Prevent one item from shrinking**

```css
.item {
  width: 200px;
}

.item:nth-child(1) {
  flex-shrink: 0;
} /* Won't shrink */
.item:nth-child(2) {
  flex-shrink: 1;
}
.item:nth-child(3) {
  flex-shrink: 1;
}
```

**Result:**

```
Container: 400px
Item 1: 200px (fixed, won't shrink)
Items 2 & 3: Share remaining 200px

┌───────────────────┐
│[   1   ][ 2 ][ 3 ]│ ← Item 1 keeps full size
└───────────────────┘
```

Item 1 stays at 200px. Items 2 and 3 shrink to fit the remaining space.

---

**Scenario 3: Different shrink factors**

```css
.item {
  width: 200px;
}

.item:nth-child(1) {
  flex-shrink: 1;
}
.item:nth-child(2) {
  flex-shrink: 3;
} /* Shrinks 3x more */
.item:nth-child(3) {
  flex-shrink: 1;
}
```

**Result:**

Item 2 shrinks three times as much as items 1 and 3.

```
┌────────────────────────────────┐
│[  1  ][2][  3  ]               │ ← Item 2 shrunk the most
└────────────────────────────────┘
```

---

#### **Common flex-shrink Values**

```css
flex-shrink: 0; /* Never shrinks - stays at base size */
flex-shrink: 1; /* Default - shrinks normally */
flex-shrink: 2; /* Shrinks twice as much as items with flex-shrink: 1 */
```

**Use case: Preventing text truncation**

```css
.container {
  display: flex;
  width: 400px;
}

.label {
  flex-shrink: 0; /* Label text won't truncate */
  white-space: nowrap;
}

.input {
  flex-shrink: 1; /* Input can shrink */
  min-width: 100px; /* But not below 100px */
}
```

This ensures the label text stays readable even on narrow screens.

---

### **flex-basis 📏**

Sets the **initial size** of a flex item **before** growing or shrinking.

**Syntax:**

```css
.item {
  flex-basis: auto; /* default - uses width/height */
}
```

**What it does:**

- Defines the base size of an item before `flex-grow` or `flex-shrink` apply
- Can be a length (`200px`, `20%`, `10rem`) or `auto`
- Takes priority over `width` (for row) or `height` (for column)

---

#### **flex-basis vs width**

**Key difference:**

- `width`: Fixed size (or max-content/min-content)
- `flex-basis`: Starting point for flexbox calculations

**Example:**

```css
.item {
  width: 200px;
  flex-basis: 300px; /* flex-basis wins */
  flex-grow: 0;
  flex-shrink: 0;
}
```

**Result:** Item is 300px wide, not 200px. `flex-basis` overrides `width`.

---

#### **flex-basis: auto**

```css
.item {
  flex-basis: auto; /* default */
  width: 200px;
}
```

**What happens:**

- `flex-basis: auto` means "use the `width` property"
- If no `width` is set, use the content's natural size

**Visual:**

```html
<div class="item">Short</div>
<div class="item">Much longer content here</div>
```

```css
.item {
  flex-basis: auto; /* Uses content size */
}
```

**Result:**

```
┌─────────────────────────────────┐
│[Short][Much longer content here]│ ← Items sized by content
└─────────────────────────────────┘
```

---

#### **flex-basis: 0**

```css
.item {
  flex-basis: 0;
  flex-grow: 1;
}
```

**What happens:**

- Item starts at 0 width
- Then grows to fill available space
- Ignores content size completely

**Use case: Equal-width items regardless of content**

```html
<div class="item">Short</div>
<div class="item">Much longer content</div>
<div class="item">Medium</div>
```

```css
.item {
  flex-basis: 0;
  flex-grow: 1;
}
```

**Result:**

```
┌─────────────────────────────────────┐
│┌──────────┐┌──────────┐┌──────────┐ |
|| Short    ||Much long-||Medium    | │ ← All items equal width
||          ||er content||          | │
|└──────────┘└──────────┘└──────────┘ |
└─────────────────────────────────────┘
```

All items are the same width, regardless of content.

---

#### **flex-basis: percentage**

```css
.item {
  flex-basis: 33.333%; /* 1/3 of container */
}
```

**What happens:**

Item takes up 33.333% of the container's width (for row) or height (for column).

**Use case: Three equal columns**

```css
.column {
  flex-basis: 33.333%;
  flex-grow: 0;
  flex-shrink: 0;
}
```

---

### **flex (Shorthand) ⚡**

The `flex` property is a **shorthand** for `flex-grow`, `flex-shrink`, and `flex-basis`.

**Syntax:**

```css
.item {
  flex: <grow> <shrink> <basis>;
}
```

**Common patterns:**

```css
/* One value = flex-grow */
flex: 1;
/* Expands to: flex-grow: 1; flex-shrink: 1; flex-basis: 0; */

/* Two values = grow and basis */
flex: 1 200px;
/* Expands to: flex-grow: 1; flex-shrink: 1; flex-basis: 200px; */

/* Three values = grow, shrink, basis */
flex: 1 1 200px;
/* flex-grow: 1; flex-shrink: 1; flex-basis: 200px; */
```

---

#### **Common flex Shorthand Values**

**1. flex: 1**

```css
.item {
  flex: 1;
}
/* Same as: flex-grow: 1; flex-shrink: 1; flex-basis: 0; */
```

**What it does:** Item grows to fill available space, ignoring content size.

**Use case:** Equal-width items.

---

**2. flex: auto**

```css
.item {
  flex: auto;
}
/* Same as: flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
```

**What it does:** Item grows to fill space, starting from its content size.

**Use case:** Items that grow but respect their content width.

---

**3. flex: none**

```css
.item {
  flex: none;
}
/* Same as: flex-grow: 0; flex-shrink: 0; flex-basis: auto; */
```

**What it does:** Item doesn't grow or shrink. Stays at its natural size.

**Use case:** Fixed-size items (like a logo).

---

**4. flex: 0 1 auto (default)**

```css
.item {
  /* This is the default if you don't set flex */
}
/* flex-grow: 0; flex-shrink: 1; flex-basis: auto; */
```

**What it does:** Item doesn't grow, can shrink, uses content size.

---

#### **Practical Examples**

**Example 1: Three equal columns**

```css
.column {
  flex: 1; /* Each column takes equal space */
}
```

---

**Example 2: Sidebar + Content**

```css
.sidebar {
  flex: 0 0 250px; /* Fixed 250px width, doesn't grow or shrink */
}

.content {
  flex: 1; /* Fills remaining space */
}
```

**Result:**

```
┌────────────────────────────────┐
│[Sidebar][    Content area    ] │
│ 250px  │  (fills remaining)    │
└────────────────────────────────┘
```

---

**Example 3: Logo + Spacer + Nav**

```css
.logo {
  flex: none; /* Fixed size */
}

.spacer {
  flex: 1; /* Fills space */
}

.nav {
  flex: none; /* Fixed size */
}
```

**Result:**

```
┌────────────────────────────────┐
│[Logo]            [Nav]         │
└────────────────────────────────┘
```

---

### **align-self 🎯**

Overrides `align-items` for a **specific item** on the cross axis.

**Syntax:**

```css
.item {
  align-self: auto | stretch | flex-start | flex-end | center | baseline;
}
```

**What it does:**

- Container's `align-items` sets the default alignment for ALL items
- Individual item's `align-self` overrides that default for JUST that item

---

#### **Example: Mixed Alignment**

```html
<div class="container">
  <div class="item">1</div>
  <div class="item special">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex;
  align-items: flex-start; /* All items align to top */
  height: 200px;
  border: 2px solid #333;
}

.item {
  width: 100px;
  height: 60px;
  background-color: #3498db;
}

.special {
  align-self: flex-end; /* This item aligns to bottom */
  background-color: #e74c3c;
}
```

**Result:**

```
┌───────────────────┐
│[1]             [3]│ ← Items 1 and 3 at top
│                   │
│                   │
│        [2]        │ ← Item 2 at bottom
└───────────────────┘
```

Items 1 and 3 follow `align-items: flex-start`. Item 2 overrides with `align-self: flex-end`.

---

#### **align-self Values**

All the same values as `align-items`:

```css
align-self: auto; /* Default - uses container's align-items */
align-self: stretch; /* Stretch to fill cross axis */
align-self: flex-start; /* Align to start of cross axis */
align-self: flex-end; /* Align to end of cross axis */
align-self: center; /* Center on cross axis */
align-self: baseline; /* Align to text baseline */
```

---

#### **Use Case: Featured Card**

```html
<div class="card">1</div>
<div class="card featured-card">Featured Card</div>
<div class="card">3</div>
```

```css
.card-grid {
  display: flex;
  align-items: flex-start; /* Cards align to top */
  gap: 20px;
}

.card {
  flex: 1;
}

.featured-card {
  align-self: stretch; /* Featured card fills full height */
  background-color: gold;
}
```

**Result:**

```
┌───────────────────────────────────────┐
│┌───────────┐┌───────────┐┌───────────┐│
││     1     ││Featured   ││     3     ││
│└───────────┘│ Card      │└───────────┘│
│             │(stretched)│             │
│             └───────────┘             │
└───────────────────────────────────────┘
```

---

### **order 🔢**

Changes the **visual order** of flex items without changing the HTML.

**Syntax:**

```css
.item {
  order: 0; /* default */
}
```

**What it does:**

- Items are displayed in order from lowest to highest `order` value
- Default is `0`
- Can be negative

---

#### **How order Works**

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</div>
```

**Default (no order set):**

```
[1] [2] [3] [4]
```

---

**With order:**

```css
.item:nth-child(1) {
  order: 2;
}
.item:nth-child(2) {
  order: 1;
}
.item:nth-child(3) {
  order: 4;
}
.item:nth-child(4) {
  order: 3;
}
```

**Result:**

```
[2] [1] [4] [3]
```

Items display in order: 2,1,4,3 based on their `order` values.

---

#### **Practical Use Case: Responsive Reordering**

**Desktop layout:**

```
┌────────────────────────────┐
│[Logo] [Nav] [Search] [User]│
└────────────────────────────┘
```

**Mobile layout (reorder without changing HTML):**

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }

  .logo {
    order: 1;
  } /* First */
  .search {
    order: 2;
  } /* Second */
  .nav {
    order: 3;
  } /* Third */
  .user {
    order: 4;
  } /* Fourth */
}
```

**Mobile result:**

```
┌──────┐
│ Logo │
├──────┤
│Search│
├──────┤
│ Nav  │
├──────┤
│ User │
└──────┘
```

The visual order changed without touching the HTML!

---

#### **Important: Accessibility Warning ⚠️**

**The `order` property only changes VISUAL order, not source order.**

This means:

- Screen readers read the HTML order, not the visual order
- Keyboard navigation follows HTML order, not visual order
- Copy-paste follows HTML order

**Best practice:** Use `order` sparingly, and only when the HTML order makes sense semantically. Don't rely on `order` to fix poor HTML structure.

---

### **Combining Item Properties 🎨**

Let's see how these properties work together:

**Example: Flexible Dashboard Layout**

```html
<div class="dashboard">
  <aside class="sidebar">Sidebar</aside>
  <main class="content">Main Content</main>
  <aside class="ads">Ads</aside>
</div>
```

```css
.dashboard {
  display: flex;
  gap: 20px;
  min-height: 100vh;
}

.sidebar {
  flex: 0 0 250px; /* Fixed 250px, doesn't grow or shrink */
  order: 1;
}

.content {
  flex: 1 1 auto; /* Grows to fill space, can shrink */
  order: 2;
}

.ads {
  flex: 0 0 200px; /* Fixed 200px */
  order: 3;
}

/* Mobile */
@media (max-width: 768px) {
  .dashboard {
    flex-direction: column;
  }

  .content {
    order: 1;
  } /* Main content first on mobile */
  .sidebar {
    order: 2;
  }
  .ads {
    order: 3;
    flex: 0 0 auto;
  } /* Auto height on mobile */
}
```

**Desktop:**

```
┌────────────────────────────────┐
│[Sidebar][  Content   ][ Ads ]  │
│ 250px  │  (flexible) │ 200px   │
└────────────────────────────────┘
```

**Mobile:**

```
┌──────────┐
│ Content  │ ← Reordered: content first
├──────────┤
│ Sidebar  │
├──────────┤
│   Ads    │
└──────────┘
```

---

### **Summary 📋**

**Item properties:**

| Property      | Controls                          | Default    | Common Values                                 |
| ------------- | --------------------------------- | ---------- | --------------------------------------------- |
| `flex-grow`   | How much item grows               | `0`        | `0` (no growth), `1` (grow equally)           |
| `flex-shrink` | How much item shrinks             | `1`        | `0` (no shrink), `1` (shrink normally)        |
| `flex-basis`  | Initial size before grow/shrink   | `auto`     | `auto`, `0`, length values                    |
| `flex`        | Shorthand for grow, shrink, basis | `0 1 auto` | `1`, `auto`, `none`, custom                   |
| `align-self`  | Individual cross-axis alignment   | `auto`     | `stretch`, `center`, `flex-start`, `flex-end` |
| `order`       | Visual order                      | `0`        | Any integer (negative allowed)                |

**Common patterns:**

```css
flex: 1; /* Grow to fill, equal width */
flex: auto; /* Grow to fill, content-based width */
flex: none; /* Fixed size, no grow/shrink */
flex: 0 0 200px; /* Fixed 200px width */
flex: 1 1 300px; /* Grow/shrink from 300px base */
```

**Remember:**

- `flex-grow` = "How hungry am I for extra space?"
- `flex-shrink` = "How willing am I to get smaller?"
- `flex-basis` = "What's my starting size?"
- `flex` shorthand is usually cleaner than individual properties
- `align-self` overrides `align-items` for one item
- `order` changes visual order, not HTML order

---

## **Common Use Cases & Patterns 🎨**

Now that you understand how flexbox works, let's look at real-world patterns you'll use constantly. These are battle-tested solutions to common layout challenges.

---

### **Pattern 1: Horizontal Navigation Bar 🧭**

**Goal:** Logo on the left, navigation links on the right.

```html
<nav class="navbar">
  <div class="logo">MyBrand</div>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

```css
.navbar {
  display: flex;
  justify-content: space-between; /* Logo left, links right */
  align-items: center; /* Vertically centered */
  padding: 1rem 2rem;
  background-color: #2c3e50;
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
  color: white;
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-links a {
  color: white;
  text-decoration: none;
}
```

**Result:**

```
┌───────────────────────────────────────────┐
│ MyBrand        Home About Services Contact│
└───────────────────────────────────────────┘
```

**Why this works:**

- `justify-content: space-between` pushes logo to far left, links to far right
- Nested flex: `.nav-links` is also a flex container for the list items
- `gap` on `.nav-links` creates spacing between menu items

---

### **Pattern 2: Centered Modal Dialog 🪟**

**Goal:** A modal perfectly centered on the screen, both horizontally and vertically.

```html
<div class="modal-overlay">
  <div class="modal">
    <h2>Confirm Action</h2>
    <p>Are you sure you want to continue?</p>
    <div class="modal-actions">
      <button class="btn-cancel">Cancel</button>
      <button class="btn-confirm">Confirm</button>
    </div>
  </div>
</div>
```

```css
.modal-overlay {
  display: flex;
  justify-content: center; /* Center horizontally */
  align-items: center; /* Center vertically */
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
}

.modal {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  max-width: 500px;
  width: 90%;
}

.modal-actions {
  display: flex;
  justify-content: flex-end; /* Buttons aligned to right */
  gap: 1rem;
  margin-top: 1.5rem;
}
```

**Result:**

```
┌─────────────────────────────┐
│                             │
│     ┌─────────────────┐     │
│     │ Confirm  Action │     │
│     │                 │     │
│     │                 │     │
│     │ Are you sure?   │     │ ← Modal centered
│     │                 │     │
│     │ [Cancel][OK]    │     │
│     └─────────────────┘     │
│                             │
└─────────────────────────────┘
```

**Why this works:**

- Overlay uses flexbox to center its child (the modal)
- `justify-content: center` + `align-items: center` = perfect centering
- Modal actions use flexbox to align buttons to the right

---

### **Pattern 3: Equal-Height Card Grid 📇**

**Goal:** Cards that wrap to multiple rows, all cards in a row have equal height.

```html
<div class="card-grid">
  <div class="card">
    <h3>Card 1</h3>
    <p>Short content.</p>
  </div>
  <div class="card">
    <h3>Card 2</h3>
    <p>
      This card has much longer content that spans multiple lines and makes it
      taller than the other cards.
    </p>
  </div>
  <div class="card">
    <h3>Card 3</h3>
    <p>Medium content here.</p>
  </div>
  <div class="card">
    <h3>Card 4</h3>
    <p>Another card.</p>
  </div>
</div>
```

```css
.card-grid {
  display: flex;
  flex-wrap: wrap; /* Cards wrap to new rows */
  gap: 20px;
}

.card {
  flex: 1 1 250px; /* Grow, shrink, base 250px */
  min-width: 250px; /* Minimum card width */
  padding: 1.5rem;
  background-color: white;
  border: 1px solid #ddd;
  border-radius: 8px;
}
```

**Result (wide screen):**

```
┌──────────┐┌─────────────┐┌──────────┐
│ Card 1   ││ Card 2      ││ Card 3   │
│          ││ This card   ││          │
│ Short    ││ has much    ││ Medium   │
│ content. ││ longer...   ││ content. │
└──────────┘└─────────────┘└──────────┘
┌──────────┐
│ Card 4   │
│          │
│ Another  │
│ card.    │
└──────────┘
```

**Result (narrow screen):**

```
┌──────────┐
│ Card 1   │
│ Short    │
└──────────┘
┌─────────────┐
│ Card 2      │
│ This card   │
│ has much... │
└─────────────┘
┌──────────┐
│ Card 3   │
│ Medium   │
└──────────┘
┌──────────┐
│ Card 4   │
│ Another  │
└──────────┘
```

**Why this works:**

- `flex-wrap: wrap` allows cards to wrap to new rows
- `flex: 1 1 250px` means cards grow to fill space but have a 250px minimum
- Cards automatically stack on narrow screens
- All cards in the same row have equal height (flexbox default)

---

### **Pattern 4: Sidebar + Content Layout 📄**

**Goal:** Fixed-width sidebar, content area fills remaining space.

```html
<div class="layout">
  <aside class="sidebar">
    <nav>
      <a href="#dashboard">Dashboard</a>
      <a href="#profile">Profile</a>
      <a href="#settings">Settings</a>
    </nav>
  </aside>
  <main class="content">
    <h1>Main Content</h1>
    <p>Content goes here...</p>
  </main>
</div>
```

```css
.layout {
  display: flex;
  min-height: 100vh;
}

.sidebar {
  flex: 0 0 250px; /* Fixed 250px, doesn't grow or shrink */
  background-color: #34495e;
  padding: 2rem 1rem;
}

.sidebar nav {
  display: flex;
  flex-direction: column; /* Stack links vertically */
  gap: 1rem;
}

.sidebar a {
  color: white;
  text-decoration: none;
  padding: 0.75rem;
  border-radius: 4px;
}

.content {
  flex: 1; /* Fills remaining space */
  padding: 2rem;
}
```

**Result:**

```
┌──────────┬─────────────────────────┐
│Dashboard │ Main Content            │
│Profile   │                         │
│Settings  │ Content goes here...    │
│          │                         │
│          │                         │
│          │                         │
│  (250px) │    (fills remaining)    │
└──────────┴─────────────────────────┘
```

**Why this works:**

- `flex: 0 0 250px` on sidebar = fixed width
- `flex: 1` on content = grows to fill remaining space
- Sidebar nav uses `flex-direction: column` to stack links vertically

---

### **Pattern 5: Sticky Footer ⬇️**

**Goal:** Footer sticks to bottom of viewport when content is short, but stays at bottom of content when content is long.

```html
<body>
  <div class="page-container">
    <header class="header">Header</header>
    <main class="main">
      <p>Page content...</p>
    </main>
    <footer class="footer">Footer</footer>
  </div>
</body>
```

```css
html,
body {
  height: 100%;
  margin: 0;
}

.page-container {
  display: flex;
  flex-direction: column; /* Stack header, main, footer vertically */
  min-height: 100%;
}

.header {
  flex: 0 0 auto; /* Natural height, doesn't grow */
  background-color: #2c3e50;
  padding: 1rem 2rem;
  color: white;
}

.main {
  flex: 1; /* Grows to fill available space */
  padding: 2rem;
}

.footer {
  flex: 0 0 auto; /* Natural height, doesn't grow */
  background-color: #34495e;
  padding: 1rem 2rem;
  color: white;
  text-align: center;
}
```

**Result (short content):**

```
┌────────────────┐
│ Header         │
├────────────────┤
│ Page content...│
│                │
│                │ ← Main expands
│                │
│                │
├────────────────┤
│ Footer         │ ← Stuck to bottom
└────────────────┘
```

**Result (long content):**

```
┌────────────────┐
│ Header         │
├────────────────┤
│ Page content...│
│                │
│ (lots of       │
│  content       │
│  here)         │
│                │
├────────────────┤
│ Footer         │ ← After content
└────────────────┘
```

**Why this works:**

- Container uses `flex-direction: column` to stack items vertically
- `min-height: 100%` ensures container is at least viewport height
- `flex: 1` on main = grows to push footer to bottom when content is short

---

### **Pattern 6: Form Layout with Labels and Inputs 📝**

**Goal:** Labels on the left, inputs on the right, aligned nicely.

```html
<form class="form">
  <div class="form-field">
    <label for="name">Name:</label>
    <input type="text" id="name" />
  </div>
  <div class="form-field">
    <label for="email">Email:</label>
    <input type="email" id="email" />
  </div>
  <div class="form-field">
    <label for="message">Message:</label>
    <textarea id="message" rows="4"></textarea>
  </div>
  <div class="form-field">
    <button type="submit">Submit</button>
  </div>
</form>
```

```css
.form {
  max-width: 500px;
}

.form-field {
  display: flex;
  gap: 1rem;
  margin-bottom: 1rem;
  align-items: flex-start; /* Align labels to top (for textarea) */
}

.form-field label {
  flex: 0 0 100px; /* Fixed 100px width for labels */
  padding-top: 0.5rem; /* Align with input text */
}

.form-field input,
.form-field textarea {
  flex: 1; /* Inputs fill remaining space */
  padding: 0.5rem;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.form-field button {
  margin-left: 116px; /* 100px label + 16px gap */
}
```

**Result:**

```
┌──────────────────────────┐
│ Name:    [input box    ] │
│ Email:   [input box    ] │
│ Message: [textarea     ] │
│          [             ] │
│          [Submit button] │
└──────────────────────────┘
```

**Why this works:**

- Each form field is a flex container with label and input
- Labels have fixed width (`flex: 0 0 100px`)
- Inputs grow to fill space (`flex: 1`)
- `align-items: flex-start` keeps labels aligned to top for textarea

---

### **Pattern 7: Media Object (Image + Text) 🖼️**

**Goal:** Image on the left, text on the right, responsive.

```html
<div class="media-object">
  <img src="avatar.jpg" alt="User avatar" class="media-image" />
  <div class="media-content">
    <h3>John Doe</h3>
    <p>Software developer passionate about web technologies and open source.</p>
  </div>
</div>
```

```css
.media-object {
  display: flex;
  gap: 1.5rem;
  align-items: flex-start; /* Align to top */
}

.media-image {
  flex: 0 0 100px; /* Fixed 100px, doesn't grow or shrink */
  width: 100px;
  height: 100px;
  border-radius: 50%;
  object-fit: cover;
}

.media-content {
  flex: 1; /* Fills remaining space */
}

.media-content h3 {
  margin: 0 0 0.5rem 0;
}

.media-content p {
  margin: 0;
}
```

**Result:**

```
┌──────────────────────────────┐
│ ┌────┐  John Doe             │
│ │Img │  Software developer   │
│ │    │  passionate about...  │
│ └────┘                       │
└──────────────────────────────┘
```

**Why this works:**

- Image has fixed size (`flex: 0 0 100px`)
- Content grows to fill space (`flex: 1`)
- `gap` creates spacing between image and text

---

### **Pattern 8: Button Group 🔘**

**Goal:** Buttons aligned horizontally with equal spacing.

```html
<div class="button-group">
  <button class="btn">Save</button>
  <button class="btn btn-primary">Submit</button>
  <button class="btn btn-danger">Delete</button>
</div>
```

```css
.button-group {
  display: flex;
  gap: 1rem;
  justify-content: flex-end; /* Align buttons to right */
}

.btn {
  padding: 0.5rem 1.5rem;
  border: 1px solid #ddd;
  background-color: white;
  border-radius: 4px;
  cursor: pointer;
}

.btn-primary {
  background-color: #3498db;
  color: white;
  border-color: #3498db;
}

.btn-danger {
  background-color: #e74c3c;
  color: white;
  border-color: #e74c3c;
}
```

**Result:**

```
┌────────────────────────────────┐
│        [Save] [Submit] [Delete]│
└────────────────────────────────┘
```

**Why this works:**

- `gap` creates consistent spacing between buttons
- `justify-content: flex-end` aligns buttons to the right
- No need for margins on individual buttons

---

### **Pattern 9: Holy Grail Layout 🏛️**

**Goal:** Classic layout with header, footer, sidebar, content, and ads.

```html
<div class="holy-grail">
  <header class="header">Header</header>
  <div class="middle">
    <aside class="sidebar">Sidebar</aside>
    <main class="content">Main Content</main>
    <aside class="ads">Ads</aside>
  </div>
  <footer class="footer">Footer</footer>
</div>
```

```css
.holy-grail {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.header,
.footer {
  flex: 0 0 auto;
  background-color: #2c3e50;
  color: white;
  padding: 1rem 2rem;
}

.middle {
  display: flex;
  flex: 1; /* Grows to fill space between header and footer */
}

.sidebar {
  flex: 0 0 200px; /* Fixed 200px */
  background-color: #ecf0f1;
  padding: 1rem;
}

.content {
  flex: 1; /* Fills remaining space */
  padding: 2rem;
}

.ads {
  flex: 0 0 150px; /* Fixed 150px */
  background-color: #ecf0f1;
  padding: 1rem;
}

/* Responsive */
@media (max-width: 768px) {
  .middle {
    flex-direction: column;
  }

  .sidebar,
  .ads {
    flex: 0 0 auto;
  }
}
```

**Result (desktop):**

```
┌─────────────────────────────────┐
│ Header                          │
├───────┬─────────────────┬───────┤
│Sidebar│ Main Content    │  Ads  │
│       │                 │       │
│(200px)│  (flexible)     │(150px)│
├───────┴─────────────────┴───────┤
│ Footer                          │
└─────────────────────────────────┘
```

**Result (mobile):**

```
┌──────────┐
│ Header   │
├──────────┤
│ Sidebar  │
├──────────┤
│ Content  │
├──────────┤
│   Ads    │
├──────────┤
│ Footer   │
└──────────┘
```

**Why this works:**

- Outer container stacks header, middle, footer vertically
- Middle section uses nested flexbox for sidebar, content, ads
- Media query changes middle from row to column on mobile

---

### **Summary 📋**

**Common patterns:**

| Pattern        | Key Properties                                   | Use Case                         |
| -------------- | ------------------------------------------------ | -------------------------------- |
| Navigation     | `justify-content: space-between`                 | Logo left, links right           |
| Centered Modal | `justify-content: center`, `align-items: center` | Perfect centering                |
| Card Grid      | `flex-wrap: wrap`, `flex: 1 1 250px`             | Responsive cards                 |
| Sidebar Layout | Sidebar: `flex: 0 0 250px`, Content: `flex: 1`   | Fixed sidebar + flexible content |
| Sticky Footer  | `flex-direction: column`, Main: `flex: 1`        | Footer at bottom                 |
| Form Layout    | Label: `flex: 0 0 100px`, Input: `flex: 1`       | Aligned form fields              |
| Media Object   | Image: `flex: 0 0 100px`, Text: `flex: 1`        | Image + text side by side        |
| Button Group   | `gap`, `justify-content: flex-end`               | Evenly spaced buttons            |

**Remember:**

- `flex: 1` = "fill available space"
- `flex: 0 0 <size>` = "fixed size"
- Nested flexbox is powerful and common
- Combine with media queries for responsive designs

---

## **Quick Reference 📚**

---

### **Container Properties (Parent) 📦**

Properties applied to the element with `display: flex`.

| Property          | Values                                                                                         | Default      | Description                           |
| ----------------- | ---------------------------------------------------------------------------------------------- | ------------ | ------------------------------------- |
| `display`         | `flex`, `inline-flex`                                                                          | n/a          | Activates flexbox                     |
| `flex-direction`  | `row`, `row-reverse`, `column`, `column-reverse`                                               | `row`        | Sets main axis direction              |
| `flex-wrap`       | `nowrap`, `wrap`, `wrap-reverse`                                                               | `nowrap`     | Controls wrapping behavior            |
| `justify-content` | `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly`            | `flex-start` | Distributes items on main axis        |
| `align-items`     | `stretch`, `flex-start`, `flex-end`, `center`, `baseline`                                      | `stretch`    | Aligns items on cross axis            |
| `align-content`   | `stretch`, `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly` | `stretch`    | Aligns rows/columns (multi-line only) |
| `gap`             | Any length value                                                                               | `0`          | Space between items                   |

---

### **Item Properties (Children) 🎁**

Properties applied to direct children of a flex container.

| Property      | Values                                                            | Default    | Description                              |
| ------------- | ----------------------------------------------------------------- | ---------- | ---------------------------------------- |
| `flex-grow`   | Number (0+)                                                       | `0`        | How much item grows relative to others   |
| `flex-shrink` | Number (0+)                                                       | `1`        | How much item shrinks relative to others |
| `flex-basis`  | Length, `auto`, `0`                                               | `auto`     | Initial size before growing/shrinking    |
| `flex`        | Shorthand                                                         | `0 1 auto` | Shorthand for grow, shrink, basis        |
| `align-self`  | `auto`, `stretch`, `flex-start`, `flex-end`, `center`, `baseline` | `auto`     | Overrides align-items for this item      |
| `order`       | Integer                                                           | `0`        | Changes visual order                     |

---

### **Axis Reference 🧭**

| flex-direction   | Main Axis    | Cross Axis   | justify-content controls | align-items controls |
| ---------------- | ------------ | ------------ | ------------------------ | -------------------- |
| `row`            | Horizontal → | Vertical ↓   | Horizontal spacing       | Vertical alignment   |
| `row-reverse`    | Horizontal ← | Vertical ↓   | Horizontal spacing       | Vertical alignment   |
| `column`         | Vertical ↓   | Horizontal → | Vertical spacing         | Horizontal alignment |
| `column-reverse` | Vertical ↑   | Horizontal → | Vertical spacing         | Horizontal alignment |

**Memory trick:**

- `justify-content` = main axis (direction items flow)
- `align-items` = cross axis (perpendicular to flow)

---

### **Common flex Shorthand Values ⚡**

```css
flex: 1;
/* Same as: flex-grow: 1; flex-shrink: 1; flex-basis: 0; */
/* Use: Equal-width items, ignore content size */

flex: auto;
/* Same as: flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
/* Use: Grow to fill, start from content size */

flex: none;
/* Same as: flex-grow: 0; flex-shrink: 0; flex-basis: auto; */
/* Use: Fixed size, no grow/shrink */

flex: 0 0 200px;
/* Same as: flex-grow: 0; flex-shrink: 0; flex-basis: 200px; */
/* Use: Fixed 200px width/height */

flex: 1 1 300px;
/* Same as: flex-grow: 1; flex-shrink: 1; flex-basis: 300px; */
/* Use: Flexible item starting at 300px */
```

---

### **Troubleshooting Checklist ✅**

**Items not appearing in a row:**

- ☐ Is `display: flex` set on the container?
- ☐ Is `flex-direction` set to `column` by mistake?

**Items not wrapping:**

- ☐ Is `flex-wrap: wrap` set?
- ☐ Do items have a `min-width` or fixed width preventing wrap?

**Item not growing to fill space:**

- ☐ Is `flex-grow` set to a value greater than 0?
- ☐ Does item have a `max-width` limiting growth?

**Item not shrinking:**

- ☐ Is `flex-shrink` set to 0?
- ☐ Does item have a `min-width` preventing shrink?

**gap not working:**

- ☐ Is `display: flex` set?
- ☐ Are you using an old browser? (gap supported in all modern browsers)

**align-content not working:**

- ☐ Is `flex-wrap: wrap` enabled?
- ☐ Do items actually wrap to multiple lines?

**justify-content or align-items reversed:**

- ☐ Check which is the main axis (check `flex-direction`)
- ☐ `justify-content` = main axis, `align-items` = cross axis

---

### **Browser Support 🌐**

Flexbox is supported in all modern browsers:

- ✅ Chrome/Edge (all versions)
- ✅ Firefox (all versions)
- ✅ Safari (all versions)
- ✅ Mobile browsers (iOS Safari, Chrome Android)

**Note:** Internet Explorer 11 has partial support with bugs. IE is no longer supported by Microsoft (as of 2022), so flexbox can be used without fallbacks in modern web development.

---

### **Flexbox vs Grid Quick Comparison 🆚**

| Feature          | Flexbox                               | CSS Grid                               |
| ---------------- | ------------------------------------- | -------------------------------------- |
| **Dimensions**   | One-dimensional (row OR column)       | Two-dimensional (rows AND columns)     |
| **Best for**     | Components, navigation, small layouts | Page layouts, complex grids            |
| **Content flow** | Content-first (items control layout)  | Layout-first (grid controls items)     |
| **Wrapping**     | Items wrap to new lines               | Items placed in grid cells             |
| **Use when**     | Distributing items along one axis     | Creating both row and column structure |

**Rule of thumb:** Use flexbox for component-level layouts, Grid for page-level layouts.

---

### **Performance Tips ⚡**

✅ **Good practices:**

- Use `gap` instead of margins for spacing
- Use `flex` shorthand instead of individual properties
- Combine with CSS Grid for optimal layouts

⚠️ **Avoid:**

- Excessive nesting (more than 3-4 levels deep)
- Using flexbox for large-scale page layouts (use Grid instead)
- Animating flex properties (use transforms instead)

---

### **Helpful Resources 🔗**

- **[CSS-Tricks Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/):** Complete visual guide with examples
- **[Flexbox Froggy](https://flexboxfroggy.com/):** Interactive game to learn flexbox
- **[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout):** Complete property reference
- **[Can I Use - Flexbox](https://caniuse.com/flexbox):** Browser compatibility checker

---
