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
```css
input[type="checkbox"],
input[type="radio"] {
    all: revert;
}
 ```
 
 or all input elements:
 ```css
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
```css
/***
    The new CSS reset - version 1.8.4 (last updated 14.2.2023)
    GitHub page: https://github.com/elad2412/the-new-css-reset
***/

/*
    Remove all the styles of the "User-Agent-Stylesheet", except for the 'display' property
    - The "symbol *" part is to solve Firefox SVG sprite bug
 */
*:where(:not(html, iframe, canvas, img, svg, video, audio):not(svg *, symbol *)) {
    all: unset;
    display: revert;
}

/* Preferred box-sizing value */
*,
*::before,
*::after {
    box-sizing: border-box;
}

/* Reapply the pointer cursor for anchor tags */
a, button {
    cursor: revert;
}

/* Remove list styles (bullets/numbers) */
ol, ul, menu {
    list-style: none;
}

/* For images to not be able to exceed their container */
img {
    max-inline-size: 100%;
    max-block-size: 100%;
}

/* removes spacing between cells in tables */
table {
    border-collapse: collapse;
}

/* Safari - solving issue when using user-select:none on the <body> text input doesn't working */
input, textarea {
    -webkit-user-select: auto;
}

/* revert the 'white-space' property for textarea elements on Safari */
textarea {
    white-space: revert;
}

/* minimum style to allow to style meter element */
meter {
    -webkit-appearance: revert;
    appearance: revert;
}

/* preformatted text - use only for this feature */
:where(pre) {
    all: revert;
}

/* reset default text opacity of input placeholder */
::placeholder {
    color: unset;
}

/* remove default dot (•) sign */
::marker {
    content: initial;
}

/* fix the feature of 'hidden' attribute.
   display:revert; revert to element instead of attribute */
:where([hidden]) {
    display: none;
}

/* revert for bug in Chromium browsers
   - fix for the content editable attribute will work properly.
   - webkit-user-select: auto; added for Safari in case of using user-select:none on wrapper element*/
:where([contenteditable]:not([contenteditable="false"])) {
    -moz-user-modify: read-write;
    -webkit-user-modify: read-write;
    overflow-wrap: break-word;
    -webkit-line-break: after-white-space;
    -webkit-user-select: auto;
}

/* apply back the draggable feature - exist only in Chromium and Safari */
:where([draggable="true"]) {
    -webkit-user-drag: element;
}

/* Revert Modal native behavior */
:where(dialog:modal) {
    all: revert;
}
```
## Browser Support
All evergreen browsers 

![Chrome](https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) | ![Edge](https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png) | ![Firefox](https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png) | ![Safari](https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png) | ![Opera](https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png) | ![Samsung Internet](https://raw.githubusercontent.com/alrra/browser-logos/master/src/samsung-internet/samsung-internet_48x48.png)
--- | --- | --- | --- | --- | --- |
88+ ✔ | 88+ ✔ | 84+ ✔ | 14+ ✔ | 75+ ✔ | 15+ ✔ |

## Extensive Reading and Watching
- [Understanding the “Initial”, “Inherit” and “Unset” CSS Keywords](https://elad.medium.com/understanding-the-initial-inherit-and-unset-css-keywords-2d70b7121695)
- [How Does CSS Work?](https://elad.medium.com/how-does-css-work-92fe7116916d)
- [The CSS Keywords That No One Really Understands (Video)](https://www.youtube.com/watch?v=nnhUBRRhKW0)

Made by [Elad Shechter (twitter)](https://twitter.com/eladsc)
