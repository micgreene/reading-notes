# **Reading Assignment 6 - Authentication**

  ## Explain what a “Singleton” is (in Computer Science terms)
   + A singleton is a class that is only meant to have one instance of itself with access to its properties. It contains a list of properties that can be assigned or accessed.
   + It is helpful for data control since only one may exist at any time.

  ## Explain how the Singleton pattern can be used with Node modules, specifically with classes
   = We can use a singleton to access the info from a class multiple time without ever re-instantiating it. By looking for an instance of itself in its constructor, we can ensure memory isn't clogged up with multiple copies of the same class.

  ## If you were tasked with building a middleware system like Express uses, what approach might you take to construct/operate it?
   1. map out the WRRC process with all the methods that will fire off in my app each step of the way. 
   2. classify each method into its CRUD function. 
   3. identify where in the process I would want my middleware to fire and in what order. 
   4. each piece of middleware would be created in a modular fashion for easy modeling. 
   5. create a large model to outline the process before I began to code. 

  ## What’s the primary difference between ES6 Classes and Constructor/Prototype Classes?
  + Ref: https://medium.com/javascript-scene/master-the-javascript-interview-what-s-the-difference-between-class-prototypal-inheritance-e4cd0a7562e9
    + Classes are like blueprints, basically models for an object to eventually be created from. Prototypes are working object instances already created that inherit from other objects.

  ## Why REST?
  + Ref: https://stackoverflow.com/questions/671118/what-exactly-is-restful-programming#:~:text=REST%20stands%20for%20Representational%20State,sometimes%20spelled%20%22ReST%22.)&text=RESTful%20applications%20use%20HTTP%20requests,%2FUpdate%2FDelete)%20operations.
    + **ReST (Representational State Transfer)** is used because all four CRUD actions can be performed using simple HTTP calls. The internet itself uses a ReST based architecture.

  ## Document the following Vocabulary Terms

   + **Router Middleware**
    + middleware alters objects that are sent in the request or the response of a WRRC before the request/response is complete.

   + **Dynamic Module Loading**
    + This refers to using modules.export for creating global references.

   + **Singleton Pattern**
    + Refers to creating a single instance of a class in order to keep referencing the same object and prevent further instantiation of anymore of the same class. 

   + **CRUD -> REST Method Matches**
    + Create <---> Post
    + Read <---> Get
    + Update <---> Put
    + Delete <---> Delete 

  ## Define Mock Testing
  
   + This refers to creating a "virtual environment" for testing. Not running your tests through your server, but through an isolated test environment to ensure expected behavior in ReSTful server methods and CRUD methods via the database. 
   + Test files are labeled 'filename.test.js'.
  
