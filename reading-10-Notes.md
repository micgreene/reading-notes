# **Reading Assignment 10 - Error Handling and Debugging with JavaScript**

  + ### Order of Execution
    + Consider the following code" 
      + `function greetUser () {`
      
          `return 'Hello' + getName();`
          
        `}`
        
        `function getName() {`
        
          `var name = 'Molly';`
          
          `return name;`
          
        `}`
        
        `var greeting= greetUser();`
        
        `alert(greeting);`
      
    + This script above creates a greeting message, then
writes it to an alert box (see right-hand page). In
order to create that greeting, two functions are used:
greetUser() and getName() .
You might think that the order of execution (the
order in which statements are processed) would be
as numbered: one through to four. However, it is a
little more complicated.
To complete step one, the interpreter needs the
results of the functions in steps two and three
(because the message contains values returned by
those functions). The order of execution is more like
this: 1, 2, 3, 2, 1, 4.
      + 1. The greeting variable gets its value from the
greetUser() function.
      + 2. greetUser() creates the message by combining
the string 'Hello' with the result of getName().
      + 3. getName() returns the name to greetUser() .
      + 2. greetUser() now knows the name, and combines
it with the string. It then returns the message to the
statement that ca lled it in step 1.
      + 1. The value of the greeting is stored in memory.
      + 4. This greeting variable is written to an alert box.
    
    
    + In 2002, Adobe introduced a feature in Flash 6 that gained the unfortunate and misleading name of “Flash cookies.” Within the Flash environment, the feature is properly known as Local Shared Objects. 
      + It allowed Flash objects to store up to 100 KB of data per domain
 
 + ### Gears
    + In 2007, Google launched Gears, an open source browser plugin aimed at providing additional capabilities in browsers. 
    + Gears provided an API to an embedded SQL database based on SQLite. 
      + After obtaining permission from the user once, Gears could store unlimited amounts of data per domain in SQL database tables.

2. ## HTML5 Storage
  + ### What is HTML Storage?
    + Certain browser vendors also refer to it as “Local Storage” or “DOM Storage.”
    + It is a way for web pages to store named key/value pairs locally, within the client web browser. Like cookies, this data persists even after you navigate away from the web site, close your browser tab, exit your browser, or what have you. Unlike cookies, this data is never transmitted to the remote web server. 
      + Unlike all previous attempts at providing persistent local storage, it is implemented natively in web browsers, so it is available even when third-party browser plugins are not.

+ ### Checking for HTML5 Storage 
    + From your JavaScript code, you’ll access HTML5 Storage through the localStorage object on the global window object. Before you can use it, you should detect whether the browser supports it:
`function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}`

3. ## Commands for Local Storage.
  + ### Storing Info
    + Data stored in local storage is always set as strings first. The proper practice is to use the JSON.stringify() method to first convert data to the proper format:
    + `//converting an array to a JSON string`
    + `imgArray = JSON.stringify(imgArray);`
    + `//setting the array into local storage under the name, 'productArray'
    + `localStorage.setItem('productArray', imgArray);`
    
  + ### Retrieving Info
    + Data stored in local storage is always set as strings first, thus we should ensure that we use the JSON.parse() method to return the data to its original format:
    + `//converting an array from a JSON string back to an array type JS object, parsing the array stored under the 'productArray' variable name`
    + `imgArray = JSON.parse(localStorage.getItem('productArray'));`
