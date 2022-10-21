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

## CSS Selectors

"Class selectros" let you apply CSS styles to a specific HTML element. They let you defferentiate between HTML elements of the same type.

The requirements to do this are:

- A `class` attribute on the HTML element in question.
- A matching CSS class selector in the stylesheet.

The syntax to apply the rules to a class is:

```css
    .class-name {
        /* rule */
    }
```


### Container divs

Multiple elements in a page can be wrapped around `<div>` tags to style them all at once.

This is how layouts are defined in more complex web pages. 

### Reusing and modifying class styles

- Classes can be reused to use in multiple elements and style them all at once.
- The *same* element can have *multiple* classes too, to alter one element in a class without altering another.

The syntax to have multiple class in one element is:

```html
    <div class='button call-to-action'>Button two</div>
```

The precedence is given by the order in the **CSS stylesheet** and not the order in the **HTML file** class attribute.

### Descendant Selectors

Descendant selectors let you target only those elements that are *inside* of another element. The syntaxis is:

```css
.class-name sub-class-name {
    /* attributes */
}
```

> Related: [child selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Child_selectors)

### Pseudo-classes for links
CSS pseudo-classes provide a mechanism for hooking into "the temporary user information" and styling the state of an element.

<h4>Basic link styles</h4>

The most common link pseudo-classes are as follows:

- :link - a link the user has never visited
- :visited - a link the user has visited before.
- :hover - a link with the user's mouse over it.
- :active - a link that's being pressed down.

The syntax to style it is:

```css
a:hover {
    color: aqua;
}

a:hover:visited {
    color orange;
}
```

### Pseudo-classes for buttons
[Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

Pseudo-classes can be applied to any kind of selector (not just type selector). 

`last-of-type`: lets you select the final element of a particular type in its parent element. 
`first-of-type`: it's the same but with the first element.

> Obs: these pseudo-classes apply to EVERY container element.

To select only one container, we could do:

```css
    .container > element:first-of-type {
        /* properties */
    }
```

## ID Selectors

ID Selectors work in pretty much the same wasy as CSS Selectors, but only *one* element can have the same ID per page, they can't be reused. 

The attribute in the HTML page is `id="id-name"` and to refer to them in a CSS stylesheet we use:

```css
    #id-name {
        /* properties */
    }
```

This practice is hard to maintain, so it's usually frowned-upon.

> `id` attributes need to be unique because they serve as the target for “URL fragments”.


## CSS Specificity

“CSS specificity” is the weight given to different categories of selectors. This means that certain selectors will always override other ones, regardless of where they appear in the stylesheet.

For example: ID selectors have higher specificity than class selectors.

The speciificity goes as follows:

- `#id`
- `.class:pseudo-class`
- `basic-element:pseudo-class` and `.class sub-class`
- `.class`
- `basic-element`

## Floats
[Example](./floats/styles.css)
[Web page](./floats/floats.html)

Floats let you put block-level element side-by-side instead of on top of each other.

> Float-based layouts have mostly been replaced with Flexbox in modern websites.

The `float` property handles the control over the *horizontal* position of an element.

The most common values are:

- `left`: this leaves the container to the left and lets the next container surround it.
- `right`: same but leaves the container to the right.
- `none`: default.

Summary:

To align block boxes we have these options:

- to the left: `float: left`
- center: `margin: 0 auto`
- to the right: `float: right`

> Child boxes float arount their parents.

With the use of multiple containers (`<div>`) inside other containers are how complex webpages are built.

When *multiple elements* are float in the *same direction*, they'll stack horizontally.

### Clearing Floats

“Clearing” a float is when we tell a block to ignore any floats that appear before it. Instead of flowing around the floated box, a cleared element always appears after any floats.

The property is called `clear` and it can take three values: `both`, `left`, `right`.

Clearing floats only fixes the height issue when there’s an element inside the container element that we can add a clear property to. 

To resolve an issue of zero-height a container with only floated elements, one can use the `overflow` property.

`overflow: hidden` recognizes the height of any floated element inside a container.


### Floats for Equal-Width Columns

Floats can be used to create multi-column layouts. 

Percentages in CSS are relative to the width of the parent element, they can be applied to columns to take-up a percentage of the parten container.


<h4> Floats for Grids </h4>

When there isn't enough room to stack a floated element horizontally, it pops down to the next line, forming a grid.

<h4> Floats for Content </h4>

The other aspect of layouts is styling the individual HTML components that go inside this overarching page structure.

<h4> Hiding Overflow (for content) </h4>

Adding `overflow: hidden` to a content element will make sure the element is 'horizontally cleared', in the meaming of that instead of floating it left (which could make it go underneath of another element if it didn't fit), it explicitly leaves it to the left (adjusting the width).

