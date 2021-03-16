Read: Class 06
Explain what a “Singleton” is (in Computer Science terms)
) A singleton is a class that is only meant to have one instance of itself with access to its properties. It contains a list of properties that can be assigned or accessed. It is helpful for data control since only one may exist at any time.
Explain how the Singleton pattern can be used with Node modules, specifically with classes
) We can use a singleton to access the info from a class multiple time without ever re-instantiating it. By looking for an instance of itself in its constructor, we can ensure memory isn't clogged up with multiple copies of the same class.
If you were tasked with building a middleware system like Express uses, what approach might you take to construct/operate it?
) I believe I would map out the WRRC process with all the methods that will fire off in my app each step of the way. Then, I could classify each method into its CRUD function. Finally, I would identify where in the process I would want my middleware to fire and in what order. Each piece of middleware would be created in a modular fashion  for easy modeling. Then I would create a large model to outline the process before I began to code. 

Document the following Vocabulary Terms
Router Middleware - middleware alters objects that are sent in the request or the response of a WRRC before the request/response is complete.

Dynamic Module Loading - This refers to using modules.export for creating global references.

Singleton Pattern - Refers to creating a single instance of a class in order to keep referencing the same object and prevent further instantiation of anymore of the same class.

 

CRUD -> REST Method Matches

Create <---> Post

Read <---> Get

Update <---> Put 

Delete <---> Delete

 

Mock Testing

This refers to creating a "virtual environment" for testing. Not running your tests through your server, but through an isolated test environment to ensure expected behavior in ReSTful server methods and CRUD methods via the database. Test files are labeled 'filename.test.js'.
