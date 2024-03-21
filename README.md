![It's finally done! Meet Landing Page Challenge](./images/banner.png)

# Meet Landing Page Challenge

## Disclaimer

This project is solely for learning purposes. I take no any responsibility or liability for the accuracy, completeness, or usefulness of any information provided in this project. You should not use it as a reference for creating your project.

I am currently no longer working on this project.

## Overview

### Introduction

Welcome to the `README.md` of this repo! The purpose of creating this project is to sharpen my coding skill.

In this file I'm going to tell you everything, starting from tools that I used, and much more.

That's it for the introduction and **happy reading!**

### The Challenge

The challenge is to build out this landing page and get it looking as close to the design as possible.

The users should be able to:
- View the optimal layout depending on their device's screen size
- See hover states for interactive elements
- Explore the site using screen reader
- See focus visible states for interactive elements

### Links

- [Live Review](https://officialmeet.netlify.app/)
- [Frontend Mentor Solution Page](https://www.frontendmentor.io/solutions/meet-landing-page-html-css-sass-aCWhmZKRk)

### Screenshots

![Desktop](./screenshots/desktop.png)

## My Process

### Built With

- **Following best practices**\* 
- HTML Semantic Tags
- [BEM (Block, Element, Modifier)](https://sparkbox.com/foundry/bem_by_example) Class *Naming Convention*
- [Sass](https://sass-lang.com/)
- CSS Flexbox
- Mobile-first workflow
- [Normalize.css](https://necolas.github.io/normalize.css/)

> * I follow guidelines. [See what guidelines that I follow.](./docs/README.md#guidelines)

### What I Learned

#### Advanced Pseudo-Elements

![Creating the circle with a number in it](./screenshots/problem-number.png)

The problem is the element is just a decoration. So, if I used an actual element on the HTML, it might be look something like this:

```html
<div class="number" aria-hidden="true">
  <p class="number__value">01</p>
</div>
```

And that is okay, but I wanted to create it as a *decorative element*. So, I thought, *"Why don't use pseudo-elements? But, is it possible?"*. Luckily, **it is possible!**

As the result, I managed to create it with **100%** pseudo-elements. Let me explain how I did that.
- First, on the HTML, I added the `number` class to the `section` and a modifier class (`number--one`) for the `content` of the number.

```html
<section class="feature number number--one">
</section>
```

- Second, I made the `number` element as `position: relative;`
- Third, I made the pseudo-elements center horizontally using absolute positioning.
```css
/**
 * 1. This is temporary code. It used to
 * to create the circle and the vertical line
 */
.number::after,
.number::before {
  content: ""; /* 1 */
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}
```
- Fourth, I used the `::after` as the circle and the `::before` as the vertical line.
- Lastly, after everything was set up, I removed the temporary `content` property and wrote each number on the modifier class.
```css
.number--one::after {
  content: "01";
}

.number--two::after {
  content: "02";
}
```

If you want to know the complete code, see [_number.scss](./scss/components/_number.scss)

## License

[MIT](./LICENSE)

## References

See the [documentation.](./docs/README.md)
