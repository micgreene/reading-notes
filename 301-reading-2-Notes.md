# **Reading Assignment 2 - jQuery**

1. ## jQuery Overview
  + ### Definition
    + jQuery is a JavaScript file that you include in your webpages. It let's you find elements using CSS-style selectors, and then do something with the elements using jQuery methods.
    + **SELECT ELEMENTS**  
      + It is simpler to access elements using jQuery's CSS-style selectors than it is using DOM queries. The selectors are also more powerful and flexible.
        + A function called `jQuery()` let's you find one or more elements in the page.It creates an object called jQuery which holds a reference to those elements. `$()` is often used as shorthand instead of typing `jQuery()` each time.
        + Example: `$('li.className')` finds all list item elements with this className.
    + **PERFORM TASKS**
      + jQuery's methods let you update the DOM tree, animate elements into and out of view, and loop through a set of elements, all in one line of code.
        + once you find your CSS element, you can now use the jQuery methods to manipulate it.
        + Example: `$('li.myClassName').addClass('newClassName');
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
} ) ;
      
  + ### Responsive vs. Adaptive vs. Mobile
    + For some the term responsive may not be new, and others might be even more acquainted with the terms adaptive or mobile. Which may leave you wondering what exactly is the difference between all of them.
    + Responsive and adaptive web design are closely related, and often transposed as one in the same. Responsive generally means to react quickly and positively to any change, while adaptive means to be easily modified for a new purpose or situation, such as change. With responsive design websites continually and fluidly change based on different factors, such as viewport width, while adaptive websites are built to a group of preset factors. A combination of the two is ideal, providing the perfect formula for functional websites. Which term is used specifically doesn’t make a huge difference.
    + Mobile, on the other hand, generally means to build a separate website commonly on a new domain solely for mobile users. While this does occasionally have its place, it normally isn’t a great idea. Mobile websites can be extremely light but they do come with the dependencies of a new code base and browser sniffing, all of which can become an obstacle for both developers and users.
    + Currently the most popular technique lies within responsive web design, favoring design that dynamically adapts to different browser and device viewports, changing layout and content along the way. This solution has the benefits of being all three, responsive, adaptive, and mobile.

2. ## Flexible Layouts
  + Responsive web design is broken down into three main components, including flexible layouts, media queries, and flexible media. The first part, flexible layouts, is the practice of building the layout of a website with a flexible grid, capable of dynamically resizing to any width. Flexible grids are built using relative length units, most commonly percentages or em units. These relative lengths are then used to declare common grid property values such as width, margin, or padding.
  + Flexible layouts do not advocate the use of fixed measurement units, such as pixels or inches. Reason being, the viewport height and width continually change from device to device. Website layouts need to adapt to this change and fixed values have too many constraints. Fortunately, Ethan pointed out an easy formula to help identify the proportions of a flexible layout using relative values.
  + The formula is based around taking the target width of an element and dividing it by the width of it’s parent element. The result is the relative width of the target element: target ÷ context = result

  + ### Relative Viewport Lengths 
    + CSS3 introduced some new relative length units, specifically related to the viewport size of the browser or device. These new units include vw, vh, vmin, and vmax. Overall support for these new units isn’t great, but it is growing. In time they look to play a large roll in building responsive websites.
    + vw
      + Viewports width
    + vh
      + Viewports height
    + vmin
      + Minimum of the viewport’s height and width
    + vmax
      + Maximum of the viewport’s height and width

3. ## Media Queries
  + ### Initializing Media Queries
    + There are a couple different ways to use media queries, using the @media rule inside of an existing style sheet, importing a new style sheet using the @import rule, or by linking to a separate style sheet from within the HTML document. Generally speaking it is recommend to use the @media rule inside of an existing style sheet to avoid any additional HTTP requests.
    + HTML
    + `<link href="styles.css" rel="stylesheet" media="all and (max-width: 1024px)">`
    + CSS
    + `/* @media Rule */`
    + `@media all and (max-width: 1024px) {...}`
    + `/* @import Rule */`
    + `@import url(styles.css) all and (max-width: 1024px) {...}`
    + Each media query may include a media type followed by one or more expressions. Common media types include all, screen, print, tv, and braille. The HTML5 specification includes new media types, even including 3d-glasses. Should a media type not be specified the media query will default the media type to screen.
    + The media query expression that follows the media type may include different media features and values, which then allocate to be true or false. When a media feature and value allocate to true, the styles are applied. If the media feature and value allocate to false the styles are ignored.
    
4. ## Media Queries
  + One popular technique with using media queries is called mobile first. The mobile first approach includes using styles targeted at smaller viewports as the default styles for a website, then use media queries to add styles as the viewport grows.
  + The operating belief behind mobile first design is that a user on a mobile device, commonly using a smaller viewport, shouldn’t have to load the styles for a desktop computer only to have them over written with mobile styles later. Doing so is a waste of bandwidth. Bandwidth that is precious to any users looking for a snappy website.
  + The mobile first approach also advocates designing with the constraints of a mobile user in mind. Before too long, the majority of Internet consumption will be done on a mobile device. Plan for them accordingly and develop intrinsic mobile experiences.
  + A breakout of mobile first media queries might look at bit like the following.
    + `/* Default styles first then media queries */`
    + `@media screen and (min-width: 400px)  {...}`
    + `@media screen and (min-width: 600px)  {...}`
    + `@media screen and (min-width: 1000px) {...}`
    + `@media screen and (min-width: 1400px) {...}`

4. ## Viewport
  + Mobile devices generally do a pretty decent job of displaying websites these days. Sometimes they could use a little assistance though, particularly around identifying the viewport size, scale, and resolution of a website. To remedy this, Apple invented the viewport meta tag.

  + ### Viewport Height & Width
    + Using the viewport meta tag with either the height or width values will define the height or width of the viewport respectively. Each value accepts either a positive integer or keyword. For the height property the keyword device-height value is accepted, and for the width property the keyword device-width is accepted. Using these keywords will inherit the device’s default height and width value.
    + For the best results, and the best looking website, it is recommend that you use the device defaults by applying the device-height and device-width values.
    + `<meta name="viewport" content="width=device-width">`
  + ### Viewport Scale
    + To control how a website is scaled on a mobile device, and how users can continue to scale a website, use the minimum-scale, maximum-scale, initial-scale, and user-scalable properties.
    + The initial-scale of a website should be set to 1 as this defines the ratio between the device height, while in a portrait orientation, and the viewport size. Should a device be in landscape mode this would be the ratio between the device width and the viewport size. Values for initial-scale should always be a positive integer between 0 and 10.
    + `<meta name="viewport" content="initial-scale=2">`

5. ## Flexible Media
  + The final, equally important aspect to responsive web design involves flexible media. As viewports begin to change size media doesn’t always follow suit. Images, videos, and other media types need to be scalable, changing their size as the size of the viewport changes.
  + One quick way to make media scalable is by using the max-width property with a value of 100%. Doing so ensures that as the viewport gets smaller any media will scale down according to its containers width.
  + `img, video, canvas {max-width: 100%;}`
  + ### Flexible Embedded Media
    + Unfortunately the max-width property doesn’t work well for all instances of media, specifically around iframes and embedded media. When it comes to third party websites, such as YouTube, who use iframes for embedded media this is a huge disappointment. Fortunately, there is a work around.
    + To get embedded media to be fully responsive, the embedded element needs to be absolutely positioned within a parent element. The parent element needs to have a width of 100% so that it may scale based on the width of the viewport. The parent element also needs to have a height of 0 to trigger the hasLayout mechanism within Internet Explorer.
    + Padding is then given to the bottom of the parent element, the value of which is set in the same aspect ratio of the video. This allows the height of the parent element to be proportionate to that of it’s width. Remember the responsive design formula from before? If a video has an aspect ratio of 16:9, 9 divided by 16 equals .5625, thus requiring a bottom padding of 56.25%. Padding on the bottom and not the top is specifically used to prevent Internet Explorer 5.5 from breaking, and treating the parent element as an absolutely positioned element.
      + HTML
      + `<figure><iframe src="https://www.youtube.com/embed/4Fqg43ozz7A"></iframe></figure>`              
      + CSS
  `figure {
  height: 0;
  padding-bottom: 56.25%; /* 16:9 */
  position: relative;
  width: 100%;
}
iframe {
  height: 100%;
  left: 0;
  position: absolute;
  top: 0;
  width: 100%;
}`
