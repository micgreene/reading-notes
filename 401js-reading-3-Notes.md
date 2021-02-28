# **Reading Assignment 3 - Express REST API**

   ## Name 3 real world use cases where you’d want to change the request with custom middleware
  + Ref: https://www.redhat.com/en/topics/middleware/what-is-middleware
    + Data management, such as adding time stamps to each request to organize when they were made.
    + Application services or API mangement.
    + Authentication, such as sending or requesting user credentials or other parameters. 
 
  ## True or false: The route handler is middleware?
  + Ref: https://scotch.io/tutorials/learn-to-use-the-new-router-in-expressjs-4
    + In and of itself route handler is just used to handle methods used to create routes in a more modular fashion, but if those methods are used to alter requests before they are completed then technically they are middleware. (I.e. you use route handler methods to create middleware)
  
  ## In what ways can a middleware function end the process and send data to the browser?
  + Ref: https://expressjs.com/en/guide/routing.html
    + Middleware will continue to pass the request from one piece of middleware to the next until the request is complete, to end that process prematurely the middleware would need to:
      + find a bad route and return a 404 error
      + encounter an error and return a 500 server error status 
  
  ## At what point in the request lifecycle can you “inject” middleware?
  + Ref: https://www.codecademy.com/articles/what-is-rest
    + Middleware can be used after the intial HTTP request, but before that request reaches the server. Or after the server responds to the user, but before that response is complete.
    + Example: `app.post('/route', timestamp, (req, res) => {res.status(200).json(sentData)})`
    + The 'timestamp' would be middleware.
  
  ## What can cause express to error with “Request headers sent twice, cannot start a second response”
   + This will happen if you attempt to send a new request at somepoint during the middleware process before the request is complete. Ensure that you are not using any HTTP request verbs ( like app.get() )during the middleware process.
