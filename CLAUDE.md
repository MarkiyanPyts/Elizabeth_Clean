# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Shopify theme project called "Elizabeth" built with TailwindCSS and Alpine.js. It's designed as a clean, modern e-commerce theme following Shopify's Online Store 2.0 structure.

## Development Commands

### CSS/Styling
```bash
# Watch and compile TailwindCSS (required for styling changes)
npx @tailwindcss/cli -i ./src/tailwind.css -o ./assets/application.css --watch
```

### Shopify Development
```bash
# Start Shopify development server
shopify theme dev
```

### Project Initialization
```bash
# Clone this theme for a new project
shopify theme init [THEME_NAME] --clone-url https://github.com/polidario/Elizabeth_Clean
```

## Architecture

### File Structure
- **`layout/theme.liquid`** - Main theme layout, includes Alpine.js CDN and core CSS/JS
- **`sections/`** - Shopify sections (header, product templates, homepage, etc.)
- **`templates/`** - JSON template files that define section arrangements
- **`snippets/`** - Reusable Liquid components (icons, product cards, etc.)
- **`assets/`** - Static assets (CSS, JS, images)
- **`src/tailwind.css`** - TailwindCSS source file
- **`config/`** - Theme configuration and settings

### Key Technologies
- **Shopify Liquid** - Templating language for all `.liquid` files
- **TailwindCSS** - Utility-first CSS framework (must be compiled to `assets/application.css`)
- **Alpine.js** - Lightweight JavaScript framework for interactivity (loaded via CDN)
- **Swiper.js** - Used for product image carousels on mobile

### Theme Architecture
- Uses Shopify's **Online Store 2.0** architecture with JSON templates
- Sections are modular and configurable via `{% schema %}` blocks
- Mobile-first responsive design with TailwindCSS
- Interactive components use Alpine.js for state management

### Important Patterns
- **Section schemas** - Each section has a `{% schema %}` block defining customizable settings
- **Responsive navigation** - Header uses Alpine.js for mobile menu and search bar toggles
- **Product variants** - Custom JavaScript handles variant selection and price updates
- **Mobile carousels** - Product images use Swiper.js for mobile touch navigation

### Development Notes
- Always compile TailwindCSS when making style changes
- Section files include both Liquid templating and JavaScript functionality
- Icons are implemented as snippets (e.g., `{% render 'icon-search' %}`)
- Customer account features are conditionally displayed based on shop settings