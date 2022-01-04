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
   + The same thing can be done using a list comprehension, but with a fraction of the code. Let’s take a look at how to create a list of squares using the list comprehension method:<br />
     `# create a list using list comprehension`<br />
     `squares = [x**2 for x in range(10)]`<br />
     `print(squares)`<br />
     
   ### Show the first letter of each word using Python
   + So far we’ve seen examples of building a list of numbers in Python. Next, let’s try working with strings and the various ways list comprehensions can be used to elegantly handle a list of strings.
   + Using list comprehensions with strings:<br />
     `# a list of the names of popular authors`<br />
     `authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]`<br />
    `# create an acronym from the first letter of the author's names`<br />
    `letters = [ name[0] for name in authors ]`<br />
    `print(letters)`
    **Output**<br />
    `['E', 'L', 'F', 'T', 'E', 'S']`<br />
    
   ### Print numbers only from a given string
   + Another interesting exercise is to extract numbers from a string. For example, we may have a database of names and phone numbers.<br />
   + we can extract the phone number from the user data.
   + Identify numbers in a string using the isdigit() method:<br />
     `# user data entered as name and phone number`<br />
     `user_data = "Elvis Presley 987-654-3210"`<br />
     `phone_number = [ x for x in user_data if x.isdigit()]`<br />
     `print(phone_number)`<br />
     **Output**<br />
     `['9', '8', '7', '6', '5', '4', '3', '2', '1', '0']`
     
   ### Parsing a file using list comprehension
   + It’s also possible to read files in Python using list comprehension. To demonstrate, I’ve created a file called dreams.txt and pasted the following text, a short poem by Langston Hughes:<br />
   *Hold fast to dreams*<br />
   *For if dreams die*<br />
   *Life is a broken-winged bird*<br />
   *That cannot fly.*<br />
   *-Langston Hughes*<br />
   + Using list comprehension, we can iterate through the lines of text in the file and store their contents in a new list.
   + **Example 8: Reading a poem with list comprehensions:**<br />
     `# open the file in read-only mode`<br />
     `file = open("dreams.txt", 'r')`<br />
     `poem = [ line for line in file ]`<br />
     `for line in poem:`<br />
       `print(line)`<br />
     **Output**
     `Hold fast to dreams`<br />
     `For if dreams die`<br />
     `Life is a broken-winged bird`<br />
     `That cannot fly.`<br />
     `-Langston Hughs`<br />
     
      ### Using functions in list comprehensions
      + So far we’ve seen how to use list comprehension to generate lists using some basic Python methods like lower() and upper(). But what if we wanted to use our own Python functions?
      + Not only can we write our own functions with list comprehensions, but we can also add filters to better control the statements.
      + **Example 9: Adding arguments to list comprehension:**<br />
        `# list comprehension with functions`<br />
        `# create a function that returns a number doubled`<br />
        `def double(x):`<br />
          `return x*2`<br /><br />
        `nums = [double(x) for x in range(1,10)]`<br />
        `print(nums)`<br />
        **Output**<br />
        `[2, 4, 6, 8, 10, 12, 14, 16, 18]`<br />
      + Filtering elements from the list can be done using additional arguments. In the following example, only even numbers are selected:
        `# add a filter so we only double even numbers`<br />
        `even_nums = [double(x) for x in range(1,10) if x%2 == 0]`<br />
        `print(even_nums)`<br />
        **Output**<br />
        `[4, 8, 12, 16]`
