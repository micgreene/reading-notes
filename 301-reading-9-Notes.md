# **Reading Assignment 9 - Functional Programming and Refactoring**

1. ## Functional Programming Overview
  + ### Definition
    + **Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.**
    + The first fundamental concept we learn when we want to understand functional programming is pure functions.
      + So how do we know if a function is pure or not? Here is a very strict definition of purity:
        + It returns the same result if given the same arguments (it is also referred as deterministic)
        + It does not cause any observable side effects
        + No External Objects
    + **It does not cause any observable side effects**
      + Examples of observable side effects include modifying a global object or a parameter passed by reference.
      + Now we want to implement a function to receive an integer value and return the value increased by 1.
        + `let counter = 1;`
        + `function increaseCounter(value) {`
        + `counter = value + 1;}`
        + `increaseCounter(counter);`
        + `console.log(counter); // 2`
      + We have the counter value. Our impure function receives that value and re-assigns the counter with the value increased by 1.
      + **Observation: mutability is discouraged in functional programming.**
        + We are modifying the global object. But how would we make it pure? Just return the value increased by 1. Simple as that.
          + `let counter = 1;`
          + `const increaseCounter = (value) => value + 1;`
          + `increaseCounter(counter); // 2`
          + `console.log(counter); // 1`
      
2. ## Functions as first-class entities
  + **The idea of functions as first-class entities is that functions are also treated as values and used as data.**
    + Functions as first-class entities can:
      + - refer to it from constants and variables
      + - pass it as a parameter to other functions
      + - return it as result from other functions
    + `const sum = (a, b) => a + b;`
    + `const subtraction = (a, b) => a - b;`
    + `const doubleOperator = (f, a, b) => f(a, b) * 2;`
    + `doubleOperator(sum, 3, 1); // 8`
    + `doubleOperator(subtraction, 3, 1); // 4`
    + Now we have an f argument, and use it to process a and b. We passed the sum and subtraction functions to compose with the doubleOperator function and create a new behavior.
  + **Declarative approach**
    + We want a more declarative way to solve this problem, and using the filter higher order function as well. A declarative Javascript solution would be something like this:
      + `function smaller(number) {`
      + `return number < this;}`
      + `function filterArray(x, listOfNumbers) {`
        + `return listOfNumbers.filter(smaller, x);}`
      + `let numbers = [10, 9, 8, 2, 7, 5, 1, 3, 0];`
      + `filterArray(3, numbers); // [2, 1, 0]`
