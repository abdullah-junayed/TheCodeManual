# 6th Step: Forms and User Input

Websites are not just for displaying information—they also collect information from users.

Think about websites like:

- Login pages
- Registration forms
- Contact pages
- Search bars
- Online surveys
- Checkout pages

All of these are built using **HTML Forms**.

---

## What is a Form?

A form is an HTML element used to collect information from users.

The `<form>` element acts as a container for input fields.

### Basic Syntax

```html
<form>
    <!-- Form elements go here -->
</form>
```

---

## A Simple Form

```html
<form>
    <label>Name:</label>
    <input type="text">

    <br><br>

    <button>Submit</button>
</form>
```

Output:

```
Name: [____________]

[ Submit ]
```

---

# The `<input>` Element

The `<input>` element creates different kinds of input fields.

Syntax:

```html
<input type="...">
```

The `type` attribute decides what kind of input appears.

---

# Common Input Types

## 1. Text Input

Used for names, usernames, cities, etc.

```html
<input type="text">
```

Output:

```
[________________]
```

Example:

```html
<label>Full Name</label>
<input type="text">
```

---

## Placeholder Text

Placeholder gives users a hint.

```html
<input
    type="text"
    placeholder="Enter your name">
```

Output:

```
[ Enter your name ]
```

---

## Password Field

Hides typed characters.

```html
<input type="password">
```

Output:

```
[ ******** ]
```

Example:

```html
<label>Password</label>

<input type="password">
```

---

## Email Field

Designed specifically for email addresses.

```html
<input type="email">
```

Example:

```html
<label>Email</label>

<input
    type="email"
    placeholder="example@email.com">
```

Browsers can automatically validate email format.

---

## Number Field

Allows only numeric values.

```html
<input type="number">
```

Example:

```html
<input
    type="number"
    min="1"
    max="100">
```

---

## Date Picker

```html
<input type="date">
```

Users can choose a date from a calendar.

---

## Color Picker

```html
<input type="color">
```

Shows a color selection tool.

---

## File Upload

```html
<input type="file">
```

Allows users to upload files.

---

# Labels

Labels tell users what an input field is for.

Example:

```html
<label>Email</label>
<input type="email">
```

Better example:

```html
<label for="email">Email</label>

<input
    id="email"
    type="email">
```

The `for` attribute connects the label to the input.

---

# Required Fields

Prevent users from submitting an empty field.

```html
<input
    type="text"
    required>
```

---

# Default Value

```html
<input
    type="text"
    value="John">
```

The field already contains "John".

---

# Readonly Field

Users can see the value but cannot change it.

```html
<input
    type="text"
    value="Admin"
    readonly>
```

---

# Disabled Field

```html
<input
    type="text"
    disabled>
```

Disabled fields cannot be edited or submitted.

---

# Radio Buttons

Radio buttons let users choose **only one option**.

Example:

```html
<input
    type="radio"
    name="gender">

<label>Male</label>

<input
    type="radio"
    name="gender">

<label>Female</label>
```

Output:

```
( ) Male

( ) Female
```

Notice both radio buttons share the same `name`.

That makes them part of one group.

---

## Default Selected Radio

```html
<input
    type="radio"
    name="gender"
    checked>
```

`checked` selects it automatically.

---

# Checkboxes

Checkboxes allow multiple selections.

Example:

```html
<input type="checkbox">
<label>HTML</label>

<input type="checkbox">
<label>CSS</label>

<input type="checkbox">
<label>JavaScript</label>
```

Output:

```
☐ HTML

☐ CSS

☐ JavaScript
```

Users can select one, two, or all.

---

# Dropdown Menu

The `<select>` element creates a dropdown.

Example:

```html
<select>

    <option>Bangladesh</option>

    <option>India</option>

    <option>Japan</option>

</select>
```

Output:

```
▼ Bangladesh
```

---

## Selected Option

```html
<option selected>
Bangladesh
</option>
```

---

# Textarea

For large amounts of text.

Example:

```html
<textarea></textarea>
```

Output:

```
-----------------------
|
|
|
-----------------------
```

Example:

```html
<label>Your Message</label>

<textarea
rows="5"
cols="40">
</textarea>
```

---

# Submit Button

```html
<button>
Submit
</button>
```

Or

```html
<input
type="submit">
```

Both submit the form.

---

# Reset Button

Resets every field.

```html
<input
type="reset">
```

---

# Form Attributes

## action

Specifies where the data goes.

```html
<form action="/submit">
```

---

## method

Defines how data is sent.

```html
<form method="GET">
```

or

```html
<form method="POST">
```

Most login and registration forms use **POST**.

---

# Complete Example

```html
<form action="/register" method="POST">

    <label>Full Name</label>
    <br>

    <input
        type="text"
        placeholder="Enter your full name"
        required>

    <br><br>

    <label>Email</label>
    <br>

    <input
        type="email"
        placeholder="example@email.com"
        required>

    <br><br>

    <label>Password</label>
    <br>

    <input
        type="password"
        required>

    <br><br>

    <label>Gender</label>

    <br>

    <input
        type="radio"
        name="gender">

    Male

    <input
        type="radio"
        name="gender">

    Female

    <br><br>

    <label>Skills</label>

    <br>

    <input type="checkbox">
    HTML

    <br>

    <input type="checkbox">
    CSS

    <br>

    <input type="checkbox">
    JavaScript

    <br><br>

    <label>Country</label>

    <br>

    <select>

        <option>Bangladesh</option>

        <option>India</option>

        <option>Japan</option>

    </select>

    <br><br>

    <label>About You</label>

    <br>

    <textarea
        rows="5"
        cols="40">
    </textarea>

    <br><br>

    <button>
        Register
    </button>

</form>
```

---

# Best Practices

✅ Always use `<label>` for every input.

✅ Use meaningful placeholders.

✅ Add `required` where necessary.

✅ Group related radio buttons using the same `name`.

✅ Use checkboxes when multiple choices are allowed.

✅ Use dropdowns for long lists.

✅ Use `<textarea>` for long messages.

---

# Common Beginner Mistakes

❌ Forgetting the `name` attribute for radio buttons.

```html
<input type="radio">
<input type="radio">
```

Each becomes independent.

Correct:

```html
<input
type="radio"
name="gender">

<input
type="radio"
name="gender">
```

---

❌ Forgetting to close the `<form>` tag.

```html
<form>

<!-- inputs -->

</form>
```

---

❌ Using text input for passwords.

Wrong:

```html
<input type="text">
```

Correct:

```html
<input type="password">
```

---

❌ Using multiple radio groups with the same name accidentally.

Always give different groups different names.

---

# Quick Summary

| Element           | Purpose            |
| ----------------- | ------------------ |
| `<form>`          | Creates a form     |
| `<input>`         | Accepts user input |
| `<label>`         | Describes an input |
| `<textarea>`      | Multi-line text    |
| `<select>`        | Dropdown menu      |
| `<option>`        | Dropdown item      |
| `<button>`        | Button             |
| `type="text"`     | Text field         |
| `type="password"` | Password field     |
| `type="email"`    | Email field        |
| `type="radio"`    | Single choice      |
| `type="checkbox"` | Multiple choices   |
| `type="submit"`   | Submit form        |
| `type="reset"`    | Reset form         |

---

# Practice Challenge

Create a **Student Registration Form** that contains:

- Full Name
- Email
- Password
- Phone Number
- Date of Birth
- Gender (Radio Buttons)
- Skills (Checkboxes)
- Country (Dropdown)
- About Yourself (Textarea)
- Submit Button
- Reset Button

Try to build the form without copying the complete example above. If you get stuck, refer back to the relevant sections in this chapter.

---

# What's Next?

In the next chapter, you'll learn about **HTML Tables**, including:

- Creating tables with `<table>`
- Adding rows and columns
- Table headers (`<th>`)
- Merging cells using `colspan` and `rowspan`
- Building clean, readable data tables

[← Back: Step 5](./lists-tables.md) · [Next: Step 7 →](./semantic-html.md)