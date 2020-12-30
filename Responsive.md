

### CSS Units

1. Absolute Units -> px, pt, cm, mm, in (etc)
2. Percentage Units -> Percentage ( relative to their parent)( usually width)
3. Relative Units -> 
      a) relative to viewport ( vh , vh, vmin , vmax)
      b) relative to font-size ( rem, em)

#### Percentages
All block level elements have a width of screen size

 div / child element is a percentage of the parent elemnent

 #### Controlling width of an image

 By setting a percentage on img tag, we can control the image size ( no overflow from the div container)

 Images default to the size of the images not the size of the container.

 ### Min and Max Width

 max-width will fix size of the container,so that layout of the texts are not messed up at larger size screens

 #### EM Unit

 font-size is relative to parent,

 you have a cascading size effect, if you set sizes on their parents

 ### REM unit( Root Em)

 always relative to the root of the document.


body{
    font-size : 1rem;
}

#### which Unit to use ??

font-size = rem
padding and margin = em /* padding and margin are relative to the size of the elements */
widths = em or percentage


Example:

```css
h1 {
    font-size: 24px;
    margin-bottom: 1em; /* 24 px */
    margin-bottom: 2em; /* 48px */
}
```

####  Flexbox Refresher

*Block elements* stack on top of each other

1.div, headr,footer, main etc
2. h1 -> h6
3. <p>
4. li

*Inline Elements* stay in the flow with the items around them
1.<a>
2.strong
3. em
4. span

We can change this behavoir of block elements

```css

display: flex;
align-items: flex-start;
justify-contents: space-between;
flex-direction : column /* default is row */

```

#### Media queries

@media (min-width: 400px) and (max-width: 649px) {
    body {
        background: purple;
    }
}

#### Flex- Direction

When we switch the flex-direction to column, the axis is flipped.

align-items will work on horizontal axis and justify-contents will work on vertical axis



