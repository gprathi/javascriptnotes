## CALL BACK HELL

```
navigator.geolocation.getCurrentPosition(position => {
    console.log(position);
    getRestaurants(position, restaurants => {
        console.log(restaurants);
        console.log('done');
    })
});
```

## PROMISES

States
a) Pending
b) Fulfilled
c) Rejected

```
const promise = new Promise((resolve,reject) => {
    setTimeout(() => resolve('done'), 1000);
})

promise
    .then((value) => {console.log(value)})
    .catch((error) => {console.log(value)})
    .finally(() => {})
```


```
const promise = new Promise((resolve, reject) => {
   navigator.geolocation.getCurrentPosition(position => {
    resolve(position); 
  }, error => {
     reject(error);
  }); 
});

promise
  .then(position => console.log(position))
  .catch(error => console.error(error))
  .finally(() => console.log('done'));

```


## FETCH

### GET

fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => 
   {   if (!response.ok) {
        throw new Error(response.status);  
      }} 
    )
  .then( data => console.log(data))
  .catch( error => console.error(error))

### POST

const blogPost = {
  title: "Cool post",
  body: "lkajsdflkjasjlfda",
  userId: 1  
}

fetch('https://jsonplaceholder.typicode.com/posts',
{
  method: "POST",
  headers: {
    "Content-type": "application/json"
  },
  body: JSON.stringify(blogPost)
})
  .then(response => response.json())
  .then( data => console.log(data))


## CHALLENGE

```javascript
fetch('https://jsonplaceholder.typicode.com/users/3')
    .then( response => {
      if(!response.ok){
          throw new Error(response.status)
      } 
      else{
         return response.json()
      } 
    })
    .then( data => console.log(data))
    .catch(error => console.error(error))
```

### ASYNC

```javascript
async function getPost() {
   const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');  
   const data = await response.json();
   console.log(data);
}

getPost()

async function getGithubUser() {
  try {    
    const response = await fetch('https://api.github.com/users/laksjdflasjfdlkjadfjk');
    if (!response.ok) {
      throw new Error(response.status);  
    }
  } catch (error) {
    console.error(error);  
  } 
}
getGithubUser();
```

### Challenge

```javascript
// Challenge: 
// Rewrite the GET API call from the previous challenge using async-await


// Challenge: 
async function getUser(){
  
  try{
 const response = await fetch('https://jsonplaceholder.typicode.com/users/3')
      if (!response.ok) {
        throw new Error(response.status);  
      } 
  const person = await response.json()
  console.log(`${person.name} works for ${person.company.name}`)     
  }
  catch(error){
    console.error(error)
  }
 }

getUser() 
```