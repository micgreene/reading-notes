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

+ **ES6**<br />
<code>class Func {<br />
  constructor(a, b) {<br />
    this.a = a<br />
    this.b = b<br />
  }<br />
<br />
  getSum() {<br />
    return this.a + this.b<br />
  }<br />
}<br />
<br />
let x = new Func(3, 4)<br />
x.getSum() // returns 7<br /></code>

## Modules - export/import
**Modules can be created to export and import code between files.**

+ index.html<br />
<code><script src="export.js"></script>
<script type="module" src="import.js"></script>
export.js

let func = (a) => a + a
let obj = {}
let x = 0

export {func, obj, x}
import.js
import {func, obj, x} from './export.js'

console.log(func(3), obj, x)</code>


## Promises/Callbacks
**Promises represent the completion of an asynchronous function. They can be used as an alternative to chaining functions.**


+ **ES6 Callback**
<code>let doSecond = () => {
  console.log('Do second.')
}

let doFirst = new Promise((resolve, reject) => {
  setTimeout(() => {
    console.log('Do first.')

    resolve()
  }, 500)
})

doFirst.then(doSecond)</code>

+ **ES6 Promise**
<code>function makeRequest(method, url) {
  return new Promise((resolve, reject) => {
    let request = new XMLHttpRequest()

    request.open(method, url)
    request.onload = resolve
    request.onerror = reject
    request.send()
  })
}

makeRequest('GET', 'https://url.json')
  .then((event) => {
    console.log(event.target.response)
  })
  .catch((err) => {
    throw new Error(err)
  })</code>
