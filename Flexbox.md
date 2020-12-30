


# Flex Container Properties

### 

1.flex-direction( row or column based formatting)
2.flex-wrap  too much content, stretching the entire screen)
3.justify-contents( horizontal)
4.align-items( vertical)
5.Align-Content ( too much content, multiple rows of content)


```css

display: flex;( turn everything into columns
flex-direction: row:column:row-reverse:column:reverse
flex-wrap: wrap;
flex-flow: row-reverse wrap; // shorthand for direction and wrap
justify-content: space-between:space-around:space-evenly:center
align-items: center:flex-start:flex-end:baseline;
align-content: flex-start:flex:end;center;

```

# Flex Item Properties

1.flex-grow:
2.flex-shrink: 0( never shrinks)
3.flex-basis


```css short
grow shrink basis
flex: 0 1 auto;
flex: 1 1 0;
flex: auto;

```

## Align-self

```
manipulate single items 
align-self: center:flex-start:flex-end;
```

## margin auto and flexbox

There are no collapsing margins.