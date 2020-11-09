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
      
    + **HANDLE EVENTS**
      + jQuery includes methods that allow you to attach event listeners to selected elements without having to write any tailback code to support older browsers.
    + **Referencing jQuery**
      + Reference your jQuery file by using this html script before your closing `</body>` tag: `<script src="j s/ jquery-1 . 11. 0 .js "></script>`
      + Basic Example: `$(' :header').addClass('headline'); $(' li : lt(3) ').hide(). fadeln(lSOO); $('li').on('click', function() {$(this) . remove();`
    + **Multiple Object Selection**
     + If a jQuery selector finds multiple cases of an element then it will return a list of ALL elements selected that are present on the page.
     + (example `$(li)` with several `<li>` elements = index 0 = li //1st one, index 1 = li //2nd one, etc.) 
    + **Get/Set Info with jQuery**
      + Get: `let content = $('li').html();`
      + Set: `$('li').html('New HTML Content')
    + **Caching jQuery Info**
      + jQuery only references information, to store it you will need to declare avariable like slways, use the '$' to mark it as a jQuery item.
      + Example: `$listItems = $('li');`
    + **Implicit Iteration**
      + jQuery wil automatically cycle through ALL elements matching the referenced element, as such it does not require a specific loop to assign each element a value.
      + Example: `$('li').addClass('seasonal') ;` will add the 'seasonal' class to ALL li items in the script.
    + **Chaining jQuery Methods**
      + In this one statement, three methods act on the same selec tion of elements: hide() hides the elements, delay( ) creates a pause, fadeIn() fades in the elements.
      + Example: `$('li [id!="one"]').hide().delay(SOO).fadeln(1400);`
    + **Checking a page is ready to work with**
      + jQuery features a handful of functions that deal with running code when the page is ready
      + `.on()` (.load - deprecated)- Fires when the page has loaded ALL resources (elements, scripts, etc)
      + `.ready()` - checks if the user's browser supports the `DOMContentLoaded` event and fires as soon as the DOM has loaded. Older brosers will instead wait for the `load` event instead.
        + Example: `$(document).ready(function(){ //code and stuff });` the first part creates a reference to the current page, .ready() will call the function passed to it after the page is finished loading its resources.
        + Example Using Event: `$('li').on('click', function() { + $(this).addClass('complete');});`
        + The shorthand for `$(document).ready(function(){ //code and stuff });` is `$(function(){ //code and stuff });` both are identical in purpose.
    + **.html()**
      + When this method is used to retrieve information from a jQuery selection, it retrieves only the HTML inside the first element in the matched set, along with any of its descendants.
      + For example: `$('ul').html();` will return this:
<li id="one"><em>fresh</em> figs</li>
<li id="two">pine nuts</li>
<li id="three">honey</li>
<li id="four">balsamic vinegar</li>
      + Whereas `$('li').html();` will return this:
<em>fresh</em> figs
    + **.text()**
      + When this method is used to retrieve the text from a jQuery selection, it returns the content from every element in the jQuery selection, along with the text from any descendants.
      + For example, `$('ul').text();` will return this:
fresh figs
pine nuts
honey
balsamic vinegar
      + Whereas `$('li').text();` will return this:
fresh figspine nutshoneybalsamic vinegar
      
2. ## 6 Reasonfor Paired Programming
  + 1. **Greater efficiency**
    + It is a common misconception that pair programming takes a lot longer and is less efficient. In reality, when two people focus on the same code base, it is easier to catch mistakes in the making. Research indicates that pair programing takes slightly longer, but produces higher-quality code that doesn’t require later effort in troubleshooting and debugging (let alone exposing users to a broken product). So, in the long-run, it’s often actually more efficient than two people working on separate features. When coming up with ideas and discussing solutions out loud, two programmers may come to a solution faster than one programmer on their own. Also, when the pair is stuck, both programmers can research the problem and reach a solution faster. Researches also identified pairing enhances technical skills, team communication, and even enjoyability of coding in the workplace.
  + 2. **Engaged collaboration**
    + When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone. It is harder to procrastinate or get off track when someone else is relying on you to complete the work. Popping open your Facebook timeline is just that less enticing when someone else is looking at your screen.
    + Another important aspect of learning to program is knowing when to ask for help. We advise our students to spend no more than fifteen minutes stuck on a problem before asking a teaching assistant or instructor for help. When developers pair program, they rely more on each other and can often find a solution together without needing to ask for additional help. Ultimately, this boosts overall confidence.
  + 3. Learning from fellow students
    + Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of. If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.
    + Often times, the developers in a pairing have different skill sets. If one programmer is more experienced in a certain skill, they can teach a student who is less familiar with that area. The less experienced developer benefits from the experienced developer’s knowledge and guidance, and the latter benefits from explaining the topic in their own words, further solidifying their own understanding.
  + **4. Social skills**
    + Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. This can become more difficult when two programmers have different personalities. Pair programming not only improves programming skills, but can also help programmers develop their interpersonal skills. When just grabbing the keyboard and taking over isn’t an option, getting good at finding the right words is a skill unto itself.
    + This has long-term career impacts. As much as employers want strong programmers, they know it’s essential to hire people who can work well with others.
  + **5. Job interview readiness**
A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen. They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base. By doing so, companies can get a better feel for how an applicant will fit into the team and their collaboration style.
    + For most roles, the ability to work with and learn from others and stellar communication skills are as (or more!) important to a company than specific technical skills. Pair programming strengthens all of those skills.
  + **6. Work environment readiness**
    + Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.
