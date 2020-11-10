## JAVSCRIPT NOTES -- TYPES AND CONDITIONALS

1.[CONDIITIONAL LOGIC](#conditional-logic--ifelseelse-if)
2.[SWITCH STATEMENT](#caseswicth-statement)
3.[Primitive Types](#primitive-type)
4.[Type Conversion](#type-conversion)
5.[Challenges](#challenges)
6.[Ternary Operator](#ternary-operator)
7.[Short Circuting with || Operator](#or-conditiional-operator)
8.[&& Operator](#-operator)

### **CONDITIONAL LOGIC ( IF/ELSE/ELSE IF)**

```
const time = "night" // could be "afternoon", "evening" and "night"

if (time === "morning") {
    console.log("Good morning!");
} else if (time === "afternoon") {
    console.log("Good afternoon!");
} else if (time === "evening") {
    console.log("Good evening!");
} else {
    console.log("Good night!");
}

```
### **CASE/SWICTH STATEMENT**

```
switch(time){
    case "morning":
        console.log("Good Morning");
        break;
    case "afternoon":
        console.log("Good Afternoon");
        break;
    case "evevning":
        console.log("Good Evening");
        break;
    default:
        console.log("Good Night");
        break;        
}

```

### **Primitive Types**

```
string
number
boolean
undefined
null
symbol

 everything else is Object type

 let message = 'some string';
 console.log(typeof message)
 ```

 ### **Type Conversion**

a) Explicit type conversion
 ```
console.log(String(42))
console.log(Boolean(message))
```
b) Implicit type conversion
```
console.log('11' * '2' ) = 22
console.log('1' + 2) = "22"
 ```
c) TRUTHY OR FALSY 

ALL FALSE VALUES , everything else is true
```
false
0
''
null
undefined
NaN
```

d) TIPS for using truthy/falsy

```
// 1) Avoid direct comparisons in conditionals

const username = null;

if (!username) {
  console.log('no user');
}

// 2) Use triple equals === (strict equals operator) 

if (null == undefined) {
  console.log('equals');
} else {
  console.log('not equals')
}

// 3) Convert to real Boolean values where needed

if (Boolean(NaN) === Boolean(NaN)) {
    console.log('equal')
} else {
    console.log('not equals')
}
```


### **Challenges**

```
// Challenge 1:
// What will the following console logs display? (they're all true and false)

// console.log("Challenge 1:")
// console.log(!undefined); // true
// console.log(Boolean(NaN)); // false
// console.log(false === false); // true
// console.log(5 === "5"); // false
// console.log("Hello" == "hello"); // false

// Challenge 2:
// What will the following console logs display? (they're all true and false)
console.log("Challenge 2:")
console.log(Boolean(0)); // false
console.log(Boolean("0")); // true
console.log(Boolean("")); // false
console.log(!null); // true
console.log(!!"hello"); // true

// Challenge 3:
// List all the falsy values in JavaScript
undefined
NaN
null
0
""
false

```



## **TERNARY OPERATOR**

```
// Challenge 1: Check if the user is allowed to add an "iPad" to its shopping cart. Write a ternary that sets the shoppingCart variable to "iPad" if the user is authenticated, and an empty string if the user isn't authenticated

const isAuthenticated = true;
let shoppingCart;

// write your code here

shoppingCart = isAuthenticated ? "iPad": ""
console.log("shoppingCart: ", shoppingCart);


// Challenge 2: Check if user is old enough. Write a ternary that sets allowedAccess to true if the age is 18 or more, or false if not
const age = 20;
let allowedAccess;

// write your code here

allowedAccess = age > 20 ? true : false
console.log("allowedAccess: ", allowedAccess);
```

## **OR CONDITIIONAL OPERATOR**

```
const response = "Reed";

// let username;

// if (response) {
//   username = response;
// } else {
//   username = "guest";
// }
// const result = 'Reed' || '';
// console.log(result);

const username = response || "guest";

// console.log(username);
```

## **&& OPERATOR**

```
const response = "Reed";
const isEmailVerified = true;

// let username;

// if (response) {
//   if (isEmailVerified) {
//     username = response;
//   }  
// } else {
//   username = "guest";
// }

const username = isEmailVerified && response || "guest";

console.log(username);
```