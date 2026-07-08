# FILE 01: Build the PetGram Home Page

---

## What Are We Building in This File?

When someone hears about PetGram and opens it in their browser, the first thing they see is the home page.

This page has one job. Tell the visitor what PetGram is in a few seconds. Make it look clean. Show them what they can do here.

By the end of this file, the PetGram home page will have three parts:

**Navbar** - A bar at the very top of the page. PetGram name on the left. Three links on the right.

**Hero section** - The big section below the navbar. A large headline. A short sentence. A button that says Get Started.

**Info boxes** - Three boxes below the hero. Each one explains one thing PetGram lets you do.

The page will not do anything interactive yet. The button will not open anything. The links will not go anywhere. That comes in File 02. Right now we focus only on structure and appearance.

---

## What is a Browser and What Does It Do?

Before writing any code, understand what a browser is actually doing.

A browser is a program. Chrome, Firefox, Edge are all browsers. They all do the same job. They take files and show them as web pages.

When you type a web address and press Enter, the browser sends a request to a server somewhere. The server sends back a file. That file is an HTML file. The browser reads it from top to bottom and builds the page on your screen.

Think of the browser as a reader. The HTML file is the script. The browser performs it on your screen.

Everything you see on any website, every button, every image, every heading, every paragraph, started as plain text in a file. The browser turned that text into what you see.

---

## What is HTML?

HTML is the language browsers understand.

But it is not a programming language. You cannot do math with it. It cannot make decisions. It does not run logic. Its only job is to describe what things are on the page.

Think about a printed magazine. It has different types of content. A big headline on the cover. Article titles inside. Paragraphs of text. Photo captions. Each of those is a different type of content. Each looks different and plays a different role.

HTML does the same thing for web pages. It says what each piece of content is.

"This is a main heading."
"This is a paragraph."
"This is a navigation menu."
"This is a button."
"This is an image."

The browser reads these labels and decides how to display each thing. Headings are large and bold by default. Paragraphs have space between them. Buttons look clickable.

Later, with CSS, you will completely change how all of these look. But HTML's job is only to say what each thing IS. Not how it should look.

---

## What is a Tag?

Labels in HTML are called tags.

Tags are words wrapped in angle brackets like this:

```
<h1>
```

That is an opening tag. It labels whatever comes after it as an h1, which means the main heading of the page.

Tags come in pairs. An opening tag and a closing tag. The closing tag has a forward slash before the word.

```
<h1>Welcome to PetGram</h1>
```

The opening `<h1>` tag says "a main heading starts here." The closing `</h1>` tag says "the heading ends here." The text between them is the actual heading content.

Some common tags you will see:

`<p>` and `</p>` for a paragraph of text.
`<nav>` and `</nav>` for a navigation bar.
`<button>` and `</button>` for a button.
`<section>` and `</section>` for a section of the page.
`<div>` and `</div>` for a generic container with no specific meaning.

Tags can go inside other tags. This is called nesting. The inner tag is the child. The outer tag is the parent.

```
<nav>
  <a href="#">Home</a>
  <a href="#">Login</a>
</nav>
```

Here `<nav>` is the parent. The two `<a>` tags are children sitting inside it. This tells the browser that those links belong to the navigation area.

---

## What is a Class?

Imagine you have five paragraphs on a page. You want four of them to look normal. One of them should have a bigger font and a different color because it is the intro paragraph.

If you write a CSS rule for `<p>`, it affects all five. You need a way to target just the one you want.

Classes solve this.

A class is a label you attach to an HTML tag. You make up the name. You put it in the tag using the `class=` attribute.

```
<p class="intro-paragraph">This is the special paragraph.</p>
<p>This is a normal paragraph.</p>
<p>This is another normal paragraph.</p>
```

Now you can write a CSS rule that targets only `intro-paragraph`. The other paragraphs are not affected because they do not have that class.

Think of classes like stickers you put on boxes. You have a room full of boxes. You put a red sticker on some of them. Now you can say "only move the boxes with red stickers." Without stickers, you either move all boxes or none.

You can also give the same class to multiple elements. Every element with that class gets the same style. If you have twenty feature cards across your site that all should look the same, they all get the same class name and one CSS rule styles all twenty at once.

---

## Tool: Claude Init

Before we write the first prompt, we set Claude Code up properly for this project.

Claude Code is powerful partly because of its memory. By default, when you close Claude and open it again, it has forgotten everything about your project. It does not know what files exist, what you are building, or what decisions you made last session.

`/init` fixes this.

When you run it, Claude looks at your project folder and creates a file called `CLAUDE.md`. This file is Claude's written memory of your project. It stores the project name, what you are building, the tech stack, and notes about important files.

Every time you open Claude Code after this, the first thing it does is read `CLAUDE.md`. By the time you type your first message, Claude already knows everything in that file. You do not have to re-explain. You just continue from where you left off.

Open the terminal in VS Code. Type:

```
claude
```

Once Claude is running, type this:

```
/init
```

Claude will ask about your project. Answer: the project is called PetGram, it is a pet photo sharing platform, and we will use HTML, CSS, JavaScript, and Node.js.

Claude creates `CLAUDE.md`. Check the VS Code Source Control panel. You will see the new file shown there.

Commit it.

```
Commit message: Initialize Claude context for PetGram
```

Now Claude remembers. Every session from here, it already knows what PetGram is.

---

## The HTML Prompts

We build the HTML structure in four prompts. Each prompt adds one section.

After each prompt, check git diff before committing. See what Claude added.

---

### Prompt 1: The Basic Page File

**Why we need this**

Every website starts with one file that the browser loads first. It is called `index.html`. The name `index` is a convention that servers and browsers understand. When someone visits your website without specifying a file, the server automatically looks for `index.html` and sends that.

Right now our project folder is empty. We need to create this file and give it the correct starting structure. The structure tells the browser that this is an HTML document, sets the title that appears in the browser tab, and links to the styling file we will create later.

**Your prompt**

```
Create the main page for a website called PetGram. The browser tab should show the name PetGram - Share Your Pets.
```

Check git diff. Commit.

```
Commit message: Create main HTML page for PetGram
```

---

### Prompt 2: The Navbar

**Why we need this**

Every website has a bar that runs across the very top. On the left is the brand name. On the right are links to other parts of the site.

This is called a navbar. Short for navigation bar. When a user lands on a new website and sees a navbar, they immediately feel comfortable. They know where they are and can see how to go somewhere else.

For PetGram, the navbar has the word PetGram on the left as the logo. On the right there are three links: Home, Explore, and Login.

Right now these links will not go anywhere because we only have one page. But having them there makes the page feel real. In later files we will build the pages these links point to.

**Your prompt**

```
Add a bar at the top of the page with the PetGram name on the left and three links on the right side: Home, Explore, and Login.
```

Check git diff. Notice the new code was added inside the body tag. Everything outside of body is unchanged.

Commit.

```
Commit message: Add top navigation bar
```

---

### Prompt 3: The Hero Section

**Why we need this**

Below the navbar is the most important section on the page. This is the first thing a visitor actually reads. You have about five seconds to tell them what PetGram is and why they should stay.

This section has three parts.

First, a big headline. Large font, bold, immediately readable. Something like "Share Your Pet's Best Moments."

Second, a short sentence below the headline. One or two lines that add a bit of context.

Third, a button that says "Get Started." A visitor who wants to sign up clicks this. Right now the button does nothing. In File 02 we will make it work.

**Your prompt**

```
Below the top bar, add a large section with a headline that says Share Your Pet's Best Moments, one short sentence below it, and a button that says Get Started.
```

Check git diff. The new section appears below the navbar in the HTML. Commit.

```
Commit message: Add hero section
```

---

### Prompt 4: The Info Boxes

**Why we need this**

After the hero section, some visitors want to understand PetGram better before clicking anything. What can I actually do here?

The info boxes answer that. Three boxes side by side. Each one describes one thing PetGram lets users do.

Box one: Share Photos. Upload photos of your pets.
Box two: Discover Pets. Browse photos that other people uploaded.
Box three: Connect. Follow other pet owners.

This layout is used everywhere on product websites. Three columns. Short and easy to read. A visitor can read all three in under ten seconds and understand the whole product.

Right now the boxes will stack vertically one under the other because we have not written CSS yet. After the CSS prompts they will line up in a proper row.

**Your prompt**

```
Below the hero section, add three boxes. The first box has the title Share Photos and a short description about uploading pet photos. The second has the title Discover Pets and a short description about browsing the feed. The third has the title Connect and a short description about following other pet owners.
```

Check git diff. Three new content blocks appear below the hero section.

Commit.

```
Commit message: Add info boxes section
```

---

## What is CSS?

Open `index.html` in your browser right now. Drag it into a browser window or right click it in VS Code and open it.

You will see plain black text on a white background. The navbar is just text at the top. The headline is large because h1 has a default size, but nothing else has any styling. The three boxes stack vertically. No colors. No layout. Nothing looks designed.

This is HTML with no CSS.

CSS stands for Cascading Style Sheets. Ignore the full name. Here is what it actually does.

CSS is a list of rules. Each rule says: find elements that match this description, and apply these visual settings to them.

Every visual thing you have ever seen on a website was set by CSS. The background color. The white text. The navbar being horizontal instead of vertical. The font being clean instead of the ugly browser default. The cards having rounded corners. All of it is CSS.

HTML says what content is. CSS says how that content looks.

---

## How CSS Connects to HTML

CSS lives in a separate file. For PetGram, it will be called `style.css`.

For the browser to apply the CSS to your HTML page, you need to tell the HTML file about the CSS file. This is done with one line inside the `<head>` section of the HTML.

```
<link rel="stylesheet" href="style.css">
```

This line tells the browser: before you display this page, load `style.css` and apply all the rules in it.

When Claude created `index.html` in Prompt 1, it included this link already. That is why the page will pick up the CSS automatically once we create `style.css`.

If you ever accidentally delete that link tag, all your CSS stops working instantly. The page goes back to plain HTML.

---

## CSS Rules and Selectors

A CSS rule looks like this:

```
selector {
  property: value;
  property: value;
}
```

The selector is how you tell CSS which element to target. The properties and values inside the braces are the visual settings you want to apply.

**Targeting by tag name**

Write the tag name directly.

```
p {
  color: gray;
  font-size: 16px;
}
```

This applies to every single `<p>` tag on the entire page.

**Targeting by class name**

Write a dot before the class name.

```
.main-banner {
  background-color: purple;
  color: white;
}
```

This applies only to elements that have `class="main-banner"`. Everything else is not affected.

**Targeting children inside a parent**

Write the parent, then a space, then the child.

```
nav a {
  text-decoration: none;
}
```

This targets `<a>` tags only when they are inside a `<nav>` element. Links anywhere else on the page are not touched.

We will use all three of these in the CSS prompts below.

---

## Flexbox

One of the most common layout problems in web design is making things sit side by side horizontally.

The navbar is a perfect example. We want PetGram on the left and the three links on the right. By default, elements stack vertically on top of each other. Getting the logo and links on the same horizontal line requires Flexbox.

When you add `display: flex` to a container element, its children stop stacking vertically and instead line up in a row side by side.

```
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

`display: flex` makes the children go horizontal.

`justify-content: space-between` spreads the children out. First child goes to the far left. Last child goes to the far right.

`align-items: center` aligns all children to the vertical center of the container. Without this they align to the top edge, which looks off.

These three lines together are why the logo ends up on the left and the links end up on the right. You will use Flexbox on almost every layout you ever build.

---

## CSS Grid

The info boxes need to sit in three equal columns side by side. For this, CSS Grid is the right tool.

Flexbox handles one direction at a time, either a row or a column.

Grid handles rows and columns at the same time.

```
.info-boxes {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
}
```

`display: grid` switches the container into grid mode.

`grid-template-columns: repeat(3, 1fr)` means three equal columns. The `1fr` means each column gets one equal fraction of the available space.

`gap: 32px` adds space between the columns so they are not touching each other.

When you put three child elements inside this grid container, they automatically fill into the three columns. First in column one, second in column two, third in column three.

---

## The CSS Prompts

Four prompts. Each one styles one section.

---

### Prompt 5: Set Up the Styling File

**Why we need this**

Before styling specific elements, two things need to happen first.

Fonts. Every browser has a default font it uses when no font is specified. Usually it is something like Arial or Times New Roman. These look generic and old. We want something cleaner. We will use a font called Inter. It is free, modern, and widely used. It comes from Google Fonts. We just include a link to it and the browser loads it automatically.

Reset. Every browser has its own built-in styles. Headings have default margins. Lists have default padding. Different browsers have slightly different defaults. A CSS reset removes all of these defaults so you start fresh. Every visual decision from this point is yours.

**Your prompt**

```
Create the styling file. Use the Inter font from Google and remove all the default spacing and sizing the browser applies. Set the page background to a very light gray.
```

Check git diff. A new `style.css` file appears. Commit.

```
Commit message: Add font and CSS reset
```

---

### Prompt 6: Style the Navbar

**Why we need this**

The navbar right now is just text stacked on top of itself. We need it to look like a real navbar.

We want a white background so it stands out from the light gray page. We want a soft shadow underneath it. We want the PetGram name on the left and the three links on the right, all on the same horizontal line.

The PetGram name should be in purple. This becomes our brand color throughout the app. The links should be dark gray. Pure black text can feel harsh. Dark gray is softer and looks more modern.

**Your prompt**

```
Make the top bar white with a soft shadow underneath it. Put the PetGram name in purple on the left side. Line the three links up horizontally on the right side.
```

Check git diff. New CSS rules appear in `style.css`. The `index.html` file has no changes.

Commit.

```
Commit message: Style navigation bar
```

---

### Prompt 7: Style the Hero Section

**Why we need this**

The hero section is the first thing the visitor really sees. It needs to make an impression.

We want a purple background. Not a flat single color but a gradient that fades from a deeper purple to a lighter purple. This looks better than a plain flat color.

The text should be white and centered. The headline should be large enough to read immediately.

The button should be white with purple text. When someone moves their mouse over the button, it should turn purple with white text. This is called a hover effect. It tells the user the button is clickable.

**Your prompt**

```
Give the hero section a purple gradient background that fades from one shade of purple to a lighter shade. Make the text centered and white. Style the button white with purple text, and when someone hovers over it, make the button turn purple with white text.
```

Check git diff. Banner styles appear in `style.css`. Look for the hover rule Claude adds for the button.

Commit.

```
Commit message: Style hero section
```

---

### Prompt 8: Style the Info Boxes

**Why we need this**

The three info boxes are currently stacking vertically. We need them side by side in equal columns using CSS Grid.

Each box should look like a card. White background. Slightly rounded corners. Comfortable space inside so the text is not pressing against the edges. A soft shadow to lift the card slightly off the page background.

Also, when a user moves their mouse over a box, the box should rise up slightly. Not instantly. Smoothly, over a fraction of a second. This kind of small animation makes the page feel alive. It also signals to the user that these boxes will eventually be clickable, which they will be in later files.

**Your prompt**

```
Arrange the three boxes side by side in equal columns. Give each box a white background with softly rounded corners and comfortable padding inside. When someone hovers over a box, make it rise up slightly with a smooth movement.
```

Check git diff. Grid layout rules and card styles appear in `style.css`.

Commit.

```
Commit message: Style info boxes
```

---

## Open It in the Browser

Open `index.html` in a browser. Right click the file in VS Code and choose "Open with Live Server" if you have that extension. Otherwise drag the file directly into a browser window.

You should see a white navbar at the top with PetGram in purple on the left and three links on the right. Below it, a section with a purple gradient background and a large white headline. Below that, three cards side by side on a light gray background.

Hover your mouse over one of the cards. It rises up smoothly. Hover over the button. It turns purple.

This is a real web page built with eight prompts.

---

## Check Your Git Log

In the terminal, type:

```
git log --oneline
```

You will see every commit in order, newest at the top. Every step is saved. Every change is labeled with what it was.

If a future prompt ever breaks something, you can come back to any of these saved points.

---

## What You Learned in This File

You now understand what a browser does with an HTML file. You understand that HTML labels content by type, not by appearance. You understand tags, nesting, and what a class is used for.

You understand what CSS is and how it connects to HTML through a link tag. You understand how selectors target elements by tag name, by class name, and by parent-child relationship.

You understand Flexbox and how it solves the problem of making things sit side by side horizontally.

You understand CSS Grid and how it creates equal columns for layouts like the info boxes.

You ran eight prompts. You kept each one focused on one thing. You checked git diff after every one. You committed each step with a clear message.

---

## What is Next

The page looks like a real product. But it is completely static. Nothing responds to clicks. The button does nothing.

File 02 adds JavaScript. JavaScript is the language that makes web pages respond to the user. When someone clicks something, JavaScript runs and decides what to do. Forms check their own data. Errors appear. The page becomes an actual experience instead of just a picture.

Open File 02 when you are ready.

---

*Course: Building Real Apps with AI in 2026*
*File: 01 of 05*
