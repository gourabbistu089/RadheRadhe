# Comprehensive JavaScript Guide

## Table of Contents
1. [Variables and Data Types](#variables-and-data-types)
2. [Functions](#functions)
3. [Arrays and Array Methods](#arrays-and-array-methods)
4. [Objects](#objects)
5. [ES6+ Features](#es6-features)
6. [Asynchronous JavaScript](#asynchronous-javascript)

## Variables and Data Types

### Declaring Variables

JavaScript has three ways to declare variables:

```javascript
var x = 5;       // Function-scoped (older, less recommended)
let y = 10;      // Block-scoped (preferred for mutable variables)
const z = 15;    // Block-scoped, constant (preferred when value won't change)
```

### Data Types

JavaScript has the following primitive data types:

- Number: `let num = 42;`
- String: `let str = "Hello";`
- Boolean: `let bool = true;`
- Undefined: `let undef;`
- Null: `let empty = null;`
- Symbol: `let sym = Symbol("unique");`
- BigInt: `let bigNum = 1234567890123456789012345678901234567890n;`

And one complex data type:

- Object: `let obj = {key: "value"};`

## Functions

### Function Declaration

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
```

### Function Expression

```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
};
```

### Arrow Function

```javascript
const greet = (name) => `Hello, ${name}!`;
```

## Arrays and Array Methods

### Creating Arrays

```javascript
let fruits = ["apple", "banana", "orange"];
```

### Array Methods

#### forEach

```javascript
fruits.forEach((fruit) => console.log(fruit));
```

#### map

```javascript
let uppercaseFruits = fruits.map((fruit) => fruit.toUpperCase());
```

#### filter

```javascript
let longFruits = fruits.filter((fruit) => fruit.length > 5);
```

#### reduce

```javascript
let numbers = [1, 2, 3, 4, 5];
let sum = numbers.reduce((acc, curr) => acc + curr, 0);
```

#### find

```javascript
let foundFruit = fruits.find((fruit) => fruit === "banana");
```

#### some

```javascript
let hasLongFruit = fruits.some((fruit) => fruit.length > 6);
```

#### every

```javascript
let allShortFruits = fruits.every((fruit) => fruit.length < 10);
```

## Objects

### Creating Objects

```javascript
let person = {
    name: "John",
    age: 30,
    greet: function() {
        return `Hello, my name is ${this.name}`;
    }
};
```

### Accessing Object Properties

```javascript
console.log(person.name);        // Dot notation
console.log(person["age"]);      // Bracket notation
```

### Object Methods

```javascript
console.log(person.greet());
```

## ES6+ Features

### Template Literals

```javascript
let name = "Alice";
console.log(`Hello, ${name}!`);
```

### Destructuring

```javascript
let {name, age} = person;
let [first, second] = fruits;
```

### Spread Operator

```javascript
let newFruits = [...fruits, "grape"];
let newPerson = {...person, job: "developer"};
```

### Default Parameters

```javascript
function greet(name = "Guest") {
    return `Hello, ${name}!`;
}
```

### Rest Parameters

```javascript
function sum(...numbers) {
    return numbers.reduce((acc, curr) => acc + curr, 0);
}
```

### Object Property Shorthand

```javascript
let name = "John";
let age = 30;
let person = {name, age};
```

### Optional Chaining

```javascript
let city = person.address?.city;
```

### Nullish Coalescing Operator

```javascript
let displayName = person.name ?? "Anonymous";
```

## Asynchronous JavaScript

### Promises

```javascript
function fetchData() {
    return new Promise((resolve, reject) => {
        // Simulating an API call
        setTimeout(() => {
            resolve("Data fetched successfully");
        }, 2000);
    });
}

fetchData()
    .then(data => console.log(data))
    .catch(error => console.error(error));
```

### Async/Await

```javascript
async function getData() {
    try {
        let data = await fetchData();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}

getData();
```

This guide covers the core concepts of modern JavaScript. For more advanced topics or specific use cases, refer to the official MDN Web Docs or other comprehensive JavaScript resources.
