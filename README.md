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
| Recipe Detail | Two-column layout: main content + Quick Facts sidebar (with Suggested for you), in-page nav |
| About | Studio philosophy, Story Pack approach, contact info |
| Team | Project leader info, responsibilities, time tracking |

## Bonus Feature: Recommendation Engine UI

This project includes **Bonus Feature 2: Recommendation Engine UI** — a CSS/HTML-only simulation of a personalized recipe suggestion system.

### Purpose
Simulates an AI-powered "suggested next step" experience: when viewing any recipe, users see 2–3 related recipes with confidence scores and explainability hints, as if a recommendation algorithm had analyzed their current context.

### Implementation
- **Where:** "Suggested for you" section in the right sidebar (aside) on every recipe detail page, filling the Quick Facts column
- **Confidence labels:** Percentage badges (e.g., 92% match) on each suggested card, styled with a gradient pill
- **Explainability hints:** Short text explaining why each recipe was suggested (e.g., "Similar cooking style · Cozy dishes", "Same protein · Quick weeknight")
- **Suggested recipes:** Curated per-page; each recipe page shows 3 related recipes with different match reasons
- **Tech:** Semantic HTML (`<section>`, `<article>`, `aria-labelledby`), CSS Grid for the card layout, no JavaScript

### AI Concept Mapping
The UI simulates a **recommendation system** (e.g., collaborative filtering or content-based filtering): given the current recipe (user state), it presents ranked alternatives with confidence scores and transparent reasoning — key concepts in explainable AI and personalized recommendation engines. All suggestions are static; the simulation conveys the *experience* of personalized recommendations without backend logic.

### Testing Evidence
1. **Layout:** Recommendation cards display in a single column in the sidebar on desktop; on mobile, they stack below the main recipe content.
2. **Accessibility:** Confidence percentages use `aria-label` for screen readers; section has `aria-labelledby`; focus states on links follow project's `:focus-visible` standards.
3. **Responsive:** At 768px breakpoint, recommendation grid collapses to a single column for readable mobile layout.

### Trade-offs
- Suggestions are hand-curated per recipe rather than dynamically generated.
- No real personalization or user-history tracking — the "personalized" experience is simulated through varied, context-aware suggestions per page.

## Browser Support

Tested on Chrome, Firefox, and Safari. Uses standard CSS (no vendor prefixes required for modern browsers).

## License

Project for educational use. CSC 4370/6370, Georgia State University.
