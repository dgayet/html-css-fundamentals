# Advanced Positioning
The are four types of positioning: `css`, `relative`, `absolute` and `fixed`.

> The vast majority of elements on a web page should be laid out according to the static flow of the page. These other positioning schemes come into play when you want to do more advanced things like tweak the position of a particular element or animate a UI component without messing up the surrounding elements.

## Positioned Elements

The CSS `position` property handles the positioning scheme of a particular element. Its default value is `static`. If it doesn't have this value, it is refered to as a *positioned element*.

### Relative Positioning

Relative positioning moves elements around *relative* to where they would normally appear in the static flow of the page.

> This is useful for nudging boxes around when the default flow is just a little bit off.

The syntax is the following:

```css
.item {
    position: relative;
    top: 30px;
    left: 30px;
}
```

The difference between margins and relative positioning is that neither the surrounding elements or parent element are affected by this.

### Absolute Positioning

In this case, the offset is relative to the entire browser window instead. The property has to be set to `absolute`. 

Unlike relative positioning, the parents and surrounding elements behave as if the element didn't exist.

### (Relatively) Absolute Positioning

Elements can be positioned relative to another *static* element. This can be done by changing the *coordinate system* of an absolutely positioned element.

> Coordinates for absolute elements are always relative to the closest container that is a positioned element. It only falls back to being relative to the browser when none of its ancestors are positioned.

So, if the parent container's position is set to `relative` and the child is set to `absolute`, the child element will be positioned relative to the parent container. However, there isn't any specified offset for the parent container because the purpose is to hook the child to the parent.

### Fixed Positioning

In this case, the element is also remeved from the normal flow of the page, and the coordinate system is relative to the entire browser window. 

The difference is that fixed elements *don't scroll* with the rest of the page.


### Positioned Elements for Animations

These advanced positioning schemes allow JavaScript to move elements around while avoiding any kind of interaction with surrounding elements.

### Positioned Elements for Menus



