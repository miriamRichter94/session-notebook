# Web Accessibility

- [What is Accessibility & Why It Matters ♿](#what-is-accessibility--why-it-matters-)
  - [Who Benefits from Accessibility](#who-benefits-from-accessibility)
  - [The Business and Legal Case](#the-business-and-legal-case)
  - [The WCAG Standard](#the-wcag-standard)
  - [How to Think About Accessibility](#how-to-think-about-accessibility)
  - [Key Takeaways 📋](#key-takeaways-)
- [Semantic HTML ♿](#semantic-html-)
  - [What Semantic Means](#what-semantic-means)
  - [Structural Semantic Elements](#structural-semantic-elements)
  - [A Complete Page Structure](#a-complete-page-structure)
  - [Heading Hierarchy](#heading-hierarchy)
  - [Semantic Inline Elements](#semantic-inline-elements)
  - [Why Divs and Spans Aren't Always the Answer](#why-divs-and-spans-arent-always-the-answer)
  - [Key Takeaways 📋](#key-takeaways--1)
- [ARIA ♿](#aria-)
  - [What ARIA Is](#what-aria-is)
  - [The First Rule of ARIA](#the-first-rule-of-aria)
  - [ARIA Roles](#aria-roles)
  - [ARIA States and Properties](#aria-states-and-properties)
  - [How to Test ARIA](#how-to-test-aria)
  - [Common ARIA Mistakes 🐞](#common-aria-mistakes-)
  - [Key Takeaways 📋](#key-takeaways--2)
- [Accessible Forms ♿](#accessible-forms-)
  - [Why Forms Need Special Attention](#why-forms-need-special-attention)
  - [Labels and Inputs](#labels-and-inputs)
  - [Wrapping Inputs in a `<form>` Element](#wrapping-inputs-in-a-form-element)
  - [Input Types](#input-types)
  - [Required Fields](#required-fields)
  - [Grouping Related Fields](#grouping-related-fields)
  - [Placeholder Text](#placeholder-text)
  - [Error Messages](#error-messages)
  - [Autocomplete](#autocomplete)
  - [A Complete Accessible Form Example](#a-complete-accessible-form-example)
  - [How to Test Form Accessibility](#how-to-test-form-accessibility)
  - [Common Mistakes 🐞](#common-mistakes-)
  - [Key Takeaways 📋](#key-takeaways--3)
- [Color and Contrast :art:](#color-and-contrast-art)
  - [Why Color Alone Is Never Enough](#why-color-alone-is-never-enough)
  - [What Contrast Ratio Means](#what-contrast-ratio-means)
  - [The WCAG Contrast Requirements](#the-wcag-contrast-requirements)
  - [What's Actually Happening With Contrast](#whats-actually-happening-with-contrast)
  - [Checking Contrast](#checking-contrast)
  - [Common Contrast Mistakes](#common-contrast-mistakes)
  - [Color Blindness Simulation](#color-blindness-simulation)
  - [Dark Mode and Contrast](#dark-mode-and-contrast)
  - [Key Takeaways 📋](#key-takeaways--4)
- [Images and Alt Text 🖼️](#images-and-alt-text-️)
  - [What Alt Text Does](#what-alt-text-does)
  - [The Core Question: What Does This Image Convey?](#the-core-question-what-does-this-image-convey)
  - [Decorative Images — When to Use Empty Alt Text](#decorative-images--when-to-use-empty-alt-text)
  - [Writing Good Alt Text](#writing-good-alt-text)
  - [Complex Images](#complex-images)
  - [Images Inside Links and Buttons](#images-inside-links-and-buttons)
  - [The `<figure>` and `<figcaption>` Elements](#the-figure-and-figcaption-elements)
  - [SVG Images](#svg-images)
  - [How to Test Image Accessibility](#how-to-test-image-accessibility)
  - [Common Mistakes 🐞](#common-mistakes--1)
  - [Key Takeaways 📋](#key-takeaways--5)
- [Interactive Elements ♿](#interactive-elements-)
  - [Keyboard Navigation](#keyboard-navigation)
  - [Focus Management](#focus-management)
  - [`tabindex`](#tabindex)
  - [Buttons vs Links](#buttons-vs-links)
  - [Accessible Names for Interactive Elements](#accessible-names-for-interactive-elements)
  - [Skip Links](#skip-links)
  - [Custom Interactive Components](#custom-interactive-components)
  - [How to Test Interactive Elements](#how-to-test-interactive-elements)
  - [Common Mistakes 🐞](#common-mistakes--2)
  - [Key Takeaways 📋](#key-takeaways--6)
- [Quick Reference 📚](#quick-reference-)
  - [Semantic HTML Elements](#semantic-html-elements)
  - [Heading Rules](#heading-rules)
  - [ARIA Quick Reference](#aria-quick-reference)
  - [Accessible Forms Patterns](#accessible-forms-patterns)
  - [Alt Text Patterns](#alt-text-patterns)
  - [Color and Contrast Requirements](#color-and-contrast-requirements)
  - [Focus Management Patterns](#focus-management-patterns)
  - [`tabindex` Reference](#tabindex-reference)
  - [Keyboard Navigation Reference](#keyboard-navigation-reference)
  - [Buttons vs Links](#buttons-vs-links-1)
  - [Visibility and Accessibility Tree](#visibility-and-accessibility-tree)
  - [Testing Tools](#testing-tools)
  - [Accessibility Checklist ✅](#accessibility-checklist-)
  - [Resources](#resources)

## **What is Accessibility & Why It Matters ♿**

When you build a website, it's easy to test it by looking at it, clicking around with a mouse, and reading the content. But not everyone experiences the web the same way. Some people navigate entirely by keyboard. Some use screen readers that convert content to audio. Some have colour blindness that makes certain colour combinations unreadable. Some have motor impairments that make precise mouse movements difficult or impossible.

Web accessibility is the practice of building websites that work for all of these people. Not just the ones who interact with the web the same way you do.

---

### **Who Benefits from Accessibility**

The most obvious answer is people with disabilities and that group is larger than most people assume. Globally, over a billion people live with some form of disability. But accessibility benefits go well beyond that:

**People with permanent disabilities:**

- Visual impairments (blindness, low vision, colour blindness)
- Auditory impairments (deafness, hard of hearing)
- Motor impairments (limited hand mobility, tremors, paralysis)
- Neurological and cognitive differences (dyslexia, ADHD, memory impairments)

**People with temporary limitations:**

- A broken arm making mouse use difficult
- An eye infection making screens hard to look at
- Recovery from surgery affecting motor control

**People with situational limitations:**

- Bright sunlight making a screen hard to read
- Holding a baby with one hand, leaving only one hand free
- Being in a loud environment where audio content can't be heard
- A slow internet connection where images don't load

**Everyone else:**

- Older users whose vision, hearing, and motor control change with age
- Users on low-end devices with small screens
- Search engines — which are essentially blind users reading your content

Accessibility done well makes websites better for everyone, not just those with disabilities. Captions on videos help someone watching without headphones. Good colour contrast helps someone reading in sunlight. Keyboard navigation helps a power user who prefers not to use a mouse.

---

### **The Business and Legal Case**

Accessibility isn't just an ethical consideration — it has real practical weight.

**Reach:** Designing accessibly means your website works for more people. Excluding users with disabilities means excluding potential customers, readers, or users. A wider accessible audience directly translates to broader reach.

**SEO:** Many accessibility practices overlap with good SEO. Semantic HTML, descriptive alt text, clear heading structure, and meaningful link text all help search engines understand and index your content. Which is essentially the same job a screen reader does.

**User experience:** Accessible design tends to be cleaner, clearer, and easier to use for everyone. Clear language, logical structure, and sufficient contrast improve the experience for all users, not just those using assistive technology.

**Legal requirement:** In many countries, web accessibility is not optional it's required by law. The Americans with Disabilities Act (ADA) in the United States, the European Accessibility Act in the EU, and the Equality Act in the UK all have implications for web accessibility. Organisations that fail to meet accessibility standards have faced lawsuits and significant fines. For public sector organisations in many countries, accessibility compliance is a legal obligation rather than a recommendation.

---

### **The WCAG Standard**

Web accessibility has a widely adopted international standard: the **Web Content Accessibility Guidelines (WCAG)**, published by the World Wide Web Consortium (W3C).

WCAG organises accessibility requirements around four principles.ontent must be:

**Perceivable**
Information must be presentable in ways users can perceive. If content is only conveyed visually, users who can't see it are excluded. Alt text for images, captions for video, and sufficient colour contrast are all perceivability requirements.

**Operable**
Interface components must be operable by all users. If something can only be used with a mouse, keyboard-only users are excluded. All functionality must be reachable and usable via keyboard.

**Understandable**
Content and interfaces must be understandable. This means clear language, predictable behaviour, and helpful error messages on forms.

**Robust**
Content must be robust enough to be interpreted by a wide range of assistive technologies. This is largely about writing valid, semantic HTML that screen readers and other tools can reliably parse.

WCAG defines three conformance levels:

- **Level A** — Minimum accessibility. Failing these requirements excludes large groups of users entirely.
- **Level AA** — The standard target for most websites. This is what most legal requirements reference.
- **Level AAA** — The highest level. Not always achievable for all content, but worth aiming for where possible.

You don't need to memorise WCAG in detail to write accessible code. Understanding the four principles gives you a mental framework for asking the right questions as you build.

---

### **How to Think About Accessibility**

The biggest shift in thinking about accessibility is moving from "does this work for me?" to "does this work for everyone?"

Some questions to ask as you build:

- Can someone navigate this without a mouse?
- Can someone understand this without seeing it?
- Can someone use this with only one hand?
- Is this understandable without context I'm assuming the user has?
- Does this rely solely on colour to convey information?

Accessibility is easiest when it's considered from the start. Retrofitting an inaccessible website is significantly more work than building accessibly in the first place. The rest of this guide covers the specific techniques — semantic HTML, ARIA, forms, contrast, alt text, and interactive elements — that make up accessible web development in practice.

---

### **Key Takeaways 📋**

- Web accessibility means building websites that work for all users regardless of ability, device, or situation
- The people who benefit include those with permanent disabilities, temporary limitations, situational constraints, and older users
- Accessibility overlaps with SEO, user experience, and legal compliance — it benefits everyone
- WCAG is the international standard, organised around four principles: Perceivable, Operable, Understandable, Robust
- Level AA is the target for most websites and what most legal requirements reference
- Accessibility is easiest when considered from the start of a project, not added afterwards

---

## **Semantic HTML ♿**

The foundation of accessible web development isn't ARIA attributes or special accessibility tools. It's writing HTML correctly in the first place. Semantic HTML is HTML that uses elements for what they were designed for, rather than using generic elements for everything and styling them to look right.

---

### **What Semantic Means**

The word "semantic" means "relating to meaning." Semantic HTML is HTML where the elements carry meaning about the content they contain not just how it looks, but what it _is_.

Compare these two approaches:

```html
<!-- Non-semantic -->
<div class="header">
  <div class="nav">
    <div class="nav-item">Home</div>
    <div class="nav-item">About</div>
  </div>
</div>

<!-- Semantic -->
<header>
  <nav>
    <a href="#">Home</a>
    <a href="#">About</a>
  </nav>
</header>
```

Both can be made to look identical with CSS. But the semantic version communicates structure to the browser, search engines, and assistive technology. A screen reader encountering `<header>` and `<nav>` knows exactly what those regions are and can tell the user about them. A screen reader encountering a `<div>` gets no useful information at all.

**Think of it like this:**

Imagine receiving two documents. One uses proper headings, sections, and labels. The other is the same text but everything is the same size, the same font, with no visual hierarchy. Both contain the same words but only one communicates structure. For a sighted user, visual styling can compensate for the second document. For someone using a screen reader, there is no visual styling only the structure of the document itself.

---

### **Structural Semantic Elements**

These elements define the regions and structure of a page. Use them to give your layout meaning beyond just visual organisation.

#### **`<header>`**

The introductory content of a page or section. Typically contains the site logo, site title, and main navigation. A page can have multiple `<header>` elements. One for the page and one inside each `<article>` or `<section>` if needed.

```html
<header>
  <a href="/" class="logo">My Website</a>
  <nav>...</nav>
</header>
```

#### **`<nav>`**

A section containing navigation links. Use it for major navigation blocks — the main menu, pagination, breadcrumbs. Not every group of links needs to be a `<nav>` — only those that serve as primary navigation.

```html
<nav>
  <a href="/">Home</a>
  <a href="/about">About</a>
  <a href="/contact">Contact</a>
</nav>
```

#### **`<main>`**

The primary content of the page. The content that's unique to this page and not repeated across pages. There should be **only one `<main>` per page**. Screen readers use it to let users jump directly to the main content, skipping repeated navigation.

```html
<main>
  <h1>About Us</h1>
  <p>Page content here...</p>
</main>
```

#### **`<section>`**

A thematic grouping of content. Use it when content forms a distinct part of the page that could logically have its own heading. Not a replacement for `<div>`. Only use `<section>` when the content genuinely forms a meaningful group.

```html
<section>
  <h2>Our Services</h2>
  <p>...</p>
</section>
```

#### **`<article>`**

A self-contained piece of content that could stand alone and be redistributed independently — a blog post, a news article, a product card, a comment. If the content makes sense on its own outside the context of the page, it's probably an `<article>`.

```html
<article>
  <h2>How to Bake Sourdough</h2>
  <p>Published: March 2026</p>
  <p>Article content...</p>
</article>
```

#### **`<aside>`**

Content that's tangentially related to the surrounding content — a sidebar, a pull quote, related links, an advertisement. Not the main content, but contextually connected to it.

```html
<aside>
  <h3>Related Articles</h3>
  <ul>
    <li><a href="#">Sourdough Starter Guide</a></li>
    <li><a href="#">Choosing the Right Flour</a></li>
  </ul>
</aside>
```

#### **`<footer>`**

The closing content of a page or section. Typically contains copyright information, secondary navigation, contact details, or links to legal pages. Like `<header>`, a page can have multiple footers.

```html
<footer>
  <p>© 2026 My Website</p>
  <nav>
    <a href="/privacy">Privacy Policy</a>
    <a href="/terms">Terms of Service</a>
  </nav>
</footer>
```

---

### **A Complete Page Structure**

Here's how these elements combine into a properly structured page:

```html
<header>
  <a href="/" class="logo">My Website</a>
  <nav>
    <a href="/">Home</a>
    <a href="/about">About</a>
    <a href="/contact">Contact</a>
  </nav>
</header>

<main>
  <article>
    <h1>Article Title</h1>
    <p>Article introduction...</p>

    <section>
      <h2>First Topic</h2>
      <p>Content...</p>
    </section>

    <section>
      <h2>Second Topic</h2>
      <p>Content...</p>
    </section>
  </article>

  <aside>
    <h2>Related Reading</h2>
    <ul>
      <li><a href="#">Related article</a></li>
    </ul>
  </aside>
</main>

<footer>
  <p>© 2026 My Website</p>
</footer>
```

A screen reader user navigating this page can immediately jump to `<main>` to skip the header and navigation, understand that the `<aside>` is supplementary, and find their way around the page without needing to read every word from top to bottom.

---

### **Heading Hierarchy**

Headings are one of the most important accessibility tools on a page. Screen reader users frequently navigate pages by jumping between headings. It's the equivalent of visually scanning a page for section titles.

This means heading levels need to communicate structure, not visual size.

**The rules:**

**Use only one `<h1>` per page.** The `<h1>` is the page's main title — the top of the document outline. Having multiple `<h1>` elements confuses the document structure.

```html
<!-- ❌ Wrong — multiple h1 elements -->
<h1>My Website</h1>
<h1>About Us</h1>

<!-- ✅ Correct — one h1, sections use h2 -->
<h1>About Us</h1>
<h2>Our Story</h2>
<h2>Our Team</h2>
```

**Don't skip heading levels.** Moving from `<h1>` to `<h3>` skips `<h2>`, which breaks the document outline and confuses assistive technology.

```html
<!-- ❌ Wrong — skips h2 -->
<h1>Page Title</h1>
<h3>First Section</h3>

<!-- ✅ Correct — logical progression -->
<h1>Page Title</h1>
<h2>First Section</h2>
<h3>Subsection within First Section</h3>
```

**Don't choose heading levels for their visual size.** If you want an `<h3>` to look bigger, use CSS. Don't use `<h2>` because it's visually larger when structurally it should be `<h3>`.

```html
<!-- ❌ Wrong — using h2 for visual size, not structure -->
<h1>Article Title</h1>
<h2>A Note</h2>
<!-- Not a major section, just styled large -->

<!-- ✅ Correct — use CSS for visual adjustments -->
<h1>Article Title</h1>
<p class="large-note">A Note</p>
```

**How to test heading structure:**

Browser extensions like **Headings Map** (available for Chrome and Firefox) display the heading outline of any page. This lets you see immediately whether headings form a logical hierarchy or jump around arbitrarily.

You can also check in browser DevTools by opening the console and typing:

```javascript
Array.from(document.querySelectorAll("h1,h2,h3,h4,h5,h6")).forEach((h) =>
  console.log(h.tagName, h.textContent),
);
```

This lists every heading on the page in order, making structural problems immediately visible.

---

### **Semantic Inline Elements**

Structure isn't limited to page-level elements. Inline elements carry meaning too:

| Element        | Meaning           | Use For                             |
| -------------- | ----------------- | ----------------------------------- |
| `<strong>`     | Strong importance | Critical information, warnings      |
| `<em>`         | Emphasis          | Stress emphasis in text             |
| `<abbr>`       | Abbreviation      | Shortened terms with a full form    |
| `<time>`       | Date or time      | Machine-readable dates              |
| `<code>`       | Code              | Inline code snippets                |
| `<blockquote>` | Quotation         | Extended quotes from another source |
| `<cite>`       | Citation          | Title of a referenced work          |

```html
<!-- abbr with title provides full form on hover and to screen readers -->
<abbr title="World Wide Web Consortium">W3C</abbr>

<!-- time with datetime makes dates machine-readable -->
<time datetime="2026-03-15">March 15, 2026</time>

<!-- strong vs b — strong has meaning, b is just visual -->
<strong>Warning: This action cannot be undone.</strong>
```

The difference between `<strong>` and `<b>`, or `<em>` and `<i>`, is meaning. `<b>` and `<i>` are purely visual — bold and italic. `<strong>` means the content is of strong importance. `<em>` means the content is emphasised. Screen readers may convey this distinction in how they read the content aloud.

---

### **Why Divs and Spans Aren't Always the Answer**

`<div>` and `<span>` are the generic, non-semantic container elements. They have no inherent meaning. Use them when no semantic element fits — for layout containers, styling hooks, or JavaScript targets.

The problem arises when they're used _instead of_ semantic elements:

```html
<!-- ❌ A navigation built entirely from divs -->
<div class="nav">
  <div class="nav-item"><a href="/">Home</a></div>
  <div class="nav-item"><a href="/about">About</a></div>
</div>

<!-- ✅ Proper semantic navigation -->
<nav>
  <a href="/">Home</a>
  <a href="/about">About</a>
</nav>
```

Both look the same in a browser. But a screen reader announces the second one as a navigation landmark — users know what it is and can navigate to it directly. The first one is just an anonymous container.

**The rule:** reach for the semantic element first. Only fall back to `<div>` or `<span>` when nothing semantic fits.

---

### **Key Takeaways 📋**

- Semantic HTML uses elements for their intended meaning, not just their visual appearance
- Screen readers and assistive technology rely on semantic structure to communicate page layout to users
- Use structural elements — `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` — to define page regions
- Only one `<h1>` per page, never skip heading levels, never choose heading levels for visual size
- Inline elements like `<strong>`, `<em>`, and `<time>` carry meaning that `<b>` and `<i>` don't
- Use `<div>` and `<span>` only when no semantic element fits
- Test heading structure with browser extensions or DevTools to verify your document outline is logical

---

## **ARIA ♿**

Semantic HTML covers a lot of ground, but it doesn't cover everything. Some interface patterns — dropdown menus, tab panels, modals, toggle buttons — have no native HTML element that accurately describes them. This is where ARIA comes in.

---

### **What ARIA Is**

ARIA stands for **Accessible Rich Internet Applications**. It's a set of HTML attributes developed by the W3C that lets you add meaning and context to elements that HTML alone can't describe.

ARIA doesn't change how an element looks or behaves in the browser. It only changes what assistive technology — primarily screen readers — communicates to the user about that element.

```html
<!-- Without ARIA — screen reader announces: "button" -->
<button>☰</button>

<!-- With ARIA — screen reader announces: "Menu, button" -->
<button aria-label="Menu">☰</button>
```

The button looks identical in both cases. The ARIA attribute changes what a screen reader tells a visually impaired user about what the button does.

---

### **The First Rule of ARIA**

Before going further, this is the most important principle in the entire ARIA specification:

> **Don't use ARIA if you can use a native HTML element instead.**

Native HTML elements come with built-in accessibility behaviour. A `<button>` is already keyboard focusable, already announces itself as a button to screen readers, and already responds to Enter and Space key presses. A `<div>` with `role="button"` requires you to manually implement all of that.

```html
<!-- ❌ Unnecessary ARIA — native button already handles this -->
<div role="button" tabindex="0" aria-pressed="false">Click me</div>

<!-- ✅ Use the native element -->
<button>Click me</button>
```

ARIA is a tool for filling gaps, not a replacement for semantic HTML. If a native element exists for what you're building, use it.

---

### **ARIA Roles**

An ARIA role defines what an element _is_ — its purpose or type. You add it with the `role` attribute.

```html
<div role="alert">Your session is about to expire.</div>
```

Roles are organised into categories. The two most practically relevant for everyday development are:

#### **Document Structure Roles**

These describe sections and structures of content:

| Role           | What It Describes                                             |
| -------------- | ------------------------------------------------------------- |
| `note`         | Supplementary content, like a side note                       |
| `tooltip`      | A contextual popup that describes an element                  |
| `figure`       | A self-contained visual like an image or diagram              |
| `presentation` | An element that has no semantic meaning (removes native role) |

```html
<div role="note">
  <p>This feature is available on paid plans only.</p>
</div>
```

#### **Widget Roles**

These describe interactive UI components:

| Role          | What It Describes                                   |
| ------------- | --------------------------------------------------- |
| `alert`       | An important, time-sensitive message                |
| `dialog`      | A modal dialog window                               |
| `menu`        | A list of choices or commands                       |
| `menuitem`    | An individual item within a menu                    |
| `tab`         | A tab in a tab panel interface                      |
| `tabpanel`    | The panel associated with a tab                     |
| `slider`      | An input that allows selecting a value from a range |
| `progressbar` | An indicator of task progress                       |

```html
<!-- A modal dialog -->
<div role="dialog" aria-labelledby="modal-title">
  <h2 id="modal-title">Confirm Deletion</h2>
  <p>Are you sure you want to delete this item?</p>
  <button>Cancel</button>
  <button>Delete</button>
</div>
```

**A full list of ARIA roles** is available in the [MDN ARIA Roles documentation](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles).

---

### **ARIA States and Properties**

Where roles define what an element _is_, ARIA states and properties define the current _condition_ of an element and its _relationship_ to other elements.

**States** change dynamically as the user interacts — they reflect the current condition of something:

| Attribute       | What It Communicates                                   |
| --------------- | ------------------------------------------------------ |
| `aria-expanded` | Whether a collapsible element is open or closed        |
| `aria-checked`  | Whether a checkbox or toggle is checked                |
| `aria-disabled` | Whether an element is disabled                         |
| `aria-hidden`   | Whether an element is hidden from assistive technology |
| `aria-pressed`  | Whether a toggle button is pressed                     |
| `aria-selected` | Whether an item is selected                            |
| `aria-busy`     | Whether an element is loading or updating              |

**Properties** tend to be more static — they describe relationships and characteristics:

| Attribute          | What It Communicates                                 |
| ------------------ | ---------------------------------------------------- |
| `aria-label`       | A text label for an element                          |
| `aria-labelledby`  | References another element that labels this one      |
| `aria-describedby` | References an element that describes this one        |
| `aria-required`    | Whether a form field is required                     |
| `aria-invalid`     | Whether a form field has an error                    |
| `aria-controls`    | References an element this one controls              |
| `aria-live`        | How aggressively to announce dynamic content updates |

---

#### **`aria-label`**

`aria-label` provides a text label for an element when there's no visible text that describes it. The value you provide is what screen readers announce instead of the element's content.

The most common use case is icon-only buttons:

```html
<!-- Without aria-label — screen reader announces nothing useful -->
<button>
  <svg>...</svg>
</button>

<!-- With aria-label — screen reader announces "Close dialog, button" -->
<button aria-label="Close dialog">
  <svg>...</svg>
</button>
```

Another common use case is when multiple similar elements exist on the same page:

```html
<!-- Two "Read more" links — screen reader user can't tell them apart -->
<a href="/post-1">Read more</a>
<a href="/post-2">Read more</a>

<!-- aria-label makes each link distinct -->
<a href="/post-1" aria-label="Read more about Sourdough Baking">Read more</a>
<a href="/post-2" aria-label="Read more about Choosing Flour">Read more</a>
```

---

#### **`aria-labelledby`**

`aria-labelledby` links an element to another element that serves as its label. Instead of writing the label text directly in the attribute, you reference the `id` of the element that contains the label.

```html
<nav aria-labelledby="nav-title">
  <h2 id="nav-title">Products</h2>
  <a href="/shoes">Shoes</a>
  <a href="/bags">Bags</a>
</nav>
```

The `<nav>` is labelled by the `<h2>` with `id="nav-title"`. A screen reader announces "Products, navigation" — the user immediately knows which navigation region this is.

**`aria-label` vs `aria-labelledby` — which to use?**

| Situation                                     | Use               |
| --------------------------------------------- | ----------------- |
| No visible text exists to serve as a label    | `aria-label`      |
| A visible element already serves as the label | `aria-labelledby` |

Prefer `aria-labelledby` when there's already visible text — it reuses existing content rather than duplicating it in a hidden attribute. Use `aria-label` when no visible text exists.

```html
<!-- aria-labelledby — reuses existing heading text -->
<section aria-labelledby="services-heading">
  <h2 id="services-heading">Our Services</h2>
  ...
</section>

<!-- aria-label — no visible label exists -->
<button aria-label="Search">
  <svg>...</svg>
</button>
```

---

#### **`aria-describedby`**

`aria-describedby` works like `aria-labelledby` but for descriptions rather than labels. A label names what something is. A description provides additional context about it.

```html
<input type="password" aria-describedby="password-requirements" />
<p id="password-requirements">
  Password must be at least 8 characters and include a number.
</p>
```

When a screen reader focuses the input, it announces the label first, then the description. The user knows what the field is _and_ what's required of them.

---

#### **`aria-expanded`**

Used on elements that control the visibility of another element — dropdown menus, accordions, navigation toggles. It tells screen readers whether the controlled content is currently open or closed.

```html
<button aria-expanded="false" aria-controls="dropdown-menu">Options</button>

<ul id="dropdown-menu" hidden>
  <li><a href="#">Edit</a></li>
  <li><a href="#">Delete</a></li>
</ul>
```

When the menu opens, JavaScript updates the attribute:

```javascript
button.setAttribute("aria-expanded", "true");
```

A screen reader user hears "Options, collapsed, button" when closed and "Options, expanded, button" when open — they know the state without needing to see it.

---

#### **`aria-hidden`**

`aria-hidden="true"` removes an element from the accessibility tree entirely — screen readers skip it as if it doesn't exist. It's used for decorative content that adds nothing meaningful.

```html
<!-- Decorative icon alongside visible text — icon adds nothing -->
<button>
  <svg aria-hidden="true">...</svg>
  Save Document
</button>
```

Without `aria-hidden`, a screen reader might announce both the SVG content and "Save Document" — redundant and confusing. With it, the icon is skipped and only "Save Document, button" is announced.

> **Important:** Never use `aria-hidden="true"` on an element that contains focusable content like links or buttons. Hiding an element from the accessibility tree while it's still keyboard-focusable creates a confusing experience where focus lands on something the screen reader says nothing about.

> **Note:** CSS hiding (`display: none`, `visibility: hidden`) already removes elements from the accessibility tree automatically — `aria-hidden` is redundant on top of it. Use `aria-hidden="true"` only when something is _visually present_ but meaningless or redundant for screen reader users, like a decorative icon sitting next to visible text.

---

#### **`aria-live`**

Webpages update dynamically — search results load, notifications appear, form errors show. By default, screen readers only announce content when the user navigates to it. `aria-live` tells screen readers to announce content automatically when it changes.

```html
<div aria-live="polite" id="status-message"></div>
```

```javascript
document.getElementById("status-message").textContent =
  "Your file has been saved.";
```

When the content changes, the screen reader announces it without the user having to navigate there.

**Values:**

| Value       | Behaviour                                           |
| ----------- | --------------------------------------------------- |
| `off`       | Default — changes not announced                     |
| `polite`    | Announces when the user is idle — doesn't interrupt |
| `assertive` | Announces immediately — interrupts current speech   |

Use `polite` for most updates. Use `assertive` only for critical alerts that need immediate attention — it interrupts whatever the screen reader is currently saying, which is disruptive if overused.

---

### **How to Test ARIA**

The best way to test ARIA is with an actual screen reader:

- **macOS / iOS:** VoiceOver — built in, activate with `Cmd + F5` on Mac
- **Windows:** NVDA — free, widely used, download at [nvaccess.org](https://www.nvaccess.org)
- **Windows:** Narrator — built in to Windows
- **Android:** TalkBack — built in, activate in Accessibility settings

**Testing checklist:**

- Navigate the page using only the Tab key — does focus move logically?
- Activate a screen reader and navigate by headings — is the structure clear?
- Trigger dynamic updates — are they announced?
- Activate icon buttons — are their labels announced?
- Open and close expandable elements — does `aria-expanded` update?

**Browser DevTools** also help. In Chrome DevTools, the **Accessibility panel** (inside the Elements tab) shows the accessibility tree for any selected element — the role, name, state, and properties that assistive technology sees.

---

### **Common ARIA Mistakes 🐞**

#### **Mistake 1: Using ARIA instead of semantic HTML**

```html
<!-- ❌ Reinventing the wheel -->
<div role="button" tabindex="0">Click me</div>

<!-- ✅ Use the native element -->
<button>Click me</button>
```

---

#### **Mistake 2: Hiding focusable elements with `aria-hidden`**

```html
<!-- ❌ Focusable button hidden from screen readers — keyboard users get stuck -->
<div aria-hidden="true">
  <button>Submit</button>
</div>
```

If something is hidden from assistive technology, it should also not be keyboard-focusable.

---

#### **Mistake 3: Not updating states dynamically**

```html
<button aria-expanded="false">Menu</button>
```

If the menu opens but `aria-expanded` stays `false`, screen reader users are told the menu is still closed. Always update ARIA states with JavaScript when the UI state changes.

---

#### **Mistake 4: Using `aria-label` to override visible text**

```html
<!-- ❌ aria-label contradicts visible text — confusing for all users -->
<button aria-label="Delete item">Save</button>
```

When an element has visible text, the `aria-label` overrides it for screen readers. A sighted user sees "Save" but a screen reader user hears "Delete item." Never use `aria-label` to say something different from what's visually shown.

---

#### **Mistake 5: Using `aria-live="assertive"` too liberally**

```html
<!-- ❌ Assertive for non-critical updates — interrupts and distracts -->
<div aria-live="assertive" id="search-results-count">247 results found</div>
```

`assertive` interrupts whatever the screen reader is currently reading. For non-critical updates like result counts, always use `polite`.

---

### **Key Takeaways 📋**

- ARIA adds meaning and state information that HTML alone can't express — it only affects assistive technology, not visual appearance
- The first rule of ARIA: don't use it if a native HTML element already handles it
- Roles define what an element _is_ — use them for custom components with no semantic HTML equivalent
- States reflect current conditions (`aria-expanded`, `aria-checked`) and must be updated dynamically with JavaScript when UI state changes
- Properties define relationships and labels (`aria-label`, `aria-labelledby`, `aria-describedby`)
- Use `aria-label` when no visible text exists, `aria-labelledby` when visible text can serve as the label
- `aria-hidden="true"` removes elements from the accessibility tree — never apply it to focusable content
- `aria-live="polite"` announces dynamic updates without interrupting — use `assertive` only for critical alerts
- Test with a real screen reader and browser DevTools to verify ARIA is working as intended

---

## **Accessible Forms ♿**

Forms are one of the most critical areas of web accessibility. They're how users search, log in, make purchases, send messages, and interact with services. A form that's inaccessible doesn't just create a poor experience. It can block a user from completing an essential task.

---

### **Why Forms Need Special Attention**

Forms introduce a specific accessibility challenge: inputs on their own have no inherent meaning. A text field is just a box. Without proper labelling and structure, a screen reader user has no way of knowing what information goes where.

Additionally, forms involve interaction — typing, selecting, submitting — which means keyboard accessibility and error handling both need careful consideration.

---

### **Labels and Inputs**

Every input field needs a visible, programmatically associated label. "Programmatically associated" means the label is connected to the input in the HTML, not just placed visually nearby.

**The correct way — using `for` and `id`:**

```html
<label for="email">Email Address</label> <input type="email" id="email" />
```

The `for` attribute on the label matches the `id` on the input. This creates an explicit connection that:

- Tells screen readers which label belongs to which input. When focus lands on the input, the screen reader announces "Email Address"
- Makes the label clickable. Clicking the label focuses the corresponding input, increasing the clickable target area
- Remains clear even when the visual layout places the label and input far apart

**What happens without it:**

```html
<!-- ❌ Visually looks fine but has no programmatic connection -->
<p>Email Address</p>
<input type="email" />
```

A screen reader user tabs to this input and hears only "edit text". No information about what to type. The visual proximity of the text means nothing to assistive technology.

---

### **Wrapping Inputs in a `<form>` Element**

All input fields should be wrapped in a `<form>` element. This isn't just structural preference. It has direct functional consequences:

- Inputs outside a `<form>` do not trigger browser validation when submitted
- Inputs outside a `<form>` do not respond to the Enter key for submission
- Screen readers use the `<form>` landmark to help users navigate to and understand form regions

```html
<!-- ❌ No form element — validation and Enter key won't work -->
<label for="name">Name</label>
<input type="text" id="name" />
<button>Submit</button>

<!-- ✅ Correct — wrapped in form -->
<form>
  <label for="name">Name</label>
  <input type="text" id="name" />
  <button type="submit">Submit</button>
</form>
```

---

### **Input Types**

Using the correct `type` attribute on inputs is an accessibility and usability consideration. The browser uses the type to:

- Show the appropriate keyboard on mobile devices (`type="email"` shows an email keyboard, `type="tel"` shows a number pad)
- Apply appropriate built-in validation
- Communicate the expected input to assistive technology

```html
<input type="text" />
<!-- Generic text -->
<input type="email" />
<!-- Email address -->
<input type="password" />
<!-- Hidden characters -->
<input type="tel" />
<!-- Phone number -->
<input type="number" />
<!-- Numeric input -->
<input type="date" />
<!-- Date picker -->
<input type="checkbox" />
<!-- Checkbox -->
<input type="radio" />
<!-- Radio button -->
<input type="search" />
<!-- Search field -->
```

Always use the most specific type that matches the expected input. Not just `type="text"` for everything.

---

### **Required Fields**

When a field is required, communicate that both visually and programmatically. Don't rely on colour or an asterisk alone. Screen readers need an explicit signal.

```html
<label for="email">
  Email Address
  <span aria-hidden="true">*</span>
</label>
<input type="email" id="email" required aria-required="true" />
```

**What's happening here:**

- `required` triggers browser built-in validation
- `aria-required="true"` explicitly tells screen readers the field is required
- The visual asterisk has `aria-hidden="true"`. Screen readers don't need to hear "asterisk", the `aria-required` already communicates the requirement

Include a note at the top of the form explaining what the asterisk means for sighted users:

```html
<form>
  <p>Fields marked with <span aria-hidden="true">*</span> are required.</p>

  <label for="name">Name <span aria-hidden="true">*</span></label>
  <input type="text" id="name" required aria-required="true" />
</form>
```

---

### **Grouping Related Fields**

When fields are logically related, like a set of radio buttons or a group of address fields then wrap them in a `<fieldset>` with a `<legend>`. The legend acts as a label for the entire group.

```html
<fieldset>
  <legend>Preferred Contact Method</legend>

  <input type="radio" id="contact-email" name="contact" value="email" />
  <label for="contact-email">Email</label>

  <input type="radio" id="contact-phone" name="contact" value="phone" />
  <label for="contact-phone">Phone</label>

  <input type="radio" id="contact-post" name="contact" value="post" />
  <label for="contact-post">Post</label>
</fieldset>
```

Without `<fieldset>` and `<legend>`, a screen reader user hears "Email, radio button" with no context about what the choice is for. With them, they hear "Preferred Contact Method — Email, radio button" — the group context comes with every option.

```html
<!-- Address fields grouped together -->
<fieldset>
  <legend>Delivery Address</legend>

  <label for="street">Street</label>
  <input type="text" id="street" />

  <label for="city">City</label>
  <input type="text" id="city" />

  <label for="postcode">Postcode</label>
  <input type="text" id="postcode" />
</fieldset>
```

---

### **Placeholder Text**

Placeholder text is not a label. It disappears when the user starts typing, which means:

- Users who need to pause and check what a field expects lose that information mid-entry
- Screen readers handle placeholder text inconsistently across browsers
- Low contrast placeholder text (which is standard in most browsers) fails contrast requirements

```html
<!-- ❌ Placeholder used as the only label -->
<input type="email" placeholder="Email Address" />

<!-- ✅ Proper label with optional placeholder for hints -->
<label for="email">Email Address</label>
<input type="email" id="email" placeholder="e.g. name@example.com" />
```

Placeholder text is fine as a supplementary hint — an example format or additional context. It should never be the primary way a field is identified.

---

### **Error Messages**

When form validation fails, error messages need to be:

- **Visible** — not hidden or only indicated by colour
- **Descriptive** — telling the user what went wrong and how to fix it
- **Programmatically associated** — connected to the relevant input via `aria-describedby`
- **Announced** — appearing in a way screen readers will communicate

```html
<label for="email">Email Address</label>
<input
  type="email"
  id="email"
  aria-describedby="email-error"
  aria-invalid="true"
/>
<p id="email-error" role="alert">
  Please enter a valid email address, e.g. name@example.com
</p>
```

**What's happening here:**

- `aria-invalid="true"` tells screen readers the field has an error
- `aria-describedby="email-error"` links the input to its error message — screen readers read the error when the input is focused
- `role="alert"` on the error message causes screen readers to announce it immediately when it appears

**Error messages must describe the problem specifically:**

```html
<!-- ❌ Vague — tells the user nothing useful -->
<p>Invalid input</p>

<!-- ✅ Specific — tells the user what went wrong and how to fix it -->
<p>Password must be at least 8 characters and include one number.</p>
```

---

### **Autocomplete**

The `autocomplete` attribute helps browsers and password managers fill in information automatically. For users with cognitive or motor impairments, not having to retype the same information repeatedly is a significant accessibility benefit.

```html
<input type="text" id="name" autocomplete="name" />
<input type="email" id="email" autocomplete="email" />
<input type="tel" id="phone" autocomplete="tel" />
<input type="text" id="street" autocomplete="street-address" />
<input type="text" id="postcode" autocomplete="postal-code" />
```

Common `autocomplete` values include `name`, `email`, `tel`, `current-password`, `new-password`, `street-address`, `postal-code`, and `country`. A full list is available in the [MDN autocomplete documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/autocomplete).

---

### **A Complete Accessible Form Example**

Putting everything together:

```html
<form>
  <p>Fields marked with <span aria-hidden="true">*</span> are required.</p>

  <label for="full-name"> Full Name <span aria-hidden="true">*</span> </label>
  <input
    type="text"
    id="full-name"
    required
    aria-required="true"
    autocomplete="name"
  />

  <label for="email"> Email Address <span aria-hidden="true">*</span> </label>
  <input
    type="email"
    id="email"
    required
    aria-required="true"
    autocomplete="email"
    aria-describedby="email-error"
    aria-invalid="false"
  />
  <p id="email-error" role="alert" hidden>
    Please enter a valid email address, e.g. name@example.com
  </p>

  <fieldset>
    <legend>Preferred Contact Method</legend>

    <input type="radio" id="contact-email" name="contact" value="email" />
    <label for="contact-email">Email</label>

    <input type="radio" id="contact-phone" name="contact" value="phone" />
    <label for="contact-phone">Phone</label>
  </fieldset>

  <button type="submit">Send Message</button>
</form>
```

---

### **How to Test Form Accessibility**

**Keyboard only:**
Tab through every field without touching the mouse. Every input should be reachable, labels should be announced, and submitting with Enter should work.

**Screen reader:**
Activate a screen reader and tab through the form. Verify:

- Each field announces its label when focused
- Required fields are identified as required
- Error messages are announced when they appear
- Grouped fields announce their group context

**Browser validation:**
Submit the form with empty required fields and invalid values. Verify the browser communicates errors clearly.

**Automated tools:**
Browser extensions like **axe DevTools** or **WAVE** can catch common form accessibility issues automatically like missing labels, missing form elements, and invalid ARIA usage.

---

### **Common Mistakes 🐞**

#### **Mistake 1: Using placeholder as a label**

```html
<!-- ❌ Label disappears when user starts typing -->
<input type="text" placeholder="Full Name" />

<!-- ✅ Always use a proper label -->
<label for="name">Full Name</label>
<input type="text" id="name" placeholder="e.g. Jane Smith" />
```

---

#### **Mistake 2: Mismatched `for` and `id`**

```html
<!-- ❌ for and id don't match — no programmatic connection -->
<label for="user-email">Email</label>
<input type="email" id="email" />

<!-- ✅ for and id match exactly -->
<label for="email">Email</label>
<input type="email" id="email" />
```

---

#### **Mistake 3: Indicating required fields with colour only**

```html
<!-- ❌ Red colour alone — invisible to colour blind users -->
<label style="color: red">Email</label>
<input type="email" id="email" />

<!-- ✅ Colour plus text plus aria-required -->
<label for="email">Email <span aria-hidden="true">*</span></label>
<input type="email" id="email" required aria-required="true" />
```

---

#### **Mistake 4: Vague error messages**

```html
<!-- ❌ Tells the user nothing useful -->
<p>Error</p>

<!-- ✅ Specific and actionable -->
<p>Email address must include an @ symbol, e.g. name@example.com</p>
```

---

#### **Mistake 5: Inputs outside a `<form>` element**

```html
<!-- ❌ No form element — Enter key and validation won't work -->
<input type="text" id="search" />
<button>Search</button>

<!-- ✅ Wrapped in form -->
<form role="search">
  <label for="search">Search</label>
  <input type="text" id="search" />
  <button type="submit">Search</button>
</form>
```

---

### **Key Takeaways 📋**

- Every input needs a programmatically associated label using matching `for` and `id` attributes
- All inputs should be wrapped in a `<form>` element for validation and keyboard submission to work
- Use the most specific `type` attribute that matches the expected input
- Required fields need both `required` and `aria-required="true"` — don't rely on colour or asterisks alone
- Group related fields with `<fieldset>` and `<legend>` to provide context for each option
- Placeholder text is not a label — it disappears and is handled inconsistently by screen readers
- Error messages must be visible, descriptive, and linked to their input with `aria-describedby`
- Use `autocomplete` attributes to reduce the burden of re-entering common information
- Test forms with keyboard only and a screen reader to catch what automated tools miss

---

## **Color and Contrast :art: **

Color is one of the most common accessibility pitfalls in web design. It's easy to choose colors that look great on a calibrated monitor in a well-lit room and not realize they're unreadable for a significant portion of your users. This section covers what contrast means, why it matters, and how to get it right.

---

### **Why Color Alone Is Never Enough**

Before getting into contrast ratios, there's a foundational rule:

**Never use color as the only way to convey information.**

Around 8% of men and 0.5% of women have some form of color blindness. The most common type is red-green color blindness — distinguishing red from green is difficult or impossible. If your form shows valid fields in green and invalid fields in red with no other visual difference, a significant portion of your users can't tell which is which.

```html
<!-- ❌ Color only — invisible distinction for color blind users -->
<input style="border-color: green" />
<!-- Valid -->
<input style="border-color: red" />
<!-- Invalid -->

<!-- ✅ Color plus additional indicator -->
<input style="border-color: green" aria-invalid="false" />
<input style="border-color: red" aria-invalid="true" />
<p>✗ Please enter a valid email address</p>
```

Color can be part of how you communicate something — it just can't be the _only_ way. Always pair color with text, icons, patterns, or other visual indicators.

**Common places this goes wrong:**

- Required fields marked only with a red asterisk and no explanation
- Error states shown only by turning a border red
- Links that are only distinguished from surrounding text by color
- Charts and graphs that use color as the only way to identify data series

---

### **What Contrast Ratio Means**

Contrast ratio is a numerical measurement of how different two colors are in terms of their relative luminance — how much light they emit or reflect. It's expressed as a ratio like `4.5:1` or `7:1`.

The higher the ratio, the more contrast between the two colors. The scale runs from `1:1` (identical colors, no contrast at all) to `21:1` (pure black on pure white, maximum contrast).

```
1:1   → No contrast   (white text on white background)
2:1   → Very low      (light gray on white)
4.5:1 → AA standard   (minimum for normal text)
7:1   → AAA standard  (enhanced, easier to read)
21:1  → Maximum       (black on white)
```

---

### **The WCAG Contrast Requirements**

WCAG defines minimum contrast ratios at two levels:

#### **Level AA — The Standard Target**

| Text Type                            | Minimum Ratio |
| ------------------------------------ | ------------- |
| Normal text (below 18pt / 14pt bold) | 4.5:1         |
| Large text (18pt+ / 14pt+ bold)      | 3:1           |
| UI components and graphical elements | 3:1           |

#### **Level AAA — Enhanced**

| Text Type   | Minimum Ratio |
| ----------- | ------------- |
| Normal text | 7:1           |
| Large text  | 4.5:1         |

**Why does large text have a lower requirement?** Larger text is inherently easier to read even at lower contrast — the letterforms are bigger and the eye can distinguish them more easily. Smaller text needs higher contrast to remain legible.

**What counts as large text?**

- 18pt (24px) or larger in regular weight
- 14pt (approximately 18.67px) or larger in bold weight

---

### **What's Actually Happening With Contrast**

Contrast ratio isn't just about how dark or light a color looks to you. It's calculated from the mathematical luminance values of the two colors. Two colors that look quite different to you might have a low contrast ratio, and two colors that seem similar might have a high one.

This is why you can't reliably judge contrast by eye. A medium blue on a white background might look perfectly readable to you but fail the 4.5:1 requirement. A dark navy on black might look obviously unreadable but the math confirms it.

```
White (#ffffff) on White (#ffffff):  1:1   ← No contrast
Black (#000000) on White (#ffffff):  21:1  ← Maximum contrast
#767676 on White (#ffffff):          4.48:1 ← Just below AA for normal text
#757575 on White (#ffffff):          4.6:1  ← Just above AA for normal text
```

The difference between those last two hex codes is almost invisible to the eye but one passes and one fails. This is why you always use a tool to check contrast rather than guessing.

---

### **Checking Contrast**

#### **Browser DevTools**

Chrome and Firefox DevTools both include contrast checking built in:

1. Open DevTools (F12)
2. Select an element with text
3. In the Styles panel, click the color swatch next to the `color` property
4. The color picker shows the contrast ratio against the background
5. A single ✓ means AA pass, double ✓✓ means AAA pass, ✗ means fail

#### **Online Tools**

- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) — enter two hex values and see the ratio and pass/fail for each WCAG level
- [Coolors Contrast Checker](https://coolors.co/contrast-checker) — visual contrast checker with sliders
- [Who Can Use](https://www.whocanuse.com) — shows how a color combination looks for different types of color blindness

#### **Browser Extensions**

- **axe DevTools** — audits the entire page and flags contrast failures with the specific elements and their ratios
- **WAVE** — highlights contrast errors directly on the page

#### **Design Tools**

Figma has contrast checking built into its color picker. Most professional design tools now include accessibility checking features — use them during design, before a single line of code is written.

---

### **Common Contrast Mistakes**

#### **Light gray text on white**

The most common failure. Light gray text looks clean and modern but frequently fails contrast requirements for body text.

```css
/* ❌ Fails AA — ratio approximately 2.3:1 */
body {
  color: #aaaaaa;
  background: #ffffff;
}

/* ✅ Passes AA — ratio approximately 7:1 */
body {
  color: #595959;
  background: #ffffff;
}
```

#### **White text on light brand colors**

Brand colors are often chosen for visual appeal, not contrast. White text on a light brand color is a frequent failure.

```css
/* ❌ White on a medium blue — may fail depending on the exact shade */
.button {
  color: #ffffff;
  background-color: #6699cc;
}

/* ✅ Darken the background or use dark text instead */
.button {
  color: #ffffff;
  background-color: #1a4f8a; /* Darker shade passes */
}
```

#### **Placeholder text**

Browser default placeholder text is intentionally low contrast — it's designed to look different from real input. Most default placeholder styles fail WCAG contrast requirements.

```css
/* ✅ Override placeholder to meet contrast requirements */
::placeholder {
  color: #767676; /* Minimum for AA on white */
  opacity: 1; /* Firefox reduces opacity by default */
}
```

#### **Disabled elements**

WCAG explicitly exempts disabled UI components from contrast requirements — the low contrast is intentional to signal unavailability. However, if you style a disabled-looking element that's actually still active, that's a problem.

---

### **Color Blindness Simulation**

Beyond contrast ratios, it's worth testing how your design looks for users with color blindness.

**Browser DevTools:**
Chrome DevTools includes a color blindness emulator:

1. Open DevTools (F12)
2. Press `Cmd+Shift+P` (Mac) or `Ctrl+Shift+P` (Windows) to open the command palette
3. Type "rendering" and select "Show Rendering"
4. Scroll to "Emulate vision deficiencies"
5. Select a color blindness type from the dropdown

This renders the entire page as it would appear to someone with that vision type — you can immediately see if critical information is lost.

**Types available:**

- Deuteranopia (red-green, most common)
- Protanopia (red-green, different type)
- Tritanopia (blue-yellow)
- Achromatopsia (full color blindness — sees only grayscale)

---

### **Dark Mode and Contrast**

If your website supports dark mode via `prefers-color-scheme`, contrast needs to be verified in both modes separately. A color combination that passes in light mode may fail in dark mode if the background and text colors aren't recalculated carefully.

```css
:root {
  --text: #1a1a1a; /* Passes on white background */
  --background: #ffffff;
}

@media (prefers-color-scheme: dark) {
  :root {
    --text: #e0e0e0; /* Must verify this passes on dark background */
    --background: #121212;
  }
}
```

Check contrast ratios for both themes — don't assume that swapping light and dark colors automatically produces passing contrast.

---

### **Key Takeaways 📋**

- Never use color as the only way to convey information — always pair it with text, icons, or other indicators
- Contrast ratio measures the luminance difference between two colors — higher is more readable
- WCAG AA requires 4.5:1 for normal text, 3:1 for large text and UI components
- You can't reliably judge contrast by eye — always use a tool to verify
- The most common failures are light gray text on white, white text on light brand colors, and low-contrast placeholder text
- Test with color blindness simulation in DevTools to verify information isn't lost for color blind users
- If you support dark mode, verify contrast in both light and dark themes independently

---

## **Images and Alt Text 🖼️**

Images are a fundamental part of the web, but they're invisible to screen readers unless you explicitly describe them. The `alt` attribute is how you bridge that gap but writing good alt text is more nuanced than just describing what you see.

---

### **What Alt Text Does**

The `alt` attribute on an `<img>` element provides a text alternative for the image. It serves three purposes:

1. **Screen readers** announce the alt text when they encounter an image — giving users who can't see the image an equivalent understanding of what it conveys
2. **Broken images** display the alt text when the image fails to load — giving all users some information about what was there
3. **Search engines** use alt text to understand image content — contributing to SEO

```html
<img
  src="sourdough-bread.jpg"
  alt="A round sourdough loaf with a scored cross pattern on a wooden board"
/>
```

---

### **The Core Question: What Does This Image Convey?**

The most important question when writing alt text isn't "what does this image show?" — it's "what information does this image convey in this context?"

The same image can need completely different alt text depending on where and why it's used:

```html
<!-- Used in a recipe article — convey what the finished result looks like -->
<img
  src="sourdough.jpg"
  alt="A golden-brown sourdough loaf with a crisp, scored crust"
/>

<!-- Used in an article about bread scoring techniques — different context, different focus -->
<img
  src="sourdough.jpg"
  alt="A sourdough loaf showing a cross scoring pattern that expanded evenly during baking"
/>

<!-- Used purely as decoration between sections -->
<img src="sourdough.jpg" alt="" />
```

Context determines what's relevant. Always ask: if this image weren't here, what information would the user be missing?

---

### **Decorative Images — When to Use Empty Alt Text**

Not every image conveys information. Some images are purely decorative — background textures, dividers, illustrations that add visual interest without adding meaning. These should have an empty `alt` attribute:

```html
<img src="decorative-swirl.png" alt="" />
```

An empty `alt=""` is not the same as omitting the `alt` attribute entirely:

- `alt=""` — tells the screen reader "this image is decorative, skip it"
- No `alt` attribute — the screen reader announces the filename instead (`"decorative-swirl dot png"`) which is meaningless and disruptive

**How to decide if an image is decorative:**

Ask yourself: if this image were removed, would any user lose information or context? If the answer is no — it's decorative. If yes — it needs alt text.

```html
<!-- ❌ Missing alt — screen reader announces the filename -->
<img src="hero-background.jpg" />

<!-- ✅ Decorative — explicitly marked as such -->
<img src="hero-background.jpg" alt="" />

<!-- ✅ Informative — describes what the image conveys -->
<img
  src="team-photo.jpg"
  alt="The five-person development team gathered around a whiteboard"
/>
```

---

### **Writing Good Alt Text**

#### **Be specific and descriptive**

Alt text should convey the meaning of the image, not just its existence.

```html
<!-- ❌ Too vague — tells the user almost nothing -->
<img src="chart.png" alt="Chart" />

<!-- ✅ Specific — conveys what the chart shows -->
<img
  src="chart.png"
  alt="Bar chart showing monthly sales figures from January to June 2026, with April having the highest sales at £42,000"
/>
```

#### **Don't start with "Image of" or "Photo of"**

Screen readers already announce that it's an image before reading the alt text. Starting with "Image of" is redundant — the user hears "Image, image of a cat" which is unnecessary repetition.

```html
<!-- ❌ Redundant prefix -->
<img src="cat.jpg" alt="Photo of a cat sitting on a windowsill" />

<!-- ✅ Just the description -->
<img src="cat.jpg" alt="A cat sitting on a windowsill watching birds outside" />
```

#### **Include relevant text in images**

If an image contains text — a banner, a poster, a screenshot — that text must be in the alt attribute:

```html
<!-- ❌ The text in the image is lost -->
<img src="sale-banner.jpg" alt="Sale banner" />

<!-- ✅ The text content is preserved -->
<img
  src="sale-banner.jpg"
  alt="Summer Sale — 50% off all items until July 31st"
/>
```

#### **Match the level of detail to the context**

For functional images like buttons or links, alt text should describe the function, not the appearance:

```html
<!-- ❌ Describes appearance — not what it does -->
<a href="/search">
  <img src="magnifying-glass.png" alt="Magnifying glass icon" />
</a>

<!-- ✅ Describes function -->
<a href="/search">
  <img src="magnifying-glass.png" alt="Search" />
</a>
```

---

### **Complex Images**

Some images are too complex to describe adequately in a short alt text — data charts, diagrams, maps, infographics. For these, alt text alone isn't enough.

**Approach 1: Describe the key takeaway in alt text, link to full description**

```html
<img
  src="annual-revenue-chart.png"
  alt="Line chart showing annual revenue growth from 2020 to 2025"
  aria-describedby="chart-description"
/>
<p id="chart-description">
  Revenue grew steadily from £1.2M in 2020 to £3.8M in 2025, with the sharpest
  growth occurring between 2022 and 2023 when revenue increased by 48%.
</p>
```

**Approach 2: Provide the data in an accessible table alongside the chart**

```html
<figure>
  <img
    src="revenue-chart.png"
    alt="Bar chart of annual revenue 2020–2025, data in table below"
  />
  <figcaption>Annual Revenue 2020–2025</figcaption>
</figure>

<table>
  <caption>
    Annual Revenue Data
  </caption>
  <thead>
    <tr>
      <th>Year</th>
      <th>Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2020</td>
      <td>£1.2M</td>
    </tr>
    <tr>
      <td>2021</td>
      <td>£1.8M</td>
    </tr>
    <tr>
      <td>2022</td>
      <td>£2.1M</td>
    </tr>
    <tr>
      <td>2023</td>
      <td>£3.1M</td>
    </tr>
    <tr>
      <td>2024</td>
      <td>£3.5M</td>
    </tr>
    <tr>
      <td>2025</td>
      <td>£3.8M</td>
    </tr>
  </tbody>
</table>
```

The chart is a visual aid. The table is the accessible data. Both together serve all users.

---

### **Images Inside Links and Buttons**

When an image is the only content inside a link or button, the alt text becomes the accessible name for that interactive element. It should describe the destination or action — not the image itself.

```html
<!-- Link with image only — alt text names the destination -->
<a href="/home">
  <img src="logo.png" alt="Return to homepage" />
</a>

<!-- Button with image only — alt text names the action -->
<button>
  <img src="send-icon.png" alt="Send message" />
</button>
```

If the image is alongside visible text that already describes the link or button, use empty alt text to avoid repetition:

```html
<!-- Visible text already describes the link — image is decorative here -->
<a href="/home">
  <img src="home-icon.png" alt="" />
  Home
</a>
```

---

### **The `<figure>` and `<figcaption>` Elements**

When an image has a visible caption, use `<figure>` and `<figcaption>` to associate them semantically:

```html
<figure>
  <img
    src="northern-lights.jpg"
    alt="Green and purple aurora borealis over a snow-covered mountain range at night"
  />
  <figcaption>
    Aurora borealis photographed in Tromsø, Norway, February 2026
  </figcaption>
</figure>
```

When `<figcaption>` is present, you can sometimes shorten the alt text if the caption already covers the description but only if the caption is genuinely informative. The alt text and figcaption serve different purposes: alt text is for users who can't see the image, figcaption is visible context for all users.

---

### **SVG Images**

SVGs used as images need accessible names just like `<img>` elements. The approach depends on how the SVG is used:

**SVG as an `<img>` tag:**

```html
<img src="icon.svg" alt="Download file" />
```

**Inline SVG — use `<title>` and `aria-labelledby`:**

```html
<svg aria-labelledby="svg-title" role="img">
  <title id="svg-title">Download file</title>
  <!-- SVG paths -->
</svg>
```

**Decorative inline SVG:**

```html
<svg aria-hidden="true">
  <!-- SVG paths -->
</svg>
```

---

### **How to Test Image Accessibility**

**Screen reader test:**
Navigate the page with a screen reader and listen to how each image is announced. Ask yourself — does what you hear give you the same understanding as seeing the image?

**Disable images:**
Some browsers and extensions let you disable image loading. Navigate the page with images off and check whether alt text provides adequate context.

**Automated tools:**
axe DevTools and WAVE both flag images with missing alt attributes. They can't judge whether alt text is _good_ — only whether it exists — but they catch the most obvious failures.

**Manual review:**
Cover each image on the page with your hand and read only the alt text. Does it give you the information the image was conveying? If not, rewrite it.

---

### **Common Mistakes 🐞**

#### **Mistake 1: Missing alt attribute entirely**

```html
<!-- ❌ Screen reader announces the filename -->
<img src="profile-photo.jpg" />

<!-- ✅ Always include alt -->
<img src="profile-photo.jpg" alt="Sarah Johnson, Lead Developer" />
```

---

#### **Mistake 2: Using the filename as alt text**

```html
<!-- ❌ Meaningless to screen reader users -->
<img src="IMG_20260315_142233.jpg" alt="IMG_20260315_142233" />

<!-- ✅ Describe what the image shows -->
<img
  src="IMG_20260315_142233.jpg"
  alt="The conference main stage during the opening keynote"
/>
```

---

#### **Mistake 3: The same alt text for every image**

```html
<!-- ❌ All images described identically — useless -->
<img src="product-1.jpg" alt="Product image" />
<img src="product-2.jpg" alt="Product image" />
<img src="product-3.jpg" alt="Product image" />

<!-- ✅ Each image described specifically -->
<img src="product-1.jpg" alt="Red leather wallet with six card slots" />
<img src="product-2.jpg" alt="Brown canvas backpack with laptop compartment" />
<img src="product-3.jpg" alt="Black minimalist card holder" />
```

---

#### **Mistake 4: Omitting alt on decorative images instead of using empty alt**

```html
<!-- ❌ Missing alt — screen reader reads filename -->
<img src="divider-wave.png" />

<!-- ✅ Empty alt — screen reader skips it -->
<img src="divider-wave.png" alt="" />
```

---

#### **Mistake 5: Redundant alt text on linked images**

```html
<!-- ❌ Screen reader hears "Home link, home icon image, Home" -->
<a href="/">
  <img src="home.png" alt="Home icon" />
  Home
</a>

<!-- ✅ Decorative — visible text already labels the link -->
<a href="/">
  <img src="home.png" alt="" />
  Home
</a>
```

---

### **Key Takeaways 📋**

- The `alt` attribute provides a text alternative for images — always include it on every `<img>` element
- Ask "what does this image _convey_ in this context?" not just "what does it show?"
- Decorative images use `alt=""` — empty, not missing — to tell screen readers to skip them
- Don't start alt text with "Image of" or "Photo of" — screen readers already announce it's an image
- If an image contains text, that text must be included in the alt attribute
- For linked or button images, alt text should describe the action or destination, not the image appearance
- Complex images like charts need extended descriptions — either in visible text or linked descriptions
- Use `<figure>` and `<figcaption>` to semantically associate images with their visible captions
- Inline SVGs need `aria-hidden="true"` if decorative, or `<title>` and `aria-labelledby` if informative

---

## **Interactive Elements ♿**

Every element a user can interact with — links, buttons, form controls, custom components — carries specific accessibility responsibilities. Interaction is where accessibility failures have the most direct impact: a button that can't be reached by keyboard, a modal that traps focus, a custom dropdown that's invisible to a screen reader. These aren't minor inconveniences, they completely block users from completing tasks.

---

### **Keyboard Navigation**

A significant portion of users navigate entirely by keyboard. People with motor impairments, power users, and screen reader users. Every interactive element on a page must be reachable and operable without a mouse.

**The basic keyboard navigation model:**

| Key           | Action                                                 |
| ------------- | ------------------------------------------------------ |
| `Tab`         | Move focus forward through interactive elements        |
| `Shift + Tab` | Move focus backward                                    |
| `Enter`       | Activate a link or button                              |
| `Space`       | Activate a button, toggle a checkbox                   |
| `Arrow keys`  | Navigate within components (menus, radio groups, tabs) |
| `Escape`      | Close a modal, dropdown, or tooltip                    |

**Testing keyboard navigation:**

Put your mouse aside and Tab through your entire page. Every interactive element should:

- Receive visible focus in a logical order
- Be activatable with Enter or Space
- Produce the expected result

If you reach a point where Tab doesn't move forward, or focus disappears, or an element is skipped entirely —> that's a keyboard accessibility failure.

---

### **Focus Management**

Focus is the browser's way of tracking which element is currently active for keyboard input. Managing focus correctly is one of the more technically involved parts of accessibility — but it's critical for complex interactions.

#### **Visible Focus Indicators**

Every interactive element must have a visible focus indicator — a visual signal showing which element currently has keyboard focus. Browsers provide a default focus outline, but many developers remove it because it looks visually inconsistent:

```css
/* ❌ Never do this — removes focus visibility for keyboard users */
* {
  outline: none;
}

button:focus {
  outline: none;
}
```

Removing the focus outline without providing an alternative leaves keyboard users with no visual indication of where they are on the page. This is a WCAG failure.

**The correct approach — style focus rather than remove it:**

```css
/* ✅ Custom focus style that's visible and on-brand */
button:focus-visible {
  outline: 3px solid #005fcc;
  outline-offset: 2px;
  border-radius: 2px;
}
```

`:focus-visible` is preferred over `:focus`. It only shows the focus indicator when navigating by keyboard, not when clicking with a mouse. This satisfies both sighted mouse users (who find the outline visually distracting when clicking) and keyboard users (who need it to navigate).

**What makes a good focus indicator:**

- High contrast against the surrounding background (3:1 minimum per WCAG)
- At least 2px thick
- Visible against both light and dark backgrounds
- Consistent across the page

---

#### **Focus Order**

Focus should move through the page in a logical sequence. Generally matching the visual reading order, left to right and top to bottom. The Tab order is determined by the order elements appear in the HTML, not their visual position via CSS.

```html
<!-- ❌ Visual order and DOM order don't match — Tab order is confusing -->
<div style="display: flex; flex-direction: row-reverse">
  <button>Third visually, first in DOM</button>
  <button>Second visually, second in DOM</button>
  <button>First visually, third in DOM</button>
</div>

<!-- ✅ DOM order matches visual order -->
<div style="display: flex">
  <button>First</button>
  <button>Second</button>
  <button>Third</button>
</div>
```

If CSS repositions elements visually, the Tab order still follows the HTML order. Keep DOM order and visual order aligned.

---

#### **Managing Focus Programmatically**

Some interactions require moving focus with JavaScript — when a modal opens, when content updates dynamically, or when a section expands.

**Opening a modal — move focus inside it:**

```javascript
const modal = document.getElementById("modal");
const firstFocusable = modal.querySelector("button, a, input");

modal.removeAttribute("hidden");
firstFocusable.focus(); // Move focus to first interactive element in modal
```

**Closing a modal — return focus to the trigger:**

```javascript
const triggerButton = document.getElementById("open-modal-btn");

modal.setAttribute("hidden", "");
triggerButton.focus(); // Return focus to where it was before modal opened
```

Without returning focus to the trigger, keyboard users are left disoriented. Their focus position is lost and they have to navigate from the beginning of the page.

---

#### **Focus Trapping in Modals**

When a modal is open, focus must stay inside it. A keyboard user should not be able to Tab out of the modal and interact with content behind it — that content is visually blocked and should be inaccessible.

```javascript
const focusableElements = modal.querySelectorAll(
  'button, a, input, select, textarea, [tabindex]:not([tabindex="-1"])',
);

const firstElement = focusableElements[0];
const lastElement = focusableElements[focusableElements.length - 1];

modal.addEventListener("keydown", (e) => {
  if (e.key !== "Tab") return;

  if (e.shiftKey) {
    // Shift+Tab — going backward
    if (document.activeElement === firstElement) {
      e.preventDefault();
      lastElement.focus(); // Wrap to last element
    }
  } else {
    // Tab — going forward
    if (document.activeElement === lastElement) {
      e.preventDefault();
      firstElement.focus(); // Wrap to first element
    }
  }
});
```

This keeps focus cycling within the modal until it's closed.

---

### **`tabindex`**

The `tabindex` attribute controls whether and how an element participates in keyboard navigation.

| Value           | Effect                                               |
| --------------- | ---------------------------------------------------- |
| `tabindex="0"`  | Adds element to natural Tab order                    |
| `tabindex="-1"` | Removes from Tab order but allows programmatic focus |
| `tabindex="1+"` | Sets explicit order — avoid this                     |

**`tabindex="0"`** — makes a non-interactive element focusable. Use this when you're building a custom interactive component from a non-interactive element:

```html
<div role="button" tabindex="0">Custom Button</div>
```

Though as covered in the ARIA section — if a native element exists, use it instead.

**`tabindex="-1"`** — removes an element from the Tab order but allows JavaScript to focus it programmatically. Used for modal dialogs and dynamic content that should receive focus when opened but not be reachable by Tab otherwise:

```javascript
const modal = document.getElementById("modal");
modal.setAttribute("tabindex", "-1");
modal.focus(); // Works even though it's not in the Tab order
```

**Avoid positive `tabindex` values** (`tabindex="1"`, `tabindex="2"`, etc.). They create an explicit Tab order that overrides the natural DOM order — creating confusing, unpredictable navigation that's nearly impossible to maintain as the page grows.

---

### **Buttons vs Links**

One of the most common semantic mistakes in interactive elements is confusing buttons and links. They look similar and can be styled identically, but they have fundamentally different meanings and keyboard behaviour.

| Element    | Use For                                      | Keyboard Activation |
| ---------- | -------------------------------------------- | ------------------- |
| `<button>` | Actions — submit, open modal, toggle, delete | Enter and Space     |
| `<a>`      | Navigation — go to a URL or page section     | Enter only          |

```html
<!-- ❌ Link used as a button — no href, triggers JavaScript -->
<a href="#" onclick="openModal()">Open Modal</a>

<!-- ✅ Button for actions -->
<button onclick="openModal()">Open Modal</button>

<!-- ❌ Button used as a link — should navigate somewhere -->
<button onclick="window.location='/about'">About Us</button>

<!-- ✅ Link for navigation -->
<a href="/about">About Us</a>
```

**Why it matters beyond semantics:**

- Screen readers announce links and buttons differently — users know what to expect before activating them
- Links can be opened in a new tab, bookmarked, and copied — buttons can't
- Space activates buttons but not links — using a link for an action means keyboard users pressing Space won't trigger it

---

### **Accessible Names for Interactive Elements**

Every interactive element needs an accessible name — the text that screen readers announce when the element receives focus. For elements with visible text, the accessible name is that text. For elements without visible text, you need to provide one explicitly.

**Elements with visible text — accessible name is automatic:**

```html
<button>Save Document</button>
<!-- Accessible name: "Save Document" -->
<a href="/about">About Us</a>
<!-- Accessible name: "About Us" -->
```

**Icon-only elements — provide accessible name via `aria-label`:**

```html
<button aria-label="Close dialog">
  <svg aria-hidden="true">...</svg>
</button>

<a href="/search" aria-label="Search">
  <svg aria-hidden="true">...</svg>
</a>
```

**Multiple identical links — differentiate with `aria-label`:**

```html
<!-- ❌ Screen reader user hears "Read more, Read more, Read more" -->
<a href="/post-1">Read more</a>
<a href="/post-2">Read more</a>
<a href="/post-3">Read more</a>

<!-- ✅ Each link is distinct -->
<a href="/post-1" aria-label="Read more about CSS Grid">Read more</a>
<a href="/post-2" aria-label="Read more about Flexbox">Read more</a>
<a href="/post-3" aria-label="Read more about Accessibility">Read more</a>
```

---

### **Skip Links**

A skip link is a hidden link at the very top of the page that becomes visible when focused, allowing keyboard and screen reader users to jump past the navigation directly to the main content. Without it, keyboard users must Tab through every navigation link on every page load before reaching the actual content.

```html
<!-- First element in the body -->
<a href="#main-content" class="skip-link">Skip to main content</a>

<header>
  <nav><!-- Navigation with many links --></nav>
</header>

<main id="main-content">
  <!-- Page content -->
</main>
```

```css
.skip-link {
  position: absolute;
  top: -100%;
  left: 0;
  padding: 1rem 2rem;
  background: #000000;
  color: #ffffff;
  font-weight: bold;
  z-index: 9999;
  text-decoration: none;
}

.skip-link:focus {
  top: 0; /* Becomes visible when focused */
}
```

When a keyboard user hits Tab as the very first action on the page, the skip link appears. Pressing Enter jumps focus directly to `<main>`. It's invisible to mouse users and doesn't affect the visual design.

---

### **Custom Interactive Components**

Sometimes you need to build interactive components that have no native HTML equivalent — tab panels, accordions, carousels, comboboxes. These require ARIA roles, states, and keyboard behaviour to be implemented manually.

**Example — accessible accordion:**

```html
<div class="accordion">
  <h3>
    <button
      aria-expanded="false"
      aria-controls="section-1-content"
      id="section-1-button"
    >
      What is CSS Grid?
    </button>
  </h3>
  <div
    id="section-1-content"
    role="region"
    aria-labelledby="section-1-button"
    hidden
  >
    <p>CSS Grid is a two-dimensional layout system...</p>
  </div>
</div>
```

```javascript
const button = document.getElementById("section-1-button");
const content = document.getElementById("section-1-content");

button.addEventListener("click", () => {
  const isExpanded = button.getAttribute("aria-expanded") === "true";

  button.setAttribute("aria-expanded", !isExpanded);

  if (isExpanded) {
    content.setAttribute("hidden", "");
  } else {
    content.removeAttribute("hidden");
  }
});
```

The ARIA Authoring Practices Guide (APG) at [w3.org/WAI/ARIA/apg](https://www.w3.org/WAI/ARIA/apg/) documents the expected keyboard behaviour and ARIA patterns for every common component type. Before building a custom component, check the APG — the keyboard interaction patterns are already defined and tested.

---

### **How to Test Interactive Elements**

**Keyboard navigation test:**

- Tab through the entire page without touching the mouse
- Verify every interactive element is reachable
- Verify focus is always visible
- Verify activating elements with Enter and Space works as expected
- Verify modals trap focus and return it on close
- Verify Escape closes modals and dropdowns

**Screen reader test:**

- Navigate by Tab and verify accessible names are announced correctly
- Activate custom components and verify state changes are announced
- Verify skip link works and lands focus in the correct location

**Automated tools:**

- axe DevTools flags missing accessible names, incorrect roles, and focus order issues
- Lighthouse (built into Chrome DevTools) includes an accessibility audit that covers interactive element issues

---

### **Common Mistakes 🐞**

#### **Mistake 1: Removing focus outlines without replacement**

```css
/* ❌ Keyboard users lose all visual orientation */
* {
  outline: none;
}

/* ✅ Style focus instead of removing it */
:focus-visible {
  outline: 3px solid #005fcc;
  outline-offset: 2px;
}
```

---

#### **Mistake 2: Using `<div>` or `<span>` for buttons**

```html
<!-- ❌ Not keyboard focusable, no semantic meaning -->
<div class="btn" onclick="submit()">Submit</div>

<!-- ✅ Native button handles everything correctly -->
<button onclick="submit()">Submit</button>
```

---

#### **Mistake 3: Using links for actions**

```html
<!-- ❌ Links navigate — they shouldn't trigger actions -->
<a href="#" onclick="deleteItem()">Delete</a>

<!-- ✅ Buttons perform actions -->
<button onclick="deleteItem()">Delete</button>
```

---

#### **Mistake 4: Not returning focus after closing a modal**

```javascript
// ❌ Focus is lost — keyboard users don't know where they are
modal.setAttribute("hidden", "");

// ✅ Return focus to the element that opened the modal
modal.setAttribute("hidden", "");
triggerButton.focus();
```

---

#### **Mistake 5: Icon buttons with no accessible name**

```html
<!-- ❌ Screen reader announces nothing useful -->
<button>
  <svg>...</svg>
</button>

<!-- ✅ aria-label provides the accessible name -->
<button aria-label="Delete item">
  <svg aria-hidden="true">...</svg>
</button>
```

---

#### **Mistake 6: Positive tabindex values**

```html
<!-- ❌ Creates unpredictable Tab order -->
<button tabindex="3">First visually</button>
<button tabindex="1">Second visually</button>
<button tabindex="2">Third visually</button>

<!-- ✅ Let the DOM order determine Tab order -->
<button>First</button>
<button>Second</button>
<button>Third</button>
```

---

### **Key Takeaways 📋**

- Every interactive element must be reachable and operable by keyboard alone
- Never remove focus outlines without providing a visible alternative — use `:focus-visible` to style rather than hide
- Focus order should follow the visual reading order — keep DOM order and visual order aligned
- When modals open, move focus inside them; when they close, return focus to the trigger
- Modals must trap focus — keyboard users should not be able to Tab out of an open modal
- `tabindex="0"` adds to Tab order, `tabindex="-1"` allows programmatic focus only — avoid positive values
- Use `<button>` for actions and `<a>` for navigation — they have different keyboard behaviour and screen reader announcements
- Every interactive element needs an accessible name — use `aria-label` for icon-only elements
- Skip links let keyboard users jump past navigation — always include one as the first element in the page
- For custom components, follow the ARIA Authoring Practices Guide for correct keyboard patterns

---

## **Quick Reference 📚**

---

### **Semantic HTML Elements**

| Element        | Purpose                                          |
| -------------- | ------------------------------------------------ |
| `<header>`     | Introductory content for a page or section       |
| `<nav>`        | Primary navigation links                         |
| `<main>`       | Primary page content — only one per page         |
| `<section>`    | Thematic grouping of content with a heading      |
| `<article>`    | Self-contained, redistributable content          |
| `<aside>`      | Tangentially related content, sidebars           |
| `<footer>`     | Closing content for a page or section            |
| `<figure>`     | Self-contained visual with optional caption      |
| `<figcaption>` | Caption associated with a `<figure>`             |
| `<time>`       | Machine-readable date or time                    |
| `<abbr>`       | Abbreviation with full form in `title` attribute |
| `<strong>`     | Content of strong importance                     |
| `<em>`         | Emphasised content                               |

---

### **Heading Rules**

```html
<!-- One h1 per page — the page title -->
<h1>Page Title</h1>

<!-- Sections use h2 -->
<h2>Section Title</h2>

<!-- Subsections use h3 -->
<h3>Subsection Title</h3>

<!-- Never skip levels -->
<!-- ❌ h1 → h3 (skips h2) -->
<!-- ✅ h1 → h2 → h3 -->

<!-- Never choose heading level for visual size — use CSS instead -->
```

---

### **ARIA Quick Reference**

#### **Common Roles**

| Role          | Use For                          |
| ------------- | -------------------------------- |
| `alert`       | Important time-sensitive message |
| `dialog`      | Modal dialog window              |
| `menu`        | List of choices or commands      |
| `menuitem`    | Item within a menu               |
| `tab`         | Tab in a tab panel               |
| `tabpanel`    | Panel associated with a tab      |
| `progressbar` | Progress indicator               |
| `note`        | Supplementary content            |
| `tooltip`     | Contextual popup description     |

#### **Common Attributes**

| Attribute          | Purpose                                            |
| ------------------ | -------------------------------------------------- |
| `aria-label`       | Provides a text label when no visible label exists |
| `aria-labelledby`  | References an existing element as the label        |
| `aria-describedby` | References an element that describes this one      |
| `aria-expanded`    | Whether a collapsible element is open or closed    |
| `aria-hidden`      | Removes element from accessibility tree            |
| `aria-required`    | Whether a form field is required                   |
| `aria-invalid`     | Whether a form field has an error                  |
| `aria-live`        | How to announce dynamic content updates            |
| `aria-controls`    | References the element this one controls           |
| `aria-pressed`     | Whether a toggle button is pressed                 |
| `aria-selected`    | Whether an item is selected                        |
| `aria-disabled`    | Whether an element is disabled                     |

#### **`aria-live` Values**

| Value       | Behaviour                         |
| ----------- | --------------------------------- |
| `off`       | Changes not announced (default)   |
| `polite`    | Announces when user is idle       |
| `assertive` | Announces immediately, interrupts |

---

### **Accessible Forms Patterns**

#### **Basic Input with Label**

```html
<label for="email">Email Address</label>
<input type="email" id="email" autocomplete="email" />
```

#### **Required Field**

```html
<label for="name"> Full Name <span aria-hidden="true">*</span> </label>
<input type="text" id="name" required aria-required="true" />
```

#### **Field with Error**

```html
<label for="email">Email Address</label>
<input
  type="email"
  id="email"
  aria-describedby="email-error"
  aria-invalid="true"
/>
<p id="email-error" role="alert">
  Please enter a valid email address, e.g. name@example.com
</p>
```

#### **Grouped Radio Buttons**

```html
<fieldset>
  <legend>Preferred Contact Method</legend>
  <input type="radio" id="by-email" name="contact" value="email" />
  <label for="by-email">Email</label>
  <input type="radio" id="by-phone" name="contact" value="phone" />
  <label for="by-phone">Phone</label>
</fieldset>
```

---

### **Alt Text Patterns**

```html
<!-- Informative image -->
<img
  src="chart.png"
  alt="Bar chart showing revenue growth from £1.2M in 2020 to £3.8M in 2025"
/>

<!-- Decorative image -->
<img src="divider.png" alt="" />

<!-- Image inside a link -->
<a href="/home">
  <img src="logo.png" alt="Return to homepage" />
</a>

<!-- Image with visible caption -->
<figure>
  <img src="photo.jpg" alt="Five developers gathered around a whiteboard" />
  <figcaption>The team during a planning session, March 2026</figcaption>
</figure>

<!-- Decorative inline SVG -->
<svg aria-hidden="true">...</svg>

<!-- Informative inline SVG -->
<svg role="img" aria-labelledby="svg-title">
  <title id="svg-title">Download file</title>
</svg>
```

---

### **Color and Contrast Requirements**

| Text Type                       | Minimum Ratio (AA) | Enhanced Ratio (AAA) |
| ------------------------------- | ------------------ | -------------------- |
| Normal text                     | 4.5:1              | 7:1                  |
| Large text (18pt+ / 14pt+ bold) | 3:1                | 4.5:1                |
| UI components and graphics      | 3:1                | —                    |

**Contrast checking tools:**

- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Coolors Contrast Checker](https://coolors.co/contrast-checker)
- Chrome DevTools color picker (shows ratio inline)

---

### **Focus Management Patterns**

#### **Custom Focus Style**

```css
/* Style focus, never remove it */
:focus-visible {
  outline: 3px solid #005fcc;
  outline-offset: 2px;
  border-radius: 2px;
}
```

#### **Skip Link**

```html
<a href="#main-content" class="skip-link">Skip to main content</a>
<main id="main-content">...</main>
```

```css
.skip-link {
  position: absolute;
  top: -100%;
  left: 0;
  padding: 1rem 2rem;
  background: #000000;
  color: #ffffff;
  font-weight: bold;
  z-index: 9999;
  text-decoration: none;
}

.skip-link:focus {
  top: 0;
}
```

#### **Modal Focus Management**

```javascript
// Open modal — move focus inside
modal.removeAttribute("hidden");
firstFocusableElement.focus();

// Close modal — return focus to trigger
modal.setAttribute("hidden", "");
triggerButton.focus();
```

---

### **`tabindex` Reference**

| Value           | Effect                                  |
| --------------- | --------------------------------------- |
| `tabindex="0"`  | Adds element to natural Tab order       |
| `tabindex="-1"` | Focusable via JavaScript only, not Tab  |
| `tabindex="1+"` | Avoid — creates unpredictable Tab order |

---

### **Keyboard Navigation Reference**

| Key           | Action                            |
| ------------- | --------------------------------- |
| `Tab`         | Move focus forward                |
| `Shift + Tab` | Move focus backward               |
| `Enter`       | Activate link or button           |
| `Space`       | Activate button, toggle checkbox  |
| `Arrow keys`  | Navigate within components        |
| `Escape`      | Close modal, dropdown, or tooltip |

---

### **Buttons vs Links**

| Element    | Use For                                | Activates With  |
| ---------- | -------------------------------------- | --------------- |
| `<button>` | Actions — submit, open modal, toggle   | Enter and Space |
| `<a href>` | Navigation — go to URL or page section | Enter only      |

---

### **Visibility and Accessibility Tree**

| Method               | Visually Hidden | Hidden from Screen Reader |
| -------------------- | --------------- | ------------------------- |
| `display: none`      | ✅ Yes          | ✅ Yes                    |
| `visibility: hidden` | ✅ Yes          | ✅ Yes                    |
| `opacity: 0`         | ✅ Yes          | ❌ No — still announced   |
| `aria-hidden="true"` | ❌ No           | ✅ Yes                    |
| `.sr-only` class     | ✅ Yes          | ❌ No — still announced   |

#### **Screen Reader Only Class**

```css
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}
```

---

### **Testing Tools**

| Tool                                                                     | Type              | What It Catches                |
| ------------------------------------------------------------------------ | ----------------- | ------------------------------ |
| [axe DevTools](https://www.deque.com/axe/)                               | Browser extension | Automated WCAG audit           |
| [WAVE](https://wave.webaim.org)                                          | Browser extension | Visual accessibility errors    |
| [Lighthouse](https://developer.chrome.com/docs/lighthouse)               | Built into Chrome | Accessibility score and issues |
| [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) | Online tool       | Contrast ratio checking        |
| [Headings Map](https://rumoroso.bitbucket.io/headingsmap/)               | Browser extension | Heading structure outline      |
| VoiceOver (macOS/iOS)                                                    | Screen reader     | Real assistive technology test |
| NVDA (Windows)                                                           | Screen reader     | Real assistive technology test |

---

### **Accessibility Checklist ✅**

#### **Structure**

- ☐ Viewport meta tag present in `<head>`
- ☐ Semantic elements used for page regions (`<header>`, `<nav>`, `<main>`, `<footer>`)
- ☐ Only one `<h1>` per page
- ☐ Heading levels not skipped
- ☐ Heading levels chosen for structure, not visual size
- ☐ Skip link as first element in `<body>`

#### **Images**

- ☐ Every `<img>` has an `alt` attribute
- ☐ Decorative images have `alt=""`
- ☐ Alt text describes what the image conveys, not just what it shows
- ☐ Images containing text have that text in the alt attribute
- ☐ Linked images have alt text describing the destination or action
- ☐ Decorative inline SVGs have `aria-hidden="true"`

#### **Color and Contrast**

- ☐ Normal text meets 4.5:1 contrast ratio
- ☐ Large text meets 3:1 contrast ratio
- ☐ UI components meet 3:1 contrast ratio
- ☐ Color is never the only way information is conveyed
- ☐ Contrast verified in both light and dark mode if applicable
- ☐ Tested with color blindness simulation

#### **Forms**

- ☐ All inputs have associated `<label>` elements with matching `for` and `id`
- ☐ All inputs wrapped in `<form>` element
- ☐ Correct `type` attribute used on all inputs
- ☐ Required fields use both `required` and `aria-required="true"`
- ☐ Required fields indicated with more than color alone
- ☐ Placeholder text not used as the only label
- ☐ Error messages are descriptive and linked via `aria-describedby`
- ☐ Related fields grouped with `<fieldset>` and `<legend>`
- ☐ `autocomplete` attributes used for common personal data fields

#### **Interactive Elements**

- ☐ All interactive elements reachable by keyboard
- ☐ Focus order follows logical reading order
- ☐ Focus indicator always visible — never `outline: none` without replacement
- ☐ `<button>` used for actions, `<a>` used for navigation
- ☐ All interactive elements have accessible names
- ☐ Icon-only buttons have `aria-label`
- ☐ Modals move focus inside on open, return focus on close
- ☐ Modals trap focus while open
- ☐ No positive `tabindex` values

#### **ARIA**

- ☐ Native HTML elements used where possible instead of ARIA
- ☐ ARIA roles only used where no native element exists
- ☐ Dynamic state attributes (`aria-expanded`, `aria-invalid`) updated via JavaScript
- ☐ `aria-hidden="true"` not applied to focusable elements
- ☐ `aria-live` regions use `polite` unless the update is critical

---

### **Resources**

- [MDN Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility) — comprehensive reference
- [The A11y Project Checklist](https://www.a11yproject.com/checklist/) — practical WCAG checklist
- [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/) — keyboard patterns for custom components
- [WebAIM](https://webaim.org) — articles, tools, and training
- [Web Accessibility Initiative](https://www.w3.org/WAI/) — official W3C accessibility resources
- [Who Can Use](https://www.whocanuse.com) — color combination simulator for different vision types
