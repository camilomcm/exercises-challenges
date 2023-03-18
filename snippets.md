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
[**JS regular expressions: exercises and practice**](https://www.w3resource.com/javascript-exercises/javascript-regexp-exercises.php)

## 1.
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
## 2.
```js
function cardNumber(number) {
  let regEx = /^\d{4}\s\d{4}\s\d{4}\s\d{4}$/; // Standard format → 1234 5678 9123 4567
  if(number !== '') {
    if(regEx.test(number)) {
      console.log('Valid credit card number');
    } else {
      console.log('Invalid credit card number');
    } 
  } else {
    console.log('There is no number');
  }
};
```
---
**LeetCode** - [Two Sum](https://leetcode.com/problems/two-sum/)

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    let resultArr = [];
    var result = nums.reduce( 
    (acc, v, i) => acc.concat(
        nums.slice(i+1).map( w => [v,w])),
    []);
    
    for(let i = 0; i < result.length; i++) {
        if(result[i].reduce((a,b) => a+b) === target) {
            let [c,d] = result[i];
            if(c === d) {
                c = nums.indexOf(c); 
                d = nums.indexOf(d)+1;    
            } else {
                c = nums.indexOf(c); 
                d = nums.indexOf(d);
            }
            resultArr.push(c);
            resultArr.push(d);
            return resultArr;  
        };
    };   
};

twoSum([1],7);
```
---
**freeCodeCamp** - [Spinal Tap Case](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/spinal-tap-case)

```js
function spinalCase(str) {
  return(str.split(/(?=[A-Z])|[\W_]/).join('-').toLowerCase())
}

spinalCase('thisIsSpinalTap');
```
---
**freeCodeCamp** - [Pig Latin](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/pig-latin)

```js
function translatePigLatin(str) {
  if(str.match(/^[^aeiou]+/)) {
    const consonantCluster = str.match(/^[^aeiou]+/)[0];
    return str.slice(consonantCluster.length)+consonantCluster+'ay';
  } else if(str.match(/^[aeiou]+/i)) {
    return str+'way';
  }
}

translatePigLatin("consonant");
```
---
**freeCodeCamp** - [Sum All Odd Fibonacci Numbers](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/sum-all-odd-fibonacci-numbers)

```js
function sumFibs(num) {
  const sol = [0,1];
  for(let i = 2;i <= num;i++) {
     sol[i] = sol[i-1] + sol[i-2]; 
  }

  let list = sol.filter(x => x <= num && x % 2 !== 0);
  return list.reduce((x,acc) => x + acc,0);
}

sumFibs(1000);
```
---
**freeCodeCamp** - [Sum All Odd Fibonacci Numbers](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/sum-all-odd-fibonacci-numbers)

```js
function sumFibs(num) {
  const sol = [0,1];
  for(let i = 2;i <= num;i++) {
     sol[i] = sol[i-1] + sol[i-2]; 
  }

  let list = sol.filter(x => x <= num && x % 2 !== 0);
  return list.reduce((x,acc) => x + acc,0);
}

sumFibs(1000);
```
---
**freeCodeCamp** - [Sum All Odd Fibonacci Numbers](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/sum-all-odd-fibonacci-numbers)

```js
function smallestCommons(arr) {
  let max = Math.max(...arr);
  let min = Math.min(...arr);
  let range = [];
  for(min;min <= max;min++) {
    range.push(min);
  }
  
  const lowestCommon = currentValue => n%currentValue === 0;
  let common = false;
  let n = max * (max-1);

  common = range.every(lowestCommon);

  while(common === false) {
    n++;
    common = range.every(lowestCommon);
  }
  return n
}

smallestCommons([1,5]);
```
---
**freeCodeCamp** - [Steamroller](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/steamroller)

```js
function steamrollArray(arr) {
  let temp = arr.toString().split(',');
  let result = temp.filter(x => x !== '').map(x => x === '[object Object]' ? {} : x).map(x => !Number(x) ? x : Number(x));
  return (result);
}

steamrollArray([[["a"]], [["b"]]]);
```