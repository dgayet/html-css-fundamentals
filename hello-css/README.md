# CSS Fundamentals

- [Tutorial followed](https://www.internetingishard.com/html-and-css/hello-css/)
- [Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

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

### Page-specific styles

`<style>`: element that is used to add page-specific CSS rules to individual HTML documents. They are added in the head of the file.

Adding this element to an HTML file will override the equivalent rule in the stylesheet linked to it. 

### Inline styles
These are the most specific ways to define CSS. They are added as an attribute to an element and they override any other style applied to them.

Syntax example:

```html
    <p> This is a dead link, let's cross it: 
        <a href="nowhere.html" style= 'color: #990000; text-decoration: line-through;'>
            obsolete link</a> </p>
```

### Multiple stylesheets

Several CSS Stylesheets can be applied to the same file using multiple `<link/>` elements on the same page. 

> Observation: The order in which they are added matter: stylesheets that come later will override styles in earlier ones.

## The CSS Box Model
- [Example](./css-box-model/box-styles.css)
- [Webpage](./css-box-model/boxes.html)

The CSS box model is a set of rules that determine the dimensions of every element in a web-page. Each HTML element rendered on the screen is a box, and they come in two flavors: "block" boxes and "inline" boxes.

Paragraphs, headings, etc, are block boxes, and emphasis and strong are inline boxes. However, one can change the behavior of a box changing the `display` property to `block` in the CSS stylesheet.

### Content, Padding, Border and Margin

This model gives each box four major properties:

- **Content**: The text, image or other media content in the element.
- **Padding**: The space between the box's content and its border.
- **Border**: The line between the box's padding and margin
- **Margin**: The space between the box and surrrounding boxes. 

<h4> Padding </h4>

The property for padding is `padding`, and defines the padding for the selected element. The `background-color` is applied to everything inside the **border** so the padding added to an elements gets colored too.

<h4> Border </h4>
Outside the padding is the border, and the syntax to style is the following:

`border: size style color`.

The border adds a line around the padding.

The are variations to the `border` property to choose which side it applies to. `border-top`, `border-bottom` and so on.

> Borders are usually used to debug, they help you see how a certain box is rendered.

<h4> Margins </h4>

Margins define the space *outside* of an element's border, space between the box and its surrounding boxes. The property is called `margin` and like borders you can choose specific sides.

The main differences between padding and margins are:

- Margins *always* have transparent backgrounds
- Padding is included in the click of an element, margins are not.
- Margins collapse vertically.

> Block and inline elements handle margins differently. Inline boxes *completely ignore* **top** and **bottom** margins of an element. Also, the padding in inline boxes is added to every side, but they don't the vertical layout of surrunding boxes.

<h5> Vertical margin collapse </h5>

When there is an element with bottom margin sitting on top of another element with top margin, only the biggest is displayed. The bigger one abosrbs the other margin.

To prevent this from happening, and invisible element should be put in between them, for example:

```html
<p> Paragraph paragraph </p>

<div style='padding-top: 1px;'></div> <!-- invisible element -->

<p> Another paragraph </p>
```

> Only *consecutive* elements can collapse into each other.

### Generic Boxes
There are HTML boxes used *purely* for the sake of styling a web page. These are: `<div>` and `<span>`.

They are container elements but they don't have any effect on the semantic structure of and HTML document.

`<div>` are block-level and `<span>` are inline elements.

### Explicit Dimensions

The properties `width` and `height` are used to explicitly define the size of a box. They override the default size of a box's content.


### Content Boxes and Border Boxes

`width` and `height` define the size of a box's *content*. The padding and border is added on top of it. One can define the size of the box (content+padding+border) with the property `width` by setting the property `box-sizing` to `border-box`. In this case the content box width is determined automatically.

### Box Alignment

One of the ways of aligning the *box* (not the content) is setting left side of the `margin` property to `auto`. 

>Obs: this only work with elements that have explicit width, otherwise they take the whole width of the browser.


### Resetting styles
Different browsers have different default styles for all of their HTML elements.

The universal CSS selector (*) lets you override default styles, like this:

```cs
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

## CSS Selector