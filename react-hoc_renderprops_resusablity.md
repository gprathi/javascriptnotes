# React Reusablity


## React Children vs props


### children
```
function Callout(){
    return(
        <div className="border">
        {children}
        </div>
    )

}

export default function App(){
return(
    <div>
    <Callout>
        <input type="text" placeholder="Enter Email">
        <button>Sign me up</button>
    </Callout>

}
</div>
)

```
### props

```
function EmailCallout(props){
    return(
        <div className="border">
                <input type="text" placeholder={props.placeholder}>
                <button>{props.btnText}</button>
        </div>
    )

}

export default function App(){
return(
    <div>
    <EmailCallout btnText="" placeholder="Enter Email" >

    

}
</div>
)

```


## Higher Order Components

```
import React from "react"
import ReactDOM from "react-dom"




function withExtraPropAdded(Component) {

    return function(props) {
        return (
            <Component anotherProp="Blah blah blah" {...props} />
        )
    }
}

function App(props) {
    console.log(props.anotherProp)
    return (
        <div>Hello world!</div>
    )
}

const ExtraPropComponent = withExtraPropAdded(App)
export default ExtraPropComponent

ReactDOM.render(<App />, document.getElementById("root"))

```