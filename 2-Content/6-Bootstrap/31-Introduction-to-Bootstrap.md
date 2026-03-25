# Day 31 — Introduction to Bootstrap

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 6 — Bootstrap
🧪 **Lab Experiment:** 14

---

## Learning Objectives

By the end of this session, students will be able to:
- Explain what Bootstrap is and why it's used
- Set up Bootstrap via CDN
- Use Bootstrap's container system and utility classes
- Apply basic Bootstrap typography and color classes

---

## 1. What is Bootstrap?

> **Analogy:** Writing CSS from scratch is like **building furniture yourself** — complete control but takes time. Bootstrap is like buying from **IKEA** — pre-built components that you assemble quickly. You get a professional result faster, and you can still customize it.

Bootstrap is a **free, open-source CSS framework** by Twitter. It provides:
- **Pre-built components** (buttons, cards, navigation, modals)
- **Responsive grid system** (12-column layout)
- **Utility classes** (spacing, colors, alignment without custom CSS)
- **Mobile-first** design

### Bootstrap 5 (Latest)

| Feature | Details |
|---------|---------|
| Version | 5.3.x |
| jQuery | Not required (pure JS) |
| Grid | 12-column, flexbox-based |
| Breakpoints | xs, sm, md, lg, xl, xxl |

---

## 2. Setting Up Bootstrap

### Via CDN (Content Delivery Network) — Quickest

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Bootstrap Page</title>
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>

    <h1>Hello Bootstrap!</h1>

    <!-- Bootstrap JS (at end of body) -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

---

## 3. Containers

```html
<!-- Fixed-width container (centered, max-width at each breakpoint) -->
<div class="container">Content here</div>

<!-- Full-width container -->
<div class="container-fluid">Spans entire width</div>

<!-- Responsive container (full-width until breakpoint) -->
<div class="container-md">Full width below md, fixed above</div>
```

---

## 4. Bootstrap Typography

```html
<h1 class="display-1">Display Heading 1</h1>
<h2 class="display-4">Display Heading 4</h2>

<p class="lead">This is a lead paragraph — larger and lighter text.</p>

<p class="text-muted">Muted gray text</p>
<p class="text-primary">Primary blue text</p>
<p class="text-success">Success green text</p>
<p class="text-danger">Danger red text</p>
<p class="text-warning">Warning yellow text</p>

<p class="fw-bold">Bold text</p>
<p class="fst-italic">Italic text</p>
<p class="text-center">Centered text</p>
<p class="text-uppercase">uppercase text</p>
```

---

## 5. Bootstrap Colors & Backgrounds

### Text Colors

| Class | Color |
|-------|-------|
| `text-primary` | Blue |
| `text-secondary` | Gray |
| `text-success` | Green |
| `text-danger` | Red |
| `text-warning` | Yellow |
| `text-info` | Light blue |
| `text-light` | White (use on dark bg) |
| `text-dark` | Black |

### Backgrounds

```html
<div class="bg-primary text-white p-3">Primary Background</div>
<div class="bg-success text-white p-3">Success Background</div>
<div class="bg-danger text-white p-3">Danger Background</div>
<div class="bg-warning p-3">Warning Background</div>
<div class="bg-dark text-white p-3">Dark Background</div>
```

---

## 6. Utility Classes

### Spacing (Margin & Padding)

Format: `{property}{sides}-{size}`

| Part | Options |
|------|---------|
| Property | `m` (margin), `p` (padding) |
| Sides | `t` (top), `b` (bottom), `s` (start/left), `e` (end/right), `x` (horizontal), `y` (vertical), blank (all) |
| Size | `0`, `1` (0.25rem), `2` (0.5rem), `3` (1rem), `4` (1.5rem), `5` (3rem), `auto` |

```html
<div class="mt-3">margin-top: 1rem</div>
<div class="px-4">padding-left and right: 1.5rem</div>
<div class="mb-5">margin-bottom: 3rem</div>
<div class="p-0">no padding</div>
<div class="mx-auto" style="width: 200px;">Centered block</div>
```

### Display & Flexbox

```html
<div class="d-flex justify-content-between">
    <span>Left</span>
    <span>Right</span>
</div>

<div class="d-none d-md-block">Hidden on small, visible on md+</div>
```

### Borders & Rounded

```html
<div class="border border-primary rounded p-3">Bordered box</div>
<img class="rounded-circle" src="..." alt="...">
```

---

## Practical Session

### 🧪 Lab Experiment 14: Bootstrap Basics Page

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Basics</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>

    <!-- Header -->
    <div class="bg-primary text-white text-center py-5">
        <div class="container">
            <h1 class="display-4 fw-bold">Welcome to Bootstrap</h1>
            <p class="lead">BCA Semester II — Web Technology Lab</p>
            <a href="#content" class="btn btn-light btn-lg mt-3">Get Started</a>
        </div>
    </div>

    <!-- Content -->
    <div class="container my-5" id="content">
        
        <!-- Typography Showcase -->
        <h2 class="text-primary mb-4">Typography</h2>
        <div class="row">
            <div class="col-md-6">
                <h1>Heading 1</h1>
                <h2>Heading 2</h2>
                <h3>Heading 3</h3>
                <h4>Heading 4</h4>
                <h5>Heading 5</h5>
                <h6>Heading 6</h6>
            </div>
            <div class="col-md-6">
                <p class="display-1">Display 1</p>
                <p class="display-4">Display 4</p>
                <p class="lead">Lead paragraph text</p>
                <p class="text-muted">Muted text</p>
                <p><mark>Highlighted text</mark></p>
                <p><small>Small text</small></p>
            </div>
        </div>
        <hr>

        <!-- Color Showcase -->
        <h2 class="text-primary mb-4">Colors</h2>
        <div class="row g-3 mb-4">
            <div class="col-md-4"><div class="bg-primary text-white p-3 rounded">Primary</div></div>
            <div class="col-md-4"><div class="bg-secondary text-white p-3 rounded">Secondary</div></div>
            <div class="col-md-4"><div class="bg-success text-white p-3 rounded">Success</div></div>
            <div class="col-md-4"><div class="bg-danger text-white p-3 rounded">Danger</div></div>
            <div class="col-md-4"><div class="bg-warning p-3 rounded">Warning</div></div>
            <div class="col-md-4"><div class="bg-info p-3 rounded">Info</div></div>
        </div>
        <hr>

        <!-- Buttons Showcase -->
        <h2 class="text-primary mb-4">Buttons</h2>
        <button class="btn btn-primary">Primary</button>
        <button class="btn btn-secondary">Secondary</button>
        <button class="btn btn-success">Success</button>
        <button class="btn btn-danger">Danger</button>
        <button class="btn btn-warning">Warning</button>
        <button class="btn btn-info">Info</button>
        <button class="btn btn-dark">Dark</button>
        <button class="btn btn-outline-primary">Outline</button>
        <br><br>
        <button class="btn btn-primary btn-sm">Small</button>
        <button class="btn btn-primary">Normal</button>
        <button class="btn btn-primary btn-lg">Large</button>
        <hr>

        <!-- Alerts -->
        <h2 class="text-primary mb-4">Alerts</h2>
        <div class="alert alert-success">✅ This is a success alert!</div>
        <div class="alert alert-danger">❌ This is a danger alert!</div>
        <div class="alert alert-warning">⚠️ This is a warning alert!</div>
        <div class="alert alert-info">ℹ️ This is an info alert!</div>

        <!-- Badges -->
        <h2 class="text-primary mb-4">Badges</h2>
        <span class="badge bg-primary">Primary</span>
        <span class="badge bg-success">Success</span>
        <span class="badge bg-danger">Danger</span>
        <span class="badge rounded-pill bg-info">Pill Badge</span>
    </div>

    <!-- Footer -->
    <div class="bg-dark text-white text-center py-3">
        <p class="mb-0">&copy; 2026 Mandsaur University — BCA Semester II</p>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

---

## Summary

| Concept | Class/Syntax |
|---------|-------------|
| CDN Link | `<link href="...bootstrap.min.css">` |
| Container | `container`, `container-fluid` |
| Typography | `display-1`, `lead`, `fw-bold` |
| Colors | `text-primary`, `bg-success` |
| Spacing | `mt-3`, `px-4`, `mb-5` |
| Buttons | `btn btn-primary`, `btn-lg` |
| Alerts | `alert alert-success` |

---

*Day 31 of 55 | Unit 6 — Bootstrap | Web Technology (25BCA060)*
