# **Reading Assignment 4 - Classes, Objects, Recursion**

 ## Objects
  + **Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.**<br />
   `class MyClass:`<br />
    &nbsp;&nbsp;&nbsp;&nbsp;`variable = "blah"`<br />
    &nbsp;&nbsp;&nbsp;&nbsp;`def function(self):`<br />
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`print("This is a message inside the class.")`

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

