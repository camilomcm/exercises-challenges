# Solutions to excersises and challenges

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