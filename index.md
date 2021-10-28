# The New CSS Reset

This new CSS reset is using the new CSS features:
- The global CSS reset keywords, ‘unset’ and ‘revert’ keywords.
- The new property of ‘all’ which can reset all properties combined.
- The :where() pseudo-class to remove specificity.
- The :not() pseudo-class with multi arguments.

## What the-new-css-reset is resetting?
This CSS reset is built from the understanding we don't want to use the default style we are getting from the browsers, except the 'display' property.

This CSS reset removes all the default styles which we are getting on specific HTML elements except the 'display' property, as I already mention, and except special HTML elements like iframe, canvas, img, svg, video.

In case you want the default style of the browser of a specific HTML element back, you can revert back to the default styles of the browser. For example:
```
input[type="checkbox"],
input[type="radio"] {
    all: revert;
}
 ```
 
 or all input elements:
 ```
 input,
 textarea,
 select {
    all: revert;
 }
 ```
## Start use the-new-css-reset
- [Download the Latest Version](https://raw.githubusercontent.com/elad2412/the-new-css-reset/main/css/reset.css)
- [Use as a NPM Package](https://www.npmjs.com/package/the-new-css-reset)

## How it Looks and Works
```
/*** The new CSS Reset - version 1.3.1 (last updated 28.10.2021) ***/

/*
    Remove all the styles of the "User-Agent-Stylesheet", except for the 'display' property
    - The "symbol *" part is to solve Firefox SVG sprite bug
 */
*:where(:not(iframe, canvas, img, svg, video):not(svg *, symbol *)) {
    all: unset;
    display: revert;
}

/* Preferred box-sizing value */
*,
*::before,
*::after {
    box-sizing: border-box;
}

/* Remove list styles (bullets/numbers) */
ol, ul {
    list-style: none;
}

/* For images to not be able to exceed their container */
img {
    max-width: 100%;
}

/* removes spacing between cells in tables */
table {
    border-collapse: collapse;
}

/* revert the 'white-space' property for textarea elements on Safari */
textarea {
    white-space: revert;
}

```
## Browser Support
All evergreen browsers 
- Chrome, Edge: version 88+
- FireFox: version 84+
- Safari/iOS browsers: version 14+
- Opera: version 75+
- Samsung Browser: version 15+

## Extensive Reading and Watching
- [Understanding the “Initial”, “Inherit” and “Unset” CSS Keywords](https://elad.medium.com/understanding-the-initial-inherit-and-unset-css-keywords-2d70b7121695)
- [How Does CSS Work?](https://elad.medium.com/how-does-css-work-92fe7116916d)
- [The CSS Keywords That No One Really Understands (Video)](https://www.youtube.com/watch?v=nnhUBRRhKW0)

Made by [Elad Shechter (twitter)](https://twitter.com/eladsc)
