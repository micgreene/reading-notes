# **Reading Assignment 12 - Docs for the HTML <canvas> Element & Chart.js**
*Excerpts from https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial & https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/

1. ###Basic Usage for Canvas
  + **Canvas
    + The `<canvas>` element has only two attributes, width and height. These are both optional and can also be set using DOM properties. When no width and height attributes are specified, the canvas will initially be 300 pixels wide and 150 pixels high. The element can be sized arbitrarily by CSS, but during rendering the image is scaled to fit its layout size: if the CSS sizing doesn't respect the ratio of the initial canvas, it will appear distorted.

      + Note: If your renderings seem distorted, try specifying your width and height attributes explicitly in the `<canvas>` attributes, and not using CSS.

    + The `<canvas>` element can be styled just like any normal image (margin, border, background…). These rules, however, don't affect the actual drawing on the canvas. When no styling rules are applied to the canvas it will initially be fully transparent.
  
  + **Fallback Content
    + The `<canvas>` element differs from an <img> tag in that, like for `<video>`, `<audio>`, or `<picture>` elements, it is easy to define some fallback content, to be displayed in older browsers not supporting it, like versions of Internet Explorer earlier than version 9 or textual browsers. You should always provide fallback content to be displayed by those browsers.

    + Providing fallback content is very straightforward: just insert the alternate content inside the <canvas> element. Browsers that don't support `<canvas>` will ignore the container and render the fallback content inside it. Browsers that do support <canvas> will ignore the content inside the container, and just render the canvas normally.

      + For example, we could provide a text description of the canvas content or provide a static image of the dynamically rendered content. This can look something like this:

        `<canvas id="stockGraph" width="150" height="150">`
         ` current stock price: $3.15 + 0.15`
        `</canvas>`
        `<canvas id="clock" width="150" height="150">`
          `<img src="images/clock.png" width="150" height="150" alt=""/>`
        `</canvas>`

    + Telling the user to use a different browser that supports canvas does not help users who can't read the canvas at all, for example. Providing a useful fallback text or sub DOM helps to make the canvas more accessible.

   + Required `</canvas>` Tag
      + As a consequence of the way fallback is provided, unlike the <img> element, the <canvas> element requires the closing tag (`</canvas>`). If this tag is not present, the rest of the document would be considered the fallback content and wouldn't be displayed.
      
   + Checking for Support
      + The fallback content is displayed in browsers which do not support `<canvas>`. Scripts can also check for support programmatically by simply testing for the presence of the getContext() method. Our code snippet from above becomes something like this:

        + `var canvas = document.getElementById('tutorial');`

        `if (canvas.getContext) {`
         ` var ctx = canvas.getContext('2d');`
          `// drawing code here`
        `} else {`
          `// canvas-unsupported code here`
        `}`
    
    
1. ### Using Chart.js
  + **Download Chart.js
    + Copy the Chart.min.js out of the unzipped folder and into the directory you’ll be working in. Then create a new html page and import the script: 
    `<!DOCTYPE html>
     `<html lang="en">
     `<head>
        `<meta charset="utf-8" />
        `<title>Chart.js demo</title>
        `<script src='Chart.min.js'></script>
    `</head>
    `<body>
    `</body>
    `</html>`
    
  + **Drawing a Line Chart
    + To draw a line chart, the first thing we need to do is create a canvas element in our HTML in which Chart.js can draw our chart. So add this to the body of our HTML page:
        `<canvas id="buyers" width="600" height="400"></canvas>`
        
    + Next, we need to write a script that will retrieve the context of the canvas, so add this to the foot of your body element:
        `<script>
          `var buyers = document.getElementById('buyers').getContext('2d');
          `new Chart(buyers).Line(buyerData);
        `</script>
    + Inside the same script tags we need to create our data, in this instance it’s an object that contains labels for the base of our chart and datasets to describe the values on the chart. Add this immediately above the line that begins `var buyers=`:

       + `var buyerData = {
         ` labels : ["January","February","March","April","May","June"],
          `datasets : [
           ` {
            `  fillColor : "rgba(172,194,132,0.4)",
             ` strokeColor : "#ACC26D",
             ` pointColor : "#fff",
             ` pointStrokeColor : "#9DB86D",
             ` data : [203,156,99,251,305,247]
            `}
          `]
        `}`
        
  + **Drawing a Pie Chart
    + To draw a pie chart, we start by creating a canvas in our HTML same as last time:
    + `<canvas id="countries" width="600" height="400"></canvas>`
    + Next, we need to get the context and to instantiate the chart:

      + `var countries= document.getElementById("countries").getContext("2d");`
      + `new Chart(countries).Pie(pieData, pieOptions);`

    + Next we need to create the data. This data is a little different to the line chart because the pie chart is simpler, we just need to supply a value and a color for each section:

     + `var pieData = [`
        `{`
          `value: 20,
          `color:"#878BB6"
        `},`
       ` {`
         ` value : 40,`
          `color : "#4ACAB4"`
       ` },`
        `{`
         ` value : 10,`
         ` color : "#FF8153"`
        `},`
        `{`
          `value : 30,`
          `color : "#FFEA88"`
        `}`
      `];`

    + Now, immediately after the pieData we’ll add our options:

    + `var pieOptions = {`
	    `segmentShowStroke : false,`
	    `animateScale : true`
      `}`
      
    + These options do two things, first they remove the stroke from the segments, and then they animate the scale of the pie so that it zooms out from nothing.
  
  + **Drawing a Bar Graph
    + Add the canvas again: 
    
    + `<canvas id="countries" width="600" height="400"></canvas>`
    
    + Next, we retrieve the element and create the graph:

      + `var income = document.getElementById("income").getContext("2d");`
      `   new Chart(income).Bar(barData);
      
     + And finally, we add in the bar chart’s data:

      `   var barData = {
      `    labels : ["January","February","March","April","May","June"],
       `   datasets : [
      `    {
      `      fillColor : "#48A497",
      `      strokeColor : "#48A4D1",
        `    data : [456,479,324,569,702,600]
       `   },
       `   {
       `     fillColor : "rgba(73,188,170,0.4)",
       `     strokeColor : "rgba(72,174,209,0.4)",
       `     data : [364,504,605,400,345,320]
       `   }
      `  ]
      `}`
      
+ This time we’ve chosen to use RGBA to specify our colors which allows us to add transparency.
  
