# Solutions to excersises and challenges

## freeCodeCamp
[Use class Syntax to Define a Constructor Function](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/use-class-syntax-to-define-a-constructor-function)

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