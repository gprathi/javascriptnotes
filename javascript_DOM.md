## DOCUMENT OBJECT MODEL

It is tree model representing nodes as objects

### Create Elements

All styles are accesses with style property

```javascript
const p = document.createElement('p');
p.innerText = 'Hello world';
document.body.append(p);

document.body.style.background = 'palegoldenrod';
p.style.color = '#05f';
```
### Get Elements

GetElementbyId
```
const el = document.getElementById('home')
console.log(el)
```

querySelectorAll('a'), querySelector('a')
```
links.forEach(link => {
  console.log(link);  
})
```

```
links.forEach(link => {
  link.matches('a[href="/login"]') 
    const loginLink = link;
    console.log(loginLink);  
   }
)

```



### Modify/Create DOM Elements

```
const newPost = document.createElement('div');
newPost.className = 'top-post';
newPost.innerHTML = "<strong>This is a new post</strong>"

// document.body.prepend(newPost);
const post = document.querySelector('.post');

post.prepend(newPost);
```

### Challenge

```javascript
// Challenge: 
// 1. Update text in the Scrimba mini-browser to match the title of this cast
// 2. Create an h2 with class 'tagline' and text "I can create HTML elements!"
// Add it right under the modified text.

const element = document.querySelector('h1');
element.innerText = "Challenge: Creating and Modifying HTML Elements";

const h2 = document.createElement('h2');
h2.className = 'tagline'
h2.innerText = 'I can create HTML element'

document.body.append(h2); // or
title.append(h2);
```

### CSS properties Javascript

```
const post = document.querySelector(".post");
post.style.backgroundColor = 'orange';

console.log(post.classname);
post.classList.remove('post')
post.classList.add('post')
post.classList.toggle('toggle')
```


### Events

```javascript
posts.forEach(post => {  
      post.addEventListener('click', event => {
 console.log(event.target);  
     console.log('Do you want to edit this post?')
  });
 });

document.body.addEventListener('click', event => {
  if (!event.target.closest('.post')) return;
  
  console.log('Do you want to edit this post?')  
})
```

Other events: MouseEver, keyup, keydown

### Challenge

```
// Challenge: 
// 1. Select h1 and add a click event listener. 
// Log the text from the element to the console.

// If you're not sure how to get text, feel free to check out hint.js

// 2. Add the same functionality to all the elements displayed
// in Scrimba web browser. Finally, try to trigger the event when you
// hover the mouse over the elements, instead of when clicking on them
  
 const h1 = document.querySelector('h1');
 h1.addEventListener('click', (event) => console.log(h1.innerText))
 h1.addEventListener('mouseover', (event) => console.log(h1.innerText))
 
  const h2 = document.querySelector('h2');
 h2.addEventListener('click', (event) => console.log(h2.innerText))
  h2.addEventListener('mouseover', (event) => console.log(h2.innerText))
 
  const h3 = document.querySelector('h3');
 h3.addEventListener('click', (event) => console.log(h3.innerText))
  h3.addEventListener('mouseover', (event) => console.log(h3.innerText))
  ```