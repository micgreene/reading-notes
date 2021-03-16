# **Reading Assignment 5 - Linked Lists**

  ## Summarize Linked List functionality
  + I have learned that a linked list is similar to a conga line, each element or "Node" in the linked list would represent a person in the conga line.

  + Each Node contains 2 properties:

   + **'value'**: could be any data
   + **'next'**: the next Node in the list   
    + *Example, in a 3 person Conga Line*:
     + 1st Dancer             --> 2nd Dancer             --> 3rd Dancer
     + 1st value: who is this --> 2nd value: who is this --> 3rd value: who is this
     + 1st next: 2nd Dancer   --> 2nd next: 3rd Dancer   --> 3rd next: null (they are at the end of the line)    

  + If this was a linked list it would be the same:
    + *Example, in a 3 person Linked List: [3, 7, 10]*:
     + 1st Node               --> 2nd Node               --> 3rd Node
     + 1st value: 3           --> 2nd value: 7           --> 3rd value: 10
     + 1st next: 7            --> 2nd next: 10           --> 3rd next: null (they are at the tail of the list)
 

The 1st node is always called the 'Head', the last node is always called the 'Tail'.

So far, the above info describes a 'Singly Linked List', meaning there is only a pointer to the next node contained in each node. 

Doubly Linked List

A 'Doubly Linked List' would ALSO contain pointers to the PREVIOUS node in the list:

Example, in a 3 person DOUBLY Linked List: [3, 7, 10]

1st Node                   -->                 2nd Node                   -->                      3rd Node

value: 3                                            value: 7                                                  value: 10

next: 2nd Node                               next: 3rd Node                                     next: null (this is the last node)

previous: null (this is the 1st)         previous: 1st Node                              previous: 2nd Node
    + There is a significant reduction in bgs and defects.
    + The amount of time saved in the final stages of development.
    + The internal quality of the code is overall improved as well as the design quality.

  ## In what case would you need to use beforeEach() or afterEach() in a test suite?
   + **Supertest**
      + https://github.com/visionmedia/supertest
   + **Nock**
      + https://github.com/nock/nock
   + **Mockserver**
      + https://www.npmjs.com/package/mockserver

  ## What is one downside of Test Driven Development
  + Ref: https://www.agilealliance.org/glossary/tdd/
   + Initial development time is increased as a result.

  ## What’s the primary difference between ES6 Classes and Constructor/Prototype Classes?
  + Ref: https://medium.com/javascript-scene/master-the-javascript-interview-what-s-the-difference-between-class-prototypal-inheritance-e4cd0a7562e9
    + Classes are like blueprints, basically models for an object to eventually be created from. Prototypes are working object instances already created that inherit from other objects.

  ## Why REST?
  + Ref: https://stackoverflow.com/questions/671118/what-exactly-is-restful-programming#:~:text=REST%20stands%20for%20Representational%20State,sometimes%20spelled%20%22ReST%22.)&text=RESTful%20applications%20use%20HTTP%20requests,%2FUpdate%2FDelete)%20operations.
    + **ReST (Representational State Transfer)** is used because all four CRUD actions can be performed using simple HTTP calls. The internet itself uses a ReST based architecture.

  ## Document the following Vocabulary Terms
  
   + **functional programming**
     + Ref: https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0
       +  the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects.
    
   + **object-oriented programming (OOP)**
     + Ref: https://en.wikipedia.org/wiki/Object-oriented_programming
       +  a programming paradigm based on the concept of "objects", which can contain data and code: data in the form of fields (often known as attributes or properties), and code, in the form of procedures (often known as methods).
    
   + **class**
     + Ref: https://en.wikipedia.org/wiki/Class_(computer_programming)
       +  an extensible program-code-template for creating objects, providing initial values for state (member variables) and implementations of behavior (member functions or methods).
    
   + **super**
     + Ref: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super
       +  The super keyword is used to access and call functions on an object's parent.
    
   + **this**
     + Ref: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this
       + when referencing an object, 'this' is a reference to all properties of the object itself
    
   + **Test Driven Development (TDD)**
     + Ref: + Ref: https://www.agilealliance.org/glossary/tdd/
       +  the process of building software by creating test cases to be passed instead of code to be tested. used to reduce the amount of bugs and defect in code during development.
    
   + **Jest**
     + Ref: https://jestjs.io/
       +  a JavaScript Testing Framework with a focus on simplicity.
    
   + **Continuous Integration (CI)**
     + Ref: https://www.ericsson.com/en/ci-cd?gclid=Cj0KCQiA4feBBhC9ARIsABp_nbWqhWNKvaYFtai_LjqvQAk1nQ9V6onePkQbgXHAKBb3dgt4IG8BkVEaAtWYEALw_wcB&gclsrc=aw.ds
       +  the continuous provision of all the elements needed to deliver a new release achieved by an automated process of secure and frequent integration of source code into source baselines and binaries into system binaries. essentially, constantly updating a product throughout its lifecycle.
    
   + **REST**
     + Ref: https://stackoverflow.com/questions/671118/what-exactly-is-restful-programming
       +  (Representational State Transfer) uses HTTP to create requests. used for simplicity and flexibility.
    
   + **Data Model**
     + Ref: https://en.wikipedia.org/wiki/Data_modeling
       +  a process used to define and analyze data requirements needed when building the logic for your code.
    

Linked Lists


