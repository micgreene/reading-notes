# **Reading Assignment 4 - Responsive Web Design and Regular Expressions**

1. ## Regex 
  + ### Cheatsheet
    + **Character classes**
      + .	any character except newline
      + \w\d\s	word, digit, whitespace
      + \W\D\S	not word, digit, whitespace
      + [abc]	any of a, b, or c
      + [^abc]	not a, b, or c
      + [a-g]	character between a & g
    + **Anchors**
      + ^abc$	start / end of the string
      + \b\B	word, not-word boundary
    + **Escaped characters**
      + \.\*\\	escaped special characters
      + \t\n\r	tab, linefeed, carriage return
    + **Groups & Lookaround**
      + (abc)	capture group
      + \1	backreference to group #1
      + (?:abc)	non-capturing group
      + (?=abc)	positive lookahead
      + (?!abc)	negative lookahead
    + **Quantifiers & Alternation**
      + a*a+a?	0 or more, 1 or more, 0 or 1
      + a{5}a{2,}	exactly five, two or more
      + a{1,3}	between one & three
      + a+?a{2,}?	match as few as possible
      + ab|cd	match ab or cd
    
2. ## Grid CSS
  + **Overview**
    + CSS Grid Layout (aka “Grid”), is a two-dimensional grid-based layout system that aims to do nothing less than completely change the way we design grid-based user interfaces. CSS has always been used to lay out our web pages, but it’s never done a very good job of it. First, we used tables, then floats, positioning and inline-block, but all of these methods were essentially hacks and left out a lot of important functionality (vertical centering, for instance). Flexbox helped out, but it’s intended for simpler one-dimensional layouts, not complex two-dimensional ones (Flexbox and Grid actually work very well together). Grid is the very first CSS module created specifically to solve the layout problems we’ve all been hacking our way around for as long as we’ve been making websites.
  + **Terminology**
    + Before diving into the concepts of Grid it’s important to understand the terminology. Since the terms involved here are all kinda conceptually similar, it’s easy to confuse them with one another if you don’t first memorize their meanings defined by the Grid specification.
      + Grid Container
        + The element on which display: grid is applied. It’s the direct parent of all the grid items. In this example container is the grid container.
          + `<div class="container">`
            + `<div class="item item-1"> </div>`
            + `<div class="item item-2"> </div>`
            + `<div class="item item-3"> </div>`
          + `</div>`
      + Grid Line
        + The dividing lines that make up the structure of the grid. They can be either vertical (“column grid lines”) or horizontal (“row grid lines”) and reside on either side of a row or column. Here the yellow line is an example of a column grid line.
      + Grid Track
        + The space between two adjacent grid lines. You can think of them like the columns or rows of the grid. Here’s the grid track between the second and third row grid lines.
        + Grid Area
          + The total space surrounded by four grid lines. A grid area may be composed of any number of grid cells. Here’s the grid area between row grid lines 1 and 3, and column grid lines 1 and 3.
