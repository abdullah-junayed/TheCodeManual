# Step 1: Introduction & Boilerplate Setup

Welcome to **TheCodeManual**, a complete developer learning guide designed to help you understand web development and programming from the foundation level.

Before creating websites with HTML, CSS, and JavaScript, every developer needs to understand the basic structure of an HTML document. This structure is called the **HTML Boilerplate**.

An HTML boilerplate is a standard starting template that provides the necessary foundation for every webpage.

---

# What is HTML?

**HTML (HyperText Markup Language)** is the standard language used to create the structure of websites.

HTML defines the different parts of a webpage, such as:

* Headings
* Paragraphs
* Images
* Links
* Forms
* Buttons
* Tables
* Website sections

HTML is not a programming language. It is a **markup language** because it uses tags to describe the structure and meaning of content.

Example:

```html
<h1>Welcome to TheCodeManual</h1>
<p>Learn web development step by step.</p>
```

In this example:

* `<h1>` creates a main heading.
* `<p>` creates a paragraph.

---

# Creating Your First HTML File

Before writing HTML code, create a file called:

```
index.html
```

The `index.html` file is usually the main entry point of a website.

Most web servers automatically look for this file when opening a website.

---

# HTML Boilerplate Structure

Every modern HTML document starts with a basic structure:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TheCodeManual</title>
</head>

<body>

    <h1>Hello, Developer!</h1>
    <p>Welcome to TheCodeManual.</p>

</body>

</html>
```

Let's understand each part.

---

# 1. Understanding `<!DOCTYPE html>`

The first line of an HTML document is:

```html
<!DOCTYPE html>
```

This is called the **DOCTYPE declaration**.

## Purpose

It tells the browser:

> "This document uses HTML5."

Browsers need this information to correctly display the webpage.

Without it, browsers may enter **quirks mode**, where they try to support older HTML behavior, which can cause unexpected layout problems.

Example:

```html
<!DOCTYPE html>
```

Important points:

* It is not an HTML tag.
* It does not create visible content.
* It must appear at the very top of the document.
* It is not case-sensitive.

Correct:

```html
<!DOCTYPE html>
```

Also works:

```html
<!doctype html>
```

---

# 2. Understanding `<html>` Tag

The `<html>` element is the root element of every HTML document.

Example:

```html
<html>
</html>
```

Everything inside an HTML page exists inside this tag.

Structure:

```html
<html>

    Everything on the webpage goes here.

</html>
```

The `<html>` element contains two main sections:

1. `<head>`
2. `<body>`

Example:

```html
<html>

<head>

</head>

<body>

</body>

</html>
```

---

# The `lang` Attribute

The `<html>` tag usually contains a `lang` attribute.

Example:

```html
<html lang="en">
```

The `lang` attribute tells browsers and search engines what language the webpage uses.

Common examples:

English:

```html
<html lang="en">
```

Bangla:

```html
<html lang="bn">
```

Spanish:

```html
<html lang="es">
```

Benefits:

* Improves SEO
* Helps screen readers
* Improves accessibility
* Helps browsers understand content language

---

# 3. Understanding `<head>` Section

The `<head>` section contains information about the webpage that is not directly visible to users.

Example:

```html
<head>

    <title>TheCodeManual</title>

</head>
```

The browser uses the information inside `<head>` to understand how the page should work.

Common elements inside `<head>`:

## Title

```html
<title>TheCodeManual</title>
```

The title appears:

* In the browser tab
* In search engine results

Example:

```
Browser Tab:
TheCodeManual
```

---

## Character Encoding

```html
<meta charset="UTF-8">
```

This tells the browser how to read characters.

UTF-8 supports:

* English
* Bangla
* Arabic
* Chinese
* Emojis
* Most writing systems

Example:

```html
<meta charset="UTF-8">
```

---

## Viewport Settings

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

This makes websites responsive on mobile devices.

Explanation:

`width=device-width`

Means:

> Use the device's screen width.

`initial-scale=1.0`

Means:

> Start with normal zoom level.

Without this, websites may look incorrect on phones.

---

# 4. Understanding `<body>` Section

The `<body>` contains everything users can see on a webpage.

Examples:

* Text
* Images
* Videos
* Buttons
* Forms
* Navigation menus

Example:

```html
<body>

<h1>TheCodeManual</h1>

<p>Learn coding from zero.</p>

<button>Start Learning</button>

</body>
```

The browser displays this content on the page.

---

# Complete HTML Boilerplate Explained

```html
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>TheCodeManual</title>

</head>


<body>

    <h1>Welcome to TheCodeManual</h1>

    <p>Your programming journey starts here.</p>

</body>


</html>
```

Flow:

```
DOCTYPE
   |
   ↓
HTML
   |
   ├── HEAD
   |     |
   |     ├── Title
   |     ├── Meta Information
   |
   |
   └── BODY
         |
         ├── Text
         ├── Images
         ├── Buttons
         └── Website Content
```

---

# VS Code Setup for HTML Development

To write HTML professionally, we will use **Visual Studio Code**.

Recommended extensions:

## Live Server

Purpose:

* Runs your webpage instantly
* Automatically refreshes changes

## Prettier

Purpose:

* Automatically formats your code
* Keeps your code clean

## Auto Rename Tag

Purpose:

Automatically updates closing tags.

Example:

Change:

```html
<h1>Hello</h1>
```

to:

```html
<h2>Hello</h2>
```

The closing tag updates automatically:

```html
<h2>Hello</h2>
```

---

# Your First Practice Task

Create a file:

```
index.html
```

Write:

```html
<!DOCTYPE html>

<html lang="en">

<head>

<title>My First Website</title>

</head>

<body>

<h1>I am learning HTML</h1>

<p>This is my first webpage.</p>

</body>

</html>
```

Open it in your browser.

Congratulations! 🎉

You have created your first webpage.

---

# Key Takeaways

After completing this step, you should understand:

✅ What HTML is
✅ Why `<!DOCTYPE html>` is required
✅ The purpose of `<html>`
✅ How the `lang` attribute works
✅ The difference between `<head>` and `<body>`
✅ How to create a basic HTML file
✅ How to prepare VS Code for development

Next Step:

**Step 2: HTML Elements, Tags, Attributes, and Text Formatting**

[← Back: The Ultimate HTML Guide](./index.md) · [Next: Step 2 →](./text-formatting.md)