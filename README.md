# Portfolio

A clean, JSON-driven portfolio site. Edit the files in `data/` to update your content — no coding needed.

---

## Folder Structure

```
portfolio/
├── index.html          ← Page structure (rarely needs editing)
├── style.css           ← All styles & color theme
├── data/
│   ├── info.json       ← Your name, about text, contact links
│   ├── projects.json   ← Your projects list
│   └── skills.json     ← Your skills & proficiency levels
└── images/
    └── projects/       ← Drop project screenshots here
        ├── myapp.png
        └── ...
```

---

## Running the Site

Because the site fetches JSON files, you need a local server — you **cannot** just open `index.html` directly in your browser.

**Option 1 — VS Code Live Server** (easiest)
1. Install the "Live Server" extension in VS Code
2. Right-click `index.html` → "Open with Live Server"

**Option 2 — Terminal**
```bash
# Node.js
npx serve .

# Python
python3 -m http.server 8080
```

Then open `http://localhost:8080` (or whatever port is shown).

---

## Editing Your Info (`data/info.json`)

Change your name, tagline, about blurbs, stats, and contact links here.

- `heroTag` — the small label above your name (e.g. `"— Open to work"`)
- `about.paragraphs` — supports basic HTML like `<strong>`, `<a>`, etc.
- `about.stats` — the 4 highlight numbers (years, projects, etc.)
- `contact.links` — set `"primary": true` on one link to make it the highlighted CTA button

---

## Adding a Project (`data/projects.json`)

Add a new object to the array:

```json
{
  "title": "My New Project",
  "description": "A short description of what it does and why it matters.",
  "image": "images/projects/my-project.png",
  "tags": ["React", "Node.js"],
  "links": [
    { "label": "Live Site", "href": "https://...", "primary": true },
    { "label": "GitHub",    "href": "https://..." }
  ]
}
```

**Images:**
- Put your screenshot in the `images/projects/` folder
- Set `"image"` to the relative path: `"images/projects/my-project.png"`
- You can also use a full URL: `"image": "https://i.imgur.com/abc123.png"`
- Leave `"image": ""` to show a letter placeholder instead

---

## Editing Skills (`data/skills.json`)

Each object is a category with a list of skills. `level` is a percentage (0–100) shown as a bar.

```json
{
  "category": "My Category",
  "items": [
    { "name": "Some Skill", "level": 85 },
    { "name": "Other Skill", "level": 70 }
  ]
}
```

---

## Changing the Color Theme (`style.css`)

Edit the CSS variables at the top of `style.css`:

```css
:root {
  --bg:      #0a0a0a;   /* Page background      */
  --border:  #1e1e1e;   /* Subtle border color  */
  --accent:  #c8f05d;   /* Primary accent color */
  --text:    #e8e8e8;   /* Main text color      */
  --muted:   #666;      /* Secondary text       */
  --card-bg: #131313;   /* Card background      */
}
```
