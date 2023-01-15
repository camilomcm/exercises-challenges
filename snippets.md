# Solutions to excersises and challenges

**freeCodeCamp** - [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)

```js
//This solution doesn't work
function lookUpProfile(name, prop) {
  for(let i = 0; i < contacts.length; i++) {
    if(contacts[i].firstName === name && contacts[i].hasOwnProperty(prop)) {
       return contacts[i][prop];   
    } else if(contacts[i].firstName !== name) {
      return 'No such contact';
    } else if(!contacts[i].hasOwnProperty(prop)) {
      return 'No such property';
    }
  }
}

//This solution works
function lookUpProfile(name, prop) {
  for(let i = 0; i < contacts.length; i++) {
    if(contacts[i].firstName === name) {
      if(contacts[i].hasOwnProperty(prop)) {
        return contacts[i][prop];
      } else {
        return 'No such property'; 
      }   
    }  
  }
  return 'No such contact';
}
```
---
**freeCodeCamp** - [Use class Syntax to Define a Constructor Function](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-class-syntax-to-define-a-constructor-function)

```js
// Only change code below this line
class Vegetable {
  constructor(vegetable) {
    this.vegetable = vegetable;
  }
  get name() {
    return this.vegetable;
  }
}
// Only change code above this line

const carrot = new Vegetable('carrot');
console.log(carrot.name); // Should display 'carrot'
```
 ---

**freeCodeCamp** - [Use getters and setters to Control Access to an Object](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-getters-and-setters-to-control-access-to-an-object)

```js
// Only change code below this line
class Thermostat {
  constructor(FahrenheitTemperature) {
    this.FahrenheitTemperature = FahrenheitTemperature;
  }

  get temperature() {
    return 5/9 * (this.FahrenheitTemperature - 32);
  }

  set temperature(celsius) {
    this.FahrenheitTemperature = celsius * 9/5 + 32;
  }
}
// Only change code above this line

const thermos = new Thermostat(76); // Setting in Fahrenheit scale
let temp = thermos.temperature; // 24.44 in Celsius
thermos.temperature = 26;
temp = thermos.temperature; // 26 in Celsius
```
---
**freeCodeCamp** - [Restrict Possible Usernames](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/restrict-possible-usernames)

```js
let username = "JackOfAllTrades";
let userCheck = /^[a-z][a-z]+\d*$|^[a-z]\d\d+$/i;
let result = userCheck.test(username);
```
---
**freeCodeCamp** - [Check For Mixed Grouping of Characters](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/check-for-mixed-grouping-of-characters)

```js
let myString = "Eleanor Roosevelt";
let myRegex = /(Franklin|Eleanor)\s\D+o{2}\D+/i; 
let result = myRegex.test(myString);
```
---
**freeCodeCamp** - [Remove Whitespace from Start and End](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/remove-whitespace-from-start-and-end)

```js
let hello = "   Hello, World!  ";
let wsRegex = /^(\s+)|(\s+)$/g;
let result = hello.replace(wsRegex,''); 
console.log(hello.match(wsRegex));
console.log(result);
```
---
**JS regular expressions: exercises and practice** - [](https://www.w3resource.com/javascript-exercises/javascript-regexp-exercises.php)
**1.**
```js
function testFirstLetter(word) {
  let regEx = /^[A-Z]/;
  if(word !== '') {
    if(regEx.test(word)) {
      console.log('First letter is uppercase');
    } else {
      console.log('First letter isn\'t uppercase');
    } 
  } else {
    console.log('There is no word');
  }
};
```