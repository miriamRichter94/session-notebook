# CSS Responsive

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

## **What is Responsive Design & Why It Matters 🌐**

You already visit the same websites from multiple devices without thinking about it. You might check a recipe on your laptop in the morning, pull it up on your phone at the supermarket, and glance at it on a tablet on the couch later. The layout adjusts each time. Text doesn't overflow, buttons don't become impossibly small, content doesn't require horizontal scrolling.

That's responsive design. And the fact that it feels invisible is exactly the point.

---

### **The Problem It Solves**

The web wasn't always like this. In the early days, websites were built for one screen size — desktop monitors — with fixed pixel widths. When smartphones arrived and people started browsing on them, those fixed layouts broke badly. Text became tiny, content spilled off screen, and users had to pinch and zoom just to read anything.

The obvious but terrible solution would be to build separate websites for each device type. One for desktop, one for mobile, maybe one for tablet. Some companies actually did this (you'd land on `m.website.com` on your phone). The maintenance cost was enormous: every update had to be made in multiple places, content could fall out of sync, and new device sizes meant new versions.

**Responsive design is the better solution:** one HTML file, one CSS file, but the layout _adapts_ based on the screen it's being viewed on. The content is identical, only the presentation changes.

---

### **How It Actually Works**

Responsive design is built on three foundations that work together:

**Responsive units**
Instead of defining everything in fixed pixels, you use units that scale relative to the viewport, the parent element, or the font size. Elements grow and shrink naturally as the screen changes.

**Media queries**
CSS rules that only activate when certain conditions are met, like "apply these styles only when the screen is at least 900px wide." This is how you make layout changes at specific screen sizes.

**Flexible layouts**
Using Flexbox and Grid with `fr` units and percentages instead of fixed pixel widths, so your layout flows and adapts rather than breaking.

These three things together give you a layout that works on a 375px phone screen and a 2560px widescreen monitor from a single stylesheet.

---

### **One Stylesheet to Rule Them All**

The phrase sounds dramatic but it's describing something genuinely useful. Instead of maintaining separate codebases for different devices, you write CSS that handles all of them. The browser figures out which rules apply based on the device it's running on.

This means:

- Update your content once, it updates everywhere
- Add a new feature once, it works on all screen sizes
- Fix a bug once, it's fixed on all devices
- No syncing issues between device-specific versions

The trade-off is that your CSS needs to be written thoughtfully from the start. Which is exactly what this guide covers.

---

### **Key Takeaways 📋**

- Responsive design = one codebase that adapts to any screen size
- The alternative (separate sites per device) is too expensive to maintain
- It's built on three foundations: responsive units, media queries, and flexible layouts
- The browser applies whichever CSS rules match the current device conditions

---

## **The Viewport 🖼️**

Before media queries or responsive units make any sense, you need to understand what the viewport actually is, because everything in responsive design is measured against it in some way.

---

### **What the Viewport Is**

The viewport is the rectangular area of the browser window where the webpage is actually visible. Not the whole webpage just the part you can see right now without scrolling.

Think of it like looking through a window at a landscape. The landscape (your webpage) might be enormous, but the window (your viewport) only shows you a portion of it at a time. Scroll down, and you're moving the window to reveal more of the landscape. The landscape itself doesn't change, your view of it does.

```
┌─────────────────────────────────┐
│         Browser Chrome          │  ← Not the viewport
├─────────────────────────────────┤
│                                 │
│                                 │
│         VIEWPORT                │  ← This is the viewport
│    (what you can see now)       │
│                                 │
│                                 │
├ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ - ─ ┤
│                                 │
│    Below the fold               │  ← Part of the page,
│    (not currently visible)      │    not currently visible
│                                 │
└─────────────────────────────────┘
```

---

### **Viewport on Desktop vs Mobile**

The viewport behaves differently depending on the device.

**On desktop:**
The viewport is the content area inside the browser. The space where the webpage actually renders, not including the tabs, address bar, or toolbars. If you resize the browser window, the viewport size changes with it. Open DevTools docked to the side, and it occupies part of that rendering space, making the viewport narrower. This is why DevTools is actually useful for testing responsive layouts. Resizing it lets you see how your layout responds to different widths.

**On mobile:**
Here's where it gets interesting. Mobile browsers have historically had a quirk: to avoid displaying desktop websites as a tiny zoomed-out mess, they would pretend their viewport was much wider than the physical screen — typically around 980px — and then scale the whole page down to fit. This meant websites designed for desktop at least looked legible on mobile, even if everything was tiny.

The problem is that this behaviour completely breaks responsive design. If your phone's screen is 390px wide but the browser is pretending it's 980px wide, your media query that targets screens under 600px will never trigger — the browser thinks it's on a wide screen.

This is exactly why the viewport meta tag exists.

---

### **The Viewport Meta Tag**

```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

This goes in the `<head>` section of your HTML. Without it, media queries will not work correctly on mobile devices. It's not optional.

**What each part does:**

`width=device-width` — tells the browser "stop pretending you're 980px wide, use the actual physical screen width as the viewport width." A phone with a 390px screen now has a 390px viewport, so your CSS sees it correctly.

`initial-scale=1` — sets the initial zoom level to 1 (no zoom). Without this, some browsers would render the page at the correct width but zoomed out, making everything tiny. `initial-scale=1` means "show the page at actual size on load."

**What's actually happening:** You're overriding the mobile browser's default "pretend to be a desktop" behaviour. You're saying "trust your own screen size, display at actual scale, and let my CSS handle the layout."

---

#### **Why This Matters for Responsive Design**

Without the viewport meta tag, this is what happens on mobile:

```
Phone screen: 390px wide
Browser pretends: 980px viewport
Your media query: @media (max-width: 600px)

Result: Query never triggers — browser thinks
        it's 980px wide, so it's not under 600px.
        Your mobile layout never activates.
```

With the viewport meta tag:

```
Phone screen: 390px wide
Browser uses: 390px viewport
Your media query: @media (max-width: 600px)

Result: Query triggers correctly — browser
        knows it's 390px wide.
        Your mobile layout activates. ✅
```

One line of HTML is the difference between responsive design working and not working on mobile.

---

### **Checking the Viewport in DevTools**

You can simulate different viewport sizes directly in your browser without needing a physical device:

1. Open DevTools (F12)
2. Click the **device toolbar icon** (looks like a phone and tablet)
3. Select a device from the dropdown, or drag the handles to resize

This shows you exactly how your layout looks at different viewport widths, and you can watch your media queries trigger in real time as you resize.

---

### **Key Takeaways 📋**

- The viewport is the visible area of the browser window — not the whole page
- On desktop it changes when you resize the browser window
- On mobile, browsers historically faked a wider viewport to display desktop sites — which breaks responsive design
- The viewport meta tag fixes this by telling the browser to use the actual screen width
- `width=device-width` = use real screen width as viewport width
- `initial-scale=1` = display at actual size, no zoom
- Without the meta tag, media queries won't trigger correctly on mobile
- You can simulate viewport sizes in DevTools without a physical device

---

## **Mobile First 📱**

Now that you understand the viewport, we can talk about the philosophy that shapes how you actually write responsive CSS and why the order you write it in matters more than you might expect.

---

### **What Mobile First Means**

Mobile first means you write your base CSS styles targeting the smallest screen size, and then use media queries to add or adjust styles as the screen gets larger.

This might feel counterintuitive. Most people think of desktop as the "full" version of a website and mobile as the stripped-down version. Mobile first flips that thinking: mobile is the foundation, and desktop is the enhancement.

**The approach in practice:**

```css
/* Base styles — written for mobile */
.container {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

/* Adjustments for larger screens */
@media (min-width: 900px) {
  .container {
    flex-direction: row;
  }
}
```

The default `flex-direction: column` stacks content vertically — exactly what you want on a narrow mobile screen. When the viewport hits 900px, it switches to a row layout. Larger screens get the enhancement, smaller screens get the base.

---

### **Mobile First vs Desktop First**

The opposite approach — **desktop first** — writes styles for large screens and uses media queries to scale down:

```css
/* Base styles — written for desktop */
.container {
  display: flex;
  flex-direction: row;
  gap: 16px;
}

/* Adjustments for smaller screens */
@media (max-width: 900px) {
  .container {
    flex-direction: column;
  }
}
```

Both produce the same visual result. So why does mobile first win?

---

### **Why Mobile First Produces Simpler CSS**

**It matches how screens grow, not shrink.**

When you start mobile and scale up, you're mostly _adding_ complexity. More columns, larger fonts, additional layout features. When you start desktop and scale down, you're _removing_ and _overriding_ things. Collapsing columns, hiding elements, reducing sizes. Overriding existing styles creates more code and more opportunity for conflicts.

**It uses `min-width` instead of `max-width` in media queries.**

`min-width` reads as "apply this when the screen is _at least_ this wide" — you're progressively enhancing. `max-width` reads as "apply this when the screen is _at most_ this wide" — you're progressively restricting. The `min-width` direction is easier to reason about because you're always building forward, never backtracking.

```css
/* Mobile first — min-width — adding complexity */
@media (min-width: 600px) {
  /* tablet and up */
}
@media (min-width: 900px) {
  /* desktop and up */
}
@media (min-width: 1200px) {
  /* wide desktop and up */
}

/* Desktop first — max-width — removing complexity */
@media (max-width: 1200px) {
  /* below wide desktop */
}
@media (max-width: 900px) {
  /* below desktop */
}
@media (max-width: 600px) {
  /* below tablet */
}
```

The `min-width` version reads in a natural forward direction. The `max-width` version reads backwards. You're constantly thinking about what to take away.

**It forces you to prioritise content.**

Mobile screens have limited space. Starting there forces you to decide what's actually essential. What does the user need most? What can be secondary? Those are good design questions that desktop-first thinking tends to skip, because there's always room for one more thing on a big screen.

---

### **Mobile First in Design vs Mobile First in Code**

These are two related but separate ideas.

**Mobile first in design** means you start sketching and prototyping the mobile layout before the desktop layout. You figure out the core content hierarchy and user flow on a small screen, then expand outward. This is a UX and design principle.

**Mobile first in code** means your base CSS targets small screens and your media queries use `min-width` to enhance for larger screens. This is a CSS writing principle.

They reinforce each other. If you designed mobile first, writing mobile first CSS feels natural because you already have the mobile layout figured out. If you designed desktop first but want to write mobile first CSS, you have to mentally translate which is why keeping them aligned is easier.

---

### **Key Takeaways 📋**

- Mobile first = write base styles for small screens, enhance for larger screens with `min-width` media queries
- Desktop first = write base styles for large screens, reduce for smaller screens with `max-width` media queries
- Mobile first produces simpler CSS because you're adding complexity, not removing it
- `min-width` queries are easier to reason about than `max-width` queries
- Mobile first in design (UX) and mobile first in code (CSS) are separate concepts that work best together
- Starting mobile forces you to prioritise what content actually matters

---

## **Responsive Units 📏**

You've already met units in the [CSS Fundamentals](css-fundamentals.md) guide — `px`, `rem`, `em`, `%`, `vw`, `vh`, and `calc()`. This section goes deeper. Responsive design depends on using the right units, and understanding _why_ each one behaves the way it does is what separates guessing from knowing.

---

### **Why Units Matter for Responsive Design**

Fixed pixel values don't adapt. A `width: 800px` element is always 800px wide. On a phone, on a desktop, on a widescreen monitor. It doesn't care about the screen it's on.

Responsive units are different. They're defined relative to something else. The viewport, the parent element, or the font size, so they naturally scale as those reference points change.

**The core question for each unit:** what is it relative to?

---

### **Percentage (`%`)**

Percentage values are relative to something else but _what_ they're relative to depends on which property you're using them on. This is the part that trips people up, so let's go through each case properly.

---

#### **Width and Height**

`width: 50%` is relative to the **parent element's width**.

```css
.parent {
  width: 600px;
}

.child {
  width: 50%; /* 50% of 600px = 300px */
}
```

```
┌──────────────────────────────────────────────┐
│              parent (600px)                  │
│  ┌───────────────────────┐                   │
│  │     child (300px)     │                   │
│  │       50% width       │                   │
│  └───────────────────────┘                   │
└──────────────────────────────────────────────┘
```

`height: 50%` is also relative to the **parent element's height** — but only if the parent has an explicitly defined height. If the parent's height is `auto` (which is the default — it grows to fit its content), the browser can't calculate 50% of "whatever it ends up being," so the percentage is ignored entirely.

```css
.parent {
  height: 400px; /* Must be explicitly set */
}

.child {
  height: 50%; /* 50% of 400px = 200px */
}
```

```
┌──────────────┐  ↑
│              │  │ 400px
│   parent     │  │
│              │  │
│  ┌────────┐  │  │ ↑
│  │        │  │  │ │ 200px
│  │ child  │  │  │ │ (50%)
│  │        │  │  │ ↓
│  └────────┘  │  │
│              │  │
└──────────────┘  ↓
```

---

#### **Padding and Margin**

This one is genuinely counterintuitive: **both horizontal and vertical padding percentages are relative to the parent's width** — not the height, even for `padding-top` and `padding-bottom`.

```css
.parent {
  width: 600px;
}

.child {
  padding-top: 10%; /* 10% of parent's WIDTH = 60px */
  padding-left: 10%; /* 10% of parent's WIDTH = 60px */
}
```

**Why?** The CSS specification made this decision to prevent circular dependencies. If `padding-top` were relative to the parent's height, and the parent's height depended on its content (including the child's padding), the browser would get stuck in an infinite loop trying to calculate the layout. Using the parent's width for all four sides breaks that dependency.

This behaviour is most commonly used to create **aspect ratio boxes** — elements that maintain a fixed ratio regardless of their width:

```css
.aspect-ratio-box {
  width: 100%;
  padding-top: 56.25%; /* 9/16 = 0.5625 = 16:9 aspect ratio */
  position: relative;
}
```

Because `padding-top` is relative to the width, as the element gets wider, the padding-top grows proportionally — maintaining the ratio.

---

#### **Font Size**

`font-size: 50%` is relative to the **parent element's font size**.

```css
.parent {
  font-size: 20px;
}

.child {
  font-size: 50%; /* 50% of 20px = 10px */
}
```

```
Parent text: 20px  →  THE QUICK BROWN FOX
Child text:  10px  →  the quick brown fox
```

This compounds when nested — the same problem as `em`. A grandchild at `50%` font-size of a child that's already at `50%` ends up at 25% of the original. This is why `rem` is generally preferred for font sizing.

---

#### **Transform**

`transform: translateX(50%)` is relative to the **element's own dimensions**, not the parent.

```css
.element {
  width: 200px;
  transform: translateX(50%); /* 50% of element's own width = 100px */
}
```

```
Original position:
┌──────────────────────┐
│       element        │
│       (200px)        │
└──────────────────────┘

After translateX(50%):
                    ┌──────────────────────┐
                    │       element        │
                    │  moved 100px right   │
                    └──────────────────────┘
```

This is what makes the centering trick from the Positioning guide work — `translate(-50%, -50%)` moves the element back by exactly half its own width and height, regardless of what size it actually is.

> Transform is covered in depth in the [Animations](css.animations.md) guide.

---

#### **When to Use `%`**

- **Fluid widths** — columns, containers, images that should be proportional to their parent
- **Aspect ratio boxes** — using `padding-top` to maintain a ratio
- **Font scaling** — though `rem` is usually preferable

**The rule to remember:** When in doubt about what a percentage is relative to, check MDN for that specific property. The pattern is consistent within categories (widths relative to parent width, font-size relative to parent font-size) but there's no single universal rule that covers every case.

---

### **Viewport Units (`vw`, `vh`, `vmin`, `vmax`)**

Viewport units are relative to the **viewport dimensions** — the visible browser area covered in [Section 2](#the-viewport-️). Unlike percentages which depend on the parent element, viewport units always refer back to the screen itself, regardless of where an element sits in the page structure.

---

#### **`vw` — Viewport Width**

`1vw` = 1% of the viewport's width. `100vw` = the full viewport width.

```css
.element {
  width: 50vw; /* Always half the viewport width */
}
```

```
Viewport (1000px wide)
┌──────────────────────────────────────────────────┐
│          ┌───────────────────────┐               │
│          │      50vw = 500px     │               │
│          └───────────────────────┘               │
└──────────────────────────────────────────────────┘

Viewport resized (600px wide)
┌──────────────────────────┐
│          ┌────────┐      │
│          │50vw=300│      │
│          └────────┘      │
└──────────────────────────┘
```

The element always takes up exactly half the screen width — not half its parent, half the actual viewport. If the parent is only 200px wide, a `50vw` element will overflow it because it's measured against the screen, not the parent.

**When to use `vw`:**

- Full-width elements that should span the entire screen (`width: 100vw`)
- Typography that scales with screen width (`font-size: 4vw`)
- Elements that need to be proportional to the screen regardless of their container

---

#### **`vh` — Viewport Height**

`1vh` = 1% of the viewport's height. `100vh` = the full viewport height.

```css
.hero {
  height: 100vh; /* Exactly as tall as the visible screen */
}
```

```
┌──────────────────────┐  ↑
│                      │  │
│                      │  │
│    100vh = full      │  │ Viewport
│    visible screen    │  │ height
│                      │  │
│                      │  │
└──────────────────────┘  ↓
 ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
│                      │
│  Below the fold      │  ← Not part of vh
│                      │
```

**When to use `vh`:**

- Full-screen hero sections (`height: 100vh`)
- Sections that should each fill exactly one screen
- Centering content vertically within the full screen height

**A practical caution with `vh` on mobile:** Mobile browsers include the address bar in their viewport height calculation, but the address bar hides as you scroll. This means `100vh` can be taller than what's actually visible, causing an unwanted scrollbar. Newer CSS units `svh` (small viewport height) and `dvh` (dynamic viewport height) exist to fix this, but browser support is still catching up. For now it's a known quirk to be aware of.

---

#### **`vmin` — Viewport Minimum**

`1vmin` = 1% of whichever viewport dimension is **smaller** — width or height.

```css
.element {
  width: 50vmin;
}
```

```
Landscape (1000px × 600px):
  vmin = 1% of 600px (height is smaller)
  50vmin = 300px

Portrait (600px × 1000px):
  vmin = 1% of 600px (width is smaller)
  50vmin = 300px
```

The value stays the same regardless of orientation because it always uses the smaller of the two dimensions.

**When to use `vmin`:** Elements that need to fit within the screen in both orientations — like a square that should always be fully visible whether you're holding your phone portrait or landscape.

```css
.square-icon {
  width: 50vmin;
  height: 50vmin; /* Always fits on screen in any orientation */
}
```

---

#### **`vmax` — Viewport Maximum**

`1vmax` = 1% of whichever viewport dimension is **larger** — width or height.

```css
.element {
  width: 50vmax;
}
```

```
Landscape (1000px × 600px):
  vmax = 1% of 1000px (width is larger)
  50vmax = 500px

Portrait (600px × 1000px):
  vmax = 1% of 1000px (height is larger)
  50vmax = 500px
```

**When to use `vmax`:** Less commonly used. Useful for elements that should always be large relative to the screen, like full-screen overlays or backgrounds that need to cover the entire screen regardless of orientation.

---

#### **Comparing All Four**

```
Viewport: 1000px wide × 600px tall

1vw   = 10px   (1% of width)
1vh   = 6px    (1% of height)
1vmin = 6px    (1% of smaller dimension — height)
1vmax = 10px   (1% of larger dimension — width)
```

| Unit   | Relative to      | Best for                                     |
| ------ | ---------------- | -------------------------------------------- |
| `vw`   | Viewport width   | Full-width layouts, scaling typography       |
| `vh`   | Viewport height  | Full-screen sections, vertical centering     |
| `vmin` | Smaller of vw/vh | Elements that must fit in both orientations  |
| `vmax` | Larger of vw/vh  | Backgrounds, overlays that must always cover |

---

### **`rem` — Root EM**

`rem` is relative to the **root element's font size** — the `<html>` element.

Browsers set a default root font size of `16px`. So by default:

- `1rem` = 16px
- `2rem` = 32px
- `0.5rem` = 8px

```css
h1 {
  font-size: 2rem;
} /* 32px by default */
p {
  font-size: 1rem;
} /* 16px by default */
.card {
  padding: 1.5rem;
} /* 24px by default */
```

**What makes `rem` powerful for responsive design:**

If you change the root font size, everything defined in `rem` scales proportionally:

```css
html {
  font-size: 16px;
} /* Default */

@media (min-width: 1200px) {
  html {
    font-size: 20px;
  } /* Scale everything up for large screens */
}
```

Now every `rem` value across your entire stylesheet gets larger on wide screens — headings, paragraphs, spacing, everything — from one change in one place.

**Question:** _"Why can I even set width and height based on font size?"_

Because font size is a reliable, intentional unit of scale in your design. If your base font is 16px, `1rem` of padding feels proportionate to that text. If you scale the font up for larger screens, the padding scales with it automatically — keeping the visual relationship between text and space consistent. It's not arbitrary: font size is one of the most fundamental measurements in typography and design.

**When to use `rem`:** Typography, spacing (margin, padding, gap), and any measurement that should scale with the overall design system.

---

### **`em` — Relative EM**

`em` is relative to the **current element's font size** (or the parent's font size when used on the `font-size` property itself).

```css
.parent {
  font-size: 20px;
}

.child {
  font-size: 1.5em; /* 1.5 × 20px = 30px */
  padding: 1em; /* 1 × 30px = 30px (relative to child's own font-size) */
}
```

**The compounding problem:**

`em` stacks when nested:

```css
.parent {
  font-size: 16px;
}
.child {
  font-size: 1.5em;
} /* 1.5 × 16px = 24px */
.grandchild {
  font-size: 1.5em;
} /* 1.5 × 24px = 36px — not what you might expect */
```

Each level multiplies the previous one. This is why `rem` is generally preferred for font sizes — it always refers back to the root, so there's no compounding.

**When `em` is actually useful:** Padding and spacing _inside_ a component that should scale with that component's font size. A button's padding defined in `em` will automatically adjust if you change the button's font size:

```css
.button {
  font-size: 1rem;
  padding: 0.5em 1em; /* Scales with button's own font size */
}

.button--large {
  font-size: 1.25rem;
  /* Padding automatically scales up too — no need to redefine it */
}
```

**When to use `em`:** Component-level spacing that should be tied to that component's font size. For everything else, prefer `rem`.

---

### **`calc()`**

`calc()` lets you perform math with CSS units — including mixing different unit types.

```css
.element {
  width: calc(100% - 40px);
  height: calc(100vh - 80px);
  font-size: calc(1rem + 0.5vw);
}
```

**Question:** _"How does `calc()` even really work?"_

The browser evaluates the expression at render time, after it knows the actual values of all the units involved. So `calc(100% - 40px)` is calculated as: "take the parent's full width, then subtract exactly 40px." You can't do this with a single unit. Percentages and pixels can't be combined without `calc()`.

**Supported operators:** `+`, `-`, `*`, `/`

**Important syntax rule:** The `+` and `-` operators **must** have spaces around them, otherwise the browser misreads the expression:

```css
/* ❌ Wrong */
width: calc(100%-40px);

/* ✅ Correct */
width: calc(100% - 40px);
```

`*` and `/` don't require spaces but it's good practice to include them for readability.

**Question:** _"Why is `width: calc(50% - 2em)` half as wide as the parent element minus 2 times the current font size?"_

Breaking it down:

- `50%` = half the parent element's width (percentage of parent width)
- `2em` = 2 times the current element's font size
- `50% - 2em` = take that half-width, then subtract that fixed font-based amount

So if the parent is 800px wide and the element's font size is 16px:

- `50%` = 400px
- `2em` = 32px
- Result = 400 - 32 = **368px**

This is useful for layouts where you want a proportional width but need to account for a fixed element like a border, gap, or icon alongside it.

**A practical example:**

```css
.sidebar {
  width: 250px;
}

.content {
  width: calc(100% - 250px - 32px); /* Full width minus sidebar minus gap */
}
```

Without `calc()`, this calculation would be impossible in pure CSS because you can't subtract a fixed pixel value from a percentage directly.

---

### **Choosing the Right Unit**

| What you're sizing               | Recommended unit | Why                                                       |
| -------------------------------- | ---------------- | --------------------------------------------------------- |
| Font sizes                       | `rem`            | Scales with root, no compounding                          |
| Component spacing (padding, gap) | `rem` or `em`    | `rem` for consistency, `em` to tie to component font size |
| Fluid widths                     | `%`              | Proportional to parent                                    |
| Full-screen sections             | `vh` / `vw`      | Proportional to viewport                                  |
| Borders                          | `px`             | Should never scale                                        |
| Mixed calculations               | `calc()`         | When you need to combine units                            |

---

### **Key Takeaways 📋**

- Responsive units scale relative to something — viewport, parent, or font size — unlike `px` which is always fixed
- `%` is relative to the parent's corresponding property — but which property it's relative to depends on what you're setting
- `vw` / `vh` are relative to the viewport dimensions — elements sized this way scale with the screen regardless of their container
- `rem` is relative to the root font size — change the root, everything in `rem` scales with it
- `em` is relative to the current element's font size — useful for component-level spacing, but compounds when nested
- `calc()` evaluates math at render time and lets you mix unit types — spaces around `+` and `-` are required
- Use `rem` for most typography and spacing, `%` for fluid widths, `vw`/`vh` for viewport-based sizing

---

## **Media Queries 🔍**

You've now got responsive units that scale automatically. But sometimes scaling isn't enough. At a certain point you don't just want things to be smaller, you want the layout to actually change. Three columns becoming one. A sidebar moving below the content. Navigation collapsing into a menu. That's what media queries are for.

---

### **What a Media Query Is**

A media query is a conditional block of CSS. It says: "only apply these styles when certain conditions are true." Everything inside the block is ignored unless the condition is met.

```css
@media (min-width: 900px) {
  .container {
    flex-direction: row;
  }
}
```

The `.container` rule only activates when the viewport is at least 900px wide. On anything narrower, the browser skips the whole block entirely.

---

### **The Syntax**

```css
@media media-type and (media-feature) {
  /* CSS rules */
}
```

Breaking it down:

- `@media` — the at-rule that opens the query
- `media-type` — what kind of output device (optional, covered below)
- `and` — combines conditions (all must be true)
- `(media-feature)` — the specific condition to test
- `{ }` — the CSS that applies when conditions are met

The simplest form skips the media type entirely:

```css
@media (min-width: 600px) {
  /* Applies when viewport is at least 600px wide */
}
```

---

### **How the Browser Actually Recognises Conditions**

**What's actually happening:** Every time something changes like the viewport resizes, the device rotates, the user changes a system setting, the browser re-evaluates all media queries on the page. It checks each condition against the current state of the device and environment. If the condition is true, the styles inside apply. If it's false, they don't.

This happens continuously in real time. You can see it in action by resizing your browser window slowly. At the exact pixel where your `min-width` condition becomes true, the styles switch instantly.

```
Viewport: 580px wide
@media (min-width: 600px) → FALSE → styles ignored

Viewport resizes to 600px
@media (min-width: 600px) → TRUE → styles applied ✅

Viewport resizes back to 599px
@media (min-width: 600px) → FALSE → styles ignored again
```

The browser isn't detecting a device type and then applying a fixed set of styles. It's constantly checking conditions against the current environment. A desktop browser window resized to 300px wide will trigger the same mobile styles as an actual phone — because the condition is purely about the viewport width, not the device itself.

---

### **Media Types**

Media types tell the browser what kind of output device the CSS applies to. There are two you'll actually encounter:

#### **`screen`**

Applies when the document is being displayed on a screen — any screen. Desktop monitors, laptops, tablets, phones — all of these are `screen`.

```css
@media screen and (min-width: 600px) {
  /* Only on screens, and only when at least 600px wide */
}
```

#### **`print`**

Applies when the document is being printed — or when the user opens Print Preview in their browser.

```css
@media print {
  .navigation {
    display: none;
  }
  .sidebar {
    display: none;
  }
  body {
    font-size: 12pt;
    color: black;
  }
}
```

**Question:** _"What is meant by print vs screen? How is that meant?"_

When someone prints a webpage or even just opens Print Preview, the browser switches to `print` media. This is actually a genuine use case. You've probably printed a webpage before and noticed the navigation, ads, and sidebars were gone, leaving just the content. That's `print` media queries at work. The developer wrote CSS that hides everything non-essential when the document is going to paper.

```
Screen view:                 Print view:
┌─────────────────────┐      ┌─────────────────┐
│ [Nav]               │      │                 │
├────────┬────────────┤      │  Article title  │
│Sidebar │  Article   │  →   │                 │
│        │  content   │      │  Article text   │
│        │            │      │  continues...   │
├────────┴────────────┤      │                 │
│ [Footer/Ads]        │      └─────────────────┘
└─────────────────────┘
```

#### **Do You Always Need to Specify a Media Type?**

No. Omitting the media type targets all media types including screen, print, and everything else. For most responsive design work this is fine:

```css
/* Targets all media types */
@media (min-width: 600px) {
}

/* Targets screen only */
@media screen and (min-width: 600px) {
}
```

The only time you'd explicitly write `screen` is if you have a separate `print` stylesheet and you want to make sure certain rules don't bleed into print styles. For everyday responsive design, leaving out the media type entirely is perfectly standard.

---

### **`min-width` and `max-width`**

These are the most common media features — the conditions that responsive design is built on.

#### **`min-width` — Mobile First**

"Apply these styles when the viewport is **at least** this wide."

```css
/* Base styles (mobile) */
.grid {
  display: grid;
  grid-template-columns: 1fr;
}

/* Tablet and up */
@media (min-width: 600px) {
  .grid {
    grid-template-columns: 1fr 1fr;
  }
}

/* Desktop and up */
@media (min-width: 900px) {
  .grid {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
```

```
< 600px:   [  1 column  ]
≥ 600px:   [ col ][ col ]
≥ 900px:   [ col ][ col ][ col ]
```

#### **`max-width` — Desktop First**

"Apply these styles when the viewport is **at most** this wide."

```css
/* Base styles (desktop) */
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

/* Below desktop */
@media (max-width: 899px) {
  .grid {
    grid-template-columns: 1fr 1fr;
  }
}

/* Mobile */
@media (max-width: 599px) {
  .grid {
    grid-template-columns: 1fr;
  }
}
```

As covered in [Section 3](#mobile-first-), `min-width` (mobile first) is preferred. It produces simpler, more maintainable CSS.

---

### **Combining Conditions**

#### **`and` — Both Must Be True**

```css
@media (min-width: 600px) and (max-width: 900px) {
  /* Only between 600px and 900px — tablet range only */
}
```

```
< 600px:        ✗ not applied
600px – 900px:  ✅ applied
> 900px:        ✗ not applied
```

This targets a specific range — useful when you want styles that only apply to one device category and not others.

#### **`,` (Comma) — Either Can Be True**

The comma works like `or` — if any condition in the list is true, the styles apply.

```css
@media (min-width: 1200px), (orientation: landscape) {
  /* Applies on wide screens OR in landscape orientation */
}
```

---

### **Writing Media Queries Inside Rules**

You can nest media queries inside existing selectors in some CSS setups, but the standard approach is to write them at the top level of your stylesheet. Grouping all your media queries at the bottom is one common pattern:

```css
/* Base styles */
.card {
  font-size: 1rem;
}
.grid {
  grid-template-columns: 1fr;
}

/* Tablet */
@media (min-width: 600px) {
  .card {
    font-size: 1.125rem;
  }
  .grid {
    grid-template-columns: 1fr 1fr;
  }
}

/* Desktop */
@media (min-width: 900px) {
  .card {
    font-size: 1.25rem;
  }
  .grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

Another common pattern is writing each media query directly after the rule it modifies — keeping related code together. Both approaches work. What matters is being consistent.

---

### **Key Takeaways 📋**

- A media query is a conditional CSS block — styles inside only apply when the condition is true
- The browser re-evaluates all media queries continuously as the environment changes — it's not a one-time device detection
- `screen` targets all screen devices, `print` targets print and print preview — you don't need to specify `screen` for everyday responsive work
- `min-width` = "at least this wide" — used in mobile first approach
- `max-width` = "at most this wide" — used in desktop first approach
- `and` combines conditions (all must be true), `,` separates alternatives (any can be true)

- Prefer `min-width` over `max-width` for simpler, forward-building CSS

---

## **Breakpoints 📐**

You've seen `min-width: 600px` and `min-width: 900px` used in the examples so far without much explanation of where those numbers come from. That's what this section is about.

---

### **What a Breakpoint Actually Is**

A breakpoint is the specific viewport width at which your layout changes. It's the value inside your media query condition. The point where one set of styles stops and another begins.

A breakpoint isn't just where you write a media query, it's a deliberate design decision about where your layout needs to adapt. Your layout should drive your breakpoints, not the other way around. The question isn't "what breakpoints should I use?", it's "at what width does my layout start to break down?" That's where you add a breakpoint.

---

```
Layout works fine      Layout starts      Layout works
on narrow screens  →   breaking here  →   again after
                            ↑
                       Add breakpoint here
```

---

### **Common Breakpoints**

In practice, most layouts need to adapt at similar points because devices cluster around certain screen sizes. These are the widely used breakpoints that target those clusters:

| Breakpoint          | Device Category      | Typical Devices             |
| ------------------- | -------------------- | --------------------------- |
| No query (default)  | Extra small / Mobile | Small phones (320px–599px)  |
| `min-width: 600px`  | Small / Large mobile | Large phones, small tablets |
| `min-width: 900px`  | Medium / Tablet      | Tablets, small laptops      |
| `min-width: 1200px` | Large / Desktop      | Laptops, desktop monitors   |
| `min-width: 1536px` | Extra large          | Large monitors, widescreens |

These aren't arbitrary numbers. They sit between the most common screen width clusters so a breakpoint doesn't land right in the middle of a popular device size.

**You won't always need all five.** Simple layouts might only need one or two breakpoints. Add them when your layout needs them, not because they're on the list.

---

### **How Breakpoints Stack in Mobile First CSS**

Because you're using `min-width`, each breakpoint builds on everything before it. Styles aren't replaced, they're added to or overridden:

```css
/* Default — all screens (mobile) */
.grid {
  grid-template-columns: 1fr;
  gap: 16px;
}

/* 600px and up — large mobile / tablet */
@media (min-width: 600px) {
  .grid {
    grid-template-columns: 1fr 1fr;
  }
}

/* 900px and up — tablet / desktop */
@media (min-width: 900px) {
  .grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }
}

/* 1200px and up — desktop */
@media (min-width: 1200px) {
  .grid {
    grid-template-columns: repeat(4, 1fr);
  }
}
```

```
< 600px:    [ 1 column,  16px gap ]
≥ 600px:    [ 2 columns, 16px gap ]
≥ 900px:    [ 3 columns, 24px gap ]
≥ 1200px:   [ 4 columns, 24px gap ]
```

Each breakpoint only declares what changes. Everything not mentioned carries forward from the previous level.

---

### **Content-Driven vs Device-Driven Breakpoints**

There are two schools of thought on choosing breakpoints:

**Device-driven**
Pick breakpoints based on common device screen sizes and target specific device categories. The table above follows this approach. It's practical and gives you a reliable system to work within.

**Content-driven**
Ignore device sizes entirely and add a breakpoint wherever your specific content starts to look wrong. Resize the browser until your layout breaks, then add a breakpoint there.

In practice, most developers combine both: start with the common breakpoints as a framework, then add additional breakpoints wherever a specific component needs it.

---

### **Framework Breakpoints**

If you ever work with CSS frameworks, they come with their own breakpoint systems. They follow the same concept but may use different values:

| Breakpoint  | This Guide | Tailwind CSS | Bootstrap |
| ----------- | ---------- | ------------ | --------- |
| Small       | 600px      | 640px        | 576px     |
| Medium      | 900px      | 768px        | 768px     |
| Large       | 1200px     | 1024px       | 992px     |
| Extra Large | 1536px     | 1280px       | 1200px    |

None of these are wrong. They're all targeting the same general device clusters, just with slightly different values. What matters is being consistent within a project.

---

### **A Pro Tip — CSS Custom Properties and Breakpoints**

You can store your breakpoints as CSS custom properties and reuse them, though custom properties can't be used directly inside media query conditions. A common workaround is to document your breakpoints as comments at the top of your stylesheet:

```css
/* Breakpoints:
   sm:  600px
   md:  900px
   lg:  1200px
   xl:  1536px
*/

@media (min-width: 600px) {
} /* sm */
@media (min-width: 900px) {
} /* md */
```

This way your breakpoint values are documented in one place and easy to reference consistently throughout your stylesheet.

However, you can use custom properties to change values _inside_ breakpoints. Which is genuinely powerful:

```css
:root {
  --gap: 16px;
  --font-size-base: 1rem;
}

@media (min-width: 900px) {
  :root {
    --gap: 24px;
    --font-size-base: 1.125rem;
  }
}

/* Every element using these variables updates automatically */
.grid {
  gap: var(--gap);
}
p {
  font-size: var(--font-size-base);
}
```

Change the variable value at a breakpoint, and every element using that variable updates automatically — no need to rewrite rules for each element individually.

---

### **Key Takeaways 📋**

- A breakpoint is the viewport width at which your layout deliberately changes
- Add breakpoints where your layout needs them, not just because they're on a standard list
- Common breakpoints cluster around 600px, 900px, 1200px, and 1536px — targeting real device size clusters
- In mobile first CSS, each breakpoint adds to or overrides what came before — styles cascade forward
- Different frameworks use slightly different breakpoint values — what matters is consistency within a project
- CSS custom properties inside media queries let you update multiple elements from one variable change

---

## **Common Media Features 🎛️**

Media queries aren't limited to screen width. The browser can detect a surprising range of device and user preferences and you can write CSS that responds to all of them. This section covers the most useful media features beyond `min-width` and `max-width`.

---

### **Screen Size**

You've already seen these throughout the guide, but let's formally define them together:

`min-width` — applies when the viewport is **at least** this wide
`max-width` — applies when the viewport is **at most** this wide
`min-height` — applies when the viewport is **at least** this tall
`max-height` — applies when the viewport is **at most** this tall

```css
@media (min-width: 900px) {
  /* Viewport is at least 900px wide */
}

@media (max-height: 600px) {
  /* Viewport is at most 600px tall */
  /* Useful for landscape phones with short screens */
}
```

`min-height` and `max-height` are less commonly used but come in handy for landscape phone layouts where the screen is wide but very short. A navbar that takes up `20vh` on a tall screen might eat half the visible content on a short one.

---

### **Orientation**

Orientation detects whether the device is in portrait or landscape mode.

```css
@media (orientation: portrait) {
  /* Height is greater than or equal to width */
}

@media (orientation: landscape) {
  /* Width is greater than height */
}
```

**What's actually happening:** The browser isn't detecting a physical rotation sensor. It's simply comparing the viewport width and height. If width ≥ height, that's landscape. If height > width, that's portrait. This means a very wide browser window on desktop is technically "landscape" even though nothing rotated.

```
Portrait:              Landscape:
┌──────────┐           ┌──────────────────────┐
│          │           │                      │
│  width   │           │   width > height     │
│    <     │           │                      │
│  height  │           └──────────────────────┘
│          │
└──────────┘
```

**When to use it:** Adjusting layouts for phones held sideways — collapsing elements that take up too much vertical space in landscape, or switching a stacked layout to side-by-side when there's suddenly more horizontal room.

```css
/* Stack content by default (portrait) */
.content {
  flex-direction: column;
}

@media (orientation: landscape) {
  /* Side by side when rotated */
  .content {
    flex-direction: row;
  }
}
```

---

### **Pointer**

The pointer feature detects what kind of pointing device the user has — useful for adjusting interactive element sizes based on input precision.

```css
@media (pointer: none) {
  /* No pointer device — keyboard only navigation */
}

@media (pointer: coarse) {
  /* Imprecise pointer — touchscreen finger */
}

@media (pointer: fine) {
  /* Precise pointer — mouse or stylus */
}
```

**What's actually happening:** The browser reports the primary pointer type. A touchscreen phone reports `coarse` (fingers are imprecise). A desktop with a mouse reports `fine` (a cursor can hit small targets). A keyboard-only device reports `none`.

**Why this matters:** Touch targets need to be larger than mouse targets because fingers are much less precise than a cursor. A button that's perfectly clickable with a mouse at 20px tall might be nearly impossible to tap accurately on a touchscreen.

```css
.button {
  padding: 0.5rem 1rem; /* Comfortable for mouse */
}

@media (pointer: coarse) {
  .button {
    padding: 1rem 2rem; /* Larger target for touch */
    min-height: 44px; /* Apple's recommended minimum touch target */
  }
}
```

**`any-pointer`** works the same way but checks if _any_ connected device has that pointer type, rather than just the primary one. A tablet with a stylus attached might have both `coarse` (touch) and `fine` (stylus) available:

```css
@media (any-pointer: fine) {
  /* Device has at least one precise pointer available */
}
```

---

### **Device Pixel Ratio (Pixel Density)**

Device pixel ratio (DPR) is the relationship between physical pixels on the screen and CSS pixels. Modern high-resolution screens (like Retina displays) pack more physical pixels into the same physical space.

```css
@media (device-pixel-ratio: 1) {
  /* Standard resolution screens */
}

@media (device-pixel-ratio: 2) {
  /* High resolution — Retina displays, most modern phones */
}

@media (device-pixel-ratio: 3) {
  /* Very high resolution — some phones and tablets */
}
```

**What's actually happening:** On a standard screen, 1 CSS pixel = 1 physical pixel. On a Retina display (DPR 2), 1 CSS pixel = 4 physical pixels (2×2). This is why images can look blurry on high-DPR screens — a 100×100px image being displayed at 200×200 physical pixels gets stretched, and the browser fills in the gaps.

```
Standard (DPR 1):              Retina (DPR 2):
1 CSS pixel = 1 physical       1 CSS pixel = 4 physical (2×2)

                               ┌──┬──┬──┬──┐
┌──┬──┐                        │▓▓│▓▓│░░│░░│
│  │  │  ← 2 CSS pixels        ├──┼──┼──┼──┤ ← CSS pixel 1    CSS pixel 2
├──┼──┤                        │▓▓│▓▓│░░│░░│   (2×2 physical)  (2×2 physical)
│  │  │  ← 2 CSS pixels        ├──┼──┼──┼──┤
└──┴──┘                        │▓▓│▓▓│░░│░░│
                               ├──┼──┼──┼──┤ ← CSS pixel 3    CSS pixel 4
                               │▓▓│▓▓│░░│░░│   (2×2 physical)  (2×2 physical)
4 CSS pixels =                 └──┴──┴──┴──┘
4 physical pixels
                                4 CSS pixels =
                                16 physical pixels

Each ▓▓ or ░░ block = 1 physical pixel
Each 2×2 block of same shade = 1 CSS pixel
```

**When to use it:** Serving higher resolution images to high-DPR screens:

```css
.logo {
  background-image: url("logo.png"); /* Standard resolution */
}

@media (device-pixel-ratio: 2) {
  .logo {
    background-image: url("logo@2x.png"); /* Double resolution */
  }
}
```

> **Note:** For most image use cases the `<picture>` element handles this more cleanly than media queries. It gets coverd in [Section 8](#responsive-images--the-picture-element-️).

---

### **Color Scheme**

Color scheme detects whether the user has set their operating system to light or dark mode.

```css
@media (prefers-color-scheme: light) {
  /* User prefers light mode */
}

@media (prefers-color-scheme: dark) {
  /* User prefers dark mode */
}
```

**What's actually happening:** The browser reads the operating system's appearance setting and exposes it as a media feature. If the user has dark mode enabled in their OS settings, `prefers-color-scheme: dark` evaluates to true.

A common pattern is to define your default styles for light mode, then override them for dark:

```css
:root {
  --background: #ffffff;
  --text: #1a1a1a;
  --card: #f5f5f5;
}

@media (prefers-color-scheme: dark) {
  :root {
    --background: #1a1a1a;
    --text: #ffffff;
    --card: #2a2a2a;
  }
}

body {
  background-color: var(--background);
  color: var(--text);
}
```

By redefining the custom properties inside the media query, every element using those variables automatically updates. You only write the override once, not for every individual element.

---

### **Reduced Motion**

Some users are sensitive to animation and movement. This can cause discomfort or nausea for people with vestibular disorders. They can signal this preference through their OS accessibility settings, and CSS can respect it.

```css
@media (prefers-reduced-motion: reduce) {
  /* User has requested less motion */
}
```

**What's actually happening:** The browser reads the "Reduce Motion" accessibility setting from the operating system and exposes it here. On macOS it's in System Preferences → Accessibility → Display → Reduce Motion. On Windows it's in Settings → Ease of Access → Display → Show animations.

The standard approach is to write animations normally, then disable or simplify them for users who've requested reduced motion:

```css
.card {
  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-8px);
}

@media (prefers-reduced-motion: reduce) {
  .card {
    transition: none;
  }

  .card:hover {
    transform: none;
  }
}
```

**Why this matters:** Respecting this preference is an accessibility consideration, not just a nice-to-have. Users who set this preference often need it. Ignoring it can cause genuine physical discomfort.

---

### **High Contrast**

Some users need higher contrast between foreground and background elements to read comfortably. This is another OS-level accessibility setting the browser can detect.

```css
@media (prefers-contrast: more) {
  /* User prefers higher contrast */
  .button {
    border: 2px solid currentColor;
    font-weight: bold;
  }
}
```

How to change this setting:

- macOS: System Preferences → Accessibility → Display → Increase Contrast
- Windows: Settings → Ease of Access → Display → Turn on high contrast

---

### **Key Takeaways 📋**

- Media features go beyond screen size — they detect orientation, input type, pixel density, and user preferences
- `orientation` compares viewport width and height — it's not a physical sensor reading
- `pointer: coarse` targets touchscreens, `pointer: fine` targets mice — use it to adjust touch target sizes
- Device pixel ratio detects screen density — use it to serve higher resolution images to high-DPR screens
- `prefers-color-scheme` reads the OS light/dark mode setting — combine with CSS custom properties for clean theming
- `prefers-reduced-motion` reads the OS accessibility setting — always respect it, ignoring it can cause discomfort

---

## **Responsive Images — The `<picture>` Element 🖼️**

Images are one of the trickiest parts of responsive design. A large high-resolution image that looks stunning on a widescreen monitor is overkill on a phone. It takes longer to download, uses more data, and gets scaled down by the browser anyway. The `<picture>` element gives you control over which image file the browser loads depending on the conditions you define.

---

### **The Problem with a Single `<img>`**

A standard `<img>` tag loads one image regardless of screen size:

```html
<img src="hero.jpg" alt="Hero image" />
```

The browser downloads `hero.jpg` on every device — a 4000px wide image on a 390px phone screen. The image gets displayed at the right size visually, but the full file was still downloaded. That's wasted bandwidth and slower load times on mobile, where users are most likely on slower connections.

---

### **How `<picture>` Works**

The `<picture>` element wraps multiple `<source>` elements and one `<img>` element. The browser reads the sources from top to bottom, finds the first one whose condition matches, and loads that image. The `<img>` at the bottom is the fallback. It loads if no source matches, or if the browser doesn't support `<picture>` at all.

```html
<picture>
  <source media="(min-width: 1200px)" srcset="hero-large.jpg" />
  <source media="(min-width: 600px)" srcset="hero-medium.jpg" />
  <img src="hero-small.jpg" alt="Hero image" />
</picture>
```

**What's actually happening:** The browser checks each `<source>` in order. If the viewport is 1400px wide, the first source matches and `hero-large.jpg` loads. If the viewport is 800px wide, the first source doesn't match, the browser moves to the second source, which does match, and `hero-medium.jpg` loads. If the viewport is 400px wide, neither source matches, so the `<img>` fallback loads `hero-small.jpg`.

```
Viewport 1400px:  source 1 matches → hero-large.jpg  ✅
Viewport 800px:   source 1 fails
                  source 2 matches → hero-medium.jpg  ✅
Viewport 400px:   source 1 fails
                  source 2 fails
                  img fallback    → hero-small.jpg    ✅
```

---

### **Why Source Order Matters**

The browser stops at the first match. It doesn't find the best match it finds the first match. This means if the largest breakpoint is placed last and the smallest first, a desktop browser will match the small image condition and load the wrong file.

**Wrong order:**

```html
<picture>
  <source media="(min-width: 600px)" srcset="hero-medium.jpg" />
  <source media="(min-width: 1200px)" srcset="hero-large.jpg" />
  <img src="hero-small.jpg" alt="Hero image" />
</picture>
```

On a 1400px viewport:

1. Browser checks `min-width: 600px` → 1400px is at least 600px → **match found**
2. Loads `hero-medium.jpg` — wrong image ❌
3. Never even looks at the second source

**Correct order — largest first:**

```html
<picture>
  <source media="(min-width: 1200px)" srcset="hero-large.jpg" />
  <source media="(min-width: 600px)" srcset="hero-medium.jpg" />
  <img src="hero-small.jpg" alt="Hero image" />
</picture>
```

On a 1400px viewport:

1. Browser checks `min-width: 1200px` → match found → loads `hero-large.jpg` ✅

On an 800px viewport:

1. Browser checks `min-width: 1200px` → 800px is not at least 1200px → no match
2. Browser checks `min-width: 600px` → match found → loads `hero-medium.jpg` ✅

**The rule:** Write sources from the most restrictive condition to the least restrictive. Largest breakpoint first, smallest last, fallback `<img>` at the bottom.

---

### **Comparing to Media Queries**

You might notice this is the opposite of how you write mobile first CSS. In CSS you write the smallest styles first and use `min-width` to add complexity upward. In `<picture>` you write the largest source first because the browser is looking for the first match, not the best match.

|              | CSS Media Queries             | `<picture>` Sources          |
| ------------ | ----------------------------- | ---------------------------- |
| **Order**    | Smallest first                | Largest first                |
| **Why**      | Each query overrides the last | Browser stops at first match |
| **Fallback** | Base styles (no query)        | `<img>` element              |

---

### **Art Direction — Different Images, Not Just Different Sizes**

`<picture>` isn't only for serving the same image at different resolutions. It's also useful for **art direction** — showing a completely different image crop or composition depending on the screen.

A wide landscape photo might work beautifully on desktop but become too small and detailed on mobile. A tighter, portrait crop of the same subject works better on a phone:

```html
<picture>
  <source media="(min-width: 900px)" srcset="team-photo-wide.jpg" />
  <source media="(min-width: 600px)" srcset="team-photo-square.jpg" />
  <img src="team-photo-portrait.jpg" alt="The team" />
</picture>
```

```
Desktop (900px+):          Tablet (600px+):        Mobile:
┌──────────────────────┐   ┌─────────────┐          ┌──────┐
│  🧑 🧑 🧑 🧑 🧑 🧑│   │🧑 🧑🧑    |          │  🧑  │
│   Wide group shot    │   │ Square crop │          │ 🧑🧑│
└──────────────────────┘   └─────────────┘          └──────┘
```

Same subject, different compositions — each optimised for the screen it's being viewed on.

---

### **The `<img>` Fallback Is Required**

The `<img>` element inside `<picture>` is not optional. It serves two purposes:

1. **Fallback** — loads if no `<source>` condition matches, or if the browser doesn't support `<picture>`
2. **`alt` text** — the `alt` attribute always goes on the `<img>`, not on the `<source>` elements

```html
<picture>
  <source media="(min-width: 900px)" srcset="image-large.jpg" />
  <img src="image-small.jpg" alt="A descriptive alt text" />
  <!-- alt always on the img, never on source -->
</picture>
```

Without the `<img>`, the entire `<picture>` element fails silently — nothing renders.

---

### **Key Takeaways 📋**

- `<picture>` lets you serve different image files based on conditions — saving bandwidth by not loading oversized images on small screens
- The browser reads `<source>` elements top to bottom and stops at the first match
- Sources must be ordered from most restrictive to least restrictive — largest breakpoint first
- Wrong source order means the browser matches too early and loads the wrong image
- `<picture>` also supports art direction — completely different image compositions per screen size
- The `<img>` fallback is required — it loads when no source matches and always carries the `alt` attribute

---

## **Quick Reference 📚**

---

### **The Viewport Meta Tag**

Always include this in the `<head>` of every HTML file:

```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

---

### **Media Query Syntax**

```css
/* Basic syntax */
@media (media-feature) {
  /* CSS rules */
}

/* With media type */
@media screen and (media-feature) {
  /* CSS rules */
}

/* Multiple conditions — all must be true */
@media (min-width: 600px) and (orientation: landscape) {
  /* CSS rules */
}

/* Multiple conditions — any can be true */
@media (min-width: 600px), (orientation: landscape) {
  /* CSS rules */
}
```

---

### **Common Breakpoints**

```css
/* Mobile first — base styles require no query */

@media (min-width: 600px) {
  /* Large mobile and up */
}

@media (min-width: 900px) {
  /* Tablet and up */
}

@media (min-width: 1200px) {
  /* Desktop and up */
}

@media (min-width: 1536px) {
  /* Large desktop and up */
}
```

---

### **Common Media Features**

| Feature                  | Values                     | What It Detects              |
| ------------------------ | -------------------------- | ---------------------------- |
| `min-width`              | any size                   | Viewport at least this wide  |
| `max-width`              | any size                   | Viewport at most this wide   |
| `min-height`             | any size                   | Viewport at least this tall  |
| `max-height`             | any size                   | Viewport at most this tall   |
| `orientation`            | `portrait` / `landscape`   | Width vs height relationship |
| `pointer`                | `none` / `coarse` / `fine` | Input device type            |
| `device-pixel-ratio`     | `1` / `2` / `3`            | Screen pixel density         |
| `prefers-color-scheme`   | `light` / `dark`           | OS light/dark mode setting   |
| `prefers-reduced-motion` | `reduce`                   | OS reduced motion setting    |
| `prefers-contrast`       | `more`                     | OS high contrast setting     |

---

### **Responsive Units**

| Unit     | Relative To                         | Common Use                        |
| -------- | ----------------------------------- | --------------------------------- |
| `%`      | Parent element (property dependent) | Fluid widths                      |
| `vw`     | Viewport width                      | Full-width layouts                |
| `vh`     | Viewport height                     | Full-screen sections              |
| `vmin`   | Smaller viewport dimension          | Elements that fit any orientation |
| `vmax`   | Larger viewport dimension           | Backgrounds and overlays          |
| `rem`    | Root font size                      | Typography and spacing            |
| `em`     | Current element font size           | Component-level spacing           |
| `calc()` | Mixed                               | Combining different units         |

---

### **Common Patterns**

#### **Responsive Navigation**

A navigation that stacks vertically on mobile and goes horizontal on desktop:

```css
.nav {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

@media (min-width: 900px) {
  .nav {
    flex-direction: row;
    gap: 24px;
  }
}
```

```
Mobile:           Desktop:
┌──────────┐      ┌────┬────┬────┬────┐
│  Home    │      │Home│About│Work│Contact│
├──────────┤      └────┴────┴────┴────┘
│  About   │
├──────────┤
│  Work    │
├──────────┤
│  Contact │
└──────────┘
```

---

#### **Responsive Navigation with Hamburger Menu**

On mobile, the full navigation is hidden and replaced with a hamburger button. Clicking the button toggles the menu open. On desktop, the hamburger disappears and the full navigation shows permanently.

**HTML:**

```html
<nav class="nav">
  <button class="hamburger">☰</button>
  <ul class="nav-menu">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Work</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

**CSS:**

```css
/* Mobile — hamburger visible, menu hidden */
.hamburger {
  display: block;
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
}

.nav-menu {
  display: none;
  list-style: none;
  padding: 0;
}

/* Menu visible when toggled open */
.nav-menu.open {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

/* Desktop — hamburger hidden, menu always visible */
@media (min-width: 900px) {
  .hamburger {
    display: none;
  }

  .nav-menu {
    display: flex;
    flex-direction: row;
    gap: 24px;
  }
}
```

**JavaScript:**

```javascript
const hamburger = document.querySelector(".hamburger");
const navMenu = document.querySelector(".nav-menu");

hamburger.addEventListener("click", () => {
  navMenu.classList.toggle("open");
});
```

```
Mobile (closed):    Mobile (open):     Desktop:
┌──────────────┐    ┌──────────────┐   ┌────┬─────┬────┬────────┐
│ ☰           │    │ ☰            │   │Home│About│Work│Contact │
└──────────────┘    ├──────────────┤   └────┴─────┴────┴────────┘
                    │ Home         │
                    ├──────────────┤
                    │ About        │
                    ├──────────────┤
                    │ Work         │
                    ├──────────────┤
                    │ Contact      │
                    └──────────────┘
```

**What's actually happening:** The HTML always contains both the hamburger button and the full menu. CSS hides or shows each part depending on the screen size. JavaScript handles the toggle — when the hamburger is clicked it adds the `open` class to the menu, which switches its `display` from `none` to `flex`. On desktop the hamburger is hidden entirely and the menu is always visible, so the JavaScript never comes into play.

---

#### **Responsive Card Grid**

A single column on mobile that expands into multiple columns on larger screens:

```css
.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
}

@media (min-width: 600px) {
  .grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (min-width: 1200px) {
  .grid {
    grid-template-columns: repeat(4, 1fr);
    gap: 24px;
  }
}
```

```
Mobile:       Tablet:           Desktop:
┌──────┐      ┌──────┬──────┐   ┌──┬──┬──┬──┐
│ Card │      │ Card │ Card │   │  │  │  │  │
├──────┤      ├──────┼──────┤   └──┴──┴──┴──┘
│ Card │      │ Card │ Card │
├──────┤      └──────┴──────┘
│ Card │
└──────┘
```

---

#### **Responsive Typography**

Base font size for mobile, scaling up for larger screens:

```css
:root {
  --font-size-base: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.25rem;
}

@media (min-width: 900px) {
  :root {
    --font-size-base: 1.125rem;
    --font-size-lg: 1.25rem;
    --font-size-xl: 1.5rem;
  }
}

@media (min-width: 1200px) {
  :root {
    --font-size-base: 1.25rem;
    --font-size-lg: 1.5rem;
    --font-size-xl: 2rem;
  }
}

body {
  font-size: var(--font-size-base);
}
h2 {
  font-size: var(--font-size-lg);
}
h1 {
  font-size: var(--font-size-xl);
}
```

---

#### **Full-Screen Hero Section**

A section that always fills the visible screen:

```css
.hero {
  height: 100vh;
  display: grid;
  place-items: center;
  padding: 2rem;
}

@media (min-width: 900px) {
  .hero {
    padding: 4rem;
  }
}
```

---

#### **Dark Mode**

Switching colors based on OS preference using custom properties:

```css
:root {
  --background: #ffffff;
  --text: #1a1a1a;
  --card: #f5f5f5;
}

@media (prefers-color-scheme: dark) {
  :root {
    --background: #1a1a1a;
    --text: #ffffff;
    --card: #2a2a2a;
  }
}

body {
  background-color: var(--background);
  color: var(--text);
}
```

---

#### **Respecting Reduced Motion**

Writing animations that disable for users who need it:

```css
.card {
  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-8px);
}

@media (prefers-reduced-motion: reduce) {
  .card {
    transition: none;
  }

  .card:hover {
    transform: none;
  }
}
```

---

#### **Responsive Images with `<picture>`**

Serving different image sizes based on viewport — largest source first:

```html
<picture>
  <source media="(min-width: 1200px)" srcset="image-large.jpg" />
  <source media="(min-width: 600px)" srcset="image-medium.jpg" />
  <img src="image-small.jpg" alt="Description" />
</picture>
```

---

#### **Larger Touch Targets on Mobile**

Making interactive elements easier to tap on touchscreens:

```css
.button {
  padding: 0.5rem 1rem;
}

@media (pointer: coarse) {
  .button {
    padding: 1rem 2rem;
    min-height: 44px;
  }
}
```

---

### **Checklist ✅**

- ☐ Viewport meta tag in `<head>` of every HTML file
- ☐ Base styles written for mobile (no media query)
- ☐ `min-width` used for breakpoints (not `max-width`)
- ☐ Breakpoints added where layout needs them, not arbitrarily
- ☐ Responsive units used instead of fixed `px` where appropriate
- ☐ `<picture>` sources ordered largest breakpoint first
- ☐ `alt` attribute on the `<img>` inside `<picture>`, not on `<source>`
- ☐ `prefers-reduced-motion` respected for any animations
- ☐ Touch targets large enough for coarse pointer devices
