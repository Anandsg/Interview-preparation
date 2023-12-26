### Explain the different ways of creating object in javascript? Explain all the 3 ways.

`Object Literal:`
The most straightforward way to create an object is by using an object literal. An object literal is a comma-separated list of key-value pairs enclosed in curly braces {}.

```js
var person = {
  name: "Anand",
  surName: "gadadgin",
  phone: "123456",
  HomeTown: "Blr",
};
```

`Constructor Function:`
A constructor function is a regular function that is used with the `new` keyword to create instances of objects. It initializes properties and methods for the newly created object.

```js
function Person (name, surName, phone) {
    this.name = name;
    this.surName = surName;
    this.phone = phone;
}
var person = new Person ('kiran', 'kodli', 123126);
console.log(person)
```

`Object.create() Method:`
The Object.create() method allows you to create a new object with the specified prototype object. It provides a way to create objects based on an existing object, allowing for prototype-based inheritance.

```js
var personPrototype = {
  sayHello: function () {
    console.log("Hello!");
  },
};

var person = Object.create(personPrototype);
person.name = "Anand";
person.surName = "gadagin";
person.phone = 12323;

console.log(person.name); // Output: Anand
```

### What is the main difference between fat arrow function and normal function?

`Difference1:` arguements objects are not available in arrow functions where as we can use arguements objects in traditional funtions

example normal function :

```js
function add(x, y) {
  console.log(arguments);
  return x + y;
}
add(10, 2); // output will be printed with 2 arguements
```

example arrow function :

```js
const add1 = (x, y) => {
  console.log(arguments);
  return x + y;
};

add1(10, 2); // ReferenceError: arguments is not defined
```

`Difference2:` we can use constructures in normal functions where as we cannot use the contrustures in fat arrow functions

example normal function :

```js
function Car (name) {
    this.brand = name;
}

let carData = new Car('BMW');
console.log(carData) // output we get new object using constructure
```

example arrow function :

```js
const Car = (name) => {
    this.brand = name;
}

let carData = new Car('Audi');
console.log(carData); // TypeError: Car is not a constructor
```

### Can you give an example to explain how "this" works differenetly with fat arrow function and normal function?

Example of normal function:

```js
const laptop= {
    name: 'MacBook',
    price: 80000,
    description: function () {
        return `This is MacBook laptop of price ${this.price}`
    }
}

console.log(laptop.description()); // Output will be - This is MacBook laptop of price `80000`
```

Example of arrow function:

```js
const laptop = {
  name: "MacBook",
  price: 80000,
  description: () => {
    return `This is MacBook laptop of price ${this.price}`;
  },
};

console.log(laptop.description()); // This is MacBook laptop of price `undefined`
```

### What are closures? Explain with an example? (Favourite interview question)

A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, `a closure gives you access to an outer function's scope from an inner function.`

example :

index.html

```js
  <body>
    <button id="orange">Orange</button>
    <button id="green">Green</button>
    <script src="index.js"></script>
  </body>
```

index.js

```
// This is not a good way so here is where closure comes into picture
document.getElementById("orange").onclick = function () {
document.body.style.backgroundColor = `orange`;
};

document.getElementById("green").onclick = function () {
document.body.style.backgroundColor = `green`;
};
```

```
// using closure

function clickHandler(color) {
return function () {
  document.body.style.backgroundColor = `${color}`;
};
}

document.getElementById("orange").onclick = clickHandler("orange");
document.getElementById("green").onclick = clickHandler("green");
```
