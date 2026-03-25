# Day 6 — Introduction to HTML: Structure, Head & Body

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 2 — HTML Fundamentals
🧪 **Lab Experiment:** 1 (Part 1)

---

## Learning Objectives

By the end of this session, students will be able to:
- Define HTML and explain its role in web development
- Write the basic structure of an HTML document
- Use the `<head>` and `<body>` sections correctly
- Create their first HTML webpage
- Use paragraph and heading tags

---

## 1. What is HTML?

### Definition

**HTML** (HyperText Markup Language) is the standard language for creating web pages. It describes the **structure** of a web page using a series of **elements** (tags).

> **Analogy:** If a webpage were a house, **HTML** would be the **skeleton/frame** — the walls, floors, and rooms. **CSS** would be the **paint and decoration**, and **JavaScript** would be the **electricity and plumbing** (making things work).

### Key Facts

| Fact | Detail |
|------|--------|
| **Created by** | Tim Berners-Lee (1991) |
| **Current version** | HTML5 (2014, Living Standard) |
| **File extension** | `.html` or `.htm` |
| **Interpreted by** | Web browsers (Chrome, Firefox, etc.) |
| **NOT a programming language** | It's a *markup* language — describes structure, doesn't have logic |

---

## 2. HTML Elements & Tags

### What is a Tag?

Tags are **keywords** enclosed in angle brackets that tell the browser how to display content.

```html
<tagname>Content goes here</tagname>
 └──┬──┘                   └───┬───┘
 Opening tag              Closing tag
```

### Types of Tags

| Type | Description | Example |
|------|-------------|---------|
| **Paired/Container** | Has opening and closing tags | `<p>Hello</p>` |
| **Self-closing/Empty** | No closing tag needed | `<br>`, `<hr>`, `<img>` |

### Anatomy of an HTML Element

```html
<p class="intro">Welcome to Web Technology!</p>
└┬┘ └────┬─────┘ └──────────┬──────────────┘└┬┘
Tag   Attribute           Content          Closing tag
```

---

## 3. Basic Structure of an HTML Document

Every HTML document follows this template:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Web Page</title>
</head>
<body>
    <!-- Your visible content goes here -->
    <h1>Hello, World!</h1>
    <p>This is my first web page.</p>
</body>
</html>
```

### Line-by-Line Explanation

| Line | Tag | Purpose |
|------|-----|---------|
| 1 | `<!DOCTYPE html>` | Tells the browser this is an HTML5 document |
| 2 | `<html lang="en">` | Root element; `lang="en"` sets language to English |
| 3 | `<head>` | Contains metadata (info ABOUT the page, not visible) |
| 4 | `<meta charset="UTF-8">` | Character encoding (supports all languages) |
| 5 | `<meta name="viewport"...>` | Makes page mobile-responsive |
| 6 | `<title>` | Text shown in browser tab |
| 7 | `</head>` | End of metadata section |
| 8 | `<body>` | Contains all VISIBLE content |
| 11 | `</body>` | End of visible content |
| 12 | `</html>` | End of document |

### Head vs Body

```
┌──────────────────────────────────────┐
│ <head> — INVISIBLE (metadata)        │
│   • Page title (browser tab)         │
│   • Character encoding               │
│   • CSS links                        │
│   • Meta descriptions (for Google)   │
│   • Favicon                          │
├──────────────────────────────────────┤
│ <body> — VISIBLE (content)           │
│   • Text, images, videos             │
│   • Links, buttons, forms            │
│   • Tables, lists                    │
│   • Everything the user sees         │
└──────────────────────────────────────┘
```

---

## 4. Heading Tags (`<h1>` to `<h6>`)

HTML provides six levels of headings, from most important (`<h1>`) to least important (`<h6>`).

```html
<h1>Main Title (Biggest)</h1>
<h2>Section Title</h2>
<h3>Sub-section Title</h3>
<h4>Sub-sub-section</h4>
<h5>Minor Heading</h5>
<h6>Smallest Heading</h6>
```

> **Real-World Analogy:** Think of headings like a **newspaper**:
> - `<h1>` = Headline on the front page
> - `<h2>` = Section headers (Sports, Politics)
> - `<h3>` = Article titles within sections
> - `<h4>` to `<h6>` = Sub-points within articles

### Best Practices

- Use only **one `<h1>`** per page (main topic)
- Don't skip levels (don't go from `<h2>` to `<h4>`)
- Use headings for **structure**, not for making text big (use CSS for that)

---

## 5. Paragraph Tag (`<p>`)

```html
<p>This is a paragraph. HTML ignores extra spaces and line breaks
   within a paragraph. Everything flows      as one block of text.</p>

<p>This is another paragraph. Each &lt;p&gt; tag creates a new block
   with space above and below.</p>
```

### Line Break (`<br>`) and Horizontal Rule (`<hr>`)

```html
<p>Line one<br>Line two<br>Line three</p>

<hr> <!-- Draws a horizontal line across the page -->
```

---

## 6. Comments in HTML

Comments are notes for developers — the browser ignores them.

```html
<!-- This is a comment. Users won't see this. -->

<!-- 
    Multi-line comments
    are also possible
-->
```

---

## Practical Session

### 🧪 Lab Experiment 1 (Part 1): Create a Webpage Describing Your Department

**Objective:** Create a webpage using HTML that describes the BCA Department at Mandsaur University using paragraph and heading tags.

#### Step 1: Create the File

1. Open **VS Code**
2. Create a new file: `department.html`
3. Type `!` and press `Tab` to generate the HTML boilerplate (Emmet shortcut)

#### Step 2: Write the Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BCA Department - Mandsaur University</title>
</head>
<body>

    <h1>Department of Computer Applications (BCA)</h1>
    <h2>Mandsaur University, Mandsaur</h2>
    
    <hr>

    <h3>About the Department</h3>
    <p>
        The Department of Computer Applications at Mandsaur University offers 
        a comprehensive three-year Bachelor of Computer Applications (BCA) program. 
        The department is committed to producing skilled IT professionals who can 
        meet the growing demands of the technology industry.
    </p>

    <h3>Vision</h3>
    <p>
        To be a center of excellence in computer education, producing innovative 
        and industry-ready graduates who contribute to the advancement of 
        information technology.
    </p>

    <h3>Mission</h3>
    <p>
        To provide quality education in computer applications through a blend 
        of theoretical knowledge and practical skills. To foster creativity, 
        critical thinking, and ethical values among students.
    </p>

    <h3>Programs Offered</h3>
    <p>
        The department offers BCA (Bachelor of Computer Applications), a 
        three-year undergraduate program spread across six semesters. The 
        curriculum covers programming languages, web development, database 
        management, networking, and software engineering.
    </p>

    <h3>Infrastructure</h3>
    <p>
        The department has well-equipped computer labs with modern hardware 
        and software. High-speed internet connectivity is available throughout 
        the department. Smart classrooms enhance the learning experience 
        with multimedia teaching aids.
    </p>

    <h3>Contact Information</h3>
    <p>
        Department of Computer Applications<br>
        Mandsaur University<br>
        Mandsaur, Madhya Pradesh, India<br>
        Phone: +91-XXXX-XXXXXX<br>
        Email: bca@mandsauruniversity.edu.in
    </p>

</body>
</html>
```

#### Step 3: View the Page

1. Right-click the file in VS Code → **"Open with Live Server"** (if Live Server extension is installed)
2. OR simply double-click the `.html` file to open in Chrome
3. Press `F12` in Chrome to open **Developer Tools** and inspect the elements

#### Step 4: Experiment

Try these modifications:
- Change the `<title>` and see it update in the browser tab
- Add another `<h3>` section about "Faculty Members"
- Try removing `<hr>` and see the difference
- Add comments (`<!-- -->`) to label different sections

---

## Practice Exercise

Create a new file `about-me.html` with:
1. Your name as `<h1>`
2. Your college and course as `<h2>`
3. A paragraph about yourself
4. A paragraph about your hobbies
5. A paragraph about your career goals
6. Use `<br>` for your contact details
7. Use `<hr>` to separate sections
8. Add at least 3 comments in the code

---

## Summary

| Concept | Key Takeaway |
|---------|-------------|
| HTML | Markup language for structuring web pages |
| `<!DOCTYPE html>` | Declares the document as HTML5 |
| `<head>` | Metadata — title, charset, links (invisible) |
| `<body>` | All visible page content |
| `<h1>` to `<h6>` | Headings from largest to smallest |
| `<p>` | Paragraphs |
| `<br>` | Line break |
| `<hr>` | Horizontal rule |
| `<!-- -->` | Comments (ignored by browser) |

---

*Day 6 of 55 | Unit 2 — HTML Fundamentals | Web Technology (25BCA060)*
