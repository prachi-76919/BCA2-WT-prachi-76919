# Day 16 — Multimedia: Audio, Video, Canvas & SVG

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 3 — HTML5
🧪 **Lab Experiment:** 9 (extended with HTML5 features)

---

## Learning Objectives

By the end of this session, students will be able to:
- Embed audio and video using HTML5 tags (review + advanced features)
- Draw graphics using the `<canvas>` element with JavaScript
- Create scalable vector graphics using `<svg>`
- Understand when to use Canvas vs SVG

---

## 1. HTML5 Audio & Video (Recap + Advanced)

### Advanced Video Features

```html
<video id="myVideo" width="640" height="360" controls preload="metadata"
       poster="https://via.placeholder.com/640x360?text=Click+Play">
    <source src="lecture.mp4" type="video/mp4">
    <source src="lecture.webm" type="video/webm">
    <track src="subtitles_en.vtt" kind="subtitles" srclang="en" label="English">
    Your browser does not support HTML5 video.
</video>
```

### The `<track>` Element (Subtitles)

```html
<track src="captions.vtt" kind="subtitles" srclang="en" label="English" default>
```

| Attribute | Purpose |
|-----------|---------|
| `kind` | `subtitles`, `captions`, `descriptions`, `chapters` |
| `srclang` | Language of the track |
| `label` | User-visible label |
| `default` | Use this track by default |

---

## 2. The `<canvas>` Element

> **Analogy:** `<canvas>` is a **blank whiteboard** in your classroom. By itself, it's empty. You need **JavaScript** (the marker) to draw shapes, text, and images on it.

### Basic Canvas Setup

```html
<canvas id="myCanvas" width="400" height="300" style="border: 1px solid #000;">
    Your browser does not support canvas.
</canvas>

<script>
    const canvas = document.getElementById('myCanvas');
    const ctx = canvas.getContext('2d');
    
    // Draw a rectangle
    ctx.fillStyle = '#1565C0';
    ctx.fillRect(50, 50, 150, 100);
    
    // Draw a circle
    ctx.beginPath();
    ctx.arc(300, 100, 50, 0, Math.PI * 2);
    ctx.fillStyle = '#E91E63';
    ctx.fill();
    
    // Draw text
    ctx.font = '20px Arial';
    ctx.fillStyle = '#333';
    ctx.fillText('Hello Canvas!', 100, 250);
    
    // Draw a line
    ctx.beginPath();
    ctx.moveTo(50, 200);
    ctx.lineTo(350, 200);
    ctx.strokeStyle = '#4CAF50';
    ctx.lineWidth = 3;
    ctx.stroke();
</script>
```

### Canvas Drawing Methods

| Method | Purpose |
|--------|---------|
| `fillRect(x, y, w, h)` | Filled rectangle |
| `strokeRect(x, y, w, h)` | Rectangle outline |
| `clearRect(x, y, w, h)` | Clear an area |
| `beginPath()` | Start a new path |
| `moveTo(x, y)` | Move pen without drawing |
| `lineTo(x, y)` | Draw line to point |
| `arc(x, y, r, start, end)` | Draw arc/circle |
| `fill()` | Fill the path |
| `stroke()` | Draw the outline |
| `fillText(text, x, y)` | Draw filled text |
| `drawImage(img, x, y)` | Draw an image |

### Indian Flag Example

```html
<canvas id="flag" width="300" height="200" style="border: 1px solid #ccc;"></canvas>
<script>
    const c = document.getElementById('flag');
    const ctx = c.getContext('2d');
    
    // Saffron stripe
    ctx.fillStyle = '#FF9933';
    ctx.fillRect(0, 0, 300, 67);
    
    // White stripe (default background)
    ctx.fillStyle = '#FFFFFF';
    ctx.fillRect(0, 67, 300, 67);
    
    // Green stripe
    ctx.fillStyle = '#138808';
    ctx.fillRect(0, 134, 300, 67);
    
    // Ashoka Chakra (simplified circle)
    ctx.beginPath();
    ctx.arc(150, 100, 25, 0, Math.PI * 2);
    ctx.strokeStyle = '#000080';
    ctx.lineWidth = 2;
    ctx.stroke();
</script>
```

---

## 3. SVG (Scalable Vector Graphics)

> **Analogy:** If Canvas is a **painting** (raster — fixed pixels), SVG is like **paper cutting art** (vector — mathematical shapes). SVG looks sharp at ANY size — zoom in 1000% and it's still crisp.

### Basic SVG

```html
<svg width="400" height="200" style="border: 1px solid #ccc;">
    <!-- Rectangle -->
    <rect x="10" y="10" width="150" height="80" 
          fill="#1565C0" stroke="#0D47A1" stroke-width="2" rx="10"/>
    
    <!-- Circle -->
    <circle cx="300" cy="60" r="50" fill="#E91E63" opacity="0.8"/>
    
    <!-- Line -->
    <line x1="10" y1="150" x2="390" y2="150" 
          stroke="#4CAF50" stroke-width="2"/>
    
    <!-- Text -->
    <text x="100" y="190" font-size="18" fill="#333">Hello SVG!</text>
    
    <!-- Ellipse -->
    <ellipse cx="200" cy="100" rx="60" ry="30" 
             fill="none" stroke="#FF9800" stroke-width="2"/>
</svg>
```

### SVG Shapes Reference

| Shape | Tag | Key Attributes |
|-------|-----|----------------|
| Rectangle | `<rect>` | x, y, width, height, rx (rounded) |
| Circle | `<circle>` | cx, cy, r |
| Ellipse | `<ellipse>` | cx, cy, rx, ry |
| Line | `<line>` | x1, y1, x2, y2 |
| Polygon | `<polygon>` | points |
| Polyline | `<polyline>` | points |
| Path | `<path>` | d (path data) |
| Text | `<text>` | x, y, font-size |

---

## 4. Canvas vs SVG

| Feature | Canvas | SVG |
|---------|--------|-----|
| **Type** | Raster (pixels) | Vector (math) |
| **Drawn with** | JavaScript | HTML/XML tags |
| **Scaling** | Loses quality when zoomed | Always crisp |
| **Performance** | Better for many objects (games) | Better for few complex shapes |
| **Interactivity** | Must handle manually | Each shape is a DOM element |
| **Best for** | Games, image editing, charts | Icons, logos, diagrams, maps |
| **File size** | Depends on resolution | Depends on complexity |

---

## Practical Session

### Interactive Canvas Drawing

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Canvas & SVG Gallery</title>
</head>
<body style="font-family: Arial; max-width: 800px; margin: 20px auto;">

    <h1>HTML5 Graphics Gallery</h1>

    <!-- Canvas Section -->
    <h2>Canvas Drawing</h2>
    <canvas id="demo" width="500" height="200" style="border:2px solid #333; display:block;"></canvas>
    <script>
        const c = document.getElementById('demo');
        const ctx = c.getContext('2d');
        
        // Gradient background
        const gradient = ctx.createLinearGradient(0, 0, 500, 0);
        gradient.addColorStop(0, '#667eea');
        gradient.addColorStop(1, '#764ba2');
        ctx.fillStyle = gradient;
        ctx.fillRect(0, 0, 500, 200);
        
        // White text
        ctx.font = 'bold 28px Arial';
        ctx.fillStyle = 'white';
        ctx.textAlign = 'center';
        ctx.fillText('Welcome to HTML5 Canvas!', 250, 80);
        
        ctx.font = '16px Arial';
        ctx.fillText('Mandsaur University - BCA Dept.', 250, 120);
        
        // Decorative circles
        ctx.beginPath();
        ctx.arc(50, 170, 20, 0, Math.PI * 2);
        ctx.fillStyle = 'rgba(255,255,255,0.3)';
        ctx.fill();
        
        ctx.beginPath();
        ctx.arc(450, 170, 20, 0, Math.PI * 2);
        ctx.fill();
    </script>

    <br>

    <!-- SVG Section -->
    <h2>SVG Drawing</h2>
    <svg width="500" height="200" style="border:2px solid #333; display:block;">
        <defs>
            <linearGradient id="grad1" x1="0%" y1="0%" x2="100%" y2="0%">
                <stop offset="0%" style="stop-color:#11998e;stop-opacity:1" />
                <stop offset="100%" style="stop-color:#38ef7d;stop-opacity:1" />
            </linearGradient>
        </defs>
        <rect width="500" height="200" fill="url(#grad1)"/>
        <text x="250" y="80" text-anchor="middle" fill="white" font-size="28" font-weight="bold">
            Welcome to SVG!
        </text>
        <text x="250" y="120" text-anchor="middle" fill="white" font-size="16">
            Scalable Vector Graphics
        </text>
        <circle cx="50" cy="170" r="20" fill="rgba(255,255,255,0.3)"/>
        <circle cx="450" cy="170" r="20" fill="rgba(255,255,255,0.3)"/>
    </svg>

</body>
</html>
```

---

## Summary

| Element | Purpose | Best For |
|---------|---------|----------|
| `<audio>` | Embed audio | Music, podcasts |
| `<video>` | Embed video | Tutorials, demos |
| `<canvas>` | Pixel-based drawing (JS) | Games, charts |
| `<svg>` | Vector-based graphics (XML) | Logos, icons, diagrams |
| `<track>` | Subtitles for video | Accessibility |

---

*Day 16 of 55 | Unit 3 — HTML5 | Web Technology (25BCA060)*
