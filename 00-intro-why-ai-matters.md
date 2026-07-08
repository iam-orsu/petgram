# FILE 00: Why AI is Important Right Now

---

## Before We Start

This course is not like the tutorials you find on YouTube where someone builds something fast and you just watch.

Here, you will actually build a real app yourself. You will type prompts, watch the AI write code, and understand what it built and why. By the end, you will have a working web application on your computer. Not a fake project. A real one.

---

## What Are We Building?

We are building something called **PetGram**.

PetGram is a simple website where people share photos of their pets. Here is how it works:

A person opens the PetGram website. They see the home page. They create an account. They log in. After logging in, they can upload a photo of their pet with a title and a small description. Other people who visit PetGram can see all the photos. If someone likes a photo, they click a like button. The like count goes up.

That is it. Upload photos. See other people's photos. Like them.

It sounds simple. But building it properly means you have to touch every part of a real web application. The page the user sees. The logic that runs in the browser. The server that handles data. The database that stores everything. The system that knows which user is logged in.

This is how real companies build their apps. We are building a small version of it so every part is easy to understand.

Here is everything PetGram will have by the end of this course:

**Home Page** - The first page a visitor sees. A navbar at the top, a big headline, and three boxes below explaining what PetGram is about.

**Login Page** - A form where the user types their email and password.

**JavaScript Validation** - Logic that checks the form before sending anything. If someone leaves a field empty, it shows an error. If the email looks wrong, it says so.

**Backend Server** - A program that runs in the background on your computer. When someone tries to log in, the browser sends the details to this program. It checks and says yes or no.

**Database** - Where all users and pet photos are stored. Not a fake list inside the code. A real database file on your computer.

**Authentication** - After login, the server gives the user a token. The browser saves this token and sends it with every future request so the server knows who is asking.

**Photo Upload** - A logged-in user can select a photo from their computer and upload it. The server saves it. The photo appears in the feed.

**Like System** - Any logged-in user can like any photo. The count saves to the database.

---

## Why AI Matters Right Now

For many years, learning to code meant one thing. You picked a language. You watched tutorials. You read documentation. You built small practice projects. Slowly, after months, you got good enough to build something real.

Most people gave up in the middle. Not because they were not smart. Because the gap between watching a tutorial and actually building something real was very big. Nobody showed them how to cross that gap.

That gap is now getting smaller very fast.

AI can now write code. Not rough code you have to fix. Working code, in the right files, that actually runs. You describe what you want in simple English. The AI writes the code and saves the files. You can run it immediately.

But there is a problem with how most people use this.

They open ChatGPT. They type "build me a login page." They copy the code. They paste it somewhere. It sort of works but not fully. Something breaks. They have no idea where to look. They paste the error back into ChatGPT. It gives a fix. The fix breaks something else. They go in circles for hours.

This happens because they are treating AI like a magic box. Type something in, get code out, paste it, hope for the best.

That is not the right way.

The right way is to understand what you are building well enough to write a clear prompt. You check what the AI produced. You understand the output well enough to catch when something looks wrong. You save each piece with git so you can go back if something breaks. You stay in control of your project even though AI is doing most of the writing.

That is what this course teaches.

---

## Two Types of Developers in 2026

Developers are now splitting into two groups.

The first group understands AI well enough to use it properly. They know what they want to build. They can describe it clearly. They review what AI writes. They understand the code well enough to know when something is wrong. They finish in hours what used to take days.

The second group either does not use AI at all, or just copies and pastes without understanding anything. When something breaks they have no idea where to start. Either way, they are falling behind.

This course puts you in the first group.

---

## What is Claude Code CLI?

This needs a proper explanation. Read this carefully.

### First, What is a CLI?

Most software you use has a graphical interface. Buttons, menus, windows. You click things.

CLI means Command Line Interface. It is a window where you type commands as plain text and press Enter. The computer reads what you typed and does something.

On Windows, this is called PowerShell or Command Prompt. On Mac it is called Terminal.

You have probably seen this in movies. A character typing very fast in a black window. That is a CLI.

It looks scary. It is not. You learn a few commands and you can do things faster than clicking with a mouse ever allows.

Every professional developer uses CLI every day. Now you will too.

### What is Claude Code?

Claude Code is an AI that lives inside your CLI.

You open your terminal, go to your project folder, type `claude` and press Enter. Claude starts up. It reads your entire project folder. It sees every file you have. It knows what you are building.

Then you type what you want. Not in a browser tab. Not in a separate app. Right there in the terminal where your code lives.

Claude thinks, writes the code, saves it to your actual files on your computer, and tells you what it did. You did not copy anything. You did not paste anything. The files are just updated.

### Why Claude Code Instead of ChatGPT in the Browser?

Here is the difference.

When you use ChatGPT or any browser AI for coding, you paste one or two files into the chat. You describe the problem. The AI gives you code back. But that code was written without seeing your other files. It might conflict with things in those files. You paste it in. Something breaks. You do not know why because the AI was working without full information.

With Claude Code CLI, you type your request. Claude reads all your files first. It understands your entire project before writing anything. It knows what variables exist, what functions are defined, what file imports what. It writes code that fits into what is already there.

Think of it like this. You are new to a city and you need directions. If you call someone who has never been there, they are just guessing. If you ask someone who grew up there, they actually know the roads. Claude Code is the person who knows the roads because it read all your files first.

### Three Claude Code Features We Use in This Course

**Feature 1: /init**

When you run `/init` inside Claude Code, it looks at your project folder and creates a file called `CLAUDE.md`. This is Claude's memory of your project.

It records things like what the project is called, what we are building, what technology we are using.

Every time you open Claude Code again, the first thing it does is read `CLAUDE.md`. By the time you type your first message, Claude already knows the full context. You do not have to re-explain yourself every session.

Without this, every time you close and reopen Claude, it has forgotten everything. With this, it always remembers.

We will run `/init` at the beginning of File 01.

**Feature 2: Agents**

An agent is Claude working through a multi-step task on its own.

When you give Claude a complicated request, agent mode means Claude does not just write one response and stop. It plans the steps, does the first step, checks the result, plans the next step, and keeps going until the task is done.

It is like telling a capable junior developer to "add a like button that saves to the database." A normal AI just gives you some code. An agent actually does the whole thing from start to finish.

We will use agents starting in File 03.

**Feature 3: Sub-Agents**

Sub-agents are multiple AI workers running at the same time on different parts of the same task.

When you have a big feature, Claude can split the work. One sub-agent handles the frontend. Another handles the backend. Another handles the database. They all work at the same time and Claude combines everything.

We will use sub-agents in File 04 and File 05.

---

## The Four Tools We Use

**Claude Code CLI** - The AI that writes and manages your code. Lives in your terminal. Reads your files.

**VS Code** - A free text editor for code. You will mostly use it to read what Claude wrote and check what changed.

**Git** - A tracking system for your code. Every change you make gets saved. You can go back to any earlier version anytime.

**Terminal (PowerShell on Windows)** - The command line window. You use it to open Claude Code, run git commands, and start your backend server.

---

## How This Course is Structured

**File 00 (this file)** - Why AI matters, what we are building, what Claude Code is, and how everything works.

**File 01** - Build the PetGram home page. HTML structure first, then CSS styling. Eight prompts, each one adding one piece.

**File 02** - Make the page work with JavaScript. Forms check their inputs. Buttons respond.

**File 03** - Build the backend server. A separate program that runs and handles login requests.

**File 04** - Add a real database. Store users. Store pet photos. Store likes.

**File 05** - Authentication and protected pages. Sessions, tokens, photo upload, and the like system.

---

## The Learning Loop

Every prompt in this course follows the same steps. Learn these steps and remember them.

**Step 1: Understand why.** We explain the concept and the reason before any prompt. What is this thing? Why do we need it?

**Step 2: You type the prompt.** Short. Clear. Simple English. You describe what you want Claude to build.

**Step 3: Claude builds it.** Claude reads your files, writes the code, and tells you what it did.

**Step 4: Check git diff.** Open VS Code Source Control. Click the changed file. Green lines are what Claude added. Red lines are what Claude removed. Read through it. You do not need to understand every character. Just know roughly what changed and where.

**Step 5: Commit.** Save this moment with a label. "Add navbar." "Style hero section." "Connect login to database."

**Step 6: Next prompt.**

This loop is how professional developers work, with or without AI. Understand the goal. Make the change. Review it. Save it. Move on.

---

## One-Time Setup

Do this once before you open File 01.

**Install VS Code**

Go to https://code.visualstudio.com and download it. Install it. Open it.

**Install Node.js**

Go to https://nodejs.org and download the LTS version. LTS means Long Term Support. It is the stable one. Install it.

After installing, open VS Code. Press `Ctrl + backtick` to open the built-in terminal. The backtick key is to the left of the 1 key on your keyboard.

Type this and press Enter:

```
node --version
```

If you see something like `v20.x.x`, Node.js is installed.

**Install Claude Code**

In the same terminal, type:

```
npm install -g @anthropic-ai/claude-code
```

Wait for it to finish. Then type:

```
claude --version
```

If you see a version number, it worked.

**Create the Project Folder**

Type each line and press Enter after each one:

```
mkdir petgram
cd petgram
git init
git config user.name "Your Name"
git config user.email "you@example.com"
code .
```

Replace "Your Name" and "you@example.com" with your actual name and email.

The last command opens VS Code with your new empty project folder.

**Log In to Claude Code**

In the terminal inside VS Code, type:

```
claude
```

The first time, it will ask you to log in with your Anthropic account. Follow the steps on screen. Once done, you will see a prompt waiting for your input. Claude Code is running and ready.

---

## The One Rule

After every prompt, before every commit, look at the git diff.

You do not need to understand every line. But you should understand roughly what changed, where it changed, and why.

This is how you stay in control. AI is writing the code. You are directing it and reviewing it. The moment you start committing code you have never looked at, you lose control of your own project.

Look at every diff. Every time.

---

## Open File 01

That is everything you need before we start building.

File 01 is where the actual code begins. We build the PetGram home page.

---

*Course: Building Real Apps with AI in 2026*
*File: 00 of 05*
