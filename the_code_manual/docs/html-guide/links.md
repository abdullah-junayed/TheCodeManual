# Step 3: Links and Navigation

So far, we have created individual web pages. But websites are rarely made of just one page—they are a collection of connected pages that users can move between.

This is where **links** come in.

HTML stands for **HyperText Markup Language**, and the word **HyperText** refers to text that links one document to another. Without links, the World Wide Web would simply be a collection of disconnected pages.

In this chapter, you'll learn how to connect pages together, link to external websites, create email and phone links, and build simple website navigation.

---

# The Anchor Tag (`<a>`)

The HTML element used to create hyperlinks is the **anchor tag**.

Syntax:

```html
<a href="destination">Link Text</a>
```

The browser needs two pieces of information:

1. **Where should the user go?**
2. **What text should the user click?**

The destination is provided using the **`href`** attribute.

Example:

```html
<a href="https://www.google.com">
    Visit Google
</a>
```

### Breakdown

```html
<a href="https://www.google.com">
    Visit Google
</a>
```

- `<a>` starts the hyperlink.
- `href` contains the destination.
- `Visit Google` is the clickable text.
- `</a>` ends the hyperlink.

When the user clicks the link, the browser opens Google.

---

# The `href` Attribute

The `href` attribute stands for **Hypertext Reference**.

It tells the browser where the link should go.

Without `href`, the anchor tag doesn't know what to open.

Example:

```html
<a href="about.html">
    About Us
</a>
```

---

# Absolute vs Relative URLs

One of the most important concepts in web development is understanding the difference between **absolute URLs** and **relative URLs**.

Choosing the correct one depends on whether you're linking to another website or another page within your own website.

---

# Absolute URLs (External Links)

An **absolute URL** contains the complete web address.

It usually starts with:

```
https://
```

Use an absolute URL whenever you want to link to another website.

Example:

```html
<a href="https://developer.mozilla.org">
    MDN Web Docs
</a>
```

Another example:

```html
<a href="https://github.com">
    GitHub
</a>
```

### Real-Life Analogy

Imagine you're sending a package to someone in another city.

You need their complete address:

- House Number
- Street
- City
- Country

Without the full address, the delivery company cannot find the destination.

An absolute URL works the same way.

---

# Relative URLs (Internal Links)

A **relative URL** links to another page inside your own website.

Instead of writing the full website address, you simply provide the location of the file.

Example:

```html
<a href="about.html">
    About
</a>
```

Another example:

```html
<a href="contact.html">
    Contact
</a>
```

If your file is inside a folder:

```html
<a href="pages/portfolio.html">
    Portfolio
</a>
```

### Real-Life Analogy

Imagine you're inside your house.

Instead of saying:

> "Go to House 24, Street 5, City..."

You simply say:

> "Go to the kitchen."

Because everyone is already inside the same house.

Relative URLs work exactly like that.

---

# When Should You Use Each?

| Situation                            | Use          |
| ------------------------------------ | ------------ |
| Link to another website              | Absolute URL |
| Link to another page in your website | Relative URL |
| Link to GitHub                       | Absolute URL |
| Link to About page                   | Relative URL |
| Link to Contact page                 | Relative URL |

---

# Opening Links in a New Tab

Normally, clicking a link replaces the current page.

Sometimes that's not what you want.

For example, if you're linking to:

- GitHub
- YouTube
- Wikipedia
- LinkedIn

it's often better to keep your own website open and open the external website in a new browser tab.

You can do this with the `target` attribute.

```html
<a
    href="https://github.com"
    target="_blank">
    Visit GitHub
</a>
```

The value `_blank` tells the browser:

> Open this link in a new tab.

---

# Why Use `target="_blank"`?

Imagine someone visits your portfolio website.

They click your GitHub link.

Without `target="_blank"`:

- Your portfolio closes.
- GitHub opens.

With `target="_blank"`:

- Your portfolio stays open.
- GitHub opens in a new tab.

This provides a better user experience.

---

# Adding Security with `rel`

When using `target="_blank"`, it's a good practice to also include the `rel` attribute.

```html
<a
    href="https://github.com"
    target="_blank"
    rel="noopener noreferrer">
    Visit GitHub
</a>
```

This improves security and performance by preventing the newly opened page from accessing your original page.

> **Best Practice:** Whenever you use `target="_blank"`, also add `rel="noopener noreferrer"`.

---

# Email Links

The anchor tag can also open the user's default email application.

Use the `mailto:` protocol.

Example:

```html
<a href="mailto:hello@thecodemanual.com">
    Email Us
</a>
```

When clicked, the user's email application opens with the recipient already filled in.

---

# Phone Links

On smartphones, users can tap a phone number to start a call.

Use the `tel:` protocol.

Example:

```html
<a href="tel:+1234567890">
    Call Support
</a>
```

On mobile devices, tapping the link opens the phone dialer.

---

# Download Links

You can even allow users to download files.

Example:

```html
<a
    href="files/guide.pdf"
    download>
    Download Guide
</a>
```

The `download` attribute tells the browser to download the file instead of opening it.

---

# Creating Website Navigation

Almost every website contains a navigation menu.

HTML provides the semantic `<nav>` element to group navigation links together.

Example:

```html
<nav>

    <a href="index.html">Home</a>

    <a href="about.html">About</a>

    <a href="services.html">Services</a>

    <a href="contact.html">Contact</a>

</nav>
```

The `<nav>` element helps browsers, search engines, and assistive technologies understand that these links are part of the site's navigation.

---

# Complete Example

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0">

    <title>My Portfolio</title>

</head>

<body>

    <h1>Welcome to My Portfolio</h1>

    <nav>

        <a href="index.html">Home</a> |

        <a href="about.html">About Me</a> |

        <a href="projects.html">Projects</a> |

        <a
            href="https://github.com"
            target="_blank"
            rel="noopener noreferrer">
            GitHub
        </a>

    </nav>

    <hr>

    <h2>Hello!</h2>

    <p>
        Thanks for visiting my website.
    </p>

    <p>

        If you'd like to work together,

        <a href="mailto:hireme@example.com">
            send me an email.
        </a>

    </p>

    <p>

        Need immediate help?

        <a href="tel:+1234567890">
            Call Me
        </a>

    </p>

</body>

</html>
```

---

# Best Practices

✅ Use meaningful link text.

Instead of:

```html
<a href="about.html">
    Click Here
</a>
```

Use:

```html
<a href="about.html">
    Learn More About Us
</a>
```

---

✅ Use relative URLs for pages inside your website.

---

✅ Use absolute URLs for external websites.

---

✅ Add `target="_blank"` only for external links.

---

✅ When using `target="_blank"`, also add:

```html
rel="noopener noreferrer"
```

---

✅ Group navigation links inside the `<nav>` element.

---

# Common Beginner Mistakes

### ❌ Forgetting the `href` attribute

Wrong:

```html
<a>
    Google
</a>
```

Correct:

```html
<a href="https://google.com">
    Google
</a>
```

---

### ❌ Using a full website URL for internal pages

Wrong:

```html
<a href="https://mywebsite.com/about.html">
```

Better:

```html
<a href="about.html">
```

---

### ❌ Using `target="_blank"` for every link

Internal pages usually should open in the same tab.

---

### ❌ Forgetting `rel="noopener noreferrer"`

Wrong:

```html
<a
    href="https://github.com"
    target="_blank">
```

Better:

```html
<a
    href="https://github.com"
    target="_blank"
    rel="noopener noreferrer">
```

---

### ❌ Using vague link text

Instead of:

```html
Click Here
```

Use:

```html
View My Portfolio
```

This improves accessibility and helps users understand where the link leads.

---

# Quick Summary

| HTML                        | Purpose                                  |
| --------------------------- | ---------------------------------------- |
| `<a>`                       | Creates a hyperlink                      |
| `href`                      | Specifies the destination                |
| `target="_blank"`           | Opens the link in a new tab              |
| `rel="noopener noreferrer"` | Improves security for new tabs           |
| `mailto:`                   | Opens the user's email app               |
| `tel:`                      | Starts a phone call on supported devices |
| `<nav>`                     | Groups navigation links                  |

---

# Practice Challenge

Create a simple website navigation that includes:

- Home
- About
- Services
- Projects
- Contact

Then add:

- A link to your favorite website (opens in a new tab).
- An email link.
- A phone link.
- A download link for a PDF file.

Try building everything from scratch before looking back at the examples.

---

# What's Next?

In the next chapter, you'll learn about **Images and Multimedia**, including:

- Displaying images with `<img>`
- Understanding the `src` and `alt` attributes
- Image paths
- Audio and video elements
- Embedding external media
- Best practices for accessible and responsive media

[← Back: Step 2](./text-formatting.md) · [Next: Step 4 →](./media.md)