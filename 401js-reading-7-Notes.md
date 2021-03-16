# **Reading Assignment 6 - Bearer Authorization**

 ## Write the following steps in the correct order:
   1. Register your application to get a client_id and client_secret
   1. Ask the client if they want to sign in via a third party
   1. Redirect to a third party authentication endpoint
   1. Receive authorization code
   1. Make a request to the access token endpoint
   1. Receive access token
   1. Make a request to a third-party API endpoint
   1. What can you do with an authorization code?
   1. This gives you sign-in privileges when you attempt to log in.

 ## What can you do with an access token?
   + This gives the signed in user a 'pass' to continue to any route in the app that requires it.

 ## What’s a benefit of using OAuth instead of your own basic authentication?
   + It is a much more complete version of crypto, offering better data security.

 ## Document the following Vocabulary Terms
 
   + **Client Secret**
    + The key the app issues a signed in user to allow users to navigate to routes that require authentication

   + **Authentication Endpoint**
    + The mechanism designed to ensure the user attempting to sign in is authorized to access the network.

   + **Access Token Endpoint**
    + A route which assigns the user an access token, requires authentication to access.

   + **API Endpoint**
    + The route which creates a data request to a 3rd party.

   + **Authorization Code**
    + The code used to identify a certain authorization request.
   
   + **Access Token**
    + The token assigned to a user to access Endpoint requiring one while navigating routes.
