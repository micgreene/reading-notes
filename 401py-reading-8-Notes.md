# **Reading Assignment 8 - Game of Greed 3**
[Home](https://micgreene.github.io/reading-notes/)<br />
 ## List Comprehensions in Python
   ### Syntax   
   + Consider the following example:<br />
   + `my_new_list = [ expression for item in list ]`
   + You can see from this example that three ingredients are necessary for a python list comprehension to work:
     1. First is the expression we’d like to carry out. *expression* inside the square brackets.
     2. Second is the object that the expression will work on. *item* inside the square brackets.
     3. Finally, we need an iterable list of objects to build our new list from. *list* inside the square brackets.
   + To understand the list comprehension, imagine it like this: you’re going to perform an expression on each item in the list. The expression will determine what item is eventually stored in the output list.
   + Not only can you perform expressions on an entire list in a single line of code, but, as we’ll see later, it’s possible to add conditional statements in the form of filters, which allows for more precision in the way lists are handled.
   
   ### Create a List with range()  
   + `# construct a basic list using range() and list comprehensions`<br />
     `# syntax`<br />
     `# [ expression for item in list ]`<br />
     `digits = [x for x in range(10)]`<br />
     `print(digits)`<br />
     **Output**<br />
     `[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]`<br />
     
   ### Create a List Using Loops and List Comprehension in Python  
   + # create a list using a for loop:<br />
     `squares = []`<br />
     `for x in range(10):`<br />
     `# raise x to the power of 2`<br />
     `squares.append(x**2)`<br />
     `print(squares)`
     **Output**<br />
     `[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]`
   + The same thing can be done using a list comprehension, but with a fraction of the code. Let’s take a look at how to create a list of squares using the list comprehension method.<br />
     `# create a list using list comprehension`<br />
     `squares = [x**2 for x in range(10)]`<br />
     `print(squares)`<br />
     
   ### Shuffle   
   + The shuffle function, shuffles the elements in list in place, so they are in a random order.
   + `from random import shuffle`<br />`x = [[i] for i in range(10)]`<br />`shuffle(x)`<br />**Output:**<br />
   `# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]`
   ### Randrange   
   + Generate a randomly selected element from range(start, stop, step)
   + `import random`<br />`for i in range(3):`<br />
     `print random.randrange(0, 101, 5)`
   
  
 ## What is Risk Analysis in Software Testing and how to perform it?<br />
   The probability of any unwanted incident is defined as Risk. In Software Testing, *risk analysis* is the process of identifying the risks in applications or software that you built and prioritizing them to test. After that, the process of assigning the level of risk is done. The categorization of the risks takes place, hence, the impact of the risk is calculated.<br />
   ### Why use Risk Analysis?
   + In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a test plan has been created,
