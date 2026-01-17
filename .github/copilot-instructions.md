# Copilot Instructions for Portfolio Website

## Project Overview
This is a simple personal portfolio website for Obiageri Stöhr, a front-end developer. The site is a static, multi-page HTML/CSS project built with Bootstrap 5 for responsive design and layout.

**Key Files:**
- [index.html](../index.html) - Homepage with project showcase
- [about.html](../about.html) - About page with contact section
- [style.css](../style.css) - Custom styling using CSS variables

## Architecture & Key Patterns

### Color System
Custom CSS variables defined in `:root` in [style.css](../style.css):
- `--primary-color`: #6c63ff (purple accent)
- `--secondary-color`: #f5f2fe (light purple background)
- `--box-shadow`: 0 5px 10px rgba(0, 0, 0, 0.3)

When adding new components, use these variables instead of hardcoding colors to maintain consistency.

### Navigation Structure
- Shared navbar component on both pages using Bootstrap collapse (`navbar-toggler`)
- Active nav links marked with `active` class (set on current page)
- Navigation uses anchor links for Contact: `/about.html#contact`
- Image paths use absolute paths starting with `/` (e.g., `/images/yoga.png`)

### Typography Scaling
Fixed font sizes defined globally:
- h1: 96px
- h2: 48px
- h3: 24px
- p: 18px (line-height: 1.5)

Maintain this scaling when modifying headings; don't use inline font-size unless overriding intentionally.

### Button/Link Pattern
Two link styles: `.primary-link` (filled purple button) and `.secondary-link` (outlined button). Both use consistent padding (20px 15px), border-radius (4px), and box-shadow. Use these classes for all CTAs.

### Bootstrap Grid Usage
- Multi-column layouts using `.row` and `.col-6` (homepage) / `.col-sm-4` (about page)
- Images use `.img-fluid rounded` for responsive sizing
- Container padding handled by Bootstrap `.container` class

## File Organization
```
/
├── index.html          # Homepage
├── about.html          # About & contact page
├── style.css           # Custom styles (Bootstrap imported via CDN)
├── image/              # Images (yoga.png, weather.png, yogurt.png)
└── .github/copilot-instructions.md
```

## Development Workflow
- **No build step**: Static files served directly
- **CSS updates**: Edit [style.css](../style.css) directly; changes are immediate on refresh
- **Adding pages**: Create new `.html` file, import Bootstrap CDN and `/style.css`, copy navbar structure
- **Image paths**: Place files in `/images/` directory and reference as `/images/filename.png`

## Common Tasks

**Adding a new project card:**
1. Follow the row structure: `.row.mt-5` with `.col-6` + image, `.col-6` + text
2. Use `.primary-link` for "Launch" button
3. Keep image and text columns balanced

**Updating contact link:**
The email link in about.html uses `obiageri:` protocol (typo - should be `mailto:`). When fixing, verify the link format matches modern email practices.

**Responsive adjustments:**
Homepage uses fixed `.col-6` (50% width). About page uses `.col-sm-4` (responsive to 3-column on medium screens). Maintain this distinction based on content.

## External Dependencies
- Bootstrap 5.0.0-beta2 (CSS + JS bundle) via CDN with SRI integrity hashes
- No custom JavaScript required for current features
- All interactivity (navbar collapse) comes from Bootstrap
