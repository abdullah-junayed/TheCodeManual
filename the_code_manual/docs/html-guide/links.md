# Step 3: Links and Navigation

Up to this point, we have built single, isolated web pages. But the magic of the World Wide Web is right there in the name—it is a *web* of connected pages. HTML literally stands for **HyperText** Markup Language, and in this step, we will learn how to create that hypertext using links.

## The Anchor Tag (`<a>`)

To create a link in HTML, we use the anchor tag: `<a>`. However, simply wrapping text in an `<a>` tag will not do anything on its own. The browser needs to know *where* the link should take the user. 

We provide this destination using the `href` (Hypertext Reference) attribute.

```html
<a href="https://www.google.com">Click here to go to Google</a>
```
- The Opening Tag: `<a href="...">` contains the destination URL.
- The Link Text: `Click here to go to Google` is the clickable text the user actually sees on the page.
- The Closing Tag: `</a>` tells the browser where the clickable area ends.

## Absolute vs. Relative URLs

Understanding the difference between absolute and relative URLs is one of the most important concepts for a beginner web developer to master.

### Absolute URLs (External Links)
An absolute URL contains the complete web address. You use this when you are linking to a completely different website that you do not own or control. It must include the `https://` protocol.

> **Analogy:** This is like mailing a letter to a friend. You need their full street address, city, state, and zip code for the mail carrier to find the destination.

```html
<p>Read more coding documentation on <a href="https://developer.mozilla.org">MDN Web Docs</a>.</p>
```

### Relative URLs (Internal Links)

A relative URL points to a file relative to the page you are currently working on. You use this when linking pages within your own website (like connecting your homepage to your "About" page). It does not need the `https://` part or your main domain name.

> **Analogy:** This is like telling a roommate to "go to the kitchen." You do not need to give them your home's full mailing address; you just give them directions relative to where they are currently standing inside the house.

```html
<a href="about.html">About Us</a>
<a href="contact.html">Contact Me</a>
<a href="pages/portfolio.html">View My Work</a>
```

## Opening Links in a New Tab

By default, when a user clicks a link, the browser leaves your page and loads the new one. If you are linking to an external website (like a Wikipedia article or a GitHub repository), you might want to keep your own website open and open the new link in a separate browser tab. 

You do this using the `target="_blank"` attribute.

```html
<a href="https://github.com" target="_blank">Open GitHub in a new tab</a>
```

## Advanced Links: Email and Phone

You can also use the anchor tag to trigger actions on the user's device, like opening their default email program or dialing a phone number on their smartphone.

* **Email (`mailto:`):** Opens the default mail client (like Outlook or Apple Mail).
* **Phone (`tel:`):** Prompts a phone call on mobile devices.

```html
<a href="mailto:hello@thecodemanual.com">Email Us</a>
<a href="tel:+1234567890">Call Support</a>
```

## Putting It All Together

Here is an example of a simple website structure, utilizing a mix of relative links for internal navigation and an absolute link (with a `target` attribute) for an external social media profile.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website Navigation</title>
</head>
<body>

    <h1>Welcome to My Portfolio</h1>

    <nav>
        <a href="index.html">Home</a> | 
        <a href="about.html">About Me</a> | 
        <a href="projects.html">Projects</a> | 
        <a href="https://linkedin.com/" target="_blank">My LinkedIn</a>
    </nav>

    <hr>

    <h2>Home Page Content</h2>
    <p>Thanks for stopping by! If you want to hire me, send me an email at <a href="mailto:hireme@example.com">hireme@example.com</a>.</p>

</body>
</html>
```