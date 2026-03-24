# HTML Fundamentals

- [Understanding HTML](#understanding-html)
  - [What HTML Actually Is](#what-html-actually-is)
  - [How Browsers Read HTML](#how-browsers-read-html)
  - [Code vs What You See](#code-vs-what-you-see)
  - [What HTML Can and Can't Do](#what-html-can-and-cant-do)
  - [Why "Markup Language"?](#why-markup-language)
- [Your First HTML File](#your-first-html-file)
  - [Step 1: Create Your HTML File](#step-1-create-your-html-file)
  - [Step 2: Understanding the Boilerplate Structure](#step-2-understanding-the-boilerplate-structure)
  - [Step 3: Add Your First Content](#step-3-add-your-first-content)
  - [Step 4: View It in Your Browser](#step-4-view-it-in-your-browser)
  - [Step 5: Make a Change and See It Update](#step-5-make-a-change-and-see-it-update)
  - [Understanding What Just Happened](#understanding-what-just-happened)
  - [Your Workflow Going Forward](#your-workflow-going-forward)
- [HTML Document Structure (Deep Dive)](#html-document-structure-deep-dive)
  - [Elements, Tags, and Attributes](#elements-tags-and-attributes)
  - [Nesting and Parent-Child Relationships](#nesting-and-parent-child-relationships)
  - [Block vs Inline Elements](#block-vs-inline-elements)
  - [The HTML Boilerplate Explained](#the-html-boilerplate-explained)
  - [Common HTML Elements with Examples](#common-html-elements-with-examples)
  - [Putting It All Together](#putting-it-all-together)
- [Semantic HTML & Structure](#semantic-html--structure)
  - [What Does "Semantic" Mean?](#what-does-semantic-mean)
  - [Why Semantic HTML Matters](#why-semantic-html-matters)
  - [Semantic vs Non-Semantic: The Difference](#semantic-vs-non-semantic-the-difference)
  - [Common Semantic Elements](#common-semantic-elements)
  - [Text-Level Semantic Elements](#text-level-semantic-elements)
  - [Media and Time Semantic Elements](#media-and-time-semantic-elements)
- [Quick Reference](#quick-reference)

---

## Understanding HTML

### What HTML Actually Is

**HTML = Structure and Content, Not Appearance**

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

### How Browsers Read HTML

When you create an HTML file and open it in a browser, here's what happens:

1. **Browser reads the HTML file** 📄 (the code you wrote)
2. **Browser interprets the tags** 🧠 (understands "this is a heading", "this is a paragraph")
3. **Browser renders the content** 🎨 (displays it on screen with default styling)
4. **Browser makes it interactive** ✨ (links become clickable, forms become functional)

**Important concept:**

You write text with HTML tags. The browser converts that into the visual page you see. The code and the result are connected but look completely different.

---

### Code vs What You See

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

You didn't tell it HOW to style these. You just told it WHAT they are. The browser applies its default styling.

---

### What HTML Can and Can't Do

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

### Why "Markup Language"?

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

## Your First HTML File

This is where we make HTML real. You're going to create an actual HTML file, write code, and see it work in your browser.

### Step 1: Create Your HTML File

1. Open your code editor (VS Code)
2. Create a new file
3. Save it as `index.html`

**Important:** The `.html` extension tells your computer this is an HTML file. Without it, the browser won't know what to do with it.

**Pro tip:** ✨ In VS Code, type `!` and press Tab to instantly generate the HTML boilerplate structure.

---

### Step 2: Understanding the Boilerplate Structure

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

**What is all this code?**

Don't worry about understanding every detail yet. For now, just know:

- `<!doctype html>` = "This is modern HTML"
- `<html>` = Container for everything
- `<head>` = Info about the page (not visible to users)
- `<body>` = Everything users actually see

We'll dive deep into what each line means later in the [HTML Boilerplate Explained](#the-html-boilerplate-explained) section.

---

### Step 3: Add Your First Content

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

### Step 4: View It in Your Browser

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

### Step 5: Make a Change and See It Update

This is the workflow you'll use constantly when building websites:

**The Edit-Save-Refresh Cycle:**

1. **Edit** your code in VS Code
2. **Save** the file (Ctrl+S / Cmd+S)
3. **Refresh** your browser (F5 or Cmd+R)
4. **See** the changes

**Try it now:**

Change your heading from:

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

### Understanding What Just Happened

You went from **text with tags** to **a visual webpage**.

The browser:

- Read your HTML code
- Interpreted what each tag means
- Applied default styling
- Displayed everything on screen

**This is the magic of HTML.** You describe WHAT things are, the browser handles HOW to show them.

---

### Your Workflow Going Forward

Every time you build a webpage, you'll follow this pattern:

1. Create HTML file ✅
2. Write boilerplate structure ✅
3. Add content inside `<body>` ✅
4. Save and view in browser ✅
5. Edit → Save → Refresh → Repeat ✅

Get comfortable with this cycle. It's how web development works.

---

## HTML Document Structure (Deep Dive)

Now that you've created your first webpage, let's understand the building blocks of HTML in detail.

### Elements, Tags, and Attributes

#### What's an Element?

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

#### Opening and Closing Tags

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

#### Self-Closing Tags (Empty Elements)

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

#### Attributes: Extra Information About Elements

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

### Nesting and Parent-Child Relationships

HTML elements can contain other elements. This creates a hierarchy.

#### Parent and Child Elements

```html
<div>
  <h2>Section Title</h2>
  <p>Section content goes here.</p>
</div>
```

- `<div>` is the **parent**
- `<h2>` and `<p>` are **children** of the div
- `<h2>` and `<p>` are **siblings** (same level)

#### Deeper Nesting

```html
<article>
  <header>
    <h1>Article Title</h1>
    <p>By <strong>Author Name</strong></p>
  </header>
  <p>Article content...</p>
</article>
```

Here:

- `<article>` is the parent of `<header>` and the second `<p>`
- `<header>` is the parent of `<h1>` and the first `<p>`
- `<strong>` is a child of the first `<p>`
- `<strong>` is a grandchild of `<header>`

#### Proper Nesting Rules

✅ **Valid nesting:**

```html
<p>This is <strong>bold text</strong>.</p>

<ul>
  <li>Item 1</li>
  <li>Item 2</li>
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

**Why proper nesting matters:**

- Browsers might display broken HTML incorrectly
- Screen readers rely on proper structure
- Your CSS and JavaScript depend on correct relationships

---

### Block vs Inline Elements

HTML elements fall into two main categories based on how they display:

#### Block Elements

**Block elements:**

- Start on a NEW line
- Take up the FULL width available
- Stack vertically like building blocks

**Common block elements:**

```html
<div>
  ,
  <p>,</p>
  <h1>
    -
    <h6>
      ,
      <ul>
        ,
        <ol>
          ,
          <li>
            ,
            <section>
              ,
              <article>
                ,
                <header>
                  ,
                  <footer>
                    ,
                    <nav>
                      ,
                      <main>
                        ,
                        <aside>
                          ,
                          <form></form>
                        </aside>
                      </main>
                    </nav>
                  </footer>
                </header>
              </article>
            </section>
          </li>
        </ol>
      </ul>
    </h6>
  </h1>
</div>
```

**Example:**

```html
<p>First paragraph</p>
<p>Second paragraph</p>
```

Result:

```
First paragraph

Second paragraph
```

Both paragraphs take full width and stack vertically.

---

#### Inline Elements

**Inline elements:**

- Stay on the SAME line as surrounding content
- Only take up as much width as they need
- Flow like words in a sentence

**Common inline elements:**

```html
<span
  >,
  <a
    >,
    <strong
      >,
      <em
        >, <img />,
        <code
          >,
          <mark
            >, <br />, <input />,
            <button></button></mark></code></em></strong></a
></span>
```

**Example:**

```html
<p>This is <strong>bold text</strong> and this is <em>italic text</em>.</p>
```

Result:

```
This is bold text and this is italic text.
```

All content flows on the same line.

---

#### Block vs Inline: Visual Comparison

```html
<!-- Block elements stack vertically -->
<div>Block 1</div>
<div>Block 2</div>
<div>Block 3</div>

<!-- Inline elements flow horizontally -->
<span>Inline 1</span>
<span>Inline 2</span>
<span>Inline 3</span>
```

**What you see:**

```
Block 1

Block 2

Block 3

Inline 1 Inline 2 Inline 3
```

---

### The HTML Boilerplate Explained

Remember this code from your first file? Now let's understand every single line.

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

#### What is "Boilerplate"?

(in the sense of programming)

Boilerplate is the **standard, repetitive code** that you need to include in every project, even though it's not the interesting or unique part.

**Think of it like:**

- Making a sandwich - you always need bread (boilerplate), but the filling (your unique code) is what makes each sandwich different
- Writing a letter - you always start with "Dear [Name]" and end with "Sincerely" (boilerplate), but the middle is your actual message
- Building a house - every house needs a foundation, walls, and a roof (boilerplate), but the interior design is unique

---

#### `<!doctype html>`

**What it does:** Tells the browser "Hey, this is a modern HTML5 document!"

**Beginner explanation:**

Think of this like the label on a food package. When you pick up a can, you need to know if it's soup or soda, right? Same thing here - the browser needs to know what kind of document it's dealing with.

In the old days (pre-2014), doctypes were LONG and complicated. HTML5 simplified it to just `<!doctype html>`.

**Is it optional?** _Technically_ yes, browsers will still try to render your page. BUT if you skip it, the browser goes into "quirks mode" where it tries to guess what you meant, and things can look broken. **Always include it** - it's the first line of every HTML file.

---

#### `<html lang="en">`

**What it does:** This is the ROOT element - everything else goes inside it. The `lang="en"` tells browsers and screen readers "this page is in English."

**Beginner explanation:**

The `<html>` tag is like the outer shell of an egg - everything else (the yolk, the white) goes inside it.

The `lang="en"` part is an **attribute**. Attributes give extra information about an element.

- `en` = English
- `de` = Deutsch (German)
- `es` = Español (Spanish)

**Why does this matter?**

- **Screen readers** (for people with visual impairments) use it to pronounce words correctly
- **Search engines** use it to understand what language your content is in
- **Translation tools** use it to know what they're translating from

**Is it optional?** The `<html>` tag itself? No, you need it. The `lang="en"` attribute? Technically yes, but **you should always include it** for accessibility reasons.

---

#### `<head>` Section

**What it does:** Contains **metadata** - information ABOUT your page, not the actual content users see.

**Beginner explanation:**

Think of a book:

- The **head** is like the book's cover and first pages (title, author, ISBN, copyright info)
- The **body** is the actual story

Users don't see what's in the `<head>`, but browsers, search engines, and other tools need it.

**Is it optional?** No, you need the `<head>` section.

---

##### Inside the `<head>`:

###### `<meta charset="UTF-8" />`

**What it does:** Tells the browser how to decode the text in your file.

**Beginner explanation:**

Computers store text as numbers. But which number represents which character? That's where "character encoding" comes in.

`UTF-8` is the most common encoding and supports:

- English letters: A, B, C
- German umlauts: ä, ö, ü, ß
- Emojis: 😊, 🚀, ❤️
- Pretty much every language in the world!

Without this line, characters like `ä` or `é` might show up as weird symbols: `Ã¤` or `Ã©`.

**Is it optional?** Technically yes, but **ALWAYS include it**. Without it, special characters can look broken. It should be one of the first things in your `<head>`.

---

###### `<meta name="viewport" content="width=device-width, initial-scale=1.0" />`

**What it does:** Makes your website work properly on mobile devices.

**Beginner explanation:**

Back in the early 2000s, websites were only designed for desktop computers. When smartphones came along, they had a problem: how to display desktop-sized websites on tiny phone screens?

Phones' default solution: "Pretend the screen is 980 pixels wide, then zoom way out so everything fits." This made websites look tiny and users had to pinch-zoom to read anything.

This `viewport` meta tag tells the phone: "No, don't do that! Make the website the actual width of the phone screen (`width=device-width`) and don't zoom in or out by default (`initial-scale=1.0`)."

**Breaking it down:**

- `width=device-width` = "Match the width of the device (phone, tablet, desktop)"
- `initial-scale=1.0` = "Start at 100% zoom (no zooming in or out)"

**Is it optional?** For desktop-only sites, yes. But in 2026, **everyone** browses on phones, so **always include it**. Without it, your site will look broken on mobile.

---

###### `<title>My First Webpage</title>`

**What it does:** Sets the text that appears in the browser tab and in search results.

**Beginner explanation:**

When you have 20 tabs open in your browser, how do you know which tab is which? The title!

This text appears:

- In the **browser tab** at the top
- In **bookmarks** when someone saves your page
- In **Google search results** as the blue clickable headline
- In the **taskbar** when you hover over the browser icon

**Is it optional?** Technically yes, but if you skip it, the browser will show the filename or URL, which looks unprofessional. **Always include a meaningful title.**

---

###### Other Common Head Elements

While the above are the essentials, you'll often see these in the `<head>` as well:

**Linking CSS:**

```html
<link rel="stylesheet" href="styles.css" />
```

**Linking JavaScript:**

```html
<script src="script.js"></script>
```

**Favicon (the little icon in the browser tab):**

```html
<link rel="icon" href="favicon.ico" />
```

**Description for search engines:**

```html
<meta name="description" content="A brief description of your page" />
```

---

#### `<body>` Section

**What it does:** Contains everything the user actually SEES and interacts with.

**Beginner explanation:**

Remember the book analogy?

- `<head>` = cover and info pages
- `<body>` = the actual story

Everything visible goes here:

- Text and paragraphs
- Images
- Buttons
- Forms
- Videos
- Links
- Everything!

**Is it optional?** Technically the browser can figure things out without it, but **never skip it**. It's fundamental HTML structure.

---

#### `</html>` - The Closing Tag

**What it does:** Closes the opening `<html>` tag from the beginning.

**Beginner explanation:**

Most HTML tags come in pairs:

- Opening tag: `<html>`
- Closing tag: `</html>`

The `/` means "this tag is closing now."

Think of it like parentheses in math: `(2 + 3)` - you need both the opening `(` and closing `)` to know what's inside.

**Is it optional?** Browsers are forgiving and will figure it out, but **always close your tags** in real projects. It's good practice and prevents bugs.

---

#### What's Actually Optional?

Here's the truth about what you can _technically_ skip:

**CAN'T SKIP (Required for valid HTML):**

- `<!doctype html>` - needed for modern rendering
- `<html>` - the root container
- `<head>` - where metadata goes
- `<title>` - every page needs a title
- `<body>` - where content goes

**TECHNICALLY OPTIONAL, BUT DON'T SKIP:**

- `<meta charset="UTF-8">` - prevents text encoding issues
- `<meta name="viewport"...>` - essential for mobile devices
- `lang="en"` - important for accessibility
- Closing tags - browsers forgive you, but don't develop bad habits!

**THE GOLDEN RULE:**

Just because you _can_ skip something doesn't mean you _should_. This boilerplate is like putting on your seatbelt - it takes 2 seconds and prevents problems down the road.

---

#### Quick Reference - Copy/Paste This Every Time

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Your Page Title Here</title>
  </head>
  <body>
    <!-- Your content goes here -->
  </body>
</html>
```

**Pro tip:** Most code editors have shortcuts to generate this automatically! In VS Code, type `!` and press Tab. Boom - instant boilerplate! ✨

---

### Common HTML Elements with Examples

Now that you understand the structure, let's look at the most common HTML elements you'll use.

#### Text Content

**Headings (h1-h6):**

```html
<h1>Main Heading (Biggest)</h1>
<h2>Subheading</h2>
<h3>Sub-subheading</h3>
<h4>Smaller heading</h4>
<h5>Even smaller</h5>
<h6>Smallest heading</h6>
```

**Paragraphs:**

```html
<p>This is a paragraph of text.</p>
<p>This is another paragraph.</p>
```

**Text Formatting:**

```html
<strong>Bold text (important)</strong>
<em>Italic text (emphasized)</em>
<mark>Highlighted text</mark>
<small>Smaller text</small>
<del>Deleted text</del>
<ins>Inserted text</ins>
<sub>Subscript</sub>
<sup>Superscript</sup>
```

---

#### Links and Media

**Links:**

```html
<a href="https://example.com">Visit Example</a>
<a href="about.html">About Page</a>
<a href="#section-id">Jump to Section</a>
<a href="mailto:email@example.com">Send Email</a>
```

**Images:**

```html
<img src="photo.jpg" alt="Description of photo" />
<img src="logo.png" alt="Company logo" width="200" />
```

**Video:**

```html
<video src="video.mp4" controls></video>
<video src="video.mp4" controls width="640" height="360"></video>
```

**Audio:**

```html
<audio src="song.mp3" controls></audio>
```

---

#### Lists

**Unordered List (bullets):**

```html
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

**Ordered List (numbers):**

```html
<ol>
  <li>First step</li>
  <li>Second step</li>
  <li>Third step</li>
</ol>
```

**Description List:**

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>

  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

---

#### Containers

**Generic containers:**

```html
<div>Block-level container</div>
<span>Inline container</span>
```

**Line breaks and horizontal rules:**

```html
<p>First line<br />Second line</p>

<hr />
<!-- Horizontal line/separator -->
```

---

#### Forms

**Basic form structure:**

```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" />

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" />

  <label for="message">Message:</label>
  <textarea id="message" name="message"></textarea>

  <button type="submit">Send</button>
</form>
```

**Common input types:**

```html
<input type="text" placeholder="Enter text" />
<input type="email" placeholder="Enter email" />
<input type="password" placeholder="Enter password" />
<input type="number" placeholder="Enter number" />
<input type="date" />
<input type="checkbox" />
<input type="radio" name="choice" />
<input type="file" />
```

**Select dropdown:**

```html
<select name="country">
  <option value="us">United States</option>
  <option value="uk">United Kingdom</option>
  <option value="de">Germany</option>
</select>
```

---

### Putting It All Together

Here's a complete example showing how these elements work together:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My Complete Page</title>
  </head>
  <body>
    <h1>Welcome to My Website</h1>

    <p>This is my <strong>first complete</strong> webpage!</p>

    <h2>About Me</h2>
    <p>I'm learning web development and this is my practice page.</p>

    <h2>My Hobbies</h2>
    <ul>
      <li>Coding</li>
      <li>Reading</li>
      <li>Gaming</li>
    </ul>

    <h2>Contact Me</h2>
    <form>
      <label for="email">Email:</label>
      <input type="email" id="email" required />

      <button type="submit">Send</button>
    </form>

    <hr />

    <p>
      <small>© 2026 My Website. All rights reserved.</small>
    </p>
  </body>
</html>
```

**What this demonstrates:**

- Proper boilerplate structure ✅
- Headings for organization ✅
- Paragraphs with text formatting ✅
- Lists for grouping items ✅
- A form for user input ✅
- Semantic organization ✅

---

## Semantic HTML & Structure

### What Does "Semantic" Mean?

**Semantic** means "relating to meaning."

In HTML, **semantic elements** have names that describe their purpose or the type of content they contain.

**Non-semantic example:**

```html
<div>Navigation menu</div>
<div>Main content</div>
<div>Sidebar</div>
```

**Semantic example:**

```html
<nav>Navigation menu</nav>
<main>Main content</main>
<aside>Sidebar</aside>
```

In the semantic version, the tag names (`<nav>`, `<main>`, `<aside>`) tell you what the content IS, not just that it's a container.

---

### Why Semantic HTML Matters

1. **Accessibility:**
   - Screen readers use semantic tags to help users navigate
   - Users can jump to `<main>` content or skip `<nav>` menus
   - Makes websites usable for people with disabilities

2. **SEO (Search Engine Optimization):**
   - Search engines understand content structure better
   - `<article>` signals this is main content
   - `<aside>` signals this is supplementary

3. **Maintainability:**
   - Code is easier to read and understand
   - Other developers know what each section does
   - Future you will thank present you

4. **Browser features:**
   - Reader modes can extract `<article>` content
   - Browsers can create outlines from headings
   - Future web features may rely on semantic structure

---

### Semantic vs Non-Semantic: The Difference

#### Non-Semantic (Bad)

```html
<div class="header">
  <div class="nav">
    <div class="link"><a href="/">Home</a></div>
    <div class="link"><a href="/about">About</a></div>
  </div>
</div>

<div class="content">
  <div class="post">
    <div class="title">My Blog Post</div>
    <div class="body">Post content...</div>
  </div>
</div>

<div class="footer">Copyright 2026</div>
```

**Problems:**

- Everything is a `<div>` - no meaning
- Relies on class names for structure
- Screen readers can't understand page structure
- Search engines don't know what's important

---

#### Semantic (Good)

```html
<header>
  <nav>
    <a href="/">Home</a>
    <a href="/about">About</a>
  </nav>
</header>

<main>
  <article>
    <h1>My Blog Post</h1>
    <p>Post content...</p>
  </article>
</main>

<footer>Copyright 2026</footer>
```

**Benefits:**

- Clear structure and meaning
- Screen readers understand the layout
- Search engines know this is an article
- Easier to read and maintain

---

### Common Semantic Elements

#### Page Structure Elements

**`<header>`**

Introductory content or navigation for a page or section.

```html
<header>
  <h1>My Website</h1>
  <nav>
    <a href="/">Home</a>
    <a href="/about">About</a>
  </nav>
</header>
```

**`<nav>`**

Navigation links (menus, table of contents).

```html
<nav>
  <a href="/">Home</a>
  <a href="/blog">Blog</a>
  <a href="/contact">Contact</a>
</nav>
```

**`<main>`**

The primary content of the page. **Only ONE `<main>` per page.**

```html
<main>
  <h1>Welcome</h1>
  <p>This is the main content...</p>
</main>
```

**`<footer>`**

Closing content (copyright, contact info, sitemap).

```html
<footer>
  <p>© 2026 My Website</p>
  <p>Contact: email@example.com</p>
</footer>
```

---

#### Content Grouping Elements

**`<section>`**

A thematic grouping of content, typically with a heading.

```html
<section>
  <h2>About Us</h2>
  <p>Information about our company...</p>
</section>

<section>
  <h2>Our Services</h2>
  <p>What we offer...</p>
</section>
```

**`<article>`**

Self-contained, independently distributable content (blog posts, news articles, forum posts).

```html
<article>
  <h2>How to Learn HTML</h2>
  <p>Posted on Feb 26, 2026</p>
  <p>Article content here...</p>
</article>
```

**`<aside>`**

Tangentially related content (sidebars, pull quotes, related links).

```html
<aside>
  <h3>Related Articles</h3>
  <ul>
    <li><a href="#">CSS Basics</a></li>
    <li><a href="#">JavaScript 101</a></li>
  </ul>
</aside>
```

---

#### Media and Content Elements

**`<figure>` and `<figcaption>`**

Self-contained content like images, diagrams, code snippets.

```html
<figure>
  <img src="chart.png" alt="Sales chart" />
  <figcaption>Q4 2025 Sales Data</figcaption>
</figure>
```

**`<details>` and `<summary>`**

Expandable/collapsible content.

```html
<details>
  <summary>Click to expand</summary>
  <p>Hidden content that appears when expanded.</p>
</details>
```

---

#### Complete Semantic Page Example

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
        <a href="/">Home</a>
        <a href="/about">About</a>
        <a href="/archive">Archive</a>
      </nav>
    </header>

    <main>
      <article>
        <h2>My First Blog Post</h2>
        <p>Posted on <time datetime="2026-02-26">February 26, 2026</time></p>
        <p>This is my first blog post about learning HTML...</p>

        <figure>
          <img src="html-diagram.png" alt="HTML structure diagram" />
          <figcaption>Basic HTML page structure</figcaption>
        </figure>
      </article>

      <aside>
        <h3>About the Author</h3>
        <p>A web development student learning HTML.</p>
      </aside>
    </main>

    <footer>
      <p>© 2026 My Blog. All rights reserved.</p>
      <p>Contact: <a href="mailto:me@example.com">me@example.com</a></p>
    </footer>
  </body>
</html>
```

---

### Text-Level Semantic Elements

These elements give meaning to specific text within your content:

**`<strong>`** - Important text (typically bold)

```html
<p>This is <strong>very important</strong>!</p>
```

**`<em>`** - Emphasized text (typically italic)

```html
<p>I <em>really</em> mean it.</p>
```

**`<mark>`** - Highlighted text

```html
<p>Search results for <mark>HTML</mark></p>
```

**`<code>`** - Code snippet

```html
<p>Use the <code>&lt;p&gt;</code> tag for paragraphs.</p>
```

**`<kbd>`** - Keyboard input

```html
<p>Press <kbd>Ctrl</kbd> + <kbd>S</kbd> to save.</p>
```

**`<abbr>`** - Abbreviation

```html
<p><abbr title="HyperText Markup Language">HTML</abbr> is awesome!</p>
```

**`<cite>`** - Citation/reference

```html
<p>As stated in <cite>The Web Design Book</cite>...</p>
```

---

### Media and Time Semantic Elements

**`<time>`** - Date or time

```html
<p>Published: <time datetime="2026-02-26">February 26, 2026</time></p>
<p>Event starts at <time>14:00</time></p>
```

**`<address>`** - Contact information

```html
<address>
  Email: <a href="mailto:contact@example.com">contact@example.com</a><br />
  Phone: (555) 123-4567
</address>
```

**`<blockquote>`** - Extended quotation

```html
<blockquote cite="https://source.com">
  <p>This is a quote from an external source.</p>
</blockquote>
```

**`<q>`** - Inline quotation

```html
<p>She said, <q>HTML is easier than I thought!</q></p>
```

---

## Quick Reference

### HTML Document Template

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Page Title</title>
  </head>
  <body>
    <!-- Your content here -->
  </body>
</html>
```

---

### Text Elements

| Element       | Purpose                      | Example                         |
| ------------- | ---------------------------- | ------------------------------- |
| `<h1>`-`<h6>` | Headings (h1 biggest)        | `<h1>Title</h1>`                |
| `<p>`         | Paragraph                    | `<p>Text here</p>`              |
| `<strong>`    | Important text (bold)        | `<strong>Important</strong>`    |
| `<em>`        | Emphasized text (italic)     | `<em>Emphasized</em>`           |
| `<mark>`      | Highlighted text             | `<mark>Highlighted</mark>`      |
| `<small>`     | Smaller text                 | `<small>Fine print</small>`     |
| `<del>`       | Deleted text (strikethrough) | `<del>Removed</del>`            |
| `<ins>`       | Inserted text (underline)    | `<ins>Added</ins>`              |
| `<sub>`       | Subscript                    | `H<sub>2</sub>O`                |
| `<sup>`       | Superscript                  | `E=mc<sup>2</sup>`              |
| `<br />`      | Line break                   | `Line 1<br />Line 2`            |
| `<hr />`      | Horizontal rule              | `<hr />`                        |
| `<code>`      | Code snippet                 | `<code>console.log()</code>`    |
| `<pre>`       | Preformatted text            | `<pre>Preserves   spaces</pre>` |

---

### Links and Media

| Element   | Purpose      | Example                                    |
| --------- | ------------ | ------------------------------------------ |
| `<a>`     | Link         | `<a href="url">Text</a>`                   |
| `<img />` | Image        | `<img src="path" alt="desc" />`            |
| `<video>` | Video player | `<video src="video.mp4" controls></video>` |
| `<audio>` | Audio player | `<audio src="song.mp3" controls></audio>`  |

**Link attributes:**

- `href` = destination URL
- `target="_blank"` = open in new tab
- `download` = download instead of navigate

**Image attributes:**

- `src` = image path (required)
- `alt` = description (required for accessibility)
- `width`, `height` = dimensions

---

### Lists

| Element | Description              | Example                      |
| ------- | ------------------------ | ---------------------------- |
| `<ul>`  | Unordered list (bullets) | See below                    |
| `<ol>`  | Ordered list (numbers)   | See below                    |
| `<li>`  | List item                | Used inside `<ul>` or `<ol>` |
| `<dl>`  | Description list         | For term/definition pairs    |
| `<dt>`  | Term in description list | `<dt>HTML</dt>`              |
| `<dd>`  | Description in list      | `<dd>Markup language</dd>`   |

**Examples:**

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

<!-- Description list -->
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

---

### Containers

| Element  | Description              | Example              |
| -------- | ------------------------ | -------------------- |
| `<div>`  | Generic block container  | `<div>Content</div>` |
| `<span>` | Generic inline container | `<span>Text</span>`  |

---

### Forms

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
  <input type="text" id="name" required />

  <label for="email">Email:</label>
  <input type="email" id="email" required />

  <label for="country">Country:</label>
  <select id="country">
    <option value="us">United States</option>
    <option value="uk">United Kingdom</option>
  </select>

  <button type="submit">Submit</button>
</form>
```

---

### Input Types

| Type       | Purpose           | Example                     |
| ---------- | ----------------- | --------------------------- |
| `text`     | Single-line text  | `<input type="text" />`     |
| `email`    | Email address     | `<input type="email" />`    |
| `password` | Password (hidden) | `<input type="password" />` |
| `number`   | Numeric input     | `<input type="number" />`   |
| `date`     | Date picker       | `<input type="date" />`     |
| `time`     | Time picker       | `<input type="time" />`     |
| `checkbox` | Checkbox          | `<input type="checkbox" />` |
| `radio`    | Radio button      | `<input type="radio" />`    |
| `file`     | File upload       | `<input type="file" />`     |
| `submit`   | Submit button     | `<input type="submit" />`   |
| `button`   | Generic button    | `<input type="button" />`   |
| `search`   | Search field      | `<input type="search" />`   |
| `url`      | URL input         | `<input type="url" />`      |
| `tel`      | Telephone number  | `<input type="tel" />`      |
| `color`    | Color picker      | `<input type="color" />`    |
| `range`    | Slider            | `<input type="range" />`    |

---

### Semantic Structure Elements

| Element        | Purpose                | Usage                                       |
| -------------- | ---------------------- | ------------------------------------------- |
| `<header>`     | Introductory content   | Page/section/article header                 |
| `<nav>`        | Navigation links       | Main menu, breadcrumbs                      |
| `<main>`       | Primary content        | Main page content (ONE per page)            |
| `<section>`    | Thematic grouping      | Related content with heading                |
| `<article>`    | Self-contained content | Blog posts, news articles                   |
| `<aside>`      | Tangential content     | Sidebars, related links                     |
| `<footer>`     | Closing content        | Page/section/article footer                 |
| `<figure>`     | Self-contained media   | Images with captions                        |
| `<figcaption>` | Caption for figure     | Describes the figure                        |
| `<time>`       | Date/time              | `<time datetime="2026-02-26">Feb 26</time>` |
| `<address>`    | Contact information    | Email, phone, address                       |
| `<details>`    | Expandable content     | Collapsible sections                        |
| `<summary>`    | Summary for details    | Visible title for `<details>`               |

---

### Common Attributes

| Attribute         | Used On                       | Purpose                  | Example                      |
| ----------------- | ----------------------------- | ------------------------ | ---------------------------- |
| `href`            | `<a>`                         | Link destination         | `href="https://example.com"` |
| `src`             | `<img>`, `<video>`, `<audio>` | Source file path         | `src="image.jpg"`            |
| `alt`             | `<img>`                       | Alternative text         | `alt="Description"`          |
| `class`           | Any element                   | CSS class for styling    | `class="highlight"`          |
| `id`              | Any element                   | Unique identifier        | `id="main-header"`           |
| `type`            | `<input>`, `<button>`         | Input/button type        | `type="email"`               |
| `placeholder`     | `<input>`, `<textarea>`       | Hint text                | `placeholder="Enter name"`   |
| `target`          | `<a>`                         | How to open link         | `target="_blank"` (new tab)  |
| `width`, `height` | `<img>`, `<video>`            | Dimensions               | `width="800"`                |
| `disabled`        | `<input>`, `<button>`         | Disable element          | `disabled`                   |
| `required`        | `<input>`, `<textarea>`       | Required field           | `required`                   |
| `value`           | `<input>`                     | Initial/default value    | `value="Default text"`       |
| `for`             | `<label>`                     | Links label to input     | `for="input-id"`             |
| `name`            | `<input>`, `<select>`         | Form field name          | `name="username"`            |
| `checked`         | `<input>` (checkbox/radio)    | Pre-selected             | `checked`                    |
| `selected`        | `<option>`                    | Pre-selected option      | `selected`                   |
| `controls`        | `<video>`, `<audio>`          | Show playback controls   | `controls`                   |
| `autoplay`        | `<video>`, `<audio>`          | Auto-play on load        | `autoplay`                   |
| `loop`            | `<video>`, `<audio>`          | Loop playback            | `loop`                       |
| `download`        | `<a>`                         | Download instead of open | `download`                   |

---

### Special Characters (HTML Entities)

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
| `™`       | `&trade;`           | Trademark            |
| `€`       | `&euro;`            | Euro symbol          |
| `£`       | `&pound;`           | Pound symbol         |
| `¥`       | `&yen;`             | Yen symbol           |
| `—`       | `&mdash;`           | Em dash              |
| `–`       | `&ndash;`           | En dash              |

**Example:**

```html
<p>Use &lt;p&gt; for paragraphs.</p>
<!-- Displays: Use <p> for paragraphs. -->

<p>Price: &euro;50 &amp; &pound;45</p>
<!-- Displays: Price: €50 & £45 -->
```

---

### Block vs Inline Elements

**Block elements** (start on new line, take full width):

- `<div>`, `<p>`, `<h1>`-`<h6>`, `<ul>`, `<ol>`, `<li>`, `<section>`, `<article>`, `<header>`, `<footer>`, `<nav>`, `<main>`, `<aside>`, `<form>`, `<table>`, `<blockquote>`, `<pre>`, `<hr />`, `<figure>`, `<details>`

**Inline elements** (stay on same line, take only needed width):

- `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<code>`, `<mark>`, `<br />`, `<input>`, `<button>`, `<label>`, `<select>`, `<textarea>`, `<small>`, `<sub>`, `<sup>`, `<abbr>`, `<cite>`, `<kbd>`, `<time>`, `<q>`

---

### Nesting Rules

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

<a href="#"><a href="#">Link inside link</a></a>
<!-- Links cannot be nested -->
```

---

### HTML Comments

```html
<!-- This is a comment -->
<!-- Comments are not displayed in the browser -->

<!--
  Multi-line comment
  for longer notes
-->
```

---

### Complete Page Example

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Complete Example</title>
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

        <figure>
          <img src="images/photo.jpg" alt="My photo" />
          <figcaption>A photo from my vacation</figcaption>
        </figure>
      </article>

      <section>
        <h2>Contact Me</h2>
        <form>
          <label for="email">Email:</label>
          <input type="email" id="email" required />

          <label for="message">Message:</label>
          <textarea id="message" required></textarea>

          <button type="submit">Send</button>
        </form>
      </section>
    </main>

    <footer>
      <p>&copy; 2026 My Website</p>
      <address>
        Email: <a href="mailto:me@example.com">me@example.com</a>
      </address>
    </footer>
  </body>
</html>
```

---

### Helpful Resources

- **MDN Web Docs:** [developer.mozilla.org](https://developer.mozilla.org)
- **W3C HTML Validator:** [validator.w3.org](https://validator.w3.org)
- **Can I Use:** [caniuse.com](https://caniuse.com) (browser compatibility)
- **HTML Spec:** [html.spec.whatwg.org](https://html.spec.whatwg.org)

---
