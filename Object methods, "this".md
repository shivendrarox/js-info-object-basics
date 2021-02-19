## [Tasks](https://javascript.info/object-methods#tasks)

### [Using "this" in object literal](https://javascript.info/object-methods#using-this-in-object-literal)

[](https://javascript.info/task/object-property-this)

importance: 5

Here the function  `makeUser`  returns an object.

What is the result of accessing its  `ref`? Why?

`function makeUser() {
  return {
    name: "John",
    ref: this
  };
}

let user = makeUser();

alert( user.ref.name ); // What's the result?
`

**solution**

```javascript

```
---
### [Create a calculator](https://javascript.info/object-methods#create-a-calculator)

[](https://javascript.info/task/calculator)

importance: 5

Create an object  `calculator`  with three methods:

-   `read()`  prompts for two values and saves them as object properties.
-   `sum()`  returns the sum of saved values.
-   `mul()`  multiplies saved values and returns the result.

`let calculator = {
  // ... your code ...
};

calculator.read();
alert( calculator.sum() );
alert( calculator.mul() );`

[Run the demo](https://javascript.info/object-methods#)

[Open a sandbox with tests.](https://plnkr.co/edit/8rDRJ4cWja4gSda3?p=preview)

solution
```javascript
let calculator = {

  

read(){

  

this.a= +prompt("value 1",0);

  

this.b= +prompt("value 2",0);

  

},

  

sum(){

  

return (this.a+this.b);

  

},

  

mul(){

  

return (this.a*this.b);

  

}

  

};
```
---
### [Chaining](https://javascript.info/object-methods#chaining)

[](https://javascript.info/task/chain-calls)

importance: 2

There’s a  `ladder`  object that allows to go up and down:

`let ladder = {
  step: 0,
  up() {
    this.step++;
  },
  down() {
    this.step--;
  },
  showStep: function() { // shows the current step
    alert( this.step );
  }
};`

Now, if we need to make several calls in sequence, can do it like this:

`ladder.up();
ladder.up();
ladder.down();
ladder.showStep(); // 1`

Modify the code of  `up`,  `down`  and  `showStep`  to make the calls chainable, like this:

`ladder.up().up().down().showStep(); // 1`

Such approach is widely used across JavaScript libraries.

[Open a sandbox with tests.](https://plnkr.co/edit/0xLdTTzOOYbWQtqN?p=preview)

solution
```javascript
let ladder = {
  step: 0,
  up() {
    this.step++;
    return this;
  },
  down() {
    this.step--;
        return this;

  },
  showStep: function() { // shows the current step
    alert( this.step );
  }
};
```
