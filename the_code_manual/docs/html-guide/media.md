# Step 4: Images and Media

A web page with only text and links can get boring pretty quickly. To truly bring your website to life, you need visual and audio content. In this step, we will learn how to embed images, audio clips, and videos directly into your HTML.

## The Image Tag (`<img>`)

To display a picture on your web page, you use the `<img>` tag. Like the `<br>` and `<hr>` tags we learned about earlier, the `<img>` tag is **self-closing**—it does not have a closing `</img>` tag.

Instead of putting text *inside* the tag, we give the browser instructions using two mandatory attributes: `src` and `alt`.

### 1. The `src` Attribute (Source)
This tells the browser exactly where to find the image file. Just like the links we learned about in Step 3, this can be a **relative URL** (a file saved in your project folder) or an **absolute URL** (an image hosted on another website).

### 2. The `alt` Attribute (Alternative Text)
This is a brief text description of the image. **You should never skip this attribute.** * **Accessibility:** Screen readers will read this text out loud to visually impaired users.
* **Fallbacks:** If the image link breaks or the user has a slow internet connection, the browser will display this text instead.
* **SEO:** Search engines cannot "see" images, so they use the `alt` text to understand what the picture is about.

```html
<img src="images/my-dog.jpg" alt="A fluffy golden retriever playing in the park">

<img src="[https://example.com/logo.png](https://example.com/logo.png)" alt="Company Logo">
```
**Pro Tip**: To change the size of an image, you can add `width` and `height` attributes directly to the HTML (e.g., `<img src="logo.png" width="300" alt="Logo">`), but in modern web development, it is highly recommended to control image sizes using CSS later on!

## The Audio Tag (`<audio>`)

HTML5 introduced a native way to embed sound files (like `.mp3` or `.wav`) without needing third-party plugins. 

Unlike the image tag, the `<audio>` tag requires both an opening and a closing tag. You also must include the `controls` attribute; otherwise, your users will have no way to press play, pause, or adjust the volume!

```html
<audio controls>
    <source src="audio/podcast-episode-1.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
</audio>
```
- `<source>`: You can provide multiple source tags if you have the audio in different formats. The browser will pick the first one it supports.
- Fallback Text: The text right before the closing </audio> tag will only be shown if the user is using a severely outdated browser that doesn't understand HTML5 audio.

## The Video Tag `(<video>)`
Embedding a video works almost identically to embedding audio. You use the `<video>` tag, include the controls attribute so the user can play it, and provide the file path using the `<source>` tag.

Because videos take up physical space on the screen, it is a good idea to set a `width` or `heigh`t so it doesn't accidentally stretch across the user's entire monitor.

```html
<video controls width="600">
    <source src="videos/coding-tutorial.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>
```
**Note on Autoplay**: You can add the `autoplay` and `muted` attributes to make a video start playing automatically in the background. However, modern browsers will usually block autoplaying videos unless they are explicitly muted.

## Putting It All Together
Here is what a complete HTML page looks like when we combine text, an image, an audio clip, and a video.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Media Portfolio</title>
</head>
<body>

    <h1>Welcome to My Media Portfolio</h1>
    <p>Check out my latest creative work below.</p>

    <hr>

    <h2>Photography</h2>
    <img src="[https://images.unsplash.com/photo-1516117172878-fd2c41f4a759](https://images.unsplash.com/photo-1516117172878-fd2c41f4a759)" alt="A person typing on a laptop displaying code" width="500">

    <h2>Music Production</h2>
    <p>Listen to my newest lo-fi beat:</p>
    <audio controls>
        <source src="music/lofi-track.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

    <h2>Filmmaking</h2>
    <p>A short film about learning to code:</p>
    <video controls width="500">
        <source src="movies/short-film.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

</body>
</html>
```