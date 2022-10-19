# HTML fundamentals

- [Tutorial followed](internetingishard.com/html-and-css/introduction/)
- [Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML)

## Structure of a web page: HTML Elements
- [Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- First webpage: [basics.html](./basics.html)

The basic structure of a web-page is as follows:

```html
<!DOCTYPE html>

<html>
    <head>
        <!-- Metadata goes here -->
    </head>

    <body>
        <!-- content goes here -->
    </body>
</html>
```

`<!DOCTYPE html>` tells the browser that the file is an HTML5 web page.

The entire webpage need to be *wrapped* in `<html>` tags. 

    `<html>`: opening tag

    `</html>`: closing tag

Inside the element `<html>` there are **two elements**: `<head>` and `<body>`. The head contains the metadata and the *visible* content is inside the body. 

### Metadata 

Elements of the metadata:

`<title>`: This is display in the tab of the webpage. 

<!-- // to be continued -->


### Paragraphs

`<p>` is the syntaxis for a paragraph, and this tag marks al the text inside as a *distinct paragraph*.


### Headings

There are six levels of headings `<h1>`, `<h2>`, .... `<h6>`.


### Lists

There are two kinds: 

`<ul>`: this is an *unordered list*. Every item of an list is called `<li>`.

`<ol>`: this refers to a *ordered list*. The elements are also called `<li>`.


### Inline Elements

This elements affect sections of text *within a line*.

`<em>`: it stands for emphasis and by default it is displayed as italics.
`<strong>`: similarly, the text wrapped around it is tipically displayed in bold.

They are not called *italics* and **bold** because they are concerned with the semantic meaning of the tag (structure of the text), not the *presentational*. That is CSS job.


### Empty HTML Elements

Some elements are "empty" or "self closing", such as line breaks and horizontal rules.

HTML Condensed consecutive spaces, tabs, or new lines as a **single space**. 

`<br/>`:  This adds a hard line break

`<hr/>`: This adds a horizontal rule, represents a thematic brak. By default it renders as a straight horizontal line.

### Images and Links
Webpages: [links](./links-and-images/images.html), [images](./links-and-images/images.html) and [extras](./links-and-images/misc/extras.html)
These elements deal with *external resources*.

- Links point the use to a different HTML document.
- Images pull another resource into the page.

`<a>`: These are called anchors. This element is used to create a link.

HTML elements have attributes, and the attribute that refers to the link that an anchor has is the `href`. 

The syntax to add an href to an anchor is: 

```html
<a href="page.html">Link</a>
```

> Reminder: content goes between the tags, attributes go inside the opening tag.

<h4>Links</h4>

There are three types of links:

- Absolute links: the most detailed way to refer to a web resource.
    * The "syntax" is: "scheme" + "domain" + "path"
    * Example: https://developer.mozilla.org/EN-US/docs/web/html

- Relative links: refers to another file from the point of the file one is editing. The only thing one need to supply is the "path".

- Root Relative links: insted of being relative to the *current page* they are relative to the *root* of the entire website. 
    * syntax: `<a href="/">Home page</a>`
    * The `/` represents the root of the webpage.

Another attribute for anchors is the `target`. This attribute defines *where* to display the page when the user clicks it (in the same page or in a new windows/tab).

The attributes are separeated by a space only.

```html
<a  href="https://developer.mozilla.org/EN-US/docs/web/html"
    target="_blank"> Mozilla Developer Network
</a>
```

<h4> Images </h4>

They use the same way of linking as explained before and the element that cotains them is `<img/>`. The attribute that points to file is `src`.

> Observation: it is an empty element.

The syntax is 

```html
<img src="some-phot.jpg"/>
```

The supported formats are:

- jpg: used to handle large color palettes without big file size. They don't allow for transparent pixels.
- gif: used for simple animations, not good for large color palettes. Transparent pixels are binary (no opacity option).
- png: good for icons, technical diagrams, logos, etc. They allow transparent pixels and opacity.
- svg: they are a vector-based graphics format. They can be scaled to *any* dimension without loss of quality.

`<width>` is the attribute to edit the image size. The syntax is:

```html
<img src="some-photo.jpg"
     width="75"/>
```

The width is specified in pixels.

`<height>` is another attribute to edit the image size.

Nevertheless, it is usually better to set image dimensions with CSS.

`<alt>` is an attribute that defines the alternative text to the image that sould be displayed.

### Reserverd Characters
[Entities](https://html.spec.whatwg.org/multipage/named-characters.html)

For example `<>`, or &, are reserver characters and in order to display them we need to use Entities.

Entities examples: `&amp; &lt; &gt;`.

Entities begin with ampersand and end with semicolon.

### Quotes
There are four different kinds of curly quotes:

- `&ldquo;`: left double quote
- `&rdquo;`: right double quote
- `&lsquo;`: left single quote
- `&rsquo;`: right single quote
