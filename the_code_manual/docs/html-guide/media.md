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

---

# Best Practices

✅ Always add an `alt` attribute to every image.

Good:

```html
<img
    src="cat.jpg"
    alt="A gray cat sleeping on a sofa">
```

The `alt` text helps screen readers understand the image and appears if the image cannot be loaded.

---

✅ Use descriptive file names.

Instead of:

```
image1.jpg
```

Use:

```
coding-workspace.jpg
```

Meaningful file names make your project easier to organize.

---

✅ Organize media files into folders.

Example project structure:

```
project/

│── index.html

│── images/
│     ├── logo.png
│     └── hero.jpg

│── audio/
│     └── podcast.mp3

│── videos/
│     └── intro.mp4
```

Keeping images, audio, and videos in separate folders makes your project much easier to maintain.

---

✅ Always include the `controls` attribute for audio and video.

Without it, users won't be able to play, pause, or adjust the media.

Example:

```html
<audio controls>

    <source
        src="music.mp3"
        type="audio/mpeg">

</audio>
```

---

✅ Specify the media format using the `type` attribute.

Example:

```html
<source
    src="video.mp4"
    type="video/mp4">
```

This helps browsers determine whether they can play the file.

---

✅ Resize images with CSS whenever possible.

Although HTML supports the `width` and `height` attributes, you'll learn in the CSS guide that styling images with CSS provides much more flexibility.

---

# Common Beginner Mistakes

### ❌ Forgetting the `alt` attribute

Wrong:

```html
<img src="dog.jpg">
```

Correct:

```html
<img
    src="dog.jpg"
    alt="A golden retriever playing in a park">
```

---

### ❌ Using incorrect file paths

Wrong:

```html
<img src="photo.png">
```

If the file is actually inside an `images` folder, the browser won't find it.

Correct:

```html
<img src="images/photo.png">
```

---

### ❌ Forgetting the `controls` attribute

Wrong:

```html
<audio>

    <source src="song.mp3">

</audio>
```

Users cannot play the audio.

Correct:

```html
<audio controls>

    <source src="song.mp3">

</audio>
```

---

### ❌ Forgetting the `<source>` element

Wrong:

```html
<video controls></video>
```

Correct:

```html
<video controls>

    <source
        src="movie.mp4"
        type="video/mp4">

</video>
```

---

### ❌ Using huge image files

Very large images make websites load slowly.

Whenever possible:

- Resize images.
- Compress images.
- Use modern image formats like WebP when appropriate.

---

# Quick Summary

| HTML Element | Purpose                                                    |
| ------------ | ---------------------------------------------------------- |
| `<img>`      | Displays an image                                          |
| `src`        | Specifies the image or media file location                 |
| `alt`        | Describes an image for accessibility                       |
| `width`      | Sets the media width                                       |
| `height`     | Sets the media height                                      |
| `<audio>`    | Embeds audio                                               |
| `<video>`    | Embeds video                                               |
| `<source>`   | Specifies the media file                                   |
| `controls`   | Displays playback controls                                 |
| `autoplay`   | Starts playback automatically (browser restrictions apply) |
| `muted`      | Starts media with the sound turned off                     |
| `loop`       | Repeats the media continuously                             |

---

# Practice Challenge

Create a webpage called **My Multimedia Gallery** that contains:

### A Heading

Add a title for your gallery.

---

### An Image

Display an image with:

- `src`
- `alt`
- `width`

---

### An Audio Player

Add an audio player using:

- `<audio>`
- `<source>`
- `controls`

---

### A Video Player

Add a video player using:

- `<video>`
- `<source>`
- `controls`
- `width`

---

### Extra Challenge

Create an `images`, `audio`, and `videos` folder inside your project and organize your files just like a real website.

---

# What's Next?

In the next chapter, you'll learn about **HTML Lists and Tables**, including:

- Creating unordered lists with `<ul>`
- Creating ordered lists with `<ol>`
- Adding list items with `<li>`
- Building tables using `<table>`
- Creating rows with `<tr>`
- Adding table headers with `<th>`
- Adding table data with `<td>`
- Organizing complex tables using `<thead>`, `<tbody>`, and `<tfoot>`

By the end of the next chapter, you'll be able to organize information into clean, structured lists and professional-looking data tables.

[← Back: Step 3](./links.md) · [Next: Step 5 →](./lists-tables.md)