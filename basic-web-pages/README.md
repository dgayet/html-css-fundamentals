# HTML and CSS fundamentals

- [Tutorial followed](internetingishard.com/html-and-css/introduction/)
- [Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML)

## Structure of a web page: HTML Elements
- [Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- First Project: [basic web pages](./basic-web-pages/basics.html)

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
These elements deal with *external resources*.

- Links point the use to a different HTML document.
- Images pull another resource into the page.
