# **Reading Assignment 11 - Audio, Video, Images**

1. ## Images
  + ### Controlling Size of Images
    + HTML 
    
`<img src="images/magnolia-large.jpg"
 class="large" alt="Magnolia" />
<img src="images/magnolia-medium.jpg"
 class="medium" alt="Magnolia" />
<img src="images/magnolia-small.jpg"
 class="small" alt="Magnolia" />`
 
   + CSS
   
`img.large {width: 500px;
height: 500px;}
img.medium{
width: 250px;
height: 250px;}
img.small {
width: 100px;
height: 100px;}`
      
  + ### Flash Cookies
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
