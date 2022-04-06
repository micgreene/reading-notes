# ES6 Syntax and Feature Overview

## Variables and constant feature comparison
+ I explain the concepts of scope and the differences between let, var, and const in the Understanding Variables, Scope, and Hoisting in JavaScript:

+ **Keyword	/ Scope	    /      Hoisting	/Can Be Reassigned	 /  Can Be Redeclared**
+ var	 /   Function scope/	Yes	  /    Yes	       /          Yes
+ let	 /   Block scope	 /   No	  /    Yes	       /          No
+ const/	  Block scope	 /   No	  /    No	         /        No

## Arrow functions
**The arrow function expression syntax is a shorter way of creating a function expression. Arrow functions do not have their own this, do not have prototypes, cannot be used for constructors, and should not be used as object methods.**

+ **ES5**
  + function func(a, b, c) {} // function declaration
  + var func = function (a, b, c) {} // function expression

+ **ES6**
  + let func = (a) => {} // parentheses optional with one parameter
  + let func = (a, b, c) => {} // parentheses required with multiple parameters

## Spread syntax
**Spread syntax can be used to expand an array.**

+ **ES6**
  + let arr1 = [1, 2, 3]
  + let arr2 = ['a', 'b', 'c']
  + let arr3 = [...arr1, ...arr2]

## Classes/constructor functions
**ES6 introducess the class syntax on top of the prototype-based constructor function.**

+ **ES6**
<code>class Func {
  constructor(a, b) {
    this.a = a
    this.b = b
  }

  getSum() {
    return this.a + this.b
  }
}

let x = new Func(3, 4)
x.getSum() // returns 7</code>
