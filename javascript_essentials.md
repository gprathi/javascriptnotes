# ESSENTIAL CONCEPTS

# Modules

```html
<script src="index.js" type="**module**"></script>
```

// Challenge:
// Often in development you can reuse someone else's code. 
// In this challenge we have a fake function that imitates getting user's 
// data from an API and return you some details.  
// Use modules to import getUser function and display the data on screen.

// Don't forget to call new App() in the end.

// Challenge stub code:

## Coding Challenge

```javascript

 

import getUserData from './utils/getUser'

class App {
  constructor() {
    this.render();
  } 
  
  render() {
    const userDetails = getUserData()
    console.log(userDetails)
    document.getElementById('root').innerHTML = `
      <div> ${userDetails.name} works in ${userDetails.company}  /div>
    `
  }
}

new App()

```
getUser.js
```
export default function getUser() {
  return {
    name: "Clementine Bauch", 
    company: "Romaguera-Jacobson"
  }
}

```

# THIS KEYWORD

4 Rules to 'this'. How is it called?

1) in the global context( global object, undefined in strict mode)
2) as a method on an object( object on left side of dot)
3) as a constructor function or class constructor( the instance itself with new)
4) as a DOM event handler( the element itself)


## State and State Management

State is data to be managed in application. ( Form, data from interacting with app)

```javascript
// state - data to be managed in app
// state -> status

class App {
  constructor() {
    this.state = {
       isAuth: false,
       error: ''  
    };  
      
    this.checkAuth();
    this.render();
    // this.$userMessage = document.getElementById("user-message");
  }

  checkAuth() {
    const user = false;
    if (user) {
      this.state = { ...this.state, isAuth: true };
    //   this.$userMessage.textContent = "Welcome back!";
    } else {
      this.state = { ...this.state, error: "You must sign in!" };
    //   this.$userMessage.textContent = "You must sign in!";
    //   this.$userMessage.style.color = "red";
    }
  }

  render() {
    const { isAuth, error } = this.state; 
      
    document.getElementById("root").innerHTML = `
      <div style="color: ${error && 'red'}">
        ${isAuth ? 'Welcome back!' : error}
      </div>
    `;
  }
}

new App();
```

# REDUCER

```
function counterReducer(count, action) {
  switch (action.type) {
    case 'INCREMENT':
      return count + 1;  
    case 'DECREMENT':  
      return count - 1;
    default:
      return count;
  }  
}

counterReducer(0, { type: 'INCREMENT' }); // 1
const result = counterReducer(1, { type: 'DECREMENT' }); // 0
console.log(result === 0);
```

```
const initialUser = {
  name: 'Mark',
  email: 'mark@gmail.com'  
};

function userReducer(state, action) {
  switch (action.type) {
     case "CHANGE_NAME":
       return { ...state, name: action.payload.name };
     case "CHANGE_EMAIL":
       return { ...state, email: action.payload.email };
     default:
       return state; 
  }  
}

const result = userReducer(initialUser, { type: 'CHANGE_EMAIL', payload: { email: 'mark@compuserve.com' } });
console.log(result.email === 'mark@compuserve.com');
```


## DECLARATIVE CODE

```javascript
const people = ['Doug', 'Fred', 'Jane'];
// const invitations = [];

// for (let i = 0; i < people.length; i++) {
//     invitations[i] = `Hi ${people[i]}, come to my party!`;
// }

const invitations = people.map(person => `Hi ${person}, come to my party!`);

console.log(invitations);
```
