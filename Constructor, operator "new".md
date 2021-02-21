## [Tasks](https://javascript.info/constructor-new#tasks)

### [Two functions – one object](https://javascript.info/constructor-new#two-functions--one-object)

[](https://javascript.info/task/two-functions-one-object)

importance: 2

Is it possible to create functions  `A`  and  `B`  such as  `new A()==new B()`?

`function A() { ... }
function B() { ... }

let a = new A;
let b = new B;

alert( a == b ); // true`

If it is, then provide an example of their code.

solution

### [Create new Calculator](https://javascript.info/constructor-new#create-new-calculator)

[](https://javascript.info/task/calculator-constructor)

importance: 5

Create a constructor function  `Calculator`  that creates objects with 3 methods:

-   `read()`  asks for two values using  `prompt`  and remembers them in object properties.
-   `sum()`  returns the sum of these properties.
-   `mul()`  returns the multiplication product of these properties.

For instance:

`let calculator = new Calculator();
calculator.read();

alert( "Sum=" + calculator.sum() );
alert( "Mul=" + calculator.mul() );`

[Run the demo](https://javascript.info/constructor-new#)

[Open a sandbox with tests.](https://plnkr.co/edit/Fno25vMDXjQGEJuY?p=preview)

solution
```js
function Calculator(){
    
    this.num1;
    this.num2;

    this.sum = function(){
        return +this.num1 + +this.num2;
    }
    
    this.read = function(){
        this.num1 = prompt("num1");
        this.num2 = prompt("num2");
    }
    
    this.mul = function(){
        return +this.num1 * +this.num2;
}
}
```

---

### [Create new Accumulator](https://javascript.info/constructor-new#create-new-accumulator)

[](https://javascript.info/task/accumulator)

importance: 5

Create a constructor function  `Accumulator(startingValue)`.

Object that it creates should:

-   Store the “current value” in the property  `value`. The starting value is set to the argument of the constructor  `startingValue`.
-   The  `read()`  method should use  `prompt`  to read a new number and add it to  `value`.

In other words, the  `value`  property is the sum of all user-entered values with the initial value  `startingValue`.

Here’s the demo of the code:

`let accumulator = new Accumulator(1); // initial value 1

accumulator.read(); // adds the user-entered value
accumulator.read(); // adds the user-entered value

alert(accumulator.value); // shows the sum of these values`

[Run the demo](https://javascript.info/constructor-new#)

[Open a sandbox with tests.](https://plnkr.co/edit/uuDv6NABOHIU6hgU?p=preview)

solution

```js
function Accumulator(val){
  this.value = val;
  
  this.read = function(){
    this.value += +prompt("value: ");
  };
}

```
