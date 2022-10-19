# CSS Fundamentals

- [Tutorial followed](https://www.internetingishard.com/html-and-css/hello-css/)
- [Documentation]()

## Presentation of a webpage: CSS Stylesheets
- [Example](./hello-css.css)
- [Webpage](./hello-css.html)

CSS adds rules to the style of HTML elements, for example:

```cs
body {
    color: #FF0000;
}
```

gives the text of the element `body` of the HTML document the color red. (`color` refers to the text color).

To link a CSS Stylesheet to an HTML document we add `<link/>` to the metadata of the HTML file.

### Unit of measurement

- px: refers to pixel.
- em: multiplier to the fontisze of the element in question. It's useful because it is relative to the base font.

Rules can refere to multiple elements, like this:

```cs
h1, h2, h3, h4, h5, h6 {
    font-family: "Helvetica", "Arial", sans-serif;
}
```

### List Styles
The `list-style-type` property lets you change the bullet icon used for `<li>`, like this:

```cs
ul {
    list-style-type: circle;
}

ol {
    list-style-type: lower-roman;
}
```

A particular value es `none`, which is commonly used when marking up menu navigation with `<li>`.

`list-style-image` lets u create custom bullets.

### Underline 

```cs
a {
  text-decoration: none;
}
```

This removes the underline from every link.


### Text Alignment
The property `text-aligned` defines the alignment of the text in an HTML element.

The accepeted values are: `left`, `right`, `center`, or `justify`. 


### Font Weight and Styles

The `font-weight` property defines the *boldness* for the text in an element, and the `font-style` one indicates whether it is in italics or not.


### The Cascade

The CSS hierarchy for every web page looks like this:

- The browser’s default stylesheet
- User-defined stylesheets
- External stylesheets (that’s us)
- Page-specific styles (that’s also us)
- Inline styles (that could be us, but it never should be)

This is ordered from least to most precedence, which means styles defined in each subsequent step override previous ones.