# **Reading Assignment 4 - Classes, Objects, Recursion**

 ## Objects
  + **Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.**<br />
   `class MyClass:`<br />
    &nbsp;&nbsp;&nbsp;&nbsp;`variable = "blah"`<br />
    &nbsp;&nbsp;&nbsp;&nbsp;`def function(self):`<br />
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`print("This is a message inside the class.")`
  
  ### Accessing Object Variables <br />
    **To access variables within an object:**<br />
    `newObject = MyClass() //create new object from class template`<br />
    `obj_var = myobjectx.variable //access object variable`
    
  ### Accessing Object Functions <br />
    **To access functions within an object:**<br />
    `newObject = MyClass() //create new object from class template`<br />
    `myobjectx.function() //calls object function`
    
  ### init()
    **The __init__() function, is a special function that is called when the class is being initiated. It's used for asigning values in a class. THis would be called a 'constructor' in other languages**<br />
    `class NumberHolder:`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;`def __init__(self, number):`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`self.number = number`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;`def returnNumber(self):`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return self.number`<br /><br />
    `var = NumberHolder(7)`<br />
    `print(var.returnNumber()) #Prints '7'`
   
       

   
       





    

 ## File Paths
   + *When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:*
    + Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
    + File Name: the actual name of the file
    + Extension: the end of the file path pre-pended with a period (.) used to indicate the file type
    
 ## Opening and Closing a File in Python
  + `file = open('dog_breeds.txt')`
  + `with open('dog_breeds.txt', 'r') as reader`
  + 'r'	Open for reading (default)
  + 'w'	Open for writing, truncating (overwriting) the file first
  + 'rb' or 'wb'	Open in binary mode (read/write using byte data)

