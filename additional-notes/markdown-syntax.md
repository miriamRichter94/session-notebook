# Markdown Syntax Reference

A beginner-friendly guide to Markdown formatting, organized by how often you'll use it.

---

## 1. The Basics

These are the building blocks you'll use in every Markdown file.

### Headers

**What they do:** Create section titles and hierarchy in your document.

**Syntax:**

```markdown
# Header 1 (Largest)

## Header 2

### Header 3

#### Header 4

##### Header 5

###### Header 6 (Smallest)
```

**Renders as:**

# Header 1 (Largest)

## Header 2

### Header 3

#### Header 4

##### Header 5

###### Header 6 (Smallest)

**When to use:** Organizing your notes, creating document structure, making section breaks.

**Best practice:** Use `#` for main title, `##` for major sections, `###` for subsections. Don't skip levels (don't go from `#` straight to `###`).

---

### Paragraphs

**What they do:** Create regular text blocks.

**Syntax:**

```markdown
This is a paragraph. Just write normally.

Leave a blank line between paragraphs to separate them.

Like this. Each paragraph gets its own space.
```

**Renders as:**

This is a paragraph. Just write normally.

Leave a blank line between paragraphs to separate them.

Like this. Each paragraph gets its own space.

**Important:** You need a **blank line** between paragraphs. If you don't leave a blank line, Markdown treats it as one continuous paragraph.

---

### Line Breaks

**What they do:** Force a new line within the same paragraph (without the paragraph spacing).

**Syntax:**

```markdown
First line  
Second line (add two spaces at the end of the line above)

Or use <br> for a line break
Like this<br>New line
```

**Renders as:**

First line  
Second line

Or use <br> for a line break
Like this<br>New line

**When to use:** When you want lines close together without full paragraph spacing (like addresses, poetry, lists of items).

---

## 2. Text Formatting

Make your text bold, italic, or stand out in other ways.

### Bold

**Syntax:**

```markdown
**This text is bold**
**This also works**
```

**Renders as:**

**This text is bold**  
**This also works**

**When to use:** Emphasizing important terms, making section intros stand out, highlighting key points.

---

### Italic

**Syntax:**

```markdown
_This text is italic_
_This also works_
```

**Renders as:**

_This text is italic_  
_This also works_

**When to use:** Emphasis, book/movie titles, foreign words, subtle highlighting.

---

### Bold AND Italic

**Syntax:**

```markdown
**_This is bold and italic_**
**_This also works_**
**_Or mix them_**
```

**Renders as:**

**_This is bold and italic_**  
**_This also works_**  
**_Or mix them_**

---

### Strikethrough

**Syntax:**

```markdown
~~This text is crossed out~~
```

**Renders as:**

~~This text is crossed out~~

**When to use:** Marking completed tasks, showing deprecated info, indicating changes.

---

### Inline Code

**Syntax:**

```markdown
Use `backticks` to highlight code or commands inline.

Example: Run the `git status` command to check your repo.
```

**Renders as:**

Use `backticks` to highlight code or commands inline.

Example: Run the `git status` command to check your repo.

**When to use:** File names, commands, variable names, short code snippets in sentences.

---

## 3. Lists

Organize information with bullets or numbers.

### Unordered Lists (Bullets)

**Syntax:**

```markdown
- Item one
- Item two
- Item three

Or use asterisks:

- Item one
- Item two

Or plus signs:

- Item one
- Item two
```

**Renders as:**

- Item one
- Item two
- Item three

**When to use:** Tasks, features, non-sequential information, brainstorming.

---

### Ordered Lists (Numbers)

**Syntax:**

```markdown
1. First item
2. Second item
3. Third item

The numbers auto-adjust, so you can use all 1s:

1. First
1. Second
1. Third
```

**Renders as:**

1. First item
2. Second item
3. Third item

**When to use:** Step-by-step instructions, rankings, sequential processes.

---

### Nested Lists

**Syntax:**

```markdown
- Main item
  - Sub-item (indent with 2 spaces)
  - Another sub-item
    - Even deeper (indent with 4 spaces)
- Another main item
  1. You can mix list types
  2. Like this
```

**Renders as:**

- Main item
  - Sub-item (indent with 2 spaces)
  - Another sub-item
    - Even deeper (indent with 4 spaces)
- Another main item
  1. You can mix list types
  2. Like this

**Pro tip:** Use 2 spaces per indentation level for nested items.

---

### Task Lists (Checkboxes)

**Syntax:**

```markdown
- [ ] Unchecked task
- [x] Completed task
- [ ] Another task
```

**Renders as:**

- [ ] Unchecked task
- [x] Completed task
- [ ] Another task

**When to use:** To-do lists, tracking progress, marking completion status.

**Note:** GitHub renders these as actual checkboxes you can click in issues/PRs.

---

## 4. Links & Images

Connect to other pages and embed visuals.

### Links

**Syntax:**

```markdown
[Link text](https://example.com)
[Link with title](https://example.com "Hover text appears here")
```

**Renders as:**

[Link text](https://example.com)  
[Link with title](https://example.com "Hover text appears here")

**When to use:** Referencing documentation, linking to resources, connecting related notes.

---

### Images

**Syntax:**

```markdown
![Alt text](path/to/image.png)
![Alt text with title](path/to/image.png "Image title on hover")
```

**Example with actual path:**

```markdown
![My screenshot](./images/screenshot.png)
![Web image](https://example.com/image.png)
```

**How it works:**

- `![Alt text]` - Description if image doesn't load
- `(path)` - Can be relative path or full URL
- `"title"` - Optional hover text

**When to use:** Adding screenshots to session notes, embedding diagrams, showing examples.

**Path tips:**

- `./images/pic.png` - Image in an `images` folder in same directory
- `../images/pic.png` - Image in parent directory's `images` folder
- `https://...` - Direct URL to image online

---

### Reference-Style Links (Advanced)

**What it does:** Lets you reuse the same URL multiple times while keeping your text clean and readable.

**The problem it solves:**

Imagine you're writing documentation and need to link to the same website multiple times. With normal links:

```markdown
Check out the [Git documentation](https://git-scm.com/doc) for more info.
You can also read [this guide](https://git-scm.com/doc) about branches.
The [official docs](https://git-scm.com/doc) have great examples.
```

That URL is repeated three times—messy, hard to read, and annoying to update if the URL changes.

**Reference-style fix:**

```markdown
Check out the [Git documentation][git-docs] for more info.
You can also read [this guide][git-docs] about branches.
The [official docs][git-docs] have great examples.

[git-docs]: https://git-scm.com/doc
```

**How it works:**

1. `[Link text][reference-id]` - The visible link text + a reference ID in brackets
2. `[reference-id]: https://actual-url.com` - At the bottom of your file, define what that reference ID points to

When rendered, all three links point to the same URL, but you only wrote the URL once.

**Another example:**

```markdown
I use [VS Code][vscode] for editing and [GitHub][gh] for version control.
Both [VS Code][vscode] and [GitHub][gh] are essential tools.

[vscode]: https://code.visualstudio.com
[gh]: https://github.com
```

**Why use it:**

- **Cleaner writing** - Text stays readable without long URLs breaking sentences
- **Easy updates** - Change the URL once at the bottom, all links update automatically
- **Reusable references** - Use the same reference ID throughout your document

**When NOT to use it:**

- If you're only linking to a URL once → just use regular `[text](url)` format
- If you want the URL visible right there → regular format is clearer

**Summary:** Optional advanced technique for repeated URLs. Most of the time regular `[text](url)` links are fine—this is a power-user option for specific situations.

---

## 5. Code Blocks

Display code or command-line examples.

### Inline Code

**Syntax:**

```markdown
Use single backticks for `inline code` within sentences.
```

**Renders as:**

Use single backticks for `inline code` within sentences.

---

### Code Blocks (No Syntax Highlighting)

**Syntax:**

````markdown
```
This is a plain code block
Multiple lines work
No syntax highlighting
```
````

**Renders as:**

```
This is a plain code block
Multiple lines work
No syntax highlighting
```

---

### Code Blocks with Syntax Highlighting

**Syntax:**

````markdown
```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}
```

```python
def greet(name):
    print(f"Hello, {name}!")
```

```bash
git status
git add .
git commit -m "Update files"
```

```html
<div class="container">
  <h1>Hello World</h1>
</div>
```

```css
.container {
  max-width: 1200px;
  margin: 0 auto;
}
```
````

**Renders as:**

```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}
```

```python
def greet(name):
    print(f"Hello, {name}!")
```

```bash
git status
git add .
```

```html
<div class="container">
  <h1>Hello World</h1>
</div>
```

```css
.container {
  max-width: 1200px;
  margin: 0 auto;
}
```

**Common language identifiers:**

- `bash` - Shell commands
- `javascript` or `js` - JavaScript
- `python` or `py` - Python
- `html` - HTML
- `css` - CSS
- `json` - JSON
- `markdown` or `md` - Markdown itself

**When to use:** Showing code examples, documenting commands, creating tutorials.

---

## 6. Tables

Organize data in rows and columns.

### Basic Table

**Syntax:**

```markdown
| Header 1 | Header 2 | Header 3  |
| -------- | -------- | --------- |
| Row 1    | Data     | More data |
| Row 2    | Data     | More data |
```

**Renders as:**

| Header 1 | Header 2 | Header 3  |
| -------- | -------- | --------- |
| Row 1    | Data     | More data |
| Row 2    | Data     | More data |

---

### Table with Alignment

**Syntax:**

```markdown
| Left-aligned | Center-aligned | Right-aligned |
| :----------- | :------------: | ------------: |
| Left         |     Center     |         Right |
| Text         |      Text      |          Text |
```

**Renders as:**

| Left-aligned | Center-aligned | Right-aligned |
| :----------- | :------------: | ------------: |
| Left         |     Center     |         Right |
| Text         |      Text      |          Text |

**Alignment symbols:**

- `:---` - Left-aligned (default)
- `:---:` - Center-aligned
- `---:` - Right-aligned

**When to use:** Comparing data, showing command options, organizing structured information.

**Pro tip:** Tables don't need to be perfectly aligned in the source—Markdown will handle it. This works too:

```markdown
| Header | Header              |
| ------ | ------------------- |
| Short  | Longer content here |
```

---

## 7. Advanced & Mixed Formatting

Extra tools for special cases.

### Horizontal Rules (Dividers)

**Syntax:**

**Syntax:**

- `---` (three dashes)
- `***` (three asterisks)
- `___` (three underscores)

**Renders as:**

---

**When to use:** Separating major sections, creating visual breaks, ending documents.

---

### Blockquotes

**Syntax:**

```markdown
> This is a quote or callout.
> You can have multiple lines.

> You can even nest quotes
>
> > Like this
```

**Renders as:**

> This is a quote or callout.
> You can have multiple lines.

> You can even nest quotes
>
> > Like this

**When to use:** Quoting sources, highlighting important notes, creating callout boxes.

---

### HTML Inside Markdown

**What it does:** Markdown supports inline HTML for advanced formatting.

**Example:**

```markdown
You can use HTML when Markdown isn't enough:

<div align="center">
  <strong>Centered bold text</strong>
</div>

<details>
<summary>Click to expand</summary>

Hidden content goes here.

</details>

Line breaks: <br>
Use HTML when needed.
```

**Renders as:**

<div align="center">
  <strong>Centered bold text</strong>
</div>

<details>
<summary>Click to expand</summary>

Hidden content goes here.

</details>

**When to use:**

- Centering elements (Markdown can't do this)
- Collapsible sections
- Custom styling
- Fine-grained control

**GitHub limitations:**

- GitHub strips certain HTML for security (no `<script>`, `<style>`, some attributes)
- Most basic HTML tags work fine (`<div>`, `<span>`, `<br>`, `<table>`, `<details>`)
- Test before assuming something works

---

### Escaping Special Characters

**What it does:** Shows Markdown syntax literally instead of formatting.

**Syntax:**

```markdown
Use backslash to escape:
\*Not italic\*
\# Not a header
\[Not a link\](url)
```

**Renders as:**

\*Not italic\*  
\# Not a header  
\[Not a link\](url)

**When to use:** When you need to show Markdown syntax itself, like in documentation or tutorials.

**Characters you might need to escape:**

```
\   backslash
`   backtick
*   asterisk
_   underscore
{}  curly braces
[]  square brackets
()  parentheses
#   hash
+   plus
-   minus
.   period
!   exclamation
```

---

### Comments (Hidden Text)

**Syntax:**

```markdown
<!-- This is a comment and won't show in the rendered document -->

You can use it for notes to yourself:

<!-- TODO: Add more examples here later -->
```

**When to use:** Notes to yourself, temporary placeholders, documentation that shouldn't render.

---

## Quick Reference Cheat Sheet

| Syntax              | What It Does                |
| ------------------- | --------------------------- |
| `# Header`          | Creates header (1-6 levels) |
| `**bold**`          | Makes text **bold**         |
| `*italic*`          | Makes text _italic_         |
| `~~strikethrough~~` | ~~Crosses out~~ text        |
| `` `code` ``        | Inline `code` formatting    |
| `[link](url)`       | Creates a link              |
| `![alt](image.png)` | Embeds an image             |
| `- item`            | Creates bullet point        |
| `1. item`           | Creates numbered list       |
| `> quote`           | Creates blockquote          |
| ` ``` `             | Creates code block          |
| `---`               | Creates horizontal rule     |
| `\| table \|`       | Creates table               |

---
