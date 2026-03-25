# Day 7 — Text Formatting, Paragraphs & Alignment

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 2 — HTML Fundamentals
🧪 **Lab Experiment:** 1 (Part 2)

---

## Learning Objectives

By the end of this session, students will be able to:
- Apply text formatting tags (bold, italic, underline, etc.)
- Use text alignment attributes
- Understand the difference between physical and logical formatting
- Insert special characters and entities in HTML

---

## 1. Text Formatting Tags

### Physical Formatting (Visual)

These tags define **how text looks**:

```html
<b>Bold text</b>
<i>Italic text</i>
<u>Underlined text</u>
<s>Strikethrough text</s>
<small>Smaller text</small>
<big>Bigger text</big>  <!-- Deprecated in HTML5 -->
<sub>Subscript</sub>    <!-- H<sub>2</sub>O renders as H₂O -->
<sup>Superscript</sup>  <!-- x<sup>2</sup> renders as x² -->
```

### Logical/Semantic Formatting (Meaningful)

These tags define **what text means** (preferred in HTML5):

```html
<strong>Important text</strong>     <!-- Looks bold, but MEANS "important" -->
<em>Emphasized text</em>            <!-- Looks italic, but MEANS "emphasis" -->
<mark>Highlighted text</mark>       <!-- Yellow background highlight -->
<del>Deleted text</del>             <!-- Strikethrough — content removed -->
<ins>Inserted text</ins>            <!-- Underlined — content added -->
<code>Code snippet</code>           <!-- Monospace font for code -->
<pre>Preformatted    text</pre>     <!-- Preserves spaces and line breaks -->
```

> **Why Semantic Tags Matter:** Screen readers for visually impaired users can understand `<strong>` means "say this with emphasis" but `<b>` just means "make it bold" — no meaning attached.

### Physical vs Semantic — Comparison

| Physical | Semantic | Looks Like | Meaning |
|----------|----------|------------|---------|
| `<b>` | `<strong>` | **Bold** | Important |
| `<i>` | `<em>` | *Italic* | Emphasized |
| `<s>` | `<del>` | ~~Strikethrough~~ | Deleted/removed |
| `<u>` | `<ins>` | <u>Underline</u> | Inserted/added |

---

## 2. More Text Tags

### Quotations

```html
<!-- Block quote (indented paragraph) -->
<blockquote>
    "Education is the most powerful weapon which you can use 
    to change the world." — Nelson Mandela
</blockquote>

<!-- Inline quotation (adds quotation marks) -->
<p>As Steve Jobs said, <q>Stay hungry, stay foolish.</q></p>

<!-- Citation -->
<p>Reference: <cite>Web Technology by N.P. Gopalan</cite></p>
```

### Abbreviations & Definitions

```html
<!-- Abbreviation (shows full form on hover) -->
<p><abbr title="HyperText Markup Language">HTML</abbr> is fun!</p>

<!-- Address block -->
<address>
    Mandsaur University<br>
    Mandsaur, Madhya Pradesh<br>
    India
</address>
```

### Preformatted Text

```html
<pre>
    This text preserves
    all    spaces    and
    line breaks exactly
    as written.
</pre>
```

> Useful for displaying code, poetry, or ASCII art.

---

## 3. Text Alignment

### Using the `align` Attribute (Old Way)

```html
<p align="left">Left aligned (default)</p>
<p align="center">Center aligned</p>
<p align="right">Right aligned</p>
<p align="justify">Justified text stretches to fill both margins evenly.</p>
```

> ⚠️ **Note:** The `align` attribute is deprecated in HTML5. Use CSS instead (which we'll learn in Unit 4). For now, it works and helps understand the concept.

### The `<center>` Tag (Deprecated)

```html
<center>
    <h1>This heading is centered</h1>
    <p>This paragraph is also centered</p>
</center>
```

> ⚠️ Also deprecated in HTML5 — use CSS `text-align: center` instead.

---

## 4. HTML Entities (Special Characters)

Some characters have special meaning in HTML (like `<` and `>`). To display them, use **entities**:

| Character | Entity Name | Entity Number | Description |
|-----------|-------------|---------------|-------------|
| `<` | `&lt;` | `&#60;` | Less than |
| `>` | `&gt;` | `&#62;` | Greater than |
| `&` | `&amp;` | `&#38;` | Ampersand |
| `"` | `&quot;` | `&#34;` | Double quote |
| `'` | `&apos;` | `&#39;` | Single quote |
| ` ` | `&nbsp;` | `&#160;` | Non-breaking space |
| `©` | `&copy;` | `&#169;` | Copyright |
| `®` | `&reg;` | `&#174;` | Registered |
| `™` | `&trade;` | `&#8482;` | Trademark |
| `₹` | `&#8377;` | `&#8377;` | Indian Rupee |
| `→` | `&rarr;` | `&#8594;` | Right arrow |

### Example

```html
<p>Price: &#8377;500 &amp; above</p>
<p>The &lt;html&gt; tag is the root element.</p>
<p>&copy; 2026 Mandsaur University. All rights reserved.</p>
```

---

## Practical Session

### 🧪 Lab Experiment 1 (Part 2): Enhanced Department Page

**Objective:** Enhance yesterday's department page with text formatting, alignment, and special characters.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BCA Department - Mandsaur University</title>
</head>
<body>

    <!-- Header Section -->
    <h1 align="center">Department of <em>Computer Applications</em> (BCA)</h1>
    <h2 align="center"><strong>Mandsaur University</strong>, Mandsaur</h2>
    
    <hr>

    <!-- About Section with Formatting -->
    <h3>About the Department</h3>
    <p>
        The Department of Computer Applications at <strong>Mandsaur University</strong> 
        offers a comprehensive <em>three-year</em> 
        <abbr title="Bachelor of Computer Applications">BCA</abbr> program. 
        The department is committed to producing <mark>skilled IT professionals</mark> 
        who can meet the growing demands of the technology industry.
    </p>

    <!-- Quote -->
    <blockquote>
        <em>"The only way to do great work is to love what you do."</em> 
        &mdash; Steve Jobs
    </blockquote>

    <!-- Course Details with Subscript/Superscript -->
    <h3>Course Highlights</h3>
    <p>
        Students learn technologies like <code>HTML</code>, <code>CSS</code>, 
        and <code>JavaScript</code>. The program covers 
        <strong>6 semesters</strong> with a focus on practical skills.
    </p>
    <p>
        Mathematical concepts like x<sup>2</sup> + y<sup>2</sup> = r<sup>2</sup> 
        and chemical formulas like H<sub>2</sub>O and CO<sub>2</sub> are 
        also used in various subjects.
    </p>

    <!-- Preformatted Text for Contact -->
    <h3>Contact</h3>
    <pre>
    Department of Computer Applications
    Mandsaur University
    Mandsaur, Madhya Pradesh 458001
    India
    </pre>

    <!-- Footer with Entities -->
    <hr>
    <p align="center">
        <small>&copy; 2026 Mandsaur University &bull; All Rights Reserved</small>
    </p>

</body>
</html>
```

### Practice Exercises

1. **Format a recipe page:** Create `recipe.html` with a recipe of your favorite dish. Use `<strong>` for ingredients, `<em>` for instructions, and `<mark>` for important tips.

2. **Create a resume page:** Build `resume.html` using:
   - `<h1>` for your name
   - `<h2>` for sections (Education, Skills, Hobbies)
   - `<strong>` and `<em>` for emphasis
   - `<pre>` for your address
   - `&bull;` entities for bullet points

---

## Summary

| Tag | Purpose | Example Output |
|-----|---------|-------|
| `<strong>` / `<b>` | Bold/Important | **Bold** |
| `<em>` / `<i>` | Italic/Emphasis | *Italic* |
| `<u>` / `<ins>` | Underline/Inserted | Underlined |
| `<del>` / `<s>` | Strikethrough/Deleted | ~~Deleted~~ |
| `<mark>` | Highlight | Highlighted |
| `<sub>` | Subscript | H₂O |
| `<sup>` | Superscript | x² |
| `<code>` | Inline code | `code` |
| `<pre>` | Preformatted text | Preserves spaces |
| `<blockquote>` | Block quotation | Indented quote |
| `&entity;` | Special characters | ©, ₹, → |

---

*Day 7 of 55 | Unit 2 — HTML Fundamentals | Web Technology (25BCA060)*
