# Quick Weeknight Recipe Studio

A responsive, CSS-only recipe microsite built for CSC 4370/6370 Project 1. Features a calm, story-driven layout with semantic HTML, Flexbox and Grid layouts, smooth transitions, and accessibility-first design.

## Project Overview

- **Track:** Recipe Studio (Track A)
- **Extension Pack:** Story Pack — narrative "Acts" structure (The Setup, Ingredients, Steps, Tips) with in-page navigation and `:target` highlighting
- **Tech Stack:** HTML5, CSS3 (no JavaScript)

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/nitesh-kumar-15/kumar_recipe_site.git
   cd kumar_recipe_site
   ```

2. Open `index.html` in a browser, or serve the folder locally:
   ```bash
   # Example with Python
   python -m http.server 8000
   # Then open http://localhost:8000
   ```

3. No build step or dependencies required.

## Project Structure

```
kumar_recipe_site/
├── index.html              # Home page
├── recipes.html            # All recipes grid
├── about.html              # About & contact
├── team-introduction.html  # Team & time tracking
├── recipe-*.html           # 7 recipe detail pages
├── styles.css              # Shared styles
├── images/                 # Hero and recipe images
│   ├── family_cooking.png
│   ├── chicken_tikka.png
│   └── ...
└── README.md
```

## Design Decisions

### Layout
- **Flexbox** for header/nav alignment
- **CSS Grid** for recipe cards (`recipe-grid`) and detail page two-column layout (`recipe-layout`)
- Responsive breakpoint at 768px: nav stacks vertically, recipe layout collapses to single column

### Design System
- CSS variables in `:root` for colors, fonts, spacing, radii, and shadows
- Reusable components: `.recipe-card`, `.chip`, `.recipe-nav`, `.aside-card`
- Consistent typography (Georgia for headings, system fonts for body)

### Motion & Accessibility
- Keyframe animations: `fadeIn`, `slideIn`
- Transitions: card hover (transform + shadow), link color
- Story Pack `:target` styling for in-page section highlighting
- `@media (prefers-reduced-motion: reduce)` to minimize motion for users who prefer it
- Visible `:focus-visible` outlines on interactive elements

### Images
- Hero image on home page
- One image per recipe on cards and detail pages
- Image wrappers with fixed height, `object-fit: cover`, and consistent background for alignment

## Pages

| Page | Purpose |
|------|---------|
| Home | Hero, featured recipes (3 cards) |
| Recipes | Full grid of all 7 recipes |
| Recipe Detail | Two-column layout: main content + Quick Facts sidebar, in-page nav |
| About | Studio philosophy, Story Pack approach, contact info |
| Team | Project leader info, responsibilities, time tracking |

## Browser Support

Tested on Chrome, Firefox, and Safari. Uses standard CSS (no vendor prefixes required for modern browsers).

## License

Project for educational use. CSC 4370/6370, Georgia State University.
