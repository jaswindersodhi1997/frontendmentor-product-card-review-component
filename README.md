# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Screenshot

![Desktop preview of the product preview card component](./design/desktop-preview.jpg)

image.png

### Links

- Solution URL: [Add your Frontend Mentor solution URL](https://www.frontendmentor.io)
- Live Site URL: https://frontendmentor-product-card-review.vercel.app/

## My process

### Built with

- Semantic HTML5 markup (`main`, `article`, `picture`, `del`)
- CSS custom properties for colors and typography
- Flexbox for page centering and vertical content spacing
- CSS Grid for the pricing row and desktop two-column card layout
- The `<picture>` element for responsive product images
- A mobile-first workflow with a desktop breakpoint at `769px`

### What I learned

This project helped me connect HTML structure with CSS layout in a more intentional way. A few patterns I focused on:

**Semantic structure and BEM-style class names**

I used an `<article>` for the product card and named classes with a consistent block/element pattern (`product-card`, `product-card__title`, `product-card__cta`). That made it easier to style each part without guessing which selector belonged to which section.

```html
<article class="product-card">
  <picture class="product-card__image">...</picture>
  <div class="product-card__content">...</div>
</article>
```

**Design tokens with CSS custom properties**

Instead of repeating color and font values, I defined them once in `:root` and reused them across the stylesheet. That kept the palette aligned with the style guide and made updates simpler.

```css
:root {
  --color-green-500: hsl(158, 36%, 37%);
  --font-primary: "Montserrat", sans-serif;
  --font-heading: "Fraunces", serif;
}
```

**Responsive images with `<picture>`**

Rather than swapping images with CSS alone, I used `<source>` elements inside `<picture>` so the browser loads the correct asset for mobile and desktop viewports.

**Combining Flexbox and Grid**

Flexbox handles vertical spacing inside the card content (`gap`, `flex-direction: column`), while Grid takes over at the desktop breakpoint to place the image and text side by side and align the pricing row.

```css
@media (min-width: 769px) {
  .product-card {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
}
```

### Continued development

Areas I want to keep improving in future projects:

- **Focus states** — The button has a hover style; I plan to add a clear `:focus-visible` state so keyboard users get the same visual feedback.
- **Unit consistency** — I mixed `rem` and `px` in places (for example, `gap: 20px` alongside `padding: 2rem`). I want to standardize on relative units where it makes sense.
- **Accessibility polish** — Reviewing contrast, touch target size, and screen reader behavior for interactive elements.

### Useful resources

- [MDN: Using CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) — Clear reference for setting up and reusing design tokens with `:root`.
- [MDN: Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images) — Helped me understand when to use `<picture>` vs a single responsive `img`.
- [CSS-Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) — Useful for centering the card and spacing content inside it.
- [CSS-Tricks: A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) — Good visual reference for the desktop two-column layout.
- [Frontend Mentor style guide](./style-guide.md) — Official colors, fonts, and layout widths for this challenge.

### AI Collaboration

- **Tool used:** Cursor (with project `AGENTS.md` guidance)
- **How I used it:** For README writing, reviewing structure, and clarifying CSS concepts while building the layout myself.
- **What worked well:** Breaking problems into smaller steps and asking targeted questions instead of copying full solutions.
- **What I learned:** Using AI as a mentor works best when I already have code to discuss and specific questions about what is not behaving as expected.

## Author

- Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/yourusername)

## Acknowledgments

Thanks to [Frontend Mentor](https://www.frontendmentor.io) for the challenge brief, assets, and style guide that made this a focused practice project.
