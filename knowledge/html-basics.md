# HTML Basics

- [What HTML Actually Is](#what-html-actually-is)
  - [HTML = Structure and Content, Not Appearance](#html--structure-and-content-not-appearance-️)
- [How Browsers Read HTML](#how-browsers-read-html-)
- [Code vs What You See](#code-vs-what-you-see-)
- [What HTML Can and Can't Do](#what-html-can-and-cant-do-)
- [Why "Markup Language"?](#why-markup-language-️)
- [Your First HTML File: From Code to Browser](#your-first-html-file-from-code-to-browser-)
- [HTML Fundamentals](#html-fundamentals-)
  - [Elements, Tags, and Attributes](#elements-tags-and-attributes-️)
  - [Nesting and Parent-Child Relationships](#nesting-and-parent-child-relationships-)
  - [Block vs Inline Elements](#block-vs-inline-elements-)
  - [Common HTML Elements with Examples](#common-html-elements-with-examples-)
  - [Putting It All Together](#putting-it-all-together-)
- [Semantic HTML & Structure](#semantic-html--structure-️)
  - [What Does "Semantic" Mean?](#what-does-semantic-mean-)
  - [Why Semantic HTML Matters](#why-semantic-html-matters-)
  - [Semantic vs Non-Semantic: The Difference](#semantic-vs-non-semantic-the-difference-)
  - [Common Semantic Elements](#common-semantic-elements-)
  - [Text-Level Semantic Elements](#text-level-semantic-elements-️)
  - [Media and Time Semantic Elements](#media-and-time-semantic-elements-️)

## **What HTML Actually Is**

#### **HTML = Structure and Content, Not Appearance 🏗️**

HTML (HyperText Markup Language) is the language that describes the **structure** and **content** of web pages. It tells the browser what things ARE, not what they LOOK like.

**Think of it like this:**

When you write a document, you have:

- 📋 Headings
- 📝 Paragraphs
- 📌 Lists
- 🔗 Links
- 🖼️ Images

HTML is how you tell the browser: "This is a heading. This is a paragraph. This is a link."

The browser then displays those elements with default styling. Later, you'll use CSS to control how things LOOK, but HTML is purely about defining WHAT things are.

---

## **How Browsers Read HTML 🌐**

When you create an HTML file and open it in a browser, here's what happens:

1. **Browser reads the HTML file** 📄 (the code you wrote)
2. **Browser interprets the tags** 🧠 (understands "this is a heading", "this is a paragraph")
3. **Browser renders the content** 🎨 (displays it on screen with default styling)
4. **Browser makes it interactive** ✨ (links become clickable, forms become functional)

**Important concept:**

You write text with HTML tags. The browser converts that into the visual page you see. The code and the result are connected but look completely different.

---

## **Code vs What You See 👀**

**What you write (HTML):**

```html
<h1>Welcome to My Website</h1>
<p>This is my first paragraph.</p>
```

**What the browser shows:**

---

# Welcome to My Website

This is my first paragraph.

---

The browser automatically:

- Makes the `<h1>` big and bold
- Adds space between the heading and paragraph
- Uses default fonts and colors

You didn't tell it HOW to style these—you just told it WHAT they are. The browser applies its default styling.

---

## **What HTML Can and Can't Do ✅❌**

**HTML CAN:** ✅

- Define structure (headings, paragraphs, lists)
- Create links to other pages
- Display images
- Build forms for user input
- Organize content with sections and containers

**HTML CANNOT:** ❌

- Control colors, fonts, or layout (that's CSS)
- Add interactivity or logic (that's JavaScript)
- Process form data or save information (that's backend code)

HTML is ONE layer of web development. It provides the foundation, but you'll need other technologies to make a fully functional, styled website.

---

## **Why "Markup Language"? 🏷️**

HTML is called a **markup language** because you "mark up" content with tags to give it meaning.

**Example:**

Plain text:

```
Welcome to My Website
This is important information.
```

Marked up with HTML:

```html
<h1>Welcome to My Website</h1>
<p>This is <strong>important</strong> information.</p>
```

The tags (like `<h1>` and `<strong>`) mark up the content to indicate its purpose and importance. The browser uses these markers to display the content appropriately.

---

## **Your First HTML File: From Code to Browser 🚀**

This is where we make HTML real. You're going to create an actual HTML file, write code, and see it work in your browser.

### **Step 1: Create Your HTML File 📄**

1. Open your code editor (VS Code)
2. Create a new file
3. Save it as `index.html`

**Important:** The `.html` extension tells your computer this is an HTML file. Without it, the browser won't know what to do with it.

**Pro tip:** ✨ In VS Code, type `!` and press Tab to instantly generate the HTML boilerplate structure.

---

### **Step 2: Understanding the Boilerplate Structure 🏗️**

Your file should now look like this:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My First Webpage</title>
  </head>
  <body></body>
</html>
```

**What is all this code?** 🤔

Each line has a specific purpose. For a detailed breakdown of what every single line means, check out the [HTML Boilerplate Guide](./html-boilerplate.md).

**Quick summary:**

- `<!doctype html>` = "This is modern HTML"
- `<html>` = Container for everything
- `<head>` = Info about the page (not visible to users)
- `<body>` = Everything users actually see

---

### **Step 3: Add Your First Content ✍️**

Now let's add actual content inside the `<body>` tags:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My First Webpage</title>
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first HTML page.</p>
    <p>I'm learning web development.</p>
  </body>
</html>
```

**What you just added:**

- `<h1>` = A level-1 heading (the biggest heading)
- `<p>` = A paragraph

---

### **Step 4: View It in Your Browser 👀**

**Two ways to open your file:**

**Option 1: From your file explorer**

- Find `index.html` on your computer
- Double-click it
- It opens in your default browser

**Option 2: From VS Code (easier)**

- Right-click on `index.html` in the file explorer
- Select "Open with Live Server" (if you have the extension)
- OR drag the file into your browser window

**What you should see:**

A webpage with:

- A big bold heading: **Hello World!**
- Two lines of regular text below it

🎉 **Congratulations! You just created your first webpage.**

---

### **Step 5: Make a Change and See It Update 🔄**

This is the workflow you'll use constantly when building websites:

**The Edit-Save-Refresh Cycle:**

1. **Edit** your code in VS Code
2. **Save** the file (Ctrl+S / Cmd+S)
3. **Refresh** your browser (F5 or Cmd+R)
4. **See** the changes

**Try it now:**

Change your heading:

```html
<h1>Hello World!</h1>
```

To:

```html
<h1>Welcome to My Website!</h1>
```

Save the file. Go to your browser. Refresh the page.

**The heading changed!** 🎊

This is how you build websites: write code → save → refresh → see result → repeat.

---

### **Step 6: Add More Elements 🧩**

Let's make the page more interesting:

```html
<body>
  <h1>Welcome to My Website!</h1>
  <p>This is my first HTML page.</p>
  <p>I'm learning web development.</p>

  <h2>What I'm Learning</h2>
  <ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
  </ul>

  <a href="https://developer.mozilla.org">Learn more about web development</a>
</body>
```

**What you added:**

- `<h2>` = A level-2 heading (smaller than h1)
- `<ul>` = An unordered list (bullet points)
- `<li>` = List items
- `<a>` = A link

Save. Refresh. See the changes. 🔥

---

### **Understanding What Just Happened 💡**

You went from **text with tags** to **a visual webpage**.

The browser:

- Read your HTML code
- Interpreted what each tag means
- Applied default styling
- Made the link clickable
- Displayed everything on screen

**This is the magic of HTML.** You describe WHAT things are, the browser handles HOW to show them.

---

### **Your Workflow Going Forward 🛠️**

Every time you build a webpage, you'll follow this pattern:

1. Create HTML file ✅
2. Write boilerplate structure ✅
3. Add content inside `<body>` ✅
4. Save and view in browser ✅
5. Edit → Save → Refresh → Repeat ✅

Get comfortable with this cycle. It's how web development works.

---

## **HTML Fundamentals 🧱**

Now that you've created your first page, let's break down how HTML actually works under the hood.

### **Elements, Tags, and Attributes 🏷️**

#### **What's an Element?**

An **element** is a complete HTML component, made up of:

- An opening tag
- Content
- A closing tag

**Example:**

```html
<p>This is a paragraph.</p>
```

- `<p>` = opening tag
- `This is a paragraph.` = content
- `</p>` = closing tag
- **The whole thing together = the element**

---

#### **Opening and Closing Tags 🔖**

Most HTML tags come in pairs:

```html
<h1>Heading</h1>
<p>Paragraph</p>
<strong>Bold text</strong>
<a>Link</a>
```

**The closing tag has a forward slash (`/`)** to show "this element is done now."

**Important rule:** Tags must close in the reverse order they opened (like Russian nesting dolls).

✅ **Correct:**

```html
<p>This is <strong>important</strong> text.</p>
```

❌ **Wrong:**

```html
<p>This is <strong>important</p></strong>
```

---

#### **Self-Closing Tags (Empty Elements) 🔚**

Some elements don't have content, so they don't need a closing tag. These are called **empty elements** or **self-closing tags**.

**Common self-closing tags:**

```html
<img src="photo.jpg" alt="Description" />
<br />
<hr />
<input type="text" />
```

Notice the `/` at the end? That's optional in HTML5, but it's good practice to include it for clarity.

---

#### **Attributes: Extra Information About Elements 📋**

Attributes give elements additional properties or settings. They go in the **opening tag** and follow this pattern:

```
attribute-name="value"
```

**Example:**

```html
<a href="https://example.com">Click here</a>
```

- `href` = attribute name
- `"https://example.com"` = attribute value

**More examples:**

```html
<img src="logo.png" alt="Company Logo" />
<input type="email" placeholder="Enter your email" />
<p class="highlight">Important text</p>
```

**Key attributes you'll use constantly:**

- `href` = destination for links
- `src` = source for images
- `alt` = alternative text for images
- `class` = CSS styling hook
- `id` = unique identifier

---

### **Nesting and Parent-Child Relationships 🪆**

HTML elements can contain other elements. This creates a hierarchy.

#### **Parent and Child Elements**

```html
<div>
  <h2>Section Title</h2>
  <p>Section content goes here.</p>
</div>
```

- `<div>` is the **parent**
- `<h2>` and `<p>` are **children** of the div
- `<h2>` and `<p>` are **siblings** (same level)

**Think of it like a family tree:** 👨‍👩‍👧‍👦

```
div (parent)
 ├── h2 (child)
 └── p (child)
```

---

#### **Deeply Nested Elements**

You can nest as many levels as needed:

```html
<article>
  <h2>Article Title</h2>
  <section>
    <h3>Section Title</h3>
    <p>This is a <strong>paragraph</strong> with <a href="#">a link</a>.</p>
  </section>
</article>
```

**The hierarchy:**

```
article (great-grandparent)
 ├── h2 (grandparent's sibling)
 └── section (grandparent)
      ├── h3 (parent's sibling)
      └── p (parent)
           ├── strong (child)
           └── a (child)
```

**Why nesting matters:**

- Organizes your content logically
- CSS and JavaScript use these relationships
- Screen readers use structure for navigation

---

### **Block vs Inline Elements 📦**

HTML elements behave in two main ways: **block** or **inline**.

#### **Block Elements 📦**

Block elements:

- Start on a **new line**
- Take up the **full width** available
- Stack vertically like boxes

**Common block elements:**

```html
<div>Container</div>
<p>Paragraph</p>
<h1>Heading</h1>
<ul>
  List
</ul>
<section>Section</section>
```

**Visual example:**

```
┌─────────────────────────┐
│ <div>First block</div>  │
└─────────────────────────┘
┌─────────────────────────┐
│ <p>Second block</p>     │
└─────────────────────────┘
```

Each element takes the full width and starts on a new line.

---

#### **Inline Elements 🔗**

Inline elements:

- Stay on the **same line**
- Only take up as much width as needed
- Flow like words in a sentence

**Common inline elements:**

```html
<a>Link</a>
<strong>Bold</strong>
<em>Italic</em>
<span>Span</span>
<img />
```

**Visual example:**

```
This is a <strong>bold word</strong> and a <a>link</a> inline.
```

They don't break the line—they flow with the text.

---

#### **Block vs Inline: Side by Side**

```html
<!-- Block elements stack -->
<div>Block 1</div>
<div>Block 2</div>

<!-- Inline elements flow -->
<span>Inline 1</span> <span>Inline 2</span>
```

**Result:**

```
Block 1
Block 2
Inline 1 Inline 2
```

**Pro tip:** You can change this behavior with CSS later, but understanding the default behavior is important.

---

### **Common HTML Elements with Examples 📚**

Let's break down the elements you'll use most often.

#### **Text Content 📝**

| Element          | Purpose                            | Example                       |
| ---------------- | ---------------------------------- | ----------------------------- |
| `<h1>` to `<h6>` | Headings (h1 biggest, h6 smallest) | `<h1>Main Title</h1>`         |
| `<p>`            | Paragraph                          | `<p>This is a paragraph.</p>` |
| `<strong>`       | Bold/important text                | `<strong>Important!</strong>` |
| `<em>`           | Italic/emphasized text             | `<em>Emphasis</em>`           |
| `<br />`         | Line break                         | `Line 1<br />Line 2`          |
| `<hr />`         | Horizontal rule (divider line)     | `<hr />`                      |

**Example in action:**

```html
<h1>Welcome to My Blog</h1>
<p>This is my first post. It's <strong>really exciting!</strong></p>
<p>I hope you <em>enjoy</em> reading it.</p>
<hr />
<p>More content below the divider.</p>
```

---

#### **Links 🔗**

```html
<a href="https://example.com">Click here</a>
```

**Attributes:**

- `href` = where the link goes
- `target="_blank"` = open in new tab

**Examples:**

```html
<!-- External link -->
<a href="https://google.com">Go to Google</a>

<!-- Open in new tab -->
<a href="https://github.com" target="_blank">GitHub</a>

<!-- Link to another page on your site -->
<a href="about.html">About Us</a>

<!-- Link to email -->
<a href="mailto:hello@example.com">Email me</a>
```

---

#### **Images 🖼️**

```html
<img src="photo.jpg" alt="Description of image" />
```

**Required attributes:**

- `src` = path to the image file
- `alt` = text description (for accessibility and if image fails to load)

**Examples:**

```html
<!-- Local image -->
<img src="logo.png" alt="Company logo" />

<!-- Image from the web -->
<img src="https://example.com/photo.jpg" alt="Mountain landscape" />

<!-- With size attributes -->
<img src="banner.jpg" alt="Website banner" width="800" height="400" />
```

**Why `alt` matters:** 🦮

- Screen readers read it to visually impaired users
- Shows if the image doesn't load
- Helps search engines understand your images

---

#### **Lists 📌**

**Unordered List (bullet points):**

```html
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

**Ordered List (numbered):**

```html
<ol>
  <li>Step one</li>
  <li>Step two</li>
  <li>Step three</li>
</ol>
```

**Nested lists:**

```html
<ul>
  <li>
    Main item
    <ul>
      <li>Sub item</li>
      <li>Sub item</li>
    </ul>
  </li>
  <li>Another main item</li>
</ul>
```

---

#### **Generic Containers 📦**

These don't have built-in meaning—they're just for grouping.

**`<div>` - Block container:**

```html
<div>
  <h2>Section Title</h2>
  <p>Section content</p>
</div>
```

**`<span>` - Inline container:**

```html
<p>This word is <span class="highlight">highlighted</span>.</p>
```

**When to use:**

- `<div>` for grouping larger sections
- `<span>` for styling small pieces of text

---

#### **Forms and Input 📋**

```html
<form>
  <input type="text" placeholder="Enter your name" />
  <input type="email" placeholder="Enter your email" />
  <button>Submit</button>
</form>
```

**Common input types:**

- `type="text"` = regular text field
- `type="email"` = email field (validates format)
- `type="password"` = password field (hides text)
- `type="number"` = number field
- `type="date"` = date picker

---

### **Putting It All Together 🧩**

Here's a complete example using everything from this section:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My Portfolio</title>
  </head>
  <body>
    <h1>John Doe - Web Developer</h1>

    <p>
      Welcome to my portfolio! I'm a <strong>web developer</strong> passionate
      about creating beautiful websites.
    </p>

    <h2>Skills</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>

    <h2>Projects</h2>
    <div>
      <h3>Portfolio Website</h3>
      <p>My personal website built with <em>modern web technologies</em>.</p>
      <a href="https://example.com">View Project</a>
    </div>

    <hr />

    <h2>Contact Me</h2>
    <p>Email: <a href="mailto:john@example.com">john@example.com</a></p>
  </body>
</html>
```

---

## **Semantic HTML & Structure 🏛️**

Now that you understand basic HTML elements, let's talk about **semantic HTML**—elements that describe what content actually MEANS, not just how it looks.

### **What Does "Semantic" Mean? 🤔**

**Semantic** = "meaningful" or "having a clear purpose"

**Non-semantic elements** like `<div>` and `<span>` are generic containers. They don't tell you anything about what's inside them.

**Semantic elements** like `<header>`, `<article>`, `<nav>` clearly describe their purpose.

---

### **Why Semantic HTML Matters ✨**

Using semantic elements has real benefits:

1. **Accessibility 🦮**
   - Screen readers use semantic tags to navigate ("Skip to main content", "Go to navigation")
   - Helps people with disabilities understand your page structure

2. **SEO (Search Engine Optimization) 🔍**
   - Google and other search engines understand your content better
   - Better ranking in search results

3. **Code Readability 📖**
   - Other developers (and future you) can understand your code faster
   - Clear structure makes maintenance easier

4. **Browser Benefits 🌐**
   - Browsers can add helpful features (like "reader mode")
   - Better default styling and behavior

---

### **Semantic vs Non-Semantic: The Difference 🆚**

**Non-semantic (bad):** 🙁

```html
<div id="header">
  <div id="nav">
    <a href="#">Home</a>
    <a href="#">About</a>
  </div>
</div>

<div id="main">
  <div class="post">
    <div class="title">My Blog Post</div>
    <div class="content">Post content here...</div>
  </div>
</div>

<div id="footer">
  <p>Copyright 2026</p>
</div>
```

This works, but it's all just `<div>` elements with descriptive IDs. Browsers and screen readers don't understand the MEANING—they just see generic containers.

---

**Semantic (good):** 😊

```html
<header>
  <nav>
    <a href="#">Home</a>
    <a href="#">About</a>
  </nav>
</header>

<main>
  <article>
    <h1>My Blog Post</h1>
    <p>Post content here...</p>
  </article>
</main>

<footer>
  <p>Copyright 2026</p>
</footer>
```

Now the HTML itself communicates structure. A screen reader knows "this is navigation" and "this is the main content."

---

### **Common Semantic Elements 📚**

#### **Page Structure Elements 🏗️**

| Element     | Purpose                | Use It For                                       |
| ----------- | ---------------------- | ------------------------------------------------ |
| `<header>`  | Introductory content   | Page header, article header, section header      |
| `<nav>`     | Navigation links       | Main menu, table of contents, breadcrumbs        |
| `<main>`    | Primary content        | The main content of the page (only ONE per page) |
| `<section>` | Thematic grouping      | A standalone section of related content          |
| `<article>` | Self-contained content | Blog posts, news articles, comments, forum posts |
| `<aside>`   | Tangential content     | Sidebars, related links, callout boxes           |
| `<footer>`  | Closing content        | Page footer, article footer, section footer      |

---

#### **`<header>` - Introductory Content 🎯**

Use for introductory content or navigation at the top of a page, section, or article.

**Example:**

```html
<!-- Page header -->
<header>
  <h1>My Website</h1>
  <nav>
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </nav>
</header>

<!-- Article header -->
<article>
  <header>
    <h2>Blog Post Title</h2>
    <p>Published on February 2, 2026</p>
  </header>
  <p>Article content...</p>
</article>
```

**Note:** You can have multiple `<header>` elements on a page (one for the page, one per article, etc.).

---

#### **`<nav>` - Navigation Links 🧭**

Use for major navigation blocks.

**Example:**

```html
<nav>
  <ul>
    <li><a href="index.html">Home</a></li>
    <li><a href="about.html">About</a></li>
    <li><a href="contact.html">Contact</a></li>
  </ul>
</nav>
```

**When NOT to use `<nav>`:**
Not every group of links needs `<nav>`. Use it for **major navigation blocks**, not for every single link list.

❌ Don't use for: Footer links, social media icons (unless they're your main navigation)
✅ Use for: Main site menu, table of contents, breadcrumb navigation

---

#### **`<main>` - Primary Content 📄**

The main content of your page. There should be **only ONE** `<main>` element per page.

**Example:**

```html
<body>
  <header>
    <h1>My Website</h1>
    <nav>...</nav>
  </header>

  <main>
    <!-- Your primary content goes here -->
    <h2>Welcome</h2>
    <p>This is the main content of the page.</p>
  </main>

  <footer>...</footer>
</body>
```

**Rule:** Don't put `<main>` inside `<header>`, `<footer>`, `<nav>`, `<aside>`, or `<article>`.

---

#### **`<section>` - Thematic Grouping 📦**

A generic section of content, usually with a heading.

**Example:**

```html
<main>
  <section>
    <h2>About Me</h2>
    <p>I'm a web developer...</p>
  </section>

  <section>
    <h2>My Skills</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
  </section>
</main>
```

**When to use `<section>`:**

- Content that logically belongs together
- Each section typically has its own heading

**Advanced note:** 💡 Like articles, sections CAN have their own `<header>` and `<footer>` elements, but in practice this is rarely needed. Most of the time, a simple heading is enough

---

#### **`<article>` - Self-Contained Content 📰**

Content that makes sense on its own, even if removed from the rest of the page.

**Think:** Could this content be syndicated, shared, or reused independently?

**Example:**

```html
<article>
  <header>
    <h2>How to Learn HTML</h2>
    <p>By Jane Doe | February 2, 2026</p>
  </header>

  <p>HTML is the foundation of web development...</p>

  <footer>
    <p>Tags: HTML, Web Development</p>
  </footer>
</article>
```

**Important note about `<header>` and `<footer>` inside articles:** 📌

You can (and should!) use `<header>` and `<footer>` inside your `<article>` elements. These are NOT the same as the page-level header and footer.

**Think of it like nested contexts:**

```html
<!-- Page-level header -->
<header>
  <h1>My Blog Website</h1>
  <nav>...</nav>
</header>

<main>
  <!-- Article-specific header -->
  <article>
    <header>
      <h2>Article Title</h2>
      <p>Article metadata (author, date, etc.)</p>
    </header>

    <p>Article content...</p>

    <!-- Article-specific footer -->
    <footer>
      <p>Article-specific info (tags, share buttons, etc.)</p>
    </footer>
  </article>

  <!-- Another article with its own header/footer -->
  <article>
    <header>
      <h2>Another Article</h2>
    </header>
    <p>Different content...</p>
    <footer>
      <p>Different tags...</p>
    </footer>
  </article>
</main>

<!-- Page-level footer -->
<footer>
  <p>&copy; 2026 My Blog</p>
</footer>
```

**Why this works:**

Each `<header>` and `<footer>` is scoped to its parent element. The `<header>` inside an `<article>` describes THAT article's introductory content, not the whole page.

**Use article headers for:**

- Article title
- Author name
- Publication date
- Category/topic

**Use article footers for:**

- Tags
- Author bio
- Related articles
- Share buttons
- Comment count

**Use `<article>` for:**

- Blog posts
- News articles
- Forum posts
- Product cards
- User comments
- Social media posts

---

#### **`<aside>` - Tangential Content 📌**

Content related to the main content but not essential to understanding it.

**Example:**

```html
<main>
  <article>
    <h2>Main Article</h2>
    <p>Article content here...</p>
  </article>

  <aside>
    <h3>Related Articles</h3>
    <ul>
      <li><a href="#">Article 1</a></li>
      <li><a href="#">Article 2</a></li>
    </ul>
  </aside>
</main>
```

**Use `<aside>` for:**

- Sidebars
- Pull quotes
- Advertising
- Related content boxes

---

#### **`<footer>` - Closing Content 🔚**

Footer information for a page, section, or article.

**Example:**

```html
<!-- Page footer -->
<footer>
  <p>&copy; 2026 My Website</p>
  <p>Contact: hello@example.com</p>
</footer>

<!-- Article footer -->
<article>
  <h2>Article Title</h2>
  <p>Article content...</p>

  <footer>
    <p>Author: John Doe</p>
    <p>Published: Feb 2, 2026</p>
  </footer>
</article>
```

---

### **Text-Level Semantic Elements ✍️**

These give meaning to specific pieces of text:

| Element    | Purpose           | Example                                               |
| ---------- | ----------------- | ----------------------------------------------------- |
| `<strong>` | Strong importance | `<strong>Warning!</strong>`                           |
| `<em>`     | Emphasis          | `<em>Really</em> important`                           |
| `<mark>`   | Highlighted text  | `<mark>search result</mark>`                          |
| `<time>`   | Dates and times   | `<time datetime="2026-02-02">Feb 2</time>`            |
| `<abbr>`   | Abbreviations     | `<abbr title="HyperText Markup Language">HTML</abbr>` |
| `<code>`   | Code snippets     | `Use <code>console.log()</code>`                      |

---

### **Media and Time Semantic Elements 🖼️⏰**

#### **`<figure>` and `<figcaption>` - Self-Contained Media**

Use `<figure>` for images, diagrams, code snippets, or other media that's referenced from the main content but could be moved elsewhere (like to a sidebar or appendix) without breaking the flow.

Use `<figcaption>` to add a caption to the figure.

**Example:**

```html
<figure>
  <img src="diagram.jpg" alt="Website architecture diagram" />
  <figcaption>
    Figure 1: Basic website architecture showing client-server communication
  </figcaption>
</figure>
```

**Another example with code:**

```html
<figure>
  <pre><code>
function greet() {
  console.log("Hello!");
}
  </code></pre>
  <figcaption>Example: A simple JavaScript greeting function</figcaption>
</figure>
```

**When to use `<figure>`:**

- Images with captions
- Code examples with descriptions
- Diagrams or charts
- Quotes with attribution

**When NOT to use `<figure>`:**
Don't use it for every image—only for images that are referenced or explained in the text and would benefit from a caption.

❌ **Don't need `<figure>`:**

```html
<img src="logo.png" alt="Company logo" />
```

✅ **Good use of `<figure>`:**

```html
<p>As shown in Figure 1 below, the process involves three steps...</p>
<figure>
  <img src="process-diagram.jpg" alt="Three-step process diagram" />
  <figcaption>Figure 1: The three-step deployment process</figcaption>
</figure>
```

---

#### **`<time>` - Dates and Times 📅**

Use `<time>` to mark up dates and times in a machine-readable format.

**Basic usage:**

```html
<time datetime="2026-02-02">February 2, 2026</time>
```

**Why use `<time>`?**

- Search engines understand the date
- Browsers and tools can add calendar functionality
- Screen readers can announce dates properly
- You can style all dates consistently with CSS

**Different formats:**

**Date only:**

```html
<time datetime="2026-02-02">Feb 2, 2026</time>
```

**Date and time:**

```html
<time datetime="2026-02-02T14:30">February 2, 2026 at 2:30 PM</time>
```

**Just the year:**

```html
<time datetime="2026">2026</time>
```

**Duration:**

```html
<time datetime="PT2H30M">2 hours 30 minutes</time>
```

**In context:**

```html
<article>
  <h2>My Blog Post</h2>
  <p>Published on <time datetime="2026-02-02">February 2, 2026</time></p>
  <p>Article content...</p>
</article>
```

**The `datetime` attribute:**

- Must be in ISO 8601 format (machine-readable)
- The text inside the tag can be human-friendly
- If you skip `datetime`, the text content must be in valid format

**Example showing the difference:**

```html
<!-- Browser/search engines see: 2026-02-02 -->
<!-- Humans see: February 2, 2026 -->
<time datetime="2026-02-02">February 2, 2026</time>
```

---

### **Putting It All Together: A Complete Page Structure 🏛️**

Here's a full example showing how semantic elements work together:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My Blog</title>
  </head>
  <body>
    <header>
      <h1>My Blog</h1>
      <nav>
        <ul>
          <li><a href="index.html">Home</a></li>
          <li><a href="about.html">About</a></li>
          <li><a href="contact.html">Contact</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <article>
        <header>
          <h2>My First Blog Post</h2>
          <p>
            Published on <time datetime="2026-02-02">February 2, 2026</time>
          </p>
        </header>

        <p>
          This is the content of my blog post. It's
          <strong>really exciting!</strong>
        </p>

        <figure>
          <img
            src="webdev-journey.jpg"
            alt="Code editor showing HTML and CSS files"
          />
          <figcaption>Figure 1: My development environment setup</figcaption>
        </figure>

        <section>
          <h3>Why I Started Blogging</h3>
          <p>I wanted to share my journey learning web development...</p>
        </section>

        <footer>
          <p>Tags: Blogging, Web Development</p>
        </footer>
      </article>

      <aside>
        <h3>Related Posts</h3>
        <ul>
          <li><a href="#">Getting Started with HTML</a></li>
          <li><a href="#">CSS Basics</a></li>
        </ul>
      </aside>
    </main>

    <footer>
      <p>&copy; 2026 My Blog. All rights reserved.</p>
      <p>Contact: <a href="mailto:hello@myblog.com">hello@myblog.com</a></p>
    </footer>
  </body>
</html>
```

---

### **When to Use What? Quick Decision Guide 🗺️**

**Is it the main navigation?** → `<nav>`

**Is it the primary content of the page?** → `<main>`

**Is it a standalone piece of content that could exist on its own?** → `<article>`

**Is it a thematic section of content?** → `<section>`

**Is it extra/tangential content?** → `<aside>`

**Is it introductory content?** → `<header>`

**Is it concluding/footer content?** → `<footer>`

**Is it media (image, code, diagram) that needs a caption?** → `<figure>` + `<figcaption>`

**Is it a date or time?** → `<time datetime="...">`

**Not sure? Just grouping stuff for styling?** → `<div>` (still perfectly fine!)

---

## **Common Mistakes & Debugging 🐞**

Everyone makes mistakes when writing HTML. Here's what goes wrong most often and how to fix it.

### **Forgotten Closing Tags ❌**

**The mistake:**

```html
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

The first `<p>` tag was never closed.

**What happens:**
The browser tries to guess where the paragraph ends, which can mess up your layout or styling.

**How to fix it:**
Always close your tags:

```html
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

**Pro tip:** Most code editors highlight unclosed tags. Look for red squiggly lines or color differences.

---

### **Wrong Nesting Order 🪆**

**The mistake:**

```html
<p>This is <strong>important text</p></strong>
```

The `<strong>` tag opened INSIDE the `<p>` but closed OUTSIDE it.

**What happens:**
Browsers try to fix it, but the result might not be what you expected. Styling can break.

**How to fix it:**
Tags must close in reverse order (like nested parentheses):

```html
<p>This is <strong>important text</strong></p>
```

**Think of it like boxes:** If you open Box A, then Box B, you must close Box B before you can close Box A.

---

### **Missing Required Attributes 🏷️**

**The mistake:**

```html
<img src="photo.jpg" /> <a>Click here</a>
```

- The `<img>` is missing the `alt` attribute
- The `<a>` is missing the `href` attribute

**What happens:**

- Image without `alt`: Screen readers can't describe the image, and if it fails to load, users see nothing
- Link without `href`: It's not actually a link—it's just text styled like a link

**How to fix it:**

```html
<img src="photo.jpg" alt="A sunset over the mountains" />
<a href="https://example.com">Click here</a>
```

**Pro tip:** Your code editor usually warns you about missing required attributes.

---

### **Typos in Tag Names 📝**

**The mistake:**

```html
<stong>Bold text</stong> <imag src="photo.jpg" alt="Photo" />
```

Typos: `stong` instead of `strong`, `imag` instead of `img`

**What happens:**
The browser doesn't recognize these tags, so they don't work at all. Text might appear unstyled, images won't load.

**How to fix it:**
Double-check spelling:

```html
<strong>Bold text</strong> <img src="photo.jpg" alt="Photo" />
```

**Pro tip:** Code editors with syntax highlighting show recognized tags in color. If a tag isn't colored, it's probably misspelled.

---

### **Incorrect File Paths 📂**

**The mistake:**

```html
<img src="photo.jpg" alt="My photo" />
```

But `photo.jpg` is actually in a folder called `images/`.

**What happens:**
The browser can't find the file. You see a broken image icon.

**How to fix it:**
Use the correct path:

```html
<img src="images/photo.jpg" alt="My photo" />
```

**Path types:**

- `photo.jpg` = same folder as your HTML file
- `images/photo.jpg` = inside the `images` folder
- `../photo.jpg` = one folder up
- `https://example.com/photo.jpg` = absolute URL

---

### **Multiple `<main>` or `<h1>` Elements ⚠️**

**The mistake:**

```html
<main>
  <h1>First Section</h1>
</main>

<main>
  <h1>Second Section</h1>
</main>
```

**What happens:**

- Multiple `<main>` elements confuse screen readers and search engines
- Multiple `<h1>` elements are allowed but not recommended (SEO and accessibility)

**How to fix it:**
Use only ONE `<main>` per page:

```html
<main>
  <h1>Page Title</h1>

  <section>
    <h2>First Section</h2>
  </section>

  <section>
    <h2>Second Section</h2>
  </section>
</main>
```

**Heading hierarchy:** Use `<h1>` once, then `<h2>`, `<h3>`, etc. in logical order.

---

### **Mixing Up Quotes 🔤**

**The mistake:**

```html
<a
  href='https://example.com">Click here</a>
<img src="photo.jpg'
  alt="Photo"
/>
```

Mixing single (`'`) and double (`"`) quotes in the same attribute.

**What happens:**
The attribute might not work correctly. Browsers might misinterpret where the value ends.

**How to fix it:**
Pick one style and stick with it (double quotes are standard):

```html
<a href="https://example.com">Click here</a> <img src="photo.jpg" alt="Photo" />
```

---

### **Forgetting `<!doctype html>` 📋**

**The mistake:**
Starting your HTML file without the doctype:

```html
<html>
  <head>
    ...
  </head>
  <body>
    ...
  </body>
</html>
```

**What happens:**
Browsers enter "quirks mode" and render things inconsistently. Your page might look broken.

**How to fix it:**
Always start with the doctype:

```html
<!doctype html>
<html>
  <head>
    ...
  </head>
  <body>
    ...
  </body>
</html>
```

---

### **How to Debug HTML 🔍**

When something doesn't look right, follow these steps:

#### **1. Check the Browser's Developer Tools 🛠️**

**How to open:**

- Right-click on your page → "Inspect" or "Inspect Element"
- Or press `F12` (Windows) / `Cmd + Option + I` (Mac)

**What to look for:**

- Red error messages in the Console tab
- Inspect the Elements tab to see how the browser interpreted your HTML
- Look for unclosed tags, misspellings, broken paths

---

#### **2. Validate Your HTML ✅**

Use the [W3C HTML Validator](https://validator.w3.org/):

1. Go to validator.w3.org
2. Upload your HTML file or paste your code
3. Click "Check"
4. It will list all errors and warnings

**Common errors it catches:**

- Unclosed tags
- Invalid nesting
- Missing required attributes
- Typos in element names

---

#### **3. Check Your File Structure 📁**

Make sure files are where you think they are:

```
project/
├── index.html
├── about.html
├── images/
│   ├── logo.png
│   └── photo.jpg
└── styles/
    └── style.css
```

If `index.html` references `images/logo.png`, that path must be correct.

---

#### **4. Simplify and Test 🧪**

If you can't find the problem:

1. Comment out sections of code
2. Test after each change
3. Narrow down where the error is

**Example:**

```html
<!-- <section>
  <h2>Broken Section</h2>
  <p>Something here is broken...</p>
</section> -->

<section>
  <h2>Working Section</h2>
  <p>This works fine.</p>
</section>
```

Uncomment sections one at a time until you find the culprit.

---

#### **5. Compare with Working Examples 📖**

If you're stuck, compare your code to:

- Examples from tutorials
- The HTML boilerplate guide
- MDN documentation

Often you'll spot the difference.

---

### **Prevention Tips 🛡️**

**1. Use a good code editor:**

- VS Code highlights syntax errors
- Auto-closes tags
- Warns about missing attributes

**2. Indent your code properly:**

❌ **Hard to read:**

```html
<div>
  <h2>Title</h2>
  <p>Content</p>
</div>
```

✅ **Easy to read:**

```html
<div>
  <h2>Title</h2>
  <p>Content</p>
</div>
```

**3. Validate regularly:**
Run your HTML through the W3C validator every so often to catch errors early.

**4. Test in multiple browsers:**
What works in Chrome might look different in Firefox or Safari. Test your pages in different browsers.

---

## **Quick Reference 📚**

Your go-to cheat sheet for HTML elements and syntax.

### **Document Structure Template 📋**

Copy this every time you start a new HTML file:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Page Title</title>
  </head>
  <body>
    <!-- Your content goes here -->
  </body>
</html>
```

**Pro tip:** ✨ In VS Code, type `!` and press Tab to generate this automatically.

For detailed explanation of each line, see the [HTML Boilerplate Guide](./html-boilerplate.md).

---

### **Common HTML Elements 🏷️**

#### **Text Content**

| Element          | Description                        | Example                      |
| ---------------- | ---------------------------------- | ---------------------------- |
| `<h1>` to `<h6>` | Headings (h1 largest, h6 smallest) | `<h1>Main Title</h1>`        |
| `<p>`            | Paragraph                          | `<p>Text content</p>`        |
| `<strong>`       | Bold/important text                | `<strong>Important</strong>` |
| `<em>`           | Italic/emphasized text             | `<em>Emphasis</em>`          |
| `<br />`         | Line break                         | `Line 1<br />Line 2`         |
| `<hr />`         | Horizontal rule (divider)          | `<hr />`                     |
| `<mark>`         | Highlighted text                   | `<mark>Highlighted</mark>`   |
| `<code>`         | Code snippet                       | `<code>console.log()</code>` |
| `<pre>`          | Preformatted text                  | `<pre>Keeps   spacing</pre>` |

---

#### **Links and Media**

| Element   | Description  | Example                           |
| --------- | ------------ | --------------------------------- |
| `<a>`     | Link         | `<a href="url">Text</a>`          |
| `<img />` | Image        | `<img src="path" alt="desc" />`   |
| `<video>` | Video player | `<video src="video.mp4"></video>` |
| `<audio>` | Audio player | `<audio src="song.mp3"></audio>`  |

---

#### **Lists**

| Element | Description              | Example                      |
| ------- | ------------------------ | ---------------------------- |
| `<ul>`  | Unordered list (bullets) | See below                    |
| `<ol>`  | Ordered list (numbers)   | See below                    |
| `<li>`  | List item                | Used inside `<ul>` or `<ol>` |
| `<dl>`  | Description list         | For term/definition pairs    |
| `<dt>`  | Term in description list | `<dt>HTML</dt>`              |
| `<dd>`  | Description in list      | `<dd>Markup language</dd>`   |

**List examples:**

```html
<!-- Unordered list -->
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>

<!-- Ordered list -->
<ol>
  <li>First</li>
  <li>Second</li>
</ol>
```

---

#### **Containers**

| Element  | Description              | Example              |
| -------- | ------------------------ | -------------------- |
| `<div>`  | Generic block container  | `<div>Content</div>` |
| `<span>` | Generic inline container | `<span>Text</span>`  |

---

#### **Forms**

| Element      | Description           | Example                           |
| ------------ | --------------------- | --------------------------------- |
| `<form>`     | Form container        | `<form>...</form>`                |
| `<input />`  | Input field           | `<input type="text" />`           |
| `<textarea>` | Multi-line text input | `<textarea></textarea>`           |
| `<button>`   | Button                | `<button>Click</button>`          |
| `<label>`    | Label for input       | `<label for="name">Name:</label>` |
| `<select>`   | Dropdown menu         | See below                         |
| `<option>`   | Dropdown option       | Used inside `<select>`            |

**Form example:**

```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" />

  <label for="email">Email:</label>
  <input type="email" id="email" />

  <button type="submit">Submit</button>
</form>
```

---

### **Semantic Elements 🏛️**

| Element        | Purpose                | Usage                                      |
| -------------- | ---------------------- | ------------------------------------------ |
| `<header>`     | Introductory content   | Page/section/article header                |
| `<nav>`        | Navigation links       | Main menu, breadcrumbs                     |
| `<main>`       | Primary content        | Main page content (ONE per page)           |
| `<section>`    | Thematic grouping      | Related content with heading               |
| `<article>`    | Self-contained content | Blog posts, news articles                  |
| `<aside>`      | Tangential content     | Sidebars, related links                    |
| `<footer>`     | Closing content        | Page/section/article footer                |
| `<figure>`     | Self-contained media   | Images with captions                       |
| `<figcaption>` | Caption for figure     | Describes the figure                       |
| `<time>`       | Date/time              | `<time datetime="2026-02-02">Feb 2</time>` |

---

### **Common Attributes 📋**

| Attribute         | Used On                       | Purpose               | Example                      |
| ----------------- | ----------------------------- | --------------------- | ---------------------------- |
| `href`            | `<a>`                         | Link destination      | `href="https://example.com"` |
| `src`             | `<img>`, `<video>`, `<audio>` | Source file path      | `src="image.jpg"`            |
| `alt`             | `<img>`                       | Alternative text      | `alt="Description"`          |
| `class`           | Any element                   | CSS class for styling | `class="highlight"`          |
| `id`              | Any element                   | Unique identifier     | `id="main-header"`           |
| `type`            | `<input>`, `<button>`         | Input/button type     | `type="email"`               |
| `placeholder`     | `<input>`, `<textarea>`       | Hint text             | `placeholder="Enter name"`   |
| `target`          | `<a>`                         | How to open link      | `target="_blank"` (new tab)  |
| `width`, `height` | `<img>`, `<video>`            | Dimensions            | `width="800"`                |
| `disabled`        | `<input>`, `<button>`         | Disable element       | `disabled`                   |
| `required`        | `<input>`                     | Required field        | `required`                   |

---

### **Input Types 📝**

| Type       | Purpose           | Example                     |
| ---------- | ----------------- | --------------------------- |
| `text`     | Single-line text  | `<input type="text" />`     |
| `email`    | Email address     | `<input type="email" />`    |
| `password` | Password (hidden) | `<input type="password" />` |
| `number`   | Numeric input     | `<input type="number" />`   |
| `date`     | Date picker       | `<input type="date" />`     |
| `checkbox` | Checkbox          | `<input type="checkbox" />` |
| `radio`    | Radio button      | `<input type="radio" />`    |
| `file`     | File upload       | `<input type="file" />`     |
| `submit`   | Submit button     | `<input type="submit" />`   |
| `button`   | Generic button    | `<input type="button" />`   |

---

### **Special Characters (HTML Entities) 🔣**

Some characters need special codes in HTML:

| Character | Entity Code         | Description          |
| --------- | ------------------- | -------------------- |
| `<`       | `&lt;`              | Less than            |
| `>`       | `&gt;`              | Greater than         |
| `&`       | `&amp;`             | Ampersand            |
| `"`       | `&quot;`            | Quote                |
| `'`       | `&apos;` or `&#39;` | Apostrophe           |
| ` `       | `&nbsp;`            | Non-breaking space   |
| `©`       | `&copy;`            | Copyright            |
| `®`       | `&reg;`             | Registered trademark |
| `€`       | `&euro;`            | Euro symbol          |

**Example:**

```html
<p>Use &lt;p&gt; for paragraphs.</p>
<!-- Displays: Use <p> for paragraphs. -->
```

---

### **Block vs Inline Elements 📦**

**Block elements** (start on new line, full width):

- `<div>`, `<p>`, `<h1>-<h6>`, `<ul>`, `<ol>`, `<li>`, `<section>`, `<article>`, `<header>`, `<footer>`, `<nav>`, `<main>`, `<aside>`

**Inline elements** (stay on same line, only take needed width):

- `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<code>`, `<mark>`, `<br />`, `<input>`, `<button>`

---

### **Nesting Rules 🪆**

✅ **Valid nesting:**

```html
<p>This is <strong>bold text</strong>.</p>
<ul>
  <li>Item</li>
</ul>
<div>
  <p>Paragraph inside div</p>
</div>
```

❌ **Invalid nesting:**

```html
<p>Paragraph <div>div inside p</div></p>
<!-- Block element inside inline element -->

<ul>
  <p>Paragraph not in li</p>
</ul>
<!-- Direct child of <ul> must be <li> -->
```

---

### **HTML Comment Syntax 💬**

```html
<!-- This is a comment -->
<!-- Comments are not displayed in the browser -->

<!--
  Multi-line comment
  for longer notes
-->
```

---

### **Complete Page Example 🎯**

Putting it all together:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My Website</title>
  </head>
  <body>
    <header>
      <h1>My Website</h1>
      <nav>
        <a href="index.html">Home</a>
        <a href="about.html">About</a>
        <a href="contact.html">Contact</a>
      </nav>
    </header>

    <main>
      <article>
        <h2>Welcome</h2>
        <p>This is my <strong>first website</strong>!</p>
        <img src="images/photo.jpg" alt="My photo" />
      </article>

      <section>
        <h2>Contact Me</h2>
        <form>
          <label for="email">Email:</label>
          <input type="email" id="email" required />
          <button type="submit">Send</button>
        </form>
      </section>
    </main>

    <footer>
      <p>&copy; 2026 My Website</p>
    </footer>
  </body>
</html>
```

---

### **Helpful Resources 🔗**

- **MDN Web Docs:** [developer.mozilla.org](https://developer.mozilla.org)
- **W3C HTML Validator:** [validator.w3.org](https://validator.w3.org)
- **Can I Use:** [caniuse.com](https://caniuse.com) (browser compatibility)
- **HTML Boilerplate Guide:** [html-boilerplate.md](./html-boilerplate.md)

---
