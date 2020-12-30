### Virtual DOM

a) What is the difference between Virtual DOM and Real DOM

The KEY difference is "diffing". It figures what changed and updates only that individual parts and not the entire DOM/page.

Shadow DOM is browser specific and is used updating certain HTML elements( e.g. Slider)

#### Real DOM

1.Browsers maintain the real DOM.  
2. Directly updates and manipualates the HTML   
3. Creates a new DOM/full repaint if it is updated   
4. An object based respresentation of HTMl DOcument and the interface for manipulating the object  

#### Virtual DOM

1.Can't direclty update the HTML.  
2.Acts as a copy of the real DOM, which can be frequently manipulated and updated without a page refresh  
3. Virtual DOM is a pattern rather than technology   
4. Sync'ed with real DOM with react-dom   


### React Limitations

1. It is a library and not framework. Next.js and Gatsby.js are full React based frameworks that provide scaffolding,additional functions.
2. It is a large library.
3. maintained by facebook and future roadmap is decided by internal team
4. Documentation is not exhaustive for newer features.
5. Learning curve is high

### JSX

1. Short for Javascript XML
2. Write Javascript with HTML like template syntax
3. Produces elements that represent objects

Element

```
import React from "react'
import React-dom from "react-dom"

const reactElement = <div>Hello<div>
const domElement = document.getElementById('root')

ReactDOM.render( reactElement, document.getElementById("root"))

```

Component

```
import React from "react'
import React-dom from "react-dom"

const Component = () => <div>Hello<div>
const domElement = document.getElementById('root')

ReactDOM.render( <Component />, document.getElementById("root"))

```

React without JSX

```

import React from "react'
import React-dom from "react-dom"

const reactElement = React.createElement( 'div','Hello', null )
const domElement = document.getElementById('root')

ReactDOM.render( reactElement, document.getElementById("root"))

```

### Props

How do you pass a value from parent and Child?

1. Value prop

How do you pass a value from child to parent?

1. Function prop

#### Prop- Drilling

passing props via multipe levels

Can you Modify props?

No. Functions are supposed to be pure components


### State and Lifecycle

State is local to the component. Props are passed to Components when it is instantiated.

State in function component is recalled every time function is called.

State in Class component persists in the object.


Component Lifecycle: componentWillMount,componentDidUpdate, componentWillUnMount

Hooks are used to manage lifecycle in function based componenent( useEffect, useState)


### Effects

When does the Effect run?

useEffect( () => {} return value, [])

[] -> Runs on mount
[variable] -> Runs on mount and when variable changes
No arryay-> runs on mounts and everytime state changes


### Refs

What is the diffrence between Refs and state variables?

Refs have a value that can persist across re-renders,

Changes in state triggers a re-render

#### When is it Used?

1. Managing focus or media
2. Triggering Animations
3. Integration with DOM libraries

What is proper way to update ref in a component?

use Effect

### Conext 

##### What is the difference between Context API and Prop-Drilling?


Context API define some data at top level and all components in the tree have access to the values.

When you use prop-drilling data has to be passed to child components using props.( n levels)

#### When you should n't use Context API?

You should n't overuse to avoid unnecessary re-renders. Only put absolutely necessary at the top level of the Context
everything else can be props or use multiple Context at different levels.

Context API at the top levels are used primarily for authentication,themes shared across the site.


### Miscellanous

#### What is a Fragment?

multiple elements are returned in a function, use a fragment.It avoids having to wrap multiple elements in a div.

#### When should you use function components and class components?

Use function component all the time, Class based components are used for Error boundaries

#### What is a Higher Order Component?

It takes a function that takes a component and returns a new components. It is like decorator pattern in Python.
It helps in reusablilty.

#### What is a portal?

A portal is a way to render children into a DOM node that exits outside of the hierarchy of the parent component.
It can live anywhere in the DOM tree and most often seen in UI components like modals.

#### What are controlled and uncontrolled components?

User has control to DOM elements in controlled elements.
In uncontrolled components, react has the control and decides when the user can control the element.


#### Convert Class based component to function based component


class based component
```
import React, {Component} from "react"
import ReactDOM from "react-dom"

class Counter extends React.Component{
    constructor(props){
        super(props)
        this.state = { count : 0}
    }

    render(){
        return(
            <div>
            <button onClick={() => this.setState( count: this.state.count - 1)}>-<button>
            {this.counter}
            <button onClick={() => this.setState( count: this.state.count + 1)}>+<button>
            </div>
        )
    }
}

const domElement = document.getElementById('root')

ReactDOM.render(<Counter />, domElement)

```


function based component
```
import React, {useState} from 'react'; 
import ReactDOM from 'react-dom';

function Counter()  {
const [count,setCount] = useState(0) 
    return (
      <div>
        <button onClick={() => 
          setCount(count - 1 )
        }>-</button>
        {count}
        <button onClick={() => 
          setCount(count + 1 )
        }
        >+</button>
      </div>
    );
}


const domElement = document.getElementById('root')

ReactDOM.render(<Counter />, domElement)
```

