# JAVASCRIPT CLASSES 

## Constructor Functions
Constructor functinon names start with Capital letter and use new keyword
to instantiate objects

```javascript
function Student(id, name, subjects = []) {
  this.id = id;
  this.name = name;
  this.subjects = subjects;  
}

console.log(new Student(1, 'Reed'));
```

## Prototype functions
```javascript
Student.prototype.addSubject = function(subject) {
  this.subjects = [...this.subjects, subject];   
}

student1.addSubject('Math');
student2.addSubject('Physics');
console.log(student2.subjects);

```

## Prototypical Inheritance with Classes

Classes are constructor functions

```javascript
class Film {
	//Your code here.
	constructor(id,title,director,releaseYear, genres = []){
	  	this.id = id;
		this.title = title;
		this.director = director;
		this.releaseYear = releaseYear;
		this.genres = genres
	}
	addGenre(genre){
		this.genres = [...this.genres, genre]
	}
	getFilmTitle(){
		return this.title
	}
	
}

const film1 = new Film('1','Roja','Mani Ratnam','1993',['Thriller','Romance']);
console.log(film1.getFilmTitle())
film1.addGenre('Mystery')
console.log(film1.genres)
```

## Share Classes with Extends

```javascript
class Product {
  constructor(name, price, discountable) {
    this.name = name;
    this.price = price;
    this.discountable = discountable;  
  }  
  
  isDiscountable() {
    return this.discountable;  
  }
}

class SaleProduct extends Product {
  constructor(name, price, discountable, percentOff) {
     super(name, price, discountable);
     this.percentOff = percentOff; 
  }  
  
  getSalePrice() {
     if (super.isDiscountable()) {
       return this.price * ((100 - this.percentOff) / 100);
     } else {
        return `${this.name} is not eligible for a discount`;
     }
  }
}

const saleProduct1 = new SaleProduct("Coffee Maker", 99, false, 20);
console.log(saleProduct1.getSalePrice());
```

## Getters and Setter

There is no private property Javascript, use _<properyname> to signal other developers not to change the property directly

```javascript
class Product {
  constructor(name, price, discountable) {
    this.name = name;
    this._price = price;
    this.discountable = discountable;
  }

  get price() {
    return this._price;
  }
  
  set price(price) {
    if (typeof price !== "number") {
      return this._price;
    } else {
      this._price = price; 
    }
  }
}

const product1 = new Product("Coffee Maker", 99.95, false);
product1.price = 30;
console.log(product1.price);
```

## Context Problems fix with bind()

```
const isAuth = true;
const user = {
  favorites: []
};

class Product {
  constructor(name, price) {
    this.name = name;
    this.price = price;
  }

  handleFavoriteProduct() {
    if (isAuth) {
      setTimeout(this.favoriteProduct.bind(this), 1000);
    } else {
      console.log("You must be signed in to favorite products!");
    }
  }

  favoriteProduct() {
    user.favorites.push(this.name);
    console.log(`${this.name} favorited!`);
  }
}

const product1 = new Product('Coaster', 89.99)
product1.handleFavoriteProduct()
```