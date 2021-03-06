# **Reading Assignment 8 - More CSS Layouts**

1. ## Controlling the Positioning of Elements
  + ### Normal Flow (This is the default behavior)
    + Every **Block Level** element appears on a new line, causing each item to appear lower down the page than the previous one.
      + Even if you specify the width of the boxes and there is space to sit side by side they will still go to the next line.
  
  + ### Relative Positioning** (`position: relative; top: 10px; left: 100px;`)
    + This moves an element from the position it would be in **Normal Flow** , shifting it then to the top,right,bottom, or left of where it would have been placed
      + This does not affect surrounding elements.
 
 + ### Absolute Positioning (`position: absolute; top: 0px;; left: 500px; width: 250px;`)
    + This positions the element in relation to its *containing element*.
    + Moves as user scrolls up or down the page.
      + This takes the element out of normal flow and does not affect surrounding elements.

+ ### Fixed Positioning (`position: fixed; top: 10px; left: 0px; padding: 10px; margin: 0px; width: 100%; background-color: grey;`)
    + This is a form of **Absolute Positioning** that positions the element in relation to the *browser window*, instead of the *containing element*..
    + Does *NOT* move as user scrolls up or down the page.
      + This takes the element out of normal flow and does not affect surrounding elements.

+ ### Floating Elements (`float: right; width: 275px; font-size: 130%; font-style: italic; margin: 0px 0px 10 px 10px; padding: 10px; border-top: 1px solid black; border-bottom: 1px solid black;`)
    + FLoating an element allows you to take that element out **Normal Flow** and positions it to the far left or right of a containing box.
      + The **Floating Element** will become a **Block Level** element around which other content flows.

+ ### Ovelapping Elements (`position: fixed; z-index: 10; top: 10px; left: 0px; padding: 10px; margin: 0px; width: 100%; background-color: grey;`)
    + When you use **Relative**, **Fixed**, or **Absolute** positiong, boxes may *overlap*. Items that appear later will sit on top of the earlier ones.
    + To control the stack order, use the **Z-Index Property**.
      + Will be a number, the larger the number, the closer the item will be to the top.


