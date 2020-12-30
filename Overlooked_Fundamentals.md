
- [INHERITANCE](#inheritance)

Global scope of CSS is a feature is not a bug.

a) inhertiance
b) specificity
c) cascading

### THE BOX MODEL

```css
.element{
    width: 200px;
    padding: 20px;
    border: 5px solid blue;
    margin: 20 px;
}

//total width = 290px => 200px + 20px + 20px+ 5px + 5px + 20px+ 20px

* {
    box-sizing: border-box;
}

*,
*::before,
*::after{
    box-sizing: border-box;
}

this will give us an accurate width of 200px;( margin is not included in this)

```

#### What happens when we dont set a width?

We don't set widths on block elements normally.


Block level elements stretch to fill the viewport.
a) heading 
b) article
c) 


When we dont set a width, box sizes varies with viewport size.

https://codepen.io/kevinpowell/pen/47b0601cf0b78a0eb035b5de75326fed

### Setting heights

DO NOT SET HEIGHTS..

only set min-height if needed.

## INHERITANCE

 THings related to typography are inhertied
 Nothing related to Layout is inherited

 The following do not inherit

 1.<button>
 2.<input>
 3.<optgroup>
 4.<select>
 5.<textarea>

 ```css
 button,
 input,
 select,
 textarea,
 optgroup{
     font-family: inherit;
 }

 a {
     color: inherit;
 }

 h2,h3,h4{
     font-weight: inherit;
 }
 ```

