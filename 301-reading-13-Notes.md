# **Reading Assignment 13 - Update/Delete**

1. ## Sending Form Data
  + ### Overview
    + Once the form data has been validated on the client-side, it is okay to submit the form. And, since we covered validation in the previous article, we're ready to submit! This article looks at what happens when a user submits a form — where does the data go, and how do we handle it when it gets there? We also look at some of the security concerns associated with sending form data.
    + **Client/server architecture**  
      + At it's most basic, the web uses a client/server architecture that can be summarized as follows. a client (usually a web browser) sends a request to a server (most of the time a web server like Apache, Nginx, IIS, Tomcat, etc.), using the HTTP protocol. The server answers the request using the same protocol.
      + An HTML form on a web page is nothing more than a convenient user-friendly way to configure an HTTP request to send data to a server. This enables the user to provide information to be delivered in the HTTP request.
    + **On the client side: defining how to send the data**
      + The <form> element defines how the data will be sent. All of its attributes are designed to let you configure the request to be sent when a user hits a submit button. The two most important attributes are action and method.
        + **The action attribute**
          + The action attribute defines where the data gets sent. Its value must be a valid relative or absolute URL. If this attribute isn't provided, the data will be sent to the URL of the page containing the form — the current page.
            + In this example, the data is sent to an absolute URL — https://example.com:
              + `<form action="https://example.com">`
            + Here, we use a relative URL — the data is sent to a different URL on the same origin:
              + `<form action="/somewhere_else">`
            + Note: It's possible to specify a URL that uses the HTTPS (secure HTTP) protocol. When you do this, the data is encrypted along with the rest of the request, even if the form itself is hosted on an insecure page accessed using HTTP. 
            + On the other hand, if the form is hosted on a secure page but you specify an insecure HTTP URL with the action attribute, all browsers display a security warning to the user each time they try to send data because the data will not be encrypted.
            + The names and values of the non-file form controls are sent to the server as name=value pairs joined with ampersands. The action value should be a file on the server that can handle the incoming data, including ensuring server-side validation. The server then responds, generally handling the data and loading the URL defined by the action attribute, causing a new page load (or a refresh of the existing page, if the action points to the same page).
            + How the data is sent depends on the method attribute.
        + **The method attribute**
          + The method attribute defines how data is sent. The HTTP protocol provides several ways to perform a request; HTML form data can be transmitted via a number of different methods, the most common being the GET method and the POST method
          + To understand the difference between those two methods, let's step back and examine how HTTP works. Each time you want to reach a resource on the Web, the browser sends a request to a URL. An HTTP request consists of two parts: a header that contains a set of global metadata about the browser's capabilities, and a body that can contain information necessary for the server to process the specific request.
    + **The GET method**
      + The GET method is the method used by the browser to ask the server to send back a given resource: "Hey server, I want to get this resource." In this case, the browser sends an empty body. Because the body is empty, if a form is sent using this method the data sent to the server is appended to the URL.
        + Consider the following form:

          `<form action="http://www.foo.com" method="GET">`
            `<div>`
              `<label for="say">What greeting do you want to say?</label>`
              `<input name="say" id="say" value="Hi">`
            `</div>`
            `<div>`
              `<label for="to">Who do you want to say it to?</label>`
              `<input name="to" id="to" value="Mom">`
            `</div>`
            `<div>`
              `<button>Send my greetings</button>`
            `</div>`
          `</form>`
          
        + Since the GET method has been used, you'll see the URL www.foo.com/?say=Hi&to=Mom appear in the browser address bar when you submit the form.
        + The data is appended to the URL as a series of name/value pairs. After the URL web address has ended, we include a question mark (?) followed by the name/value pairs, each one separated by an ampersand (&). In this case we are passing two pieces of data to the server:
          + say, which has a value of Hi
          + to, which has a value of Mom
        + The HTTP request looks like this:
          `GET /?say=Hi&to=Mom HTTP/2.0`
          `Host: foo.com`
    + **The POST method**
      + The POST method is a little different. It's the method the browser uses to talk to the server when asking for a response that takes into account the data provided in the body of the HTTP request: "Hey server, take a look at this data and send me back an appropriate result." If a form is sent using this method, the data is appended to the body of the HTTP request.
        + Let's look at an example — this is the same form we looked at in the GET section above, but with the method attribute set to POST.

          `<form action="http://www.foo.com" method="POST">`
           ` <div>`
              `<label for="say">What greeting do you want to say?</label>`
              `<input name="say" id="say" value="Hi">`
            `</div>`
            `<div>`
              `<label for="to">Who do you want to say it to?</label>`
              `<input name="to" id="to" value="Mom">`
            `</div>`
            `<div>`
              `<button>Send my greetings</button>`
            `</div>`
          `</form>`
          
        + When the form is submitted using the POST method, you get no data appended to the URL, and the HTTP request looks like so, with the data included in the request body instead:

          `POST / HTTP/2.0`
          `Host: foo.com`
          `Content-Type: application/x-www-form-urlencoded`
          `Content-Length: 13`
          `say=Hi&to=Mom`
        + The Content-Length header indicates the size of the body, and the Content-Type header indicates the type of resource sent to the server. We'll discuss these headers later on.`
    + **Viewing HTTP requests**
     + HTTP requests are never displayed to the user (if you want to see them, you need to use tools such as the Firefox Network Monitor or the Chrome Developer Tools). As an example, your form data will be shown as follows in the Chrome Network tab. After submitting the form:
      + Open the developer tools.
      + Select "Network"
      + Select "All"
      + Select "foo.com" in the "Name" tab
      + Select "Headers"
    + The only thing displayed to the user is the URL called. As we mentioned above, with a GET request the user will see the data in their URL bar, but with a POST request they won't. This can be very important for two reasons:
      + If you need to send a password (or any other sensitive piece of data), never use the GET method or you risk displaying it in the URL bar, which would be very insecure.
      + If you need to send a large amount of data, the POST method is preferred because some browsers limit the sizes of URLs. In addition, many servers limit the length of URLs they accept.
    + **On the server side: retrieving the data**
      +Whichever HTTP method you choose, the server receives a string that will be parsed in order to get the data as a list of key/value pairs. The way you access this list depends on the development platform you use and on any specific frameworks you may be using with it.
        + **Example: Raw PHP**
         + PHP offers some global objects to access the data. Assuming you've used the POST method, the following example just takes the data and displays it to the user. Of course, what you do with the data is up to you. You might display it, store it into a database, send it by email, or process it in some other way.

            `<?php
              `// The global $_POST variable allows you to access the data sent with the POST method by name`
              `// To access the data sent with the GET method, you can use $_GET`
              `$say = htmlspecialchars($_POST['say']);`
              `$to  = htmlspecialchars($_POST['to']);`
              `echo  $say, ' ', $to;`
            `?>`
          + This example displays a page with the data we sent. You can see this in action in our example php-example.html file — which contains the same example form as we saw before, with a method of POST and an action of php-example.php. When it is submitted, it sends the form data to php-example.php, which contains the PHP code seen in the above block. When this code is executed, the output in the browser is Hi Mom.
            + Note: This example won't work when you load it into a browser locally — browsers cannnot interpret PHP code, so when the form is submitted the browser will just offer to download the PHP file for you. To get it to work, you need to run the example through a PHP server of some kind. Good options for local PHP testing are MAMP (Mac and Windows) and AMPPS (Mac, Windows, Linux).
            + Note also that if you are using MAMP but don't have MAMP Pro installed (or if the MAMP Pro demo time trial has expired), you might have trouble getting it working. To get it working again, we have found that you can load up the MAMP app, then choose the menu options MAMP > Preferences > PHP, and set "Standard Version:" to "7.2.x" (x will differ depending on what version you have installed).
    + **A special case: sending files**
      + Sending files with HTML forms is a special case. Files are binary data — or considered as such — whereas all other data is text data. Because HTTP is a text protocol, there are special requirements for handling binary data.
      + **The enctype attribute**
        + This attribute lets you specify the value of the Content-Type HTTP header included in the request generated when the form is submitted. This header is very important because it tells the server what kind of data is being sent. By default, its value is application/x-www-form-urlencoded. In human terms, this means: "This is form data that has been encoded into URL parameters."
        + If you want to send files, you need to take three extra steps:
          + Set the method attribute to POST because file content can't be put inside URL parameters.
          + Set the value of enctype to multipart/form-data because the data will be split into multiple parts, one for each file plus one for the text data included in the form body (if text is also entered into the form).
          + Include one or more <input type="file"> controls to allow your users to select the file(s) that will be uploaded.
            + For example:

              `<form method="post" action="https://www.foo.com" enctype="multipart/form-data">`
                `<div>`
                 ` <label for="file">Choose a file</label>`
                  `<input type="file" id="file" name="myFile">`
                `</div>`
                `<div>`
                  `<button>Send the file</button>`
                `</div>`
              `</form>`
              
          + Note: Servers can be configured with a size limit for files and HTTP requests in order to prevent abuse.
   
