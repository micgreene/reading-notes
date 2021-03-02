# **Reading Assignment 4 - Data Modeling**

  ## Name 3 advantages to Test Driven Development
  + Ref: https://rapidapi.com/blog/put-vs-patch
    + **PUT**
      + An http verb used to completely modify a resource via data sent from a client. This means it will completely replace the entity with the new data sent or create a new one if none exist.
    + **PATCH**
      + An http verb used to partially update a resource via data sent from a client. This means the original data will remain and only the additonal data sent will be appended.

  ## In what case would you need to use beforeEach() or afterEach() in a test suite?
   + **Supertest**
      + https://github.com/visionmedia/supertest
   + **Nock**
      + https://github.com/nock/nock
   + **Mockserver**
      + https://www.npmjs.com/package/mockserver

  ## What is one downside of Test Driven Development
   + **Swagger**
   + https://swagger.io/  
     + Allows user to design and model APIs according to specifications. Builds reusable code for APIs in many languages. Has interactive API documentation. Allows for simple functional tests on APIs. Allows you to set API style guidelines. One of the more popular tools.
   + **APIDoc**
   + https://apidocjs.com/#getting-started  
     + Allows user to design and model APIs as well. Allows for simple functional tests on APIs. I think allows for creation of documentation.

  ## What’s the primary difference between ES6 Classes and Constructor/Prototype Classes?
  + Ref: https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
    + Client errors (400–499)
    + Server errors (500–599)

  ## Why REST?
  + Ref: https://smartbear.com/blog/soap-vs-rest-whats-the-difference
    + Both are Web API Services designed to ensure that programs built on different platforms and programming languages could exchange data in an easy manner.
    + **SOAP (Simple Object Access Protocol)** is older, built on the XML framework and considered by many to be more rigid to work with, working with Javascript means all requests required XML framework.
    + **REST (Representational State Transfer)** is designed to create requests using a URL rather than an XML call. This makes many consider REST a more flexible choice.

  ## Document the following Vocabulary Terms
   + **Web Server**
   + https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server
      + A computer hosting data with an HTTP server. Usually consists of a static web server plus extra software, most commonly an application server and a database. The application server updates the hosted files before sending content to your browser via the HTTP server.
   + **Express**
   + https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction
     + The most popular Node web framework. Express allows us to handle web requests and the templating and rendering of information received by giving us the ability to:
       + Write handlers for requests with different HTTP verbs at different URL paths (routes).
       + Integrate with "view" rendering engines in order to generate responses by inserting data into templates.
       + Set common web application settings like the port to use for connecting, and the location of templates that are used for rendering the response.
       + Add additional request processing "middleware" at any point within the request handling pipeline.
   + **Routing**
   + https://www.cloudflare.com/learning/network-layer/what-is-routing
     + The process of routing paths through networks. Routers receive a packet in which they read the header of to determine its destination, then they send it. This is done sometimes millions of times a second.
   + **WRRC**
   + https://www.codecademy.com/articles/request-response-cycle-static
      + Web Request/Response Cycle, the basic cycle of functions for a user web request. First a request is made via a browser, then sent via a router to a controller to handke the request where it is passed to the view. The view renders the page as html, then passes it back to the controller to relay it to the browser, where the page can be rendered for the user.
