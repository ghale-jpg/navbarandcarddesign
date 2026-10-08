# Meridian Supply — HTML & CSS Assignment

**Student:** Rohit Bhattarai
**Student ID:** 2602412468
**Course:** FSE
**Submission date:** 10/6/2026

A single-page online storefront built with semantic HTML5 and responsive CSS, submitted
as `index.html`, `style.css` and this README.

---

## 1. What the project is

An online store called **Meridian Supply**, selling six everyday desk and carry products.
Every line of both code files carries its own comment explaining what that line does, so
each rule can be explained line by line during the viva.

## 2. File structure

```
html-css-assignment/
├── index.html      → the page structure (HTML only, no styling in it)
├── style.css       → every visual rule, in 14 numbered sections
└── README.md       → this document
```

## 3. How to run it

1. Unzip the folder.
2. Double-click `index.html` — it opens in any browser and works immediately.
3. Scroll the page and drag the window narrower to watch the layout change.

No server, no build step and no JavaScript are needed. The photos are loaded from public
image URLs so the page looks complete on its own. To use local copies instead, save the
photos into an `images` folder next to `index.html` and change each `src` attribute to
e.g. `images/field-notebook.jpg`.

## 4. How each requirement is met

| # | Requirement | Where | How it was met |
|---|-------------|-------|----------------|
| 1 | Navigation bar with 4 links + 1 of my own choice | `<header class="site-header">` | Home, Shop, About, Contact (the four required) plus **New Arrivals**, my own choice. Each link anchors to a section id. |
| 2 | Hover effect on the navigation | `.nav__link::after` | A 1px accent underline grows from 0 to 100% width on hover; the text also darkens. |
| 3 | Hero section with a heading and an introduction | `.hero` | An `<h1>` headline, a short introduction paragraph, two calls to action, three key promises and a hero photograph. |
| 4 | One reusable card component | `.card` | The card (photo, tag, title, price, description, rating, button) is written once and used six times — identical markup, different content. |
| 5 | Six cards in a card layout | `.card-grid` | CSS Grid: 3 columns on desktop → 2 on tablet → 1 on mobile. |
| 6 | Footer | `<footer class="site-footer">` | Brand line, three link groups (Shop, Company, Assignment), plus a copyright strip. |
| 7 | Responsive design | `@media` rules at the end of the CSS | 900px and 640px breakpoints; the menu collapses to a hamburger and the grids reflow. |
| 8 | Comments on every line | both files | One comment per line, in HTML `<!-- ... -->` and CSS `/* ... */`. |
| 9 | Semantic HTML | throughout | `header`, `nav`, `main`, `section`, `article`, `figure`, `footer`, `ul`/`li`, `dl`/`dt`/`dd`, `button`. |
| 10 | Accessibility | skip link, `aria-label`, `alt`, `:focus-visible` | Keyboard users can skip the menu, every landmark is labelled, focus rings are always visible, and motion respects `prefers-reduced-motion`. |

## 5. Design decisions

- **Colour:** an off-white paper background (`#f9f9f7`) with charcoal text (`#1a1a1a`) — about
  14:1 contrast, well past the WCAG AA minimum of 4.5:1. One accent colour, blue (`#2563eb`),
  is used for links, buttons and tags so the page never looks busy.
- **Type:** Inter for text, IBM Plex Mono for prices so the digits line up in a column.
- **Spacing:** one scale of five spacing values keeps the rhythm consistent across every section.
- **Layout:** Flexbox where items sit on one axis (the navbar, the button rows) and Grid where
  items sit on two axes (the cards, the footer). Each tool is used for what it was designed for.

## 6. Responsive behaviour

| Screen width | Cards per row | Navigation | Other |
|--------------|---------------|------------|-------|
| Above 900px | 3 | Horizontal links | Two-column hero and about, four-column footer |
| 641–900px | 2 | Horizontal links | Hero and about stack to one column, footer becomes two columns |
| 640px and below | 1 | Collapsed behind a hamburger | Everything single column, larger tap targets |

## 7. Challenges and how I solved them

1. **Making the mobile menu without JavaScript.**
   A checkbox with `position: absolute; opacity: 0` sits before the link list, and the hamburger
   is a `<label>` pointing at it. The rule `.nav__checkbox:checked ~ .nav__list` shows the
   menu. Hidden checkboxes still receive clicks from their label, so this works for mouse,
   touch and keyboard without a single line of script.

2. **Keeping all six cards exactly the same height.**
   The cards are columns (`flex-direction: column`), the text area has `flex: 1`, and the
   footer row has `margin-top: auto`. That pushes the button row to the bottom of every card,
   so cards with shorter descriptions do not end early.

3. **The two things that broke first.**
   The sticky header covered headings when I clicked a nav link, fixed with
   `scroll-padding-top: 5rem` on `html`. And on phones the grid overflowed sideways, because a
   grid column defaults to at least the width of its content; the single-column media query
   removed that.

## 8. Learning resources I used

| Resource | What I used it for |
|----------|--------------------|
| MDN Web Docs — HTML element reference | Choosing the correct semantic element for each block |
| MDN Web Docs — CSS Grid Layout guide | `grid-template-columns: repeat(3, 1fr)` and the media-query overrides |
| CSS-Tricks — A Complete Guide to Flexbox | The navbar row and the `margin-top: auto` card footer trick |
| web.dev — Learn Responsive Design | The viewport meta tag and the mobile-first breakpoints |
| MDN Web Docs — `box-sizing` | Understanding why `box-sizing: border-box` keeps a 300px card at 300px |
| MDN Web Docs — CSS `clamp()` | Fluid heading sizes that scale between a min and a max with the screen |
| MDN Web Docs — `:focus-visible` | Showing the focus ring only to keyboard users, not mouse users |
| MDN Web Docs — `prefers-reduced-motion` | Switching off transitions for visitors who ask for less motion |
| CSS-Tricks — `aspect-ratio` | Reserving the photo space before the image loads so the page never jumps |
| CSS-Tricks — "Building a Pure CSS Hamburger Menu" | The checkbox + label trick that opens the mobile menu with no JavaScript |
| Smashing Magazine — "Inclusive Components" (Heydon Pickering) | Choosing `<article>` for a self-contained card and a description list for contact details |
| A List Apart — "How to Size Text in CSS" | Setting 1rem (16px) as the accessible baseline and 1.6 line-height for reading |
| W3C — CSS Box Model (W3C Recommendation) | The reset rules that remove default margins and padding from every element |
| Google Fonts — Inter & IBM Plex Mono | Loading the text and price typefaces with `preconnect` so text does not flicker in |
| Kevin Powell — "Modern CSS" (YouTube) | Building the spacing scale and the hover underline that grows from 0 to 100% |

## 9. Questions I can answer about the code

- **Why HTML first, then CSS?** HTML describes meaning; CSS describes appearance. Keeping them
  apart means the structure still makes sense with the stylesheet removed.
- **Why `<article>` for a card?** Each card would still make sense on its own, which is exactly
  what `article` means to a screen reader.
- **Why is there only one `<h1>`?** Headings form an outline. One `h1` for the page, `h2` for each
  section, `h3` inside a section — never skipping a level.
- **Why `box-sizing: border-box`?** So a card set to 300px measures 300px including its padding
  and border, instead of growing wider than the grid cell.
- **What does `1fr` mean?** "One fraction of the free space", which is how three equal columns
  are made.

## 10. Use of AI tools

I used an AI assistant to help structure the project and to check my CSS. I reviewed every line,
rewrote sections in my own words, tested the page at each breakpoint by resizing the browser, and
I can explain any line of both files. This disclosure follows the [Course Name] academic honesty
policy.

## 11. Before submitting — final checklist

- [ ] Replaced every `[bracketed placeholder]` in this file and in the footer of `index.html`
- [ ] Captured the four screenshots: navigation bar, one card, the whole grid, and the mobile view
- [ ] Checked the page at 1400px, 900px and 375px wide
- [ ] Tabbed through the page with the keyboard to confirm every link and button is reachable
- [ ] Added my own learning resource to the table in section 8
- [ ] Zipped the folder and checked the zip opens and `index.html` still works
