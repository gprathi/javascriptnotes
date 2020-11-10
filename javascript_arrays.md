

## **ARRAY OPERATIONS - PUSH, POP, LENGTH, Check Existence of Element**

```
// Challenge: 
// 1. Create an array - favouriteSongs[] -  and add your 3 favourite songs using push()
// 2. Log out the last song in the array, and make it so that your solution will log out the last one regardless of how many items there are in the array
// 3. Invoke the pop method on your created array. What values do you have left in the array? 

const favouriteSongs = []

favouriteSongs.push('Hotel California','Naa Cheli roja','Johnny Johnny')

console.log(favouriteSongs[favouriteSongs.length -1 ])

favouriteSongs.pop();

for ( const song of favouriteSongs){
    console.log(song);
}

```

## **ARRAY OPERATIONS - Check Existence of Element**
```javascript
const temperatures = [69, 82, 73, 64]; // 0, 1, 2, 3; -1

console.log(temperatures.includes(50));

const temperatures = [
    { degrees: 69, isRecordTemp: false }, 
    { degrees: 82, isRecordTemp: true }, 
    { degrees: 73, isRecordTemp: false }, 
    { degrees: 64, isRecordTemp: false }
];

temperatures.some(temperature => temperature.isRecordTemp === true);

temperatures.every(temperature => temperature.isRecordTemp === true); 

```

## Challenge

```
// Challenge:
// Here's a list of 5 most popular songs on Spotify.
// 1) Check if any song has won a Grammy
// 2) Check if all the songs were streamed for at least 1.5 million times
// Note: the timesStreamed value is already in million

const songs = [
    {song: "Shape of You", timesStreamed: 2.384, wonGrammy: true},
    {song: "One Dance", timesStreamed: 1.791, wonGrammy: false},
    {song: "Rockstar", timesStreamed: 1.781	, wonGrammy: false},
    {song: "Closer", timesStreamed: 1.688, wonGrammy: false},
    {song: "Thinking Out Loud", timesStreamed: 1.461, wonGrammy: true}
]


const wonGrammy = songs.some(song => song.wonGrammy)
console.log(wonGrammy)
const allMegaHits = songs.every(song => song.timesStreamed > 1.5)
console.log(allMegaHits)
```

## ARRAY MAP OPERATAION
It creates a new array object

```javascript
const temperatures = [
  { degrees: 69, isRecordTemp: false },
  { degrees: 82, isRecordTemp: true },
  { degrees: 73, isRecordTemp: false },
  { degrees: 64, isRecordTemp: false }
];

const newTemps = temperatures.map(temperature => 
temperature.degrees > 70 ? { ...temperature, isHigh: true } : temperature 
);
```

## ARRAYS FILTER OPERATION

```javascript
const restaurants = [
  { name: 'Cap City Diner', milesAway: 2.2 },
  { name: 'Chop Shop', milesAway: 4.1 },
  { name: 'Northstar Cafe', milesAway: 0.9 },
  { name: 'City Tavern', milesAway: 0.5 },
  { name: 'Shake Shack', milesAway: 5.3 }
]

const results = restaurants.filter(restaurant => restaurant.name.startsWith('C'))
console.log(results);
```

## ARRAYS FIND OPERATION

```javascript
const restaurants = [
  { name: 'Cap City Diner', milesAway: 2.2 },
  { name: 'Chop Shop', milesAway: 4.1 },
  { name: 'Northstar Cafe', milesAway: 0.9 },
  { name: 'City Tavern', milesAway: 0.5 },
  { name: 'Shake Shack', milesAway: 5.3 }
]

const result = restaurants.find(restaurant => 
  restaurant.name.toLowerCase().includes('north') && restaurant.milesAway < 2
)
console.log(result);
```

## ARRAYS REDUCE OPERATION

```javascript
const menuItems = [
  { item: "Blue Cheese Salad", price: 8 },
  { item: "Spicy Chicken Rigatoni", price: 18 },
  { item: "Ponzu Glazed Salmon", price: 23 },
  { item: "Philly Cheese Steak", price: 13 },
  { item: "Baked Italian Chicken Sub", price: 12 },
  { item: "Pan Seared Ribeye", price: 31 }
];

const total = menuItems.reduce((accumulator,menuItem) => {
    return accumulator + menuItem.price
},0);
console.log(total)


```

## Challenge

```javascript
// Challenge: 
// Use reduce() to sum the weights of all the cars
// Stretch goal: 
// Use reduce to sum the weights of only the electric cars 

const cars = [
  { name: "Toyota", isElectric: false, weight: 1320 },
  { name: "Ford", isElectric: false, weight: 1400 },
  { name: "Volkswagen", isElectric: false, weight: 1370 },
  { name: "Honda", isElectric: false, weight: 1375 },
  { name: "Tesla", isElectric: true, weight: 1750 },
  { name: "BMW", isElectric: true, weight: 1350 },  
];


const sum = cars.reduce((accumulator,car) =>{
    console.log(`
        accumulator: ${accumulator}
        weight: ${car.weight}
        `
    )
    return car.isElectric ? accumulator + car.weight : accumulator
},0 )
console.log(sum)
```

### ARRAY REDUCE used for MAP OPERATION

```javascript
const numbers = [1, 2, 3, 4, 5, 6];

const doubledNumbers = numbers.reduce((acc, num) => {
  acc.push(num * 2);
  return acc;
}, []);
console.log('doubled numbers', doubledNumbers);
console.log('numbers', numbers);

```

```javascript
const numbers = [1, 2, 3, 4, 5, 6];

// const doubledNumbers = numbers.reduce((acc, num) => {
//   acc.push(num * 2);
//   return acc;
// }, []);
// console.log('doubled numbers', doubledNumbers);
// console.log('numbers', numbers);

const newArray = numbers.reduce((acc,number) => {
    if(number > 3){
        acc.push(number)
    }
    return acc
},[])
console.log(newArray)
```

## ARRAY SPREAD OPERATOR

```javascript
const lunchMenuIdeas = ['Harvest Salad', 'Southern Fried Chicken'];
const allMenuIdeas = [...lunchMenuIdeas];
allMenuIdeas.push('Club Sandwich');
console.log(lunchMenuIdeas);
```

```javascript
const breakfastMenuIdeas = ["Buckwheat Pancakes"];
const dinnerMenuIdeas = ["Glazed Salmon", "Meatloaf", "American Cheeseburger"];

const allMenuIdeas = ["Harvest Salad", "Southern Fried Chicken"];

const otherMenuIdeas = [...breakfastMenuIdeas, ...allMenuIdeas];
console.log(otherMenuIdeas);
```

## ARRAYS UPDATE

```
const breakfastMenuIdeas = ["Buckwheat Pancakes"];
const dinnerMenuIdeas = ["Glazed Salmon", "Meatloaf", "American Cheeseburger"];

const allMenuIdeas = [
    ...breakfastMenuIdeas, 
    "Harvest Salad", 
    "Southern Fried Chicken",
    ...dinnerMenuIdeas
];

const saladIndex = allMenuIdeas.findIndex(idea => idea === 'Harvest Salad');

const finalMenuIdeas = [
  ...allMenuIdeas.slice(0, saladIndex),
  "Garden Salad",
  ...allMenuIdeas.slice(saladIndex + 1)
];

console.log(finalMenuIdeas);
```

## ARRAYS REMOVE ITEM

```javascript
const breakfastMenuIdeas = ["Buckwheat Pancakes"];
const dinnerMenuIdeas = ["Glazed Salmon", "Meatloaf", "American Cheeseburger"];

const allMenuIdeas = [
    ...breakfastMenuIdeas, 
    "Harvest Salad", 
    "Southern Fried Chicken",
    ...dinnerMenuIdeas
];

const saladIndex = allMenuIdeas.findIndex(idea => idea === 'Harvest Salad');

const meatloafIndex = allMenuIdeas.findIndex(idea => idea === 'Meatloaf');

const finalMenuIdeas = [
  ...allMenuIdeas.slice(0, meatloafIndex),
  ...allMenuIdeas.slice(meatloafIndex + 1)
]

console.log(finalMenuIdeas);
```

## ARRAY REST operator

```javascript
const finalMenuItems = [
  "American Cheeseburger",
  "Southern Fried Chicken",
  "Glazed Salmon"
];

const [winner, ...losers] = finalMenuItems;

console.log({ winner, losers });
```