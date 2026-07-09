# Step 2: Text Formatting & Headings

Now that we have our boilerplate set up, it is time to put some actual content inside the `<body>` tag. The most fundamental type of content on the web is text. 

In HTML, we do not just dump text onto the page; we wrap it in specific tags to give it structure and meaning. This tells the browser—and search engines like Google—what the text represents.

## Headings: Structuring Your Content

Headings are used to create a hierarchy on your web page, just like the table of contents in a book. HTML provides six levels of headings, from `<h1>` (the most important) down to `<h6>` (the least important).

```html
<h1>This is the Main Title</h1>
<h2>This is a Major Section Heading</h2>
<h3>This is a Sub-section Heading</h3>
<h4>This is a Minor Heading</h4>
<h5>This is a Very Minor Heading</h5>
<h6>This is the Smallest Heading</h6>
```

### The Golden Rules of Headings:
* **Only use one `<h1>` per page:** The `<h1>` represents the main topic of that specific page. Search engines rely heavily on it to figure out what your page is about.
* **Do not skip levels:** Always go in order. Do not jump from an `<h2>` straight down to an `<h4>`.
* **Do not use headings just to make text big or bold:** Headings are for structure. If you just want text to look bigger, you will use CSS later on.

## Paragraphs: The Standard Text

For regular blocks of text, we use the paragraph tag: `<p>`.

```html
<p>This is a standard paragraph of text. Browsers will automatically add a little bit of space (margin) before and after a paragraph to make it easy to read.</p>
<p>This is a second paragraph. It will appear below the first one.</p>
```
**An Important Note on White Space**: If you press Enter a bunch of times or add a ton of spaces inside a `<p>` tag in your VS Code editor, the browser will ignore it. HTML collapses multiple spaces and line breaks into a single space. To force a line break, you need a special tag.

## Line Breaks and Thematic Breaks

Sometimes you need to break a line of text without starting a whole new paragraph, or you want to visually separate sections.

* **Line Break (`<br>`):** Forces the text to drop to the next line. This is a "self-closing" tag, meaning it does not need a closing `</br>` tag.
* **Horizontal Rule (`<hr>`):** Creates a horizontal line across the page to separate content. It is also self-closing.

```html
<p>This is the first line.<br>This is the second line immediately below it.</p>
<hr>
<p>This paragraph is separated from the one above it by a line.</p>
```

## Inline Emphasis: Semantic vs. Visual

When you want to emphasize specific words inside a paragraph, you use inline tags. In modern HTML, we focus on semantic tags—tags that describe the meaning of the text, not just how it looks.

### Bold Text (`<strong>` vs. `<b>`)
If you want to make text bold to show that it is important, use the `<strong>` tag. Screen readers will actually read this text with a stronger voice to visually impaired users. *(Note: The older `<b>` tag also makes text bold, but it carries no semantic importance. Stick to `<strong>`!)*

### Italic Text (`<em>` vs. `<i>`)
If you want to emphasize a word or phrase, use the `<em>` (emphasis) tag. Browsers will display this as italic text. *(Note: Like the bold tag, the older `<i>` tag makes text italic but lacks meaning. Stick to `<em>`!)*

```html
<p>This is a normal sentence, but <strong>this part is very important</strong>.</p>
<p>I am <em>really</em> excited to learn HTML!</p>
```

## Putting It All Together

Here is what a complete, properly formatted section of a web page looks like when we combine headings, paragraphs, and emphasis:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Favorite Hobby</title>
</head>
<body>

    <h1>All About Photography</h1>
    
    <h2>Why I Love Taking Photos</h2>
    <p>Photography is more than just a hobby for me; it is a way to <strong>capture memories</strong> that last forever. I take my camera with me almost everywhere I go.</p>

    <hr>

    <h2>My Favorite Gear</h2>
    <p>I currently shoot on a mirrorless camera. Getting the right lens is <em>crucial</em> for good portraits.</p>

</body>
</html>
```

---

# Best Practices

✅ Use only one `<h1>` on each page.

---

✅ Use headings in order.

```
h1
 └── h2
      └── h3
```

Avoid skipping heading levels unless there's a good reason.

---

✅ Use `<strong>` instead of `<b>` when the text is important.

---

✅ Use `<em>` instead of `<i>` when emphasizing words or phrases.

---

✅ Use paragraphs for blocks of text instead of inserting multiple `<br>` tags.

---

# Common Beginner Mistakes

### ❌ Using multiple `<h1>` elements unnecessarily

Wrong:

```html
<h1>Home</h1>
<h1>About</h1>
<h1>Contact</h1>
```

Better:

```html
<h1>My Website</h1>

<h2>Home</h2>

<h2>About</h2>

<h2>Contact</h2>
```

---

### ❌ Skipping heading levels

Wrong:

```html
<h1>Main Title</h1>

<h3>Section</h3>
```

Better:

```html
<h1>Main Title</h1>

<h2>Section</h2>
```

---

### ❌ Using `<br>` to create large spaces

Wrong:

```html
<p>Hello</p>

<br>
<br>
<br>

<p>World</p>
```

Use paragraphs and CSS for spacing instead.

---

### ❌ Using `<b>` and `<i>` everywhere

Prefer:

```html
<strong>
```

and

```html
<em>
```

because they provide meaning as well as styling.

---

# Quick Summary

| HTML Element  | Purpose            |
| ------------- | ------------------ |
| `<h1>`        | Main page heading  |
| `<h2>`–`<h6>` | Section headings   |
| `<p>`         | Paragraph          |
| `<br>`        | Line break         |
| `<hr>`        | Horizontal divider |
| `<strong>`    | Important text     |
| `<em>`        | Emphasized text    |

---

# Practice Challenge

Create a webpage called **My Favorite Hobby** that contains:

- One `<h1>` heading.
- Two `<h2>` headings.
- Three paragraphs.
- A horizontal rule.
- At least one `<strong>` element.
- At least one `<em>` element.
- A paragraph containing a line break with `<br>`.

Try writing everything yourself before looking back at the examples.

---

# What's Next?

In the next chapter, you'll learn about **Links and Navigation**, including:

- Creating hyperlinks with `<a>`
- Understanding the `href` attribute
- Absolute and relative URLs
- Opening links in a new tab
- Creating email and phone links
- Building simple website navigation menus

By the end of the next chapter, you'll be able to connect multiple web pages together and navigate between them just like a real website.

[← Back: Step 1](./setup.md) · [Next: Step 3 →](./links.md)