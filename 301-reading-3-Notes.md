# **Reading Assignment 3 - Flexbox and Templating**

1. ## Javascript Templating
  + ### Definition
    + Javascript templating is a fast and efficient technique to render client-side view templates with Javascript by using a JSON data source. The template is HTML markup, with added templating tags that will either insert variables or run programming logic.
    +The template engine then replaces variables and instances declared in a template file with actual values at runtime, and convert the template into an HTML file sent to the client.
    + **Mustache**  
      + mustache.js is an implementation of the mustache template system in JavaScript. Mustache is a logic-less template syntax. It can be used for HTML, config files, source code — anything. It works by expanding tags in a template using values provided in a hash or object.
        + It is often referred to as “logic-less” because there are no if statements, else clauses, or for loops. Instead, there are only tags. Some tags are replaced with a value, some nothing, and others a series of values. Example:
        + `Mustache.render(“Hello, {{name}}”, { name: “Sherlynn” });`
        + `//returns: Hello, Sherlynn`
        + In the above, we see two braces around {{ name }}. This is Mustache syntax to show that it is a placeholder. When Mustache compiles this, it will look for the ‘name’ property in the object we pass in, and replace {{ name }} with the actual value, e,g, “Sherlynn”.
    + **Mustache Express**
      + If you intend you use mustache with Node and Express, you can use mustache-express. Mustache Express lets you use Mustache and Express together easily. To install:
        + `npm install mustache --save`
        + `var mustachExpress = require('mustache-express');`
        + `app.engine('html', mustacheExpress());`
        + `app.set('view engine', 'html');`
        + `app.set('views', _dirName + '/src/views');`
      + Next, we would create a 'views' folder inside of the 'src' directory and fill it with an html file called, in this case, 'hello.html'. Inside of 'hello.html' we will have a headline tag with our templating info:
        + `<h1> Hello: {{ name }}</h1>`
      + In our javascript file:
        + `res.render('hello', {"name": "Sherlynn"})`
      + Whereby the first parameter ‘hello’ refers to the hello.html file (no need to include the extension (e.g. hello.html) as it has been previously set as html. The second parameter would be the JSON data itself. We can also pass in a variable representing the data, for example:
        + `var nameObject = {"name": "Sherlynn"}`
        + `res.render('hello', nameObject)`      
    
2. ## Flexbox Basics
  + 1. **Overiview of Flexbox**
    + Since flexbox is a whole module and not a single property, it involves a lot of things including its whole set of properties. Some of them are meant to be set on the container (parent element, known as “flex container”) whereas the others are meant to be set on the children (said “flex items”).
    + If “regular” layout is based on both block and inline flow directions, the flex layout is based on “flex-flow directions”. Please have a look at this figure from the specification, explaining the main idea behind the flex layout.
    + A diagram explaining flexbox terminology. The size across the main axis of flexbox is called the main size, the other direction is the cross size. Those sizes have a main start, main end, cross start, and cross end.
    + Items will be laid out following either the main axis (from main-start to main-end) or the cross axis (from cross-start to cross-end).
      + main axis – The main axis of a flex container is the primary axis along which flex items are laid out. Beware, it is not necessarily horizontal; it depends on the flex-direction property (see below).
      + main-start | main-end – The flex items are placed within the container starting from main-start and going to main-end.
      + main size – A flex item’s width or height, whichever is in the main dimension, is the item’s main size. The flex item’s main size property is either the ‘width’ or ‘height’ property, whichever is in the main dimension.
      + cross axis – The axis perpendicular to the main axis is called the cross axis. Its direction depends on the main axis direction.
      + cross-start | cross-end – Flex lines are filled with items and placed into the container starting on the cross-start side of the flex container and going toward the cross-end side.
      + cross size – The width or height of a flex item, whichever is in the cross dimension, is the item’s cross size. The cross size property is whichever of ‘width’ or ‘height’ that is in the cross dimension.

 
