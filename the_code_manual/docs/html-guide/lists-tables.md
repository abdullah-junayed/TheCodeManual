---
title: Lists and Tables
description: Organize content in HTML using unordered lists, ordered lists, and complex data tables.
---

# Step 5: Lists and Tables — Organizing Data in HTML

> **TheCodeManual** · HTML Fundamentals Track · Step 5

Not everything on a web page is a paragraph. Sometimes information is inherently a *collection* — a set of ingredients, a sequence of setup steps, a table of prices. HTML gives you three purpose-built tools for this: the **unordered list** (`<ul>`), the **ordered list** (`<ol>`), and the **table** (`<table>`).

Pick the wrong one and your page still *looks* fine — but it stops making sense to screen readers, search engines, and the next developer who opens your code. Pick the right one, and structure communicates meaning for free. That's the whole lesson in one sentence: **use the tag that matches the shape of your data, not the one that happens to render the way you want.**

## What You'll Learn

- How to build unordered and ordered lists, and nest them for hierarchy
- The attributes that control numbering in `<ol>` (`start`, `type`, `reversed`)
- Why tables exist for *data*, not for page layout
- How to structure "complex" tables with `<thead>`, `<tbody>`, and `<tfoot>`
- How to merge cells with `colspan` and `rowspan`
- How to make tables accessible with `<caption>` and `scope`
- The mistakes almost every beginner makes with lists and tables — so you can skip them

---

## Unordered Lists — `<ul>`

Think of `<ul>` as a sticky note of bullet points. The items are related, but their **order carries no meaning** — shuffling them wouldn't change what the list means.

```html
<h3>Frontend Tools I Use</h3>
<ul>
  <li>VS Code</li>
  <li>Chrome DevTools</li>
  <li>Figma</li>
  <li>Git</li>
</ul>
```

Every item goes inside a `<ul>...</ul>` container, and every item is wrapped in its own `<li>` (list item) tag. The browser adds a bullet point automatically — that's just the default *style*, not a structural rule, and you'll learn how to change it once you get to the CSS guide. Worth knowing now so you don't assume the bullet is mandatory.

### Nesting Lists

Real data is often hierarchical — a category with sub-items. To nest a list, place the *entire* child `<ul>` **inside an `<li>`** of the parent list, not as a sibling of the parent's `<li>` elements:

```html
<ul>
  <li>Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </li>
  <li>Backend
    <ul>
      <li>Node.js</li>
      <li>Databases</li>
    </ul>
  </li>
</ul>
```

> ⚠️ **Common mistake:** Putting a `<ul>` directly after a `<li>` as a sibling, instead of nesting it *inside* that `<li>`. Browsers often render it in a way that looks okay, but it's invalid HTML — and it breaks the clean parent-child structure that later styling and scripting both rely on.

---

## Ordered Lists — `<ol>`

If `<ul>` is a sticky note, `<ol>` is a recipe. **Sequence is the point.** Swap step 2 and step 3, and the instructions stop working.

```html
<h3>Setting Up VS Code</h3>
<ol>
  <li>Download VS Code from code.visualstudio.com</li>
  <li>Install the "ESLint" and "Prettier" extensions</li>
  <li>Open your project folder via File → Open Folder</li>
  <li>Open the integrated terminal via View → Terminal</li>
</ol>
```

By default, browsers number items `1, 2, 3, ...` — but `<ol>` has three attributes that give you real control:

| Attribute  | What it does                                         | Example                      |
| ---------- | ---------------------------------------------------- | ---------------------------- |
| `start`    | Sets the starting number                             | `<ol start="5">` begins at 5 |
| `type`     | Changes the numbering style: `1`, `A`, `a`, `I`, `i` | `<ol type="A">` → A, B, C... |
| `reversed` | Counts down instead of up                            | `<ol reversed>` → 5, 4, 3... |

```html
<ol type="A" start="3">
  <li>Section C</li>
  <li>Section D</li>
  <li>Section E</li>
</ol>
```

### Nesting Ordered Lists

Same rule as before: the nested `<ol>` lives *inside* the `<li>` it belongs to.

```html
<ol>
  <li>Install prerequisites
    <ol type="a">
      <li>Node.js</li>
      <li>Git</li>
    </ol>
  </li>
  <li>Clone the repository</li>
</ol>
```

> ⚠️ **Common mistake:** Choosing `<ol>` or `<ul>` based on how you *want it to look* rather than what the data *means*. A screen reader announces "List, 4 items" for a `<ul>`, but explicitly announces position for an `<ol>` — it communicates sequence on purpose. Force numbers onto a list where order doesn't matter (or strip them from one where it does), and you're sending the wrong signal to every assistive technology and search engine parsing your page.

---

## Tables — `<table>`

A table is for exactly one kind of data: **anything that naturally forms rows and columns**, like a spreadsheet — sales figures, comparison charts, schedules, pricing plans.

> 📌 **A short history lesson:** In the late 1990s and early 2000s, developers used nested `<table>` elements to build entire *page layouts* — headers, sidebars, footers, all crammed into table cells because CSS layout tools didn't exist yet. It worked, but it was a nightmare to maintain and meant nothing to screen readers. Today, layout belongs to CSS Grid and Flexbox — full stop. If you catch yourself reaching for a `<table>` to line things up visually, that's the signal to reach for CSS instead. Tables are for **data**, never for layout.

### Basic Anatomy

```html
<table>
  <tr>
    <th>Language</th>
    <th>Type</th>
  </tr>
  <tr>
    <td>JavaScript</td>
    <td>Interpreted</td>
  </tr>
  <tr>
    <td>C</td>
    <td>Compiled</td>
  </tr>
</table>
```

- `<table>` — the container for the whole table
- `<tr>` — table row
- `<th>` — header cell (bold and centered by default, and semantically marks it as a header)
- `<td>` — a regular data cell

This works, but it's the "toy example" version. Real, production tables need more structure — which is where "complex" tables come in.

### Structuring Complex Tables

Once a table has more than a couple of rows, wrap it in three semantic groups: `<thead>` for the header row(s), `<tbody>` for the actual data, and `<tfoot>` for summary rows like totals. Add a `<caption>` so the table has an accessible title, and a `scope` attribute on every `<th>` so assistive tech knows exactly which cells that header describes.

```html
<table>
  <caption>Monthly Budget Tracker — July 2026</caption>
  <thead>
    <tr>
      <th scope="col">Category</th>
      <th scope="col">Budgeted</th>
      <th scope="col">Spent</th>
      <th scope="col">Remaining</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Groceries</th>
      <td>$400</td>
      <td>$350</td>
      <td>$50</td>
    </tr>
    <tr>
      <th scope="row">Transport</th>
      <td>$150</td>
      <td>$120</td>
      <td>$30</td>
    </tr>
    <tr>
      <th scope="row">Entertainment</th>
      <td>$100</td>
      <td>$110</td>
      <td>-$10</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th scope="row">Total</th>
      <td>$650</td>
      <td>$580</td>
      <td>$70</td>
    </tr>
  </tfoot>
</table>
```

Two `scope` values are used here:
- `scope="col"` — this header describes everything *below it in the column*
- `scope="row"` — this header describes everything *to its right in the row*

Without `scope`, a screen reader just reads "$350" with no context. With it, a user hears something closer to "Spent, Groceries: $350" — the difference between a usable table and an unusable one.

### Merging Cells — `colspan` and `rowspan`

Sometimes one cell needs to stretch across multiple columns or rows.

**`colspan`** stretches a cell horizontally — useful for a banner or grouped label:

```html
<table>
  <thead>
    <tr>
      <th scope="col">Service</th>
      <th scope="col">Status</th>
      <th scope="col">Uptime</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>API Server</td>
      <td>Online</td>
      <td>99.9%</td>
    </tr>
    <tr>
      <td colspan="3">⚠ Scheduled maintenance: Sunday, 2-4 AM UTC</td>
    </tr>
  </tbody>
</table>
```

**`rowspan`** stretches a cell vertically — useful for grouping rows under a shared label:

```html
<table>
  <caption>Development Team by Department</caption>
  <thead>
    <tr>
      <th scope="col">Department</th>
      <th scope="col">Name</th>
      <th scope="col">Role</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row" rowspan="2">Frontend</th>
      <td>Ayesha</td>
      <td>UI Developer</td>
    </tr>
    <tr>
      <td>Rafi</td>
      <td>React Developer</td>
    </tr>
    <tr>
      <th scope="row" rowspan="2">Backend</th>
      <td>Junayed</td>
      <td>API Developer</td>
    </tr>
    <tr>
      <td>Farhan</td>
      <td>Database Engineer</td>
    </tr>
  </tbody>
</table>
```

Notice that when a cell uses `rowspan="2"`, the **next row has one fewer `<td>`** — the spanned cell already fills that slot. This is the single most common source of broken tables: the cell count in each row must account for whatever's being spanned from above.

### Putting It All Together

A genuinely complex table combines a multi-row header with both `colspan` and `rowspan`:

```html
<table>
  <caption>Product Sales by Quarter (Units Sold)</caption>
  <thead>
    <tr>
      <th scope="col" rowspan="2">Product</th>
      <th scope="colgroup" colspan="2">First Half</th>
      <th scope="colgroup" colspan="2">Second Half</th>
    </tr>
    <tr>
      <th scope="col">Q1</th>
      <th scope="col">Q2</th>
      <th scope="col">Q3</th>
      <th scope="col">Q4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Laptop Sleeves</th>
      <td>120</td>
      <td>150</td>
      <td>200</td>
      <td>180</td>
    </tr>
    <tr>
      <th scope="row">Mechanical Keyboards</th>
      <td>80</td>
      <td>95</td>
      <td>110</td>
      <td>130</td>
    </tr>
  </tbody>
</table>
```

The "Product" header uses `rowspan="2"` to stay vertically centered across both header rows, while "First Half" and "Second Half" use `colspan="2"` to group Q1/Q2 and Q3/Q4 underneath them. This is exactly the pattern you'll see in real analytics dashboards.

---

## `<ul>` vs `<ol>` vs `<table>` — Choosing the Right Tag

| Scenario                      | Use       | Why                                      |
| ----------------------------- | --------- | ---------------------------------------- |
| Steps in a tutorial           | `<ol>`    | Sequence changes the meaning             |
| List of favorite tools        | `<ul>`    | No inherent order                        |
| Comparing three pricing plans | `<table>` | Data has two dimensions (plan × feature) |
| A simple checklist            | `<ul>`    | Presence matters, not position           |
| Monthly sales by region       | `<table>` | Rows and columns are both meaningful     |
| Ranked leaderboard            | `<ol>`    | Position **is** the data                 |

---

## Common Pitfalls Recap

- **Using `<table>` for page layout.** That's a CSS Grid/Flexbox job now.
- **Skipping `<th>`.** If every cell is a `<td>`, you've lost the header semantics that make a table navigable by screen readers.
- **Mismatched `colspan`/`rowspan` math.** If a row's cell count doesn't account for spans from previous rows, the table visually breaks even though no error is thrown.
- **Nesting lists as siblings instead of children.** A nested `<ul>` belongs *inside* the `<li>` it's a sub-list of.
- **Picking `<ol>`/`<ul>` for looks, not meaning.** Semantics first, styling second.

---

## Try It Yourself

Before moving to Step 6, build a small "My Tech Stack" section using everything above:

1. An **unordered list** of the programming languages you know
2. An **ordered list** of the steps you personally follow when starting a new project
3. A **table** comparing three code editors (Editor, Free/Paid, Best For) — add a `<caption>` and proper `scope` attributes for extra credit

<details>
<summary>Stuck? Click for a hint</summary>

Start with the table's `<thead>` first — get the three column headers right with `scope="col"` before you touch a single row of data. It's much easier to fill in a correct skeleton than to fix a broken one.

</details>

---

## Key Takeaways

- `<ul>` is for unordered collections; `<ol>` is for anything where sequence matters
- Nested lists live *inside* the parent `<li>`, not next to it
- `<ol>` supports `start`, `type`, and `reversed` for numbering control
- Tables are for tabular *data* — never for layout
- `<thead>`, `<tbody>`, and `<tfoot>` organize complex tables into logical groups
- `colspan` merges columns, `rowspan` merges rows — and the cell count in every row must account for both
- `<caption>` and `scope` aren't optional extras — they're what makes a table usable with a screen reader

## Quick Reference

| Tag / Attribute                   | Purpose                                               |
| --------------------------------- | ----------------------------------------------------- |
| `<ul>`                            | Unordered (bullet) list container                     |
| `<ol>`                            | Ordered (numbered) list container                     |
| `<li>`                            | A single list item                                    |
| `start`                           | Starting number for `<ol>`                            |
| `type`                            | Numbering style: `1`, `A`, `a`, `I`, `i`              |
| `reversed`                        | Counts the list down instead of up                    |
| `<table>`                         | Table container                                       |
| `<caption>`                       | Accessible title for the table                        |
| `<thead>` / `<tbody>` / `<tfoot>` | Groups header, body, and footer rows                  |
| `<tr>`                            | Table row                                             |
| `<th>`                            | Header cell                                           |
| `<td>`                            | Data cell                                             |
| `colspan`                         | Merges cells across columns                           |
| `rowspan`                         | Merges cells across rows                              |
| `scope`                           | Links a header to its column or row for accessibility |

---

---

# Best Practices

✅ Use **`<ul>`** when the order of items does not matter.

Examples:

- Shopping lists
- Features
- Programming languages
- Favorite books

---

✅ Use **`<ol>`** when the order is important.

Examples:

- Recipes
- Tutorials
- Installation steps
- Rankings

---

✅ Always wrap every list item inside an `<li>` element.

Correct:

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

---

✅ Use tables only for displaying data.

Examples:

- Student records
- Product prices
- Monthly reports
- Timetables

Do **not** use tables to build your website layout.

---

✅ Use table headers (`<th>`) whenever possible.

Headers make tables easier to understand for both users and screen readers.

---

✅ Add a `<caption>` for larger or more complex tables.

A caption tells users what the table is about before they start reading it.

---

# Common Beginner Mistakes

### ❌ Using a table for page layout

Wrong:

Using tables to position headers, sidebars, and footers.

Correct:

Use CSS (Flexbox or Grid) for layouts and use tables only for tabular data.

---

### ❌ Forgetting the `<li>` tag

Wrong:

```html
<ul>
    HTML
    CSS
    JavaScript
</ul>
```

Correct:

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

---

### ❌ Choosing the wrong list type

Wrong:

Using `<ol>` when the order doesn't matter.

Correct:

Use:

- `<ul>` for unordered items.
- `<ol>` for ordered steps.

---

### ❌ Forgetting table headers

Wrong:

```html
<table>

<tr>
<td>Name</td>
<td>Age</td>
</tr>

</table>
```

Better:

```html
<table>

<tr>
<th>Name</th>
<th>Age</th>
</tr>

</table>
```

---

### ❌ Incorrect `rowspan` or `colspan`

When merging cells, remember that the merged cell already occupies space.

Otherwise, your table structure becomes broken.

---

# Quick Summary

| HTML Element | Purpose                            |
| ------------ | ---------------------------------- |
| `<ul>`       | Creates an unordered (bullet) list |
| `<ol>`       | Creates an ordered (numbered) list |
| `<li>`       | Represents a list item             |
| `<table>`    | Creates a table                    |
| `<tr>`       | Creates a table row                |
| `<th>`       | Creates a table header             |
| `<td>`       | Creates a table data cell          |
| `<thead>`    | Groups table header rows           |
| `<tbody>`    | Groups the main table content      |
| `<tfoot>`    | Groups footer rows                 |
| `<caption>`  | Adds a title to a table            |
| `colspan`    | Merges columns                     |
| `rowspan`    | Merges rows                        |
| `scope`      | Improves table accessibility       |

---

# Practice Challenge

Create a webpage that contains:

### A Programming Languages List

Create an unordered list with:

- HTML
- CSS
- JavaScript
- C

---

### A Learning Roadmap

Create an ordered list showing these steps:

1. Learn HTML
2. Learn CSS
3. Learn JavaScript
4. Build Projects
5. Learn a Backend Language

---

### A Student Marks Table

Create a table with:

| Name  | HTML | CSS | JavaScript |
| ----- | ---- | --- | ---------- |
| Alex  | 90   | 85  | 88         |
| Sarah | 95   | 91  | 94         |
| John  | 80   | 78  | 82         |

For an extra challenge:

- Add a `<caption>`.
- Use `<thead>` and `<tbody>`.
- Use `<th>` for the headers.
- Try creating a merged cell using `colspan` or `rowspan`.

---

# What's Next?

In the next chapter, you'll learn about **HTML Forms and User Input**, including:

- Creating forms with `<form>`
- Text fields and password inputs
- Radio buttons
- Checkboxes
- Dropdown menus
- Textareas
- Submit and Reset buttons
- Form validation using HTML attributes

By the end of the next chapter, you'll be able to build contact forms, login pages, registration forms, and other interactive forms that collect user input.

[← Back: Step 4](./media.md) · [Next: Step 6 →](./forms.md)