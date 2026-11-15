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
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Screenshot

<p align="center">
  <img src="assets/images/screenshot.png" alt="Screenshot of the product preview card on desktop, with the perfume image on the left and the product details on the right" width="600">
</p>

### Links

- GitHub repository: [YOUR-REPO-NAME](https://github.com/hossamelgendy101/YOUR-REPO-NAME)
- Live site: [YOUR-LIVE-SITE](https://YOUR-LIVE-SITE-URL)

## My process

### Built with

- Semantic HTML5 markup (`article`, `picture`, `button`, `s`)
- CSS custom properties
- Flexbox
- Mobile-first workflow with a `min-width` media query
- Google Fonts (Fraunces and Montserrat)

### What I learned

- **Art direction with `<picture>`:** The mobile and desktop images are different crops (a wide image on mobile and a tall one on desktop), so `srcset` alone was not the right tool. I used `<picture>` with a `<source media="(min-width: 700px)">` for the desktop image and an `<img>` as the mobile default. I also learned that the CSS goes on the `<img>` inside `<picture>`, not on the `<picture>` element, and that a missing unit in the `media` attribute makes the browser silently ignore it.
- **Keeping the image and the layout in sync:** The image swap and the card layout switch have to happen at the same breakpoint, so I used the same value (700px) in the HTML and in the CSS.
- **Switching direction with Flexbox:** The card is a normal block on mobile (image on top), and `display: flex` in the media query puts the image and content side by side. The image uses a fixed `width`, `height: 100%` and `object-fit: cover` so it fills the card's height without being stretched.
- **Corner radius on the image:** The rounded corners move from the top of the image on mobile to the left side on desktop (`border-radius: 8px 0 0 8px`).
- **Choosing the right element for each part:** I used `<s>` for the old price (a value that is no longer valid) instead of `<del>`, a `<p>` for the "PERFUME" label because it is not a heading, and a `<button>` for "Add to Cart" because it performs an action and does not navigate anywhere. The decorative cart icon has an empty `alt`.
- **Debugging silent mistakes:** A typo in a pseudo-class and a missing `px` unit were ignored by the browser without any error, so I learned to verify each rule in the DevTools.

```html
<picture>
  <source media="(min-width: 700px)" srcset="assets/images/image-product-desktop.jpg">
  <img src="assets/images/image-product-mobile.jpg" width="350" height="342"
       alt="Perfume bottle on a light surface with green leaves">
</picture>
```

### Continued development

- Use `clamp()` for fluid typography in a project where the font sizes change between mobile and desktop (the fonts in this design are fixed, so it wasn't needed).
- Learn Sass/SCSS after getting comfortable with plain CSS.
- Add JavaScript interactions, such as updating a cart count when clicking the button.
- Reduce repeated CSS by sharing classes between similar elements.

### AI Collaboration

During this project, I collaborated with an AI assistant (**Claude**) to enhance my workflow and problem-solving process.

- **Tools used:** Claude, as a technical consultant and reviewer.
- **How I used it:** For reviewing my HTML structure, understanding when to use `<picture>` instead of `srcset`, and finding the causes of layout bugs by checking values in the DevTools.
- **What worked well:** It guided me step by step without giving me the full solution, and it caught silent mistakes like a missing unit and a mistyped pseudo-class.
- **What I did myself:** I wrote the HTML and CSS by hand, read the values from Figma, and tested the layout on different screen sizes.

## Author

- GitHub - [@hossamelgendy101](https://github.com/hossamelgendy101)
- Frontend Mentor - [@hossamnabil](https://www.frontendmentor.io/profile/hossamnabil)
- Twitter - [@hossamelgendy](https://www.twitter.com/hossamelgendy)

## Acknowledgments

- Thanks to **Frontend Mentor** for this challenge.
- Thanks to the developer community and AI assistant tools for guidance and feedback.