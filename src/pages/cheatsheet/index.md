---
layout: ../../layouts/Cheatsheet.astro
---

# Website Making Cheatsheet

Most websites have a heap of boilerplate, that help make sure your website is scaled on mobile,
properly defined as an HTML document ([to avoid quirks mode](https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Quirks_mode_and_standards_mode)), know the document's charset without storing its charset header, etc... This can just be copied!


```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <!-- your actual website goes here -->
</body>
</html>
```

## HTML

HTML elements usually look like this:

```html
<tag attribute="value">
    Children of this element
</tag>
```

where we have a starting `<tag>`, an ending `</tag>` (mind the slash), some 'children' of the tag,
and occasional attributes.

For example, a blue header may look like:

```html
<h1 color="blue">
    My header
</h1>
```

(`h1` is one of six header types of decreasing size).

You can also nest elements:

```html
<p>My <b>bold</b> text</p>
```

where `<p>paragraph</p>` is a paragraph element.

You can also add links via `<a href="https://example.com">My link text</a>`

Sometimes, there are elements without that closing `</>` syntax, like images:

```html
<img src="https://example.com/image.png" alt="Accessible description of my image" />
```

where `alt` is some description of your image for screenreaders.

## Layout

HTML encourages using 'semantic' elements (like `<header>`, `<main>`, `<footer>` to organize your website). For example:

```html
<header>
    <h1>My header</h1>
</header>
<main>
    About me. Other things about me
</main>
```

## Styling

HTML also comes with CSS (fancy name for stylesheets) to style your website.

For example, to make a (simple) website have dark theme support and use your _computer's_ default font, you can add a `<style>` tag under the `<head>` of your website:

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Website</title>
  <style>
    html {
      /* Use your computer's font */
      font-family: system-ui;
      /* Change the colors automatically to be your system's theme. */
      color-scheme: light dark;
    }
  </style>
</head>
```

### Styling: Layout

It's nice to have a page with a good layout. Flexbox is your friend here. For example, the [card template](https://reed-cstar.github.io/website-workshop/templates/card.html) (right click -> view source) uses flexboxes to center a webpage.

For example, we can make a website be centered horizontally (but not vertically):

```css
html {
  display: flex;
  /* Centers horizontal elements. You can use align-items: center; for vertical elements. */
  justify-content: center;
}

body {
  /* The body can only be up to 70 normal characters long. */
  max-width: 70ch;
}
```

There's a lovely guide by [csstricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) on other flexbox shenanigans.

### Styling: Fun

We can use these stylesheets to change the style of various things:

```css
body {
  /* Makes the page red */
  background: red;
  /* Or you can give the page a gradient, generated with https://cssgradient.io/. */
  background: linear-gradient(
    90deg,
    rgba(42, 123, 155, 1) 0%,
    rgba(87, 199, 133, 1) 50%,
    rgba(237, 221, 83, 1) 100%);
}

/* Styles big headers */
h1 {
  /*
    There are units for sizes: we recommend
    'rem', which stands for X times as much as
    the system font size. There are other good units
    too, like ch for character.
  */
  font-size: 2rem;
}
```