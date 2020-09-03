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
height: 500px;}`

`img.medium{
width: 250px;
height: 250px;}`

`img.small {
width: 100px;
height: 100px;}`
      
  + ### Aligning Images
    + HTML
 `<p><img src="images/magnolia-medium.jpg"
 alt="Magnolia" class="align-left medium" />
 <b><i>Magnolia</i></b> is a large genus that
 contains over 200 flowering plant species...</p>
<p><img src="images/magnolia-medium.jpg"
 alt="Magnolia" class="align-right medium" />
Some magnolias, such as <i>Magnolia stellata</i>
 and <i>Magnolia soulangeana</i>, flower quite
 early in the spring before the leaves open...</p>`
  
  + CSS
`img.align-left {
float: left;
margin-right: 10px;}

img.align-right {
float: right;
margin-left: 10px;}

img.medium {
width: 250px;
height: 250px;}`

  + ### Aligning Images
    + HTML
    
`<p><img src="images/magnolia-medium.jpg"
 alt="Magnolia" class="align-center medium" />
 <b><i>Magnolia</i></b> is a large genus that
 contains over 200 flowering plant species. It
 is named after French botanist Pierre Magnol and,
 having evolved before bees appeared, the
 flowers were developed to encourage pollination
 by beetle.</p>`
 
    + CSS
    
`img.align-center {
display: block;
margin: 0px auto;}

img.medium {
width: 250px;
height: 250px;}`
 
+ ### Background Images
  + Repeating
CSS

`body {
background-image: url("images/header.gif");
background-repeat: repeat-x;}`

  + No-Repeat

`body {
background-image: url("images/tulip.gif");
background-repeat: no-repeat;
background-attachment: fixed; //whether the background element will scroll with page or no}`

  + Background-Position

`body {
background-image: url("images/tulip.gif");
background-repeat: no-repeat;
background-position: center top;}`

  + List of all possible background-position:
               left top
               left center
               left bottom
               center top
               center center
               center bottom
               right top
               right center
               right bottom
  
`body {
background-image: url("images/tulip.gif");
background-repeat: no-repeat;
background-position: 50% 50%;}`

  + You can also use a pair of pixels
or percentages. These represent
the distance from the top left
corner of the browser window
(or containing box). The top left
corner is equal to 0% 0%. The
example shown, with values of
50% 50%, centers the image
horizontally and vertically.

  + Shorthand
  
`body {
background: #ffffff url("images/tulip.gif")
 no-repeat top right;}`
 
 + ### Image Rollovers & Sprites
 
  + HTML
  
`a class="button" id="add-to-basket">
Add to basket</a>
<a class="button" id="framing-options">
Framing options</a>`

  + CSS
  
`.button {
height: 36px;
background-image: url("images/button-sprite.jpg");
text-indent: -9999px;
display: inline-block;}
a#add-to-basket {
width: 174px;
background-position: 0px 0px;}
a#framing-options {
width: 210px;
background-position: -175px 0px;}
a#add-to-basket:hover {
background-position: 0px -40px;}
a#framing-options:hover {
background-position: -175px -40px;}
a#add-to-basket:active {
background-position: 0px -80px;}
a#framing-options:active {
background-position: -175px -80px;}`

  + Gradients
  
`#gradient {
/* fallback color */
background-color: #66cccc;
/* fallback image */
background-image: url(images/fallback-image.png);
/* Firefox 3.6+ */
background-image: -moz-linear-gradient(#336666,
 #66cccc);
/* Safari 4+, Chrome 1+ */
background-image: -webkit-gradient(linear, 0% 0%,
 0% 100%, from(#66cccc), to(#336666));
/* Safari 5.1+, Chrome 10+ */
background-image: -webkit-linear-gradient(#336666,
 #66cccc);
/* Opera 11.10+ */
background-image: -o-linear-gradient(#336666,
 #66cccc);
height: 150px;
width: 300px;}`

  + To overlay text on an image with
high contrast, you can place a
semi-transparent background
color (or "screen") behind the
text to improve legibility.
 
 
1. ## Search Engine
Optimization (SEO)

  + ### The Basics
    + Search engine optimization (or
SEO) is the practice of trying
to help your site appear nearer
the top of search engine results
when people look for the topics
that your website covers. 
    + At the heart of SEO is the idea of
working out which terms people
are likely to enter into a search
engine to find your site and then
using these terms in the right
places on your site to increase
the chances that search engines
will show a link to your site in
their results.

  + ### On-Page Techniques
    + Search engine optimization (or
SEO) is the practice of trying
to help your site appear nearer
the top of search engine results
when people look for the topics
that your website covers. 
    + At the heart of SEO is the idea of
working out which terms people
are likely to enter into a search
engine to find your site and then
using these terms in the right
places on your site to increase
the chances that search engines
will show a link to your site in
their results.

  + ### Off-Page Techniques
    + Getting other sites to link to you
is just as important as on-page
techniques. Search engines help
determine how to rank your
site by looking at the number of
other sites that link to yours.
    + They are particularly interested
in sites whose content is related
to yours. For example, if you
were running a website that
sold fish bait, then a link from
a hairdresser is not likely to be
considered as relevant as one
from an angling community.
    + Search engines also look at the
words between the opening
<a> tag and closing </a> tag
in the link. If the text in the link
contains keywords (rather than
just click here or your website
address) it may be considered
more relevant.
  + On Page SEO Examples:  
    + 1: Page Title
The page title appears at the top
of the browser window or on the
tab of a browser. It is specified in
the <title> element which lives
inside the <head> element.
    + 2: URL / Web Address
The name of the file is part of
the URL. Where possible, use
keywords in the file name.
    + 3: Headings
If the keywords are in a heading
<hn> element then a search
engine will know that this page is
all about that subject and give it
greater weight than other text.
    + 4: Text
Where possible, it helps to
repeat the keywords in the main
body of the text at least 2-3
times. Do not, however, over-use
these terms, because the text
must be easy for a human to
read.
    + 5: Link Text
Use keywords in the text that
create links between pages
(rather than using generic
expressions such as "click here").
    + 6: Image Alt Text
Search engines rely on you
providing accurate descriptions
of images in the alt text. This
will also help your images show
up in the results of image-based
searches.
    + 7: Page Descriptions
The description also lives inside
the <head> element and is
specified using a <meta> tag.
      + It should be a sentence that
describes the content of the
page. (These are not shown in
the browser window but they
may be displayed in the results
pages of search engines.)
      + Never try to fool search engines!
They will penalize you for it. For
example, never add text in the
same color as the background of
the page as they can detect this.
