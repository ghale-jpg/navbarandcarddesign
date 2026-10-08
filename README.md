# HTML & CSS — Navigation Bar and Card Design

## Student Information
- **Name:** Rohit Bhattarai
- **Student ID:** 2602412468
- **Course/Module:** FSE
- **Level:** L4 Sem 2
- **Assignment:** HTML & CSS Practical Assignment — Navigation Bar and Responsive Card Layout

## Project Description
A small, responsive online shop called **Himal Bazaar**, with a layout inspired by the Nepali marketplace [daraz.com.np](https://www.daraz.com.np) (category shortcuts, product cards with discount badges and prices, add-to-cart buttons). The name, products, prices and images are my own fictional versions; nothing was copied from Daraz. It has a sticky navigation bar (hamburger menu on mobile), an introduction with category chips, six product cards in a responsive grid, short About and Deals sections, and a footer.

## Technologies Used
- HTML5 (semantic elements)
- CSS3 (variables, selectors, box model, transitions)
- CSS Flexbox (navbar, card internals, footer)
- CSS Grid (card layout)
- Responsive CSS (media queries)

## Learning Resources
> Fill this table with the resources YOU really used, in your own words. The rows below are examples of the level of detail expected; replace them.

| No. | Resource | Topic Learned | What I Learned | How I Applied It |
|-----|----------|---------------|----------------|------------------|
| 1 | [Teacher's lecture] | [Selectors] | [your own explanation] | [where in your code] |
| 2 | [University material] | [Semantic HTML] | [your own explanation] | [e.g. used `<header>`, `<nav>`, `<main>`, `<footer>`] |
| 3 | [YouTube tutorial] | [Navbar] | [your own explanation] | [e.g. `display: flex` + `justify-content: space-between` on `.navbar`] |
| 4 | [MDN] | [CSS Grid / cards] | [your own explanation] | [e.g. `repeat(3, 1fr)` grid + media queries] |

## Screenshots

### Navigation Bar
![Navigation Bar](screenshots/navigation-bar.png)

### Card Design
![Card Design](screenshots/card-design.png)

### Card Layout
![Card Layout](screenshots/card-layout.png)

### Responsive Design
![Responsive Design](screenshots/responsive-design.png)

## Key Concepts Learned
- **Semantic HTML:** `<header>`, `<nav>`, `<main>`, `<section>`, `<article>` and `<footer>` describe the meaning of content, which helps screen readers, search engines and other developers.
- **CSS selectors:** element, class, descendant (`.nav-links a`), grouped (`h1, h2, h3`), attribute (`section[id]`), pseudo-class (`:hover`, `:checked`) and sibling (`+`, `~`) selectors.
- **Box model:** content + padding + border + margin; `box-sizing: border-box` makes width include padding and border.
- **Flexbox:** one-dimensional layout. Used for the navbar, to stack card content, and to push the button to the card bottom with `margin-top: auto`.
- **Grid:** two-dimensional layout. Used for cards because it gives equal-height rows and easy column control.
- **Typography:** serif headings, sans-serif body, `clamp()` for fluid heading size, `ch` units for readable line length.
- **Spacing:** `gap` for space between items, padding for space inside, margin for space outside.
- **Hover effects:** `:hover` + `transition` for nav links, buttons and card lift.
- **Responsive design:** `meta viewport` and media queries at 992px (2 columns), 768px (mobile menu) and 600px (1 column).

## Challenges and Solutions
1. **Cards had different heights because descriptions had different lengths.** I made `.card` a column flex container, gave `.card-body` `flex: 1`, and used `margin-top: auto` on the button so every button sits at the bottom and Grid keeps each row equal.
2. **The mobile menu needed to open without JavaScript.** I used a hidden checkbox and a `<label>` as the hamburger button. The selector `.nav-toggle-input:checked ~ .nav-links` shows the menu when the box is checked.
3. *(Add your own real challenge here.)*

## AI Usage Disclosure
AI assistance (Claude by Anthropic) was used to generate the initial version of the code and comments. I have read the code, tested it in the browser, and [describe what you changed or checked yourself]. I can explain each part of it.

## GitHub Repository
[https://github.com/your-username/html-css-assignment](https://github.com/your-username/html-css-assignment)
