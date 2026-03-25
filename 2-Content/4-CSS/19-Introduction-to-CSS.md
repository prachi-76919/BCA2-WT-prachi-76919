# Day 19 — Introduction to CSS

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 4 — CSS (Cascading Style Sheets)
🧪 **Lab Experiment:** 10

---

## Learning Objectives

By the end of this session, students will be able to:
- Explain what CSS is and why it's needed
- Write CSS using all three methods: inline, internal, and external
- Understand CSS syntax (selectors, properties, values)
- Apply basic styling to HTML elements

---

## 1. What is CSS?

> **Analogy:** If HTML is the **skeleton** of a building (structure), CSS is the **paint, wallpaper, flooring, and furnishing** (appearance). The same skeleton can look completely different with different CSS — modern, traditional, minimalist, or colorful.

**CSS = Cascading Style Sheets**
- **Cascading**: Styles can come from multiple sources and are applied in a specific order of priority
- **Style Sheets**: Files/rules that define how HTML elements look

### Why CSS?

| Without CSS | With CSS |
|-------------|----------|
| Plain black text on white | Colors, fonts, spacing |
| No layout control | Multi-column layouts |
| Content and style mixed | Separation of concerns |
| Change style = change every page | Change one CSS file = change entire website |

---

## 2. CSS Syntax

```css
selector {
    property: value;
    property: value;
}
```

**Example:**
```css
h1 {
    color: blue;
    font-size: 24px;
    text-align: center;
}
```

| Part | What It Means |
|------|---------------|
| `h1` | Selector — which elements to style |
| `color` | Property — what aspect to change |
| `blue` | Value — what to change it to |
| `{ }` | Declaration block |
| `;` | End of each declaration |

---

## 3. Three Ways to Add CSS

### 1. Inline CSS (on the element itself)

```html
<h1 style="color: red; font-size: 30px;">Hello World</h1>
<p style="background-color: yellow; padding: 10px;">Styled paragraph</p>
```

**Pros:** Quick for testing  
**Cons:** Repetitive, hard to maintain, mixes content and style

### 2. Internal CSS (in the `<head>` with `<style>`)

```html
<head>
    <style>
        h1 {
            color: navy;
            text-align: center;
        }
        p {
            font-size: 16px;
            line-height: 1.6;
        }
    </style>
</head>
```

**Pros:** Styles for one page in one place  
**Cons:** Must repeat on every page

### 3. External CSS (separate .css file) ✅ **Best Practice**

**style.css:**
```css
h1 {
    color: navy;
    text-align: center;
}
p {
    font-size: 16px;
    line-height: 1.6;
}
```

**index.html:**
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

**Pros:** One file styles the entire website; clean separation  
**Cons:** Extra HTTP request (minimal impact)

---

## 4. CSS Selectors

| Selector | Example | Selects |
|----------|---------|---------|
| Element | `p { }` | All `<p>` elements |
| Class | `.highlight { }` | Elements with `class="highlight"` |
| ID | `#header { }` | Element with `id="header"` |
| Universal | `* { }` | All elements |
| Group | `h1, h2, h3 { }` | Multiple elements |
| Descendant | `div p { }` | `<p>` inside `<div>` |

### Class vs ID

```html
<!-- Class: reusable (can apply to many elements) -->
<p class="highlight">This is highlighted</p>
<p class="highlight">This too</p>

<!-- ID: unique (one per page) -->
<div id="header">Only one header</div>
```

```css
.highlight { background-color: yellow; }  /* Class: dot prefix */
#header { background-color: navy; }        /* ID: hash prefix */
```

---

## 5. Common CSS Properties

### Text Properties

| Property | Values | Example |
|----------|--------|---------|
| `color` | Color name, hex, rgb | `color: #1565C0;` |
| `font-size` | px, em, rem, % | `font-size: 18px;` |
| `font-family` | Font names | `font-family: Arial, sans-serif;` |
| `font-weight` | normal, bold, 100-900 | `font-weight: bold;` |
| `font-style` | normal, italic | `font-style: italic;` |
| `text-align` | left, center, right, justify | `text-align: center;` |
| `text-decoration` | none, underline, line-through | `text-decoration: none;` |
| `text-transform` | uppercase, lowercase, capitalize | `text-transform: uppercase;` |
| `line-height` | Number, px | `line-height: 1.6;` |
| `letter-spacing` | px | `letter-spacing: 2px;` |

---

## Practical Session

### 🧪 Lab Experiment 10: CSS Styling

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Styling Demo</title>
    <style>
        /* Universal reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f4f4f4;
        }

        /* Header styling */
        header {
            background-color: #1565C0;
            color: white;
            text-align: center;
            padding: 30px 20px;
        }
        header h1 {
            font-size: 32px;
            letter-spacing: 2px;
            text-transform: uppercase;
        }
        header p {
            font-size: 14px;
            margin-top: 5px;
            opacity: 0.8;
        }

        /* Navigation */
        nav {
            background-color: #0D47A1;
            padding: 12px;
            text-align: center;
        }
        nav a {
            color: white;
            text-decoration: none;
            margin: 0 15px;
            font-size: 16px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Main content */
        main {
            max-width: 800px;
            margin: 30px auto;
            padding: 0 20px;
        }

        /* Article styling */
        article {
            background: white;
            padding: 25px;
            margin-bottom: 20px;
            border-left: 4px solid #1565C0;
        }
        article h2 {
            color: #1565C0;
            margin-bottom: 10px;
        }
        article p {
            font-size: 16px;
            color: #555;
        }

        /* Highlight class */
        .highlight {
            background-color: #FFF9C4;
            padding: 2px 8px;
            font-weight: bold;
        }

        /* Important class */
        .important {
            color: #C62828;
            font-weight: bold;
        }

        /* Footer */
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 15px;
            font-size: 14px;
        }
    </style>
</head>
<body>

    <header>
        <h1>Mandsaur University</h1>
        <p>Department of Computer Applications</p>
    </header>

    <nav>
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Courses</a>
        <a href="#">Contact</a>
    </nav>

    <main>
        <article>
            <h2>Welcome to BCA Program</h2>
            <p>The <span class="highlight">Bachelor of Computer Applications</span> 
               program prepares students for the IT industry with a blend of 
               theoretical knowledge and practical skills.</p>
        </article>

        <article>
            <h2>Web Technology Course</h2>
            <p>In this course, you will learn HTML, CSS, JavaScript, and Bootstrap.
               <span class="important">Attendance above 75% is mandatory.</span></p>
        </article>

        <article>
            <h2>CSS Styling</h2>
            <p>Today we learned three ways to add CSS:
               <span class="highlight">inline</span>, 
               <span class="highlight">internal</span>, and 
               <span class="highlight">external</span>.
               External CSS is the recommended approach.</p>
        </article>
    </main>

    <footer>
        <p>&copy; 2026 Mandsaur University. All Rights Reserved.</p>
    </footer>

</body>
</html>
```

---

## Summary

| Concept | Details |
|---------|---------|
| CSS | Cascading Style Sheets — controls appearance |
| Inline CSS | `style="..."` on element |
| Internal CSS | `<style>` in `<head>` |
| External CSS | Separate `.css` file linked with `<link>` |
| Selector | Targets elements: element, `.class`, `#id` |
| Declaration | `property: value;` |
| Best practice | Always use external CSS |

---

*Day 19 of 55 | Unit 4 — CSS | Web Technology (25BCA060)*
