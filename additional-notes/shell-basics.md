# Shell Basics

## Understanding the Layers

### How Terminal, Shell, and OS Work Together

When you use your computer with clicks and windows, you're interacting with the **Operating System (OS)** through a graphical interface (GUI). But there's another way to talk to your computer: through text commands.

Here's how the pieces fit together:

```
┌─────────────────────────────────────┐
│   Operating System (OS)             │  ← The actual computer system
│   (macOS, Windows, Linux)           │     (manages files, runs programs)
└─────────────────────────────────────┘
              ↕
┌─────────────────────────────────────┐
│   Shell                             │  ← The interpreter
│   (zsh, bash, PowerShell)           │     (understands your commands)
└─────────────────────────────────────┘
              ↕
┌─────────────────────────────────────┐
│   Terminal                          │  ← The interface
│   (Terminal, iTerm, Git Bash)       │     (where you type commands)
└─────────────────────────────────────┘
```

**What each layer does:**

- **Terminal**: The window where you type. It's just a text interface—it doesn't understand commands itself.
- **Shell**: The brain. It takes the text you type, figures out what you mean, and tells the OS what to do.
- **OS**: The actual computer system. It executes the commands (create files, open programs, etc).

**Why this matters:**

When you type `ls` in the Terminal, here's what happens:

1. Terminal captures your text
2. Shell interprets "ls means list directory contents"
3. OS retrieves the directory listing
4. Shell formats it
5. Terminal displays it back to you

You're not talking directly to the computer—you're going through layers.

---

## **Core Concepts Before Commands**

### **Directories and Files: What You Need to Know**

You already know what folders and files are from using your computer normally. But when you use the terminal, you need to understand them differently.

**In a GUI (clicking around):**

- You SEE folders
- You CLICK to open them
- You SEE where you are

**In the terminal (typing commands):**

- You can't see anything unless you ask
- You tell the computer where to go with text
- You need to imagine the structure

**Key concept: `You're always "standing" inside a directory.`**

When you open the terminal, you're not floating in empty space. You're inside a specific directory (usually your home directory). Every command you run happens FROM that location.

---

### **The File System Tree Structure**

Your computer organizes everything like a tree with branches:

```
/                          (root - the very top)
└── Users
    └── raven              (your home directory ~)
        ├── Documents
        │   ├── resume.pdf
        │   └── Projects
        │       └── bootcamp
        │           ├── index.html
        │           └── style.css
        ├── Downloads
        │   └── image.png
        └── Desktop
```

**Important things to notice:**

- Directories can contain other directories (nested structure)
- Everything has a LOCATION (its position in the tree)
- To get somewhere, you follow the branches

---

### **Current Working Directory: Where You Are Right Now**

At any moment in the terminal, you're "standing" in one specific directory. This is called your **current working directory**.

**Example prompt:**

```bash
raven@laptop ~/Documents %
```

This tells you:

- `raven@laptop` = your username and computer name
- `~/Documents` = you're currently in the Documents directory
- `%` = the shell is ready for a command

**Why this matters:**

When you type a command like `ls`, the computer looks in your CURRENT directory. If you want to work with files somewhere else, you need to either:

1. Move to that directory first (`cd`)
2. Tell the computer the exact path to look

---

### **Paths: Absolute vs Relative**

A **path** is the location of a file or directory. There are two ways to describe a path:

**Absolute Path** = The FULL address from the root

```bash
/Users/raven/Documents/resume.pdf
```

This works from anywhere. It's the complete route.

**Relative Path** = The address from WHERE YOU ARE NOW

```bash
Documents/resume.pdf
```

This only works if you're standing in `/Users/raven/`

**Special shortcuts:**

- `~` = your home directory (`/Users/raven`)
- `.` = current directory (where you are now)
- `..` = parent directory (one level up)

**Example:**

If you're in `/Users/raven/Documents/Projects`:

- `cd ..` takes you to `/Users/raven/Documents`
- `cd ../..` takes you to `/Users/raven`
- `cd ~` takes you to `/Users/raven` (no matter where you are)

---

### **Understanding the Prompt**

The prompt tells you important information:

```bash
raven@laptop ~/Documents/Projects %
```

Breaking it down:

- `raven` = your username
- `@laptop` = your computer name
- `~/Documents/Projects` = where you currently are
- `%` = shell is waiting for input

**Note on prompt symbols:**

The symbol at the end varies depending on your shell and configuration:

- `%` is common in zsh (default on macOS)
- `$` is common in bash
- `>` appears in PowerShell or custom configurations
- `#` indicates root/admin user (be careful!)

**Your prompt might look different from examples you see online—that's normal.** What matters is recognizing WHERE you are (the path) and that the shell is ready for a command.

**If you ever get lost, type `pwd` (print working directory) to see exactly where you are.**

---

## **Essential Commands with Context**

This section breaks down commands by what they DO, not just what they're called. Each command includes examples showing what you'll actually see in the terminal.

### **Navigation Commands**

These commands help you move around the file system and understand where you are.

#### **`pwd` - Print Working Directory**

**What it does:** Shows you exactly where you are in the file system.

**When to use it:** When you're lost or want to confirm your location before running other commands.

**Example:**

```bash
~ % pwd
/Users/raven
```

**Common mistake:** `None`. This command is safe and simple. Use it whenever you're uncertain.

---

#### **`ls` - List Directory Contents**

**What it does:** Shows all files and folders in your current directory.

**When to use it:** To see what's available before you navigate or work with files.

**Example:**

```bash
~/Documents % ls
Projects    resume.pdf    notes.txt
```

**Useful variations:**

- `ls -l` = detailed list (shows permissions, size, date)
- `ls -a` = shows hidden files (files starting with `.`)
- `ls -la` = combines both

**Common mistake:** Expecting to see files that are in a different directory. <br>
**Remember:** `ls` only shows what's in your CURRENT location.

---

#### **`cd` - Change Directory**

**What it does:** Moves you to a different directory.

**When to use it:** Every time you need to work with files in a different location.

**Examples:**

```bash
~ % cd Documents
~/Documents % pwd
/Users/raven/Documents
```

```bash
~/Documents % cd ..
~ % pwd
/Users/raven
```

```bash
~/Documents/Projects % cd ~
~ % pwd
/Users/raven
```

**Common mistakes:**

- Trying to `cd` into a file (you can only `cd` into directories)
- Forgetting spaces matter: `cd Documents` works, `cdDocuments` doesn't
- Not using tab completion (type `cd Doc` then hit Tab. It autocompletes!)

---

### **File and Directory Operations**

These commands create, copy, move, and delete files and directories.

#### **`touch` - Create a New File**

**What it does:** Creates an empty file with the name you specify.

**When to use it:** Starting a new document, creating placeholder files.

**Example:**

```bash
~/Documents % ls
Projects

~/Documents % touch notes.txt

~/Documents % ls
Projects    notes.txt
```

**Common mistake:** Creating a file without an extension (like `touch notes` instead of `touch notes.txt`). It works, but you won't know what type of file it is later.

---

#### **`mkdir` - Make Directory**

**What it does:** Creates a new folder.

**When to use it:** Organizing your files into new folders.

**Example:**

```bash
~/Documents % mkdir bootcamp

~/Documents % ls
Projects    bootcamp    notes.txt
```

**Useful variation:**

- `mkdir -p Projects/bootcamp/week1` = creates nested directories all at once (parent directories too)

Without `-p`, you'd have to create each level separately:

```bash
mkdir Projects
cd Projects
mkdir bootcamp
cd bootcamp
mkdir week1
```

With `-p`, one command does it all.

**Common mistake:** Forgetting to use `-p` when creating multiple nested directories. Without it, you'll get an error if the parent directories don't already exist.

---

#### **`cp` - Copy Files**

**What it does:** Duplicates a file or directory.

**When to use it:** Making backups, copying files to different locations.

**Example:**

```bash
~/Documents % cp notes.txt notes-backup.txt

~/Documents % ls
notes.txt    notes-backup.txt
```

**Useful flags:**

- `cp -r Projects Projects-backup` = copies a directory and ALL its contents (recursive)
- `cp -i notes.txt backup.txt` = asks for confirmation before overwriting (interactive)
- `cp -v notes.txt backup.txt` = shows what's being copied (verbose)

**Why these matter:**

The `-r` flag is essential for directories—without it, `cp` won't work on folders.

The `-i` flag is a safety net. If `backup.txt` already exists, it'll ask: "overwrite backup.txt? (y/n)" instead of silently replacing it.

The `-v` flag helps you see what's actually happening, especially useful when copying multiple files.

**Common mistakes:**

- Forgetting `-r` when copying directories. Without it: `cp: Projects is a directory (not copied)`
- Accidentally overwriting files (use `-i` if you're unsure)

---

#### **`mv` - Move or Rename**

**What it does:** Moves a file to a different location OR renames it (same operation).

**When to use it:** Organizing files, fixing filenames.

**Examples:**

**Renaming:**

```bash
~/Documents % mv old-name.txt new-name.txt
```

**Moving to a different directory:**

```bash
~/Documents % mv notes.txt Projects/
```

**Useful flags:**

- `mv -i old.txt new.txt` = asks for confirmation before overwriting (interactive)
- `mv -v old.txt new.txt` = shows what's being moved (verbose)

**Why these matter:**

The `-i` flag prevents accidental overwrites. If `new.txt` already exists, it'll ask: "overwrite new.txt? (y/n)"

The `-v` flag shows you what happened: `old.txt -> new.txt`

**Common mistake:** Accidentally overwriting a file. If you move `file.txt` to a location where `file.txt` already exists, it replaces it without warning (unless you use `-i`).

---

#### **`rm` - Remove (Delete) Files**

**What it does:** Permanently deletes files. **There is NO trash bin. It's gone forever.**

**When to use it:** Cleaning up files you're absolutely sure you don't need.

**Example:**

```bash
~/Documents % rm old-notes.txt
```

**For directories:**

- `rm -r old-folder` = deletes a directory and ALL its contents (recursive)
- `rm -ri old-folder` = asks for confirmation for each file before deleting (recursive + interactive)

**Safety flag:**

- `rm -i old-notes.txt` = asks for confirmation before deleting (interactive)
- `rm -ri old-folder` = asks for confirmation for each file in the folder (can be tedious with many files)

When you use `-i`, you'll see:

```bash
~/Documents % rm -i old-notes.txt
remove old-notes.txt? (y/n)
```

Type `y` to confirm deletion, or `n` to cancel.

**Dangerous flags (use with extreme caution):**

- `rm -f` = force delete without confirmation
- `rm -rf` = force delete directory and all contents without ANY confirmation

**⚠️ CRITICAL WARNING:**

- `rm` is permanent. You CANNOT undo it.
- `rm -rf` is extremely dangerous—it will obliterate everything you point it at without asking.
- Always double-check what you're deleting: use `ls` first to confirm.
- Never run `rm -rf /` or `rm -rf ~` (these will destroy your entire system or home directory)

**Common mistakes:**

- Deleting the wrong file because you're in the wrong directory. Always `pwd` before `rm`.
- Using `-rf` casually -> this should feel dangerous because it IS dangerous.

---

### **Viewing and Editing Content**

#### **`cat` - Print File Contents**

**What it does:** Displays the entire contents of a file in the terminal.

**When to use it:** Quickly reading small files without opening an editor.

**Example:**

```bash
~/Documents % cat notes.txt
This is the content of my notes file.
Line 2 of the file.
```

**Common mistake:** Using `cat` on huge files. It'll flood your terminal. Use it only for small files.

---

#### **`nano` - Text Editor**

**What it does:** Opens a simple text editor inside the terminal.

**When to use it:** Editing files directly in the terminal (useful for config files or quick edits).

**Example:**

```bash
~/Documents % nano notes.txt
```

This opens the editor. Edit the file, then:

- `Ctrl + O` to save (it'll ask for filename, just press Enter to confirm)
- `Ctrl + X` to exit

**Common mistake:** Forgetting how to exit. The commands are shown at the bottom of nano (^ means Ctrl).

---

#### **`open` - Open in Default Application**

**What it does:** Opens a file or directory using the default program (macOS/Linux).

**When to use it:** Opening files in their associated apps, or opening Finder from terminal.

**Examples:**

```bash
~/Documents % open resume.pdf
```

(Opens the PDF in Preview)

```bash
~/Documents % open .
```

(Opens the current directory in Finder)

**Common mistake:** Trying to use `open` on Windows.It doesn't work. Windows uses `start` instead.

---

#### **`code` - Open in VS Code**

**What it does:** Opens files or directories in Visual Studio Code.

**When to use it:** Opening your project folders or specific files directly from the terminal.

**Examples:**

```bash
~/Documents/bootcamp % code .
```

(Opens the current directory in VS Code)

```bash
~/Documents % code index.html
```

(Opens `index.html` in VS Code)

```bash
~/Documents % code Projects/bootcamp
```

(Opens the `bootcamp` folder in VS Code)

**Important:** This command doesn't work automatically. You need to install it first.

---

**Troubleshooting: "command not found: code"**

If you get this error, the `code` command isn't installed in your system PATH. Here's how to fix it:

**On macOS:**

1. Open VS Code
2. Press `Cmd + Shift + P` to open the Command Palette
3. Type "shell command"
4. Select **"Shell Command: Install 'code' command in PATH"**
5. Restart your terminal
6. Try `code .` again

**On Windows:**

The `code` command should work automatically if you checked "Add to PATH" during VS Code installation. If it doesn't work:

1. Open VS Code
2. Press `Ctrl + Shift + P`
3. Type "shell command"
4. Select **"Shell Command: Install 'code' command in PATH"**
5. Restart your terminal

**On Linux:**

Usually works automatically. If not, you may need to add VS Code to your PATH manually (check VS Code documentation for your distro).

---

**Common mistakes:**

- Trying to use `code` before installing the shell command
- Forgetting to restart the terminal after installation
- Typing `vscode` or `vs-code` instead of just `code`

---

### **Utility Commands**

#### **`clear` - Clear the Screen**

**What it does:** Clears all previous output from your terminal window.

**When to use it:** When your terminal is cluttered and you want a fresh view.

**Example:**

```bash
~ % clear
```

**Shortcut:** `Ctrl + L` does the same thing.

**Common mistake:** None. It's harmless. Your command history is still saved.

---

#### **`curl` - Fetch Content from a URL**

**What it does:** Retrieves content from a web address and displays it in the terminal.

**When to use it:** Testing APIs, downloading files, checking your IP address.

**Example:**

```bash
~ % curl ipinfo.io
{
  "ip": "123.45.67.89",
  "city": "Berlin",
  "region": "Berlin",
  "country": "DE"
}
```

**Common mistake:** Expecting a pretty webpage view. `curl` shows the raw HTML/data.

---

## **Common Mistakes & Troubleshooting**

This section covers the errors beginners run into most often and how to fix them.

### **"command not found"**

**What you see:**

```bash
~/Documents % sl
zsh: command not found: sl
```

**What went wrong:**

- You mistyped the command (typo: `sl` instead of `ls`)
- Or the command doesn't exist on your system
- Or the command isn't installed/in your PATH

**How to fix it:**

- Double-check spelling: `ls` not `sl`
- Make sure you're using the right command for your OS (e.g., `open` on Mac, `start` on Windows)
- If it's a tool that needs installation (like `code`), follow the installation steps

---

### **"No such file or directory"**

**What you see:**

```bash
~/Documents % cd bootcamp
cd: no such file or directory: bootcamp
```

**What went wrong:**

- The folder doesn't exist in your current location
- You're in the wrong directory
- You mistyped the folder name (case-sensitive!)

**How to fix it:**

1. Check where you are: `pwd`
2. See what's available: `ls`
3. Verify the exact folder name (including capitalization)
4. If the folder is elsewhere, use the full path or navigate to the parent folder first

**Example:**

```bash
~/Documents % pwd
/Users/raven/Documents

~/Documents % ls
Projects    notes.txt

~/Documents % cd Projects/bootcamp
~/Documents/Projects/bootcamp %
```

---

### **"Permission denied"**

**What you see:**

```bash
~/Documents % rm system-file.txt
rm: system-file.txt: Permission denied
```

**What went wrong:**

- You don't have permission to delete/modify that file
- The file is protected by the system
- You need admin/root access

**How to fix it:**

- Don't force it with `sudo` unless you're ABSOLUTELY sure what you're doing
- Check if you're trying to modify system files (you probably shouldn't be)
- Make sure you own the file: `ls -l` shows file permissions

**When you might see this:**

- Trying to modify files in protected system directories
- Working with files created by another user
- Attempting to delete files without proper permissions

---

### **Accidentally Deleted Something Important**

**What you did:**

```bash
~/Documents % rm important-file.txt
```

**What went wrong:**
You deleted a file you actually needed.

**How to fix it:**
**You can't.** Terminal deletion is permanent. There's no Trash/Recycle Bin.

**Prevention:**

- Always use `ls` before `rm` to confirm what you're targeting
- Use `rm -i` to get confirmation prompts
- Keep backups of important files
- Double-check your current directory with `pwd` before deleting

---

### **Lost and Don't Know Where You Are**

**What happened:**
You've been navigating around and now you have no idea where you are in the file system.

**How to fix it:**

```bash
% pwd
/Users/raven/Documents/Projects/bootcamp/week1/exercises/css
```

Now you know exactly where you are.

**Quick escape back to familiar ground:**

```bash
% cd ~
~ %
```

This takes you back to your home directory, no matter where you were.

---

### **Typed Something Wrong and Can't Stop It**

**What happened:**
You started a command that's running forever, or you typed something and it's stuck.

**How to fix it:**
Press `Ctrl + C` to cancel the current command.

**Example:**

```bash
~/Documents % curl some-broken-url-that-hangs-forever
^C
~/Documents %
```

The `^C` shows that you pressed Ctrl+C and stopped the command.

---

### **Terminal is Cluttered and Messy**

**What happened:**
You've run a bunch of commands and the terminal is full of output.

**How to fix it:**

```bash
% clear
```

Or press `Ctrl + L`

This clears the screen. Your command history is still saved—you just get a clean view.

---

### **Can't Remember the Exact Command You Used Before**

**What happened:**
You ran a long command earlier and need to run it again, but you don't remember exactly what you typed.

**How to fix it:**
Press the **Up Arrow** key to scroll through your command history.

Keep pressing up until you find the command you want, then press Enter to run it again.

**Pro tip:** Press `Ctrl + R` and start typing part of the command. It will search your history and autocomplete.

---

### **Typed a Long Folder Name Wrong**

**What happened:**

```bash
~/Documents % cd Projects/web-development-bootcamp-2025
cd: no such file or directory
```

You mistyped part of the long folder name.

**How to fix it:**
Use **Tab completion**:

```bash
~/Documents % cd Pro<TAB>
~/Documents % cd Projects/
~/Documents/Projects % cd web<TAB>
~/Documents/Projects % cd web-development-bootcamp-2025/
```

Press Tab after typing a few letters—the terminal autocompletes the rest. If there are multiple matches, press Tab twice to see options.

---

## **Helpful Shortcuts & Quick Reference**

### **Keyboard Shortcuts That Save Time**

These shortcuts work in most terminals and will make your life significantly easier.

#### **Navigation & Editing**

- **Tab** - Autocomplete file/folder names
  - Type first few letters, press Tab to complete
  - Press Tab twice to see all options if there are multiple matches

- **Up Arrow** - Scroll through previous commands
  - Keep pressing to go further back in history
  - Press Down Arrow to go forward

- **Ctrl + R** - Search command history
  - Start typing part of a command you used before
  - Press Ctrl + R again to cycle through matches
  - Press Enter to run it, or Right Arrow to edit it first

- **Ctrl + A** - Jump to beginning of line
- **Ctrl + E** - Jump to end of line

- **Ctrl + U** - Delete everything before cursor

- **Ctrl + K** - Delete everything after cursor

- **Ctrl + W** - Delete the word before cursor

#### **Terminal Control**

- **Ctrl + C** - Cancel/stop the current command
  - Use this when something is stuck or running too long

- **Ctrl + L** or `clear` - Clear the terminal screen
  - Your history is still saved, just gives you a clean view

- **Ctrl + D** - Exit the terminal (same as typing `exit`)

---

### **Quick Reference: Essential Commands**

| Command                 | What It Does                       | Example                      |
| ----------------------- | ---------------------------------- | ---------------------------- |
| `pwd`                   | Print current directory path       | `pwd`                        |
| `ls`                    | List contents of current directory | `ls`                         |
| `ls -la`                | List with details and hidden files | `ls -la`                     |
| `cd <folder>`           | Change into a folder               | `cd Documents`               |
| `cd ..`                 | Go up one directory level          | `cd ..`                      |
| `cd ~`                  | Go to home directory               | `cd ~`                       |
| `touch <file>`          | Create a new empty file            | `touch index.html`           |
| `mkdir <folder>`        | Create a new folder                | `mkdir my-project`           |
| `mkdir -p <path>`       | Create nested folders              | `mkdir -p projects/web/css`  |
| `cp <source> <dest>`    | Copy a file                        | `cp notes.txt backup.txt`    |
| `cp -r <source> <dest>` | Copy a folder                      | `cp -r folder folder-backup` |
| `cp -i <source> <dest>` | Copy with confirmation             | `cp -i file.txt backup.txt`  |
| `mv <old> <new>`        | Move or rename                     | `mv old.txt new.txt`         |
| `mv -i <old> <new>`     | Move with confirmation             | `mv -i file.txt ../file.txt` |
| `rm <file>`             | Delete a file (permanent!)         | `rm old-file.txt`            |
| `rm -i <file>`          | Delete with confirmation           | `rm -i file.txt`             |
| `rm -r <folder>`        | Delete a folder and contents       | `rm -r old-folder`           |
| `rm -ri <folder>`       | Delete folder with confirmation    | `rm -ri old-folder`          |
| `cat <file>`            | Display file contents              | `cat notes.txt`              |
| `nano <file>`           | Edit file in terminal              | `nano config.txt`            |
| `open <file>`           | Open file in default app (macOS)   | `open image.png`             |
| `open .`                | Open current folder in Finder      | `open .`                     |
| `code <file/folder>`    | Open in VS Code                    | `code .`                     |
| `clear`                 | Clear terminal screen              | `clear`                      |
| `curl <url>`            | Fetch content from URL             | `curl ipinfo.io`             |

---

### **Special Symbols Reference**

| Symbol | Meaning                          | Example                             |
| ------ | -------------------------------- | ----------------------------------- |
| `~`    | Your home directory              | `cd ~`                              |
| `.`    | Current directory                | `code .`                            |
| `..`   | Parent directory (one level up)  | `cd ..`                             |
| `/`    | Root directory or path separator | `/Users/raven/Documents`            |
| `*`    | Wildcard (matches anything)      | `rm *.txt` (deletes all .txt files) |
