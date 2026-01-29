# HTML Basics

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
