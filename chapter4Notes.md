# **Reading Assignment 4 - HTML Links, JS Functions, and Intro to CSS Layout**

1. ### HTML Linking
  + Linking to other sites
    + `<a href="ABSOLUTE or RELATIVE URL"> **Link Text** </a>`
      + An Absolute URL is the complete address of a webpage.  The Relative URL is the shortened name of the html file if that page is attached to the same domain name.
  + Directory Structure
    + The top file of our hierarchy is called the "ROOT"
    + Files and folders have relationships similar to a real family. (i.e., Parent/Child folders, Grandparent/Grndchild folders)
  + Email Links
    + `<a href="mailto:email@address.com"> **Link Text** </a>`
    + The 'mailto:' command targets an email address and opens the user's email client.
  + Opening Links in New Windows
    + `<a href="web address" target="_blank"> **Link Text** </a>`
    + The target="_blank" attribute opens a new window when clicked
  + Linking to a Specific Part of the Same Page
    + One line of code could be: `<a href="#first_story">First Story</a>` This creates a link to the "first_story" id.
    + To link to it, make anothe line: `<h2 id="first_story">First Story</h2>`
    + clicking on the link will scroll the page down to the ID clicked on.

1. ### Site Layout Using CSS
  + **Building Blocks**
    + Block-Level Elements - start on a new line
      + Examples: <h1> <p> <ul> <li> <div>
    + Inline Elements - flow **in between** surrounding text
      + Examples: <img> <b> <i>
  
  + **Containing Elements**
    + Block level elements may be nested inside of eachother:

    `<p>`
      `<div></div>`
    `</p>`
  
