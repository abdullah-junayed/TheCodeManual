---
title: "Step 7: Semantic HTML"
description: "Write modern, accessible web pages using header, footer, main, article, and section."
series: "TheCodeManual"
track: "HTML"
step: 7
---

<!-- Frontmatter above works with most static site generators (Docusaurus, VitePress, Next.js/MDX, Jekyll, Hugo, Astro). Delete this block if your setup doesn't use it. -->

# Step 7: Semantic HTML

*Writing modern, accessible web pages using `<header>`, `<footer>`, `<main>`, `<article>`, and `<section>`*

> **Prerequisites:** You should already be comfortable with basic HTML tags (`<div>`, `<p>`, `<h1>`–`<h6>`, `<a>`, lists) and have VS Code set up from earlier steps in this series.

---

## What You'll Learn

By the end of this step, you'll be able to:

- Explain *why* semantic HTML matters — not just what the tags are
- Correctly use `<header>`, `<main>`, `<article>`, `<section>`, and `<footer>`
- Tell the difference between `<article>` and `<section>` (the #1 beginner mix-up)
- Structure a full page that's friendly to screen readers **and** search engines
- Spot and avoid the most common semantic HTML mistakes

---

## 1. What Is Semantic HTML, Really?

Picture a building where every door is labeled "Room." You could still find your way around by trying each door — but it's slow, and if someone is describing the building to you over the phone instead of you seeing it, it's nearly impossible.

Now picture the same building with doors labeled "Kitchen," "Bedroom," "Exit." Suddenly *anyone* — sighted or not — understands the layout just from the labels.

That's the difference between `<div>` soup and semantic HTML:

- A `<div>` is a generic, unlabeled "Room." It carries no meaning — it's just a box.
- `<header>`, `<main>`, `<article>`, `<section>`, and `<footer>` are **labeled doors**. They tell browsers, screen readers, search engines, and other developers exactly what role each part of the page plays.

**Semantic HTML** means choosing elements based on the *meaning* of the content, not how it looks. Appearance is CSS's job — structure and meaning are HTML's job.

---

## 2. Semantic vs. Non-Semantic, Side by Side

Same page, two ways:

**❌ Div soup — works, but says nothing about itself**
```html
<div class="header">
  <div class="logo">TheCodeManual</div>
  <div class="nav">...</div>
</div>
<div class="main-content">
  <div class="post">
    <div class="post-title">Learning to Code</div>
    <div class="post-body">...</div>
  </div>
</div>
<div class="footer">© 2026 TheCodeManual</div>
```

**✅ Semantic HTML — self-describing structure**
```html
<header>
  <h1>TheCodeManual</h1>
  <nav>...</nav>
</header>
<main>
  <article>
    <h2>Learning to Code</h2>
    <p>...</p>
  </article>
</main>
<footer>
  <p>&copy; 2026 TheCodeManual</p>
</footer>
```

Both render identically by default. The second version can be understood by a screen reader, a search engine crawler, or a teammate skimming your code — without reading a single class name.

---

## 3. The Core Elements

### `<header>`

Introductory content for whichever "section" it sits in — the whole page, or just one `<article>`. Usually holds a logo, title, nav, or tagline.

> ⚠️ **Common mix-up:** `<header>` is *not* the same as `<head>`. `<head>` holds invisible metadata (`<title>`, `<meta>`, CSS links). `<header>` is visible content inside `<body>`.

```html
<header>
  <h1>TheCodeManual</h1>
  <nav>
    <a href="/">Home</a>
    <a href="/tutorials">Tutorials</a>
  </nav>
</header>
```

You can have more than one `<header>` on a page — one for the site, and one inside each `<article>` for that post's title and date.

### `<main>`

The dominant, unique content of the page — the reason the page exists.

**Two hard rules:**
1. Only **one** `<main>` per page.
2. It must **not** be nested inside `<article>`, `<aside>`, `<header>`, `<footer>`, or `<nav>`.

```html
<main>
  <h1>Welcome to TheCodeManual</h1>
  <p>Your all-in-one guide to HTML, CSS, JS, and C.</p>
</main>
```

`<main>` also gives screen reader users a "skip to content" landmark, letting them jump past the nav bar instead of tabbing through every link first.

### `<article>`

A **self-contained** chunk of content that would still make sense if you cut it out and pasted it somewhere else entirely — a blog post, a news story, a forum reply, a product card.

**The test:** *Could this be lifted out and dropped into an RSS feed, a different site, or a "related posts" widget, and still make sense on its own?* If yes → `<article>`.

```html
<article>
  <header>
    <h2>Understanding Semantic HTML</h2>
    <p><time datetime="2026-07-09">July 9, 2026</time></p>
  </header>
  <p>Semantic HTML gives meaning to structure...</p>
  <footer>
    <p>Written by Junayed</p>
  </footer>
</article>
```

Notice the nested `<header>` and `<footer>` — they describe *this article*, not the whole page.

### `<section>`

A **thematic grouping** of content — usually with its own heading — that's part of a larger whole but doesn't stand alone.

**The test:** *Is this a distinct "chapter" or theme of what's around it, but meaningless outside that context?* If yes → `<section>`. If it's just a styling wrapper with no theme of its own → plain `<div>`.

```html
<section>
  <h2>What You'll Learn</h2>
  <ul>
    <li>Semantic tags</li>
    <li>Accessibility basics</li>
  </ul>
</section>
```

### `<footer>`

Footer content for its nearest section — copyright, contact links, sitemap, or (inside an `<article>`) author info.

```html
<footer>
  <p>&copy; 2026 TheCodeManual. All rights reserved.</p>
  <nav>
    <a href="/privacy">Privacy</a>
    <a href="/contact">Contact</a>
  </nav>
</footer>
```

Like `<header>`, you can have more than one — a page footer and an article footer are both valid.

---

## 4. `<article>` vs `<section>` — The #1 Beginner Confusion

Both group content. The difference is whether the content **stands on its own**.

| Ask yourself                                                                                | Answer | Use         |
| ------------------------------------------------------------------------------------------- | ------ | ----------- |
| "Would this make sense ripped out of context — in an RSS feed, a different page, a widget?" | Yes    | `<article>` |
| "Is this a themed chunk of the surrounding content, but meaningless alone?"                 | Yes    | `<section>` |
| "Do I just need a box to apply CSS to, with no real topic of its own?"                      | Yes    | `<div>`     |

They also nest into each other freely:
- A blog homepage `<section>` can contain several `<article>` cards.
- One long `<article>` can be broken into `<section>`s — "Introduction," "Examples," "Conclusion."

---

## 5. Putting It All Together

Here's a small blog homepage using everything above, plus `<nav>` and `<aside>` for context:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>TheCodeManual — Blog</title>
</head>
<body>

  <header>
    <h1>TheCodeManual</h1>
    <nav>
      <a href="/">Home</a>
      <a href="/tutorials">Tutorials</a>
      <a href="/about">About</a>
    </nav>
  </header>

  <main>
    <section>
      <h2>Latest Tutorials</h2>

      <article>
        <header>
          <h3>Step 6: CSS Flexbox</h3>
          <p><time datetime="2026-07-02">July 2, 2026</time></p>
        </header>
        <p>Build flexible, responsive layouts with Flexbox...</p>
        <footer><p>By Junayed · 5 min read</p></footer>
      </article>

      <article>
        <header>
          <h3>Step 7: Semantic HTML</h3>
          <p><time datetime="2026-07-09">July 9, 2026</time></p>
        </header>
        <p>Structure pages that both humans and machines understand...</p>
        <footer><p>By Junayed · 7 min read</p></footer>
      </article>
    </section>

    <aside>
      <h2>Related Topics</h2>
      <ul>
        <li><a href="#">HTML Forms</a></li>
        <li><a href="#">CSS Grid</a></li>
      </ul>
    </aside>
  </main>

  <footer>
    <p>&copy; 2026 TheCodeManual. Built while learning to code.</p>
  </footer>

</body>
</html>
```

**Notice the shape:** one `<header>`, one `<main>`, one page-level `<footer>` — and inside `<main>`, a `<section>` full of `<article>` cards sitting next to an `<aside>`. That's the standard skeleton behind most modern sites, from blogs to documentation hubs like this one.

> 🛠️ **VS Code tip:** Type `header>h1+nav` in an empty HTML file and hit `Tab`. That's [Emmet](https://docs.emmet.io/) — built into VS Code — expanding into a fully nested `<header>` with a heading and nav. Try `main>section>article*2` too.

---

## 6. Why This Actually Matters

**Accessibility.** Screen readers expose these elements as *landmarks* — regions a user can jump between with a keystroke instead of tabbing through the entire page. Each semantic tag maps to an implicit ARIA role:

| Element     | Implicit landmark role | Notes                                                                                                                                                |
| ----------- | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `<header>`  | `banner`               | Only at the top level — nested inside `<article>`/`<section>`/etc. it's *not* a landmark                                                             |
| `<nav>`     | `navigation`           |                                                                                                                                                      |
| `<main>`    | `main`                 | Only one per page                                                                                                                                    |
| `<article>` | `article`              |                                                                                                                                                      |
| `<section>` | `region`               | **Only if it has an accessible name** (a heading + `aria-labelledby`, or `aria-label`) — an unlabeled `<section>` isn't exposed as a landmark at all |
| `<aside>`   | `complementary`        |                                                                                                                                                      |
| `<footer>`  | `contentinfo`          | Only at the top level, same rule as `<header>`                                                                                                       |

That `<section>` caveat trips people up constantly — it's covered again in the mistakes list below.

**SEO.** Search engine crawlers use structural cues to tell your actual content apart from boilerplate like navigation and footers, which helps them understand what a page is *about*. Semantic markup isn't a magic ranking boost, but it removes ambiguity that `<div>` soup creates.

**Maintainability.** Six months from now, you (or a teammate) can scan `<header>`, `<main>`, `<article>` and immediately understand the page's shape — no class-name archaeology required.

---

## 7. Common Mistakes to Avoid

- ❌ **Multiple `<main>` elements** on one page — only one is allowed.
- ❌ **Nesting `<main>`** inside `<article>`, `<aside>`, `<header>`, `<footer>`, or `<nav>` — not permitted.
- ❌ **`<section>` with no heading** — if there's nothing to title it, it's probably just a `<div>`.
- ❌ **Confusing `<header>` with `<head>`** — one is visible content, one is invisible metadata.
- ❌ **Treating `<article>` and `<section>` as interchangeable** — a page full of unnamed `<section>`s is barely better than `<div>` soup for a screen reader user, since none of them are exposed as named landmarks.
- ❌ **Wrapping the whole page in `<section>`** instead of `<main>`.

---

## 8. Try It Yourself

Refactor this div-soup snippet into semantic HTML using what you just learned:

```html
<div id="top">
  <div class="logo">My Blog</div>
  <div class="links"><a href="#">Home</a> <a href="#">About</a></div>
</div>
<div id="content">
  <div class="post">
    <div class="title">My First Post</div>
    <div class="text">Hello world!</div>
  </div>
</div>
<div id="bottom">Copyright 2026</div>
```

<details>
<summary>✅ Show solution</summary>

```html
<header>
  <div class="logo">My Blog</div>
  <nav>
    <a href="#">Home</a>
    <a href="#">About</a>
  </nav>
</header>
<main>
  <article>
    <h2>My First Post</h2>
    <p>Hello world!</p>
  </article>
</main>
<footer>
  <p>Copyright 2026</p>
</footer>
```

</details>

---

## Key Takeaways

- Semantic HTML replaces meaningless `<div>`s with tags that describe *what* the content is, not just *where* it sits.
- `<main>` is unique and singular; `<header>`, `<footer>`, `<article>`, and `<section>` can repeat.
- `<article>` = stands alone. `<section>` = themed chunk of something bigger. `<div>` = no meaning, just a box.
- An unlabeled `<section>` doesn't get exposed as a landmark — give it a heading.
- These tags are free accessibility and SEO wins that cost nothing extra to write.

---

## Next Up

Now that your pages have real structure, **Step 8** moves on to styling that structure — turning this semantic skeleton into an actual designed layout with CSS.

*Update the links below to match your actual file paths:*

[← Back: Step 6](./forms.md) · [Next: Step 8 →](./meta-tags.md)