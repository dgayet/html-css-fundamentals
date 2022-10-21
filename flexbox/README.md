# Flexible Box
[Documentation]()
[Example](styles.css)
[Web page](flexbox.html)

## Introduction

The FlexBox layout mode offers *complete* control over the alignment, direction, order and size of the boxes. Flexbox was invented to break out of the limitations of floats.

> Pretty much the only reasons to use floats is when the text will go around a box, or when support for legacy web browsers is needed.

Flexbox uses two types of boxes: `flex containers` and `flex items`. The `flex container` groups a bunch of `flex item` together and define how they're positioned. 

Every HTML element that's a direct cihld of a flex container is an `item`. Even though the items can be handled individually, usually the container determines its style.

> The main purpose of flex items are to let their container know how *many* things it needs to position.

Every box/element has to have a box container, for example:
 - a `<div class=grid>` should have a `<div class=grid-container>`
 - an image `<img src='item.png'>` should have `<div class=item-container>`

## Flex Containers

To make a container of type `flex`, the property `display` of the HTML element has to be set to `flex`. Everything in the box now is rendered with flexbox instead of the default box model.

### Aligning and Distributing Flex Items

The property to change horizontal alignment is `justify-content`. It can be set to `center`, `flex-start`, `flex-end`, `space-around` or `space-between`.

The property is added to the *parent* element (the container) instead of the element to center (the item). 

> Usually the items are manipulated through the container that holds them.

### Grouping Flex Items

Flex containers only know how to position elements that are *one* level deep. Flex items can be grouped in order to be treated by their parent as a single item. 

The way to group items is simply wrapping the items in a `<div>` container.

### Cross-Axis (Vertical) Alignment

Flex containers can also define the vertical alignment of their items. The property is called `align-items` and it can be set to `center`, `flex-start`, `flex-end`, `stretch` and `baseline`. Most of them are pretty straightforward. 


In order for this property to have effect on an element, the container has to have the height *explicitly defined*, otherwise there won't be space to align.


> When the property is set to `stretch`, the box for each item extends the full height of the flex container, regardless of how much content it contains.


### Wrapping Flex Items

The `flex-wrap` property forces items that don't fit to get bumped down to the next row.

The syntax is: `flex-wrap: wrap;`.

### Flex Container Direction

The container can render its items horizontally or vertically. The fault direction is horizontal but it can be changed to vertically with the property `flex-direction` if it is set to `column`.

<h4> Alignment Considerations </h4>

when the direction of a container is rotated, it *also* is the `justify-content` property. Once it is rotated, the `justify-content` refers to vertical alignment, and `align-items` refers to the horizontal one.


### Flex Container Order
The `flex-direction` property also gives control over the order in which items appear via the `row-reverse` and `column-reverse` properties. Setting the property to any of those values will make the items render in reverse order (per-row).

## Flex Items
There's also possible to manipulate individual items.

### Flex Item Order
Adding an `order` property to a flex item defines its order in the container without affecting surrounding items. Its default value is `0`, and increasing or decreasing it from there moves the item to the right or left, respectively.

This is applied globally to the container, it's not row-wise.

### Flex Item Alignment

The same thing goes for vertical alignment on items of a container.

The property to do this is `align-self`, and it overrides the `align-items` value. The values it can take are the same as the `align-item` ones.

### Flexible Items

Flex items can shrink or stretch to match the width of their containers.

The `flex` property defines the width of the items in a flex container. It tells the flex container how to distribute extra space to each item.

- For example, an item with a `flex` value of `2` wil grow twice as fast as items with the default value of `1`.

- Setting the property to `initial` gives the item its explicit `width property`.

### Flex Items and Auto-Margins

Auto-margins in flexbox can be used as an alternative to an extra `<div>` when trying to align a group of items to the left/right of a container. Auto-margins eat up all the extra space in a flex container.

