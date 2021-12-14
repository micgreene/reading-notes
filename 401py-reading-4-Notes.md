# **Reading Assignment 4 - Classes, Objects, Recursion**

 ## Objects
   **Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.**<br />
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
   **The __init__() function, is a special function that is called when the class is being initiated. It's used for asigning values in a class. This would be called a 'constructor' in other languages**<br />
    `class NumberHolder:`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;`def __init__(self, number):`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`self.number = number`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;`def returnNumber(self):`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return self.number`<br /><br />
    `var = NumberHolder(7)`<br />
    `print(var.returnNumber()) #Prints '7'`
    
  
  ## File PathsRecursive Functions in Python
  **A recursive function is a function defined in terms of itself via self-referential expressions.**<br />
    This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result. All recursive functions share a common structure made up of two parts:<br /> 
      *the Base Case*<br />
      *the Recursive Case*<br /><br />
    To demonstrate this structure, let’s write a recursive function for calculating n!:    
  
  *Decompose the original problem into simpler instances of the same problem.* **This is the recursive case:**<br />
    
    `n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1`
    `n! = n x (n−1)!`
    
  *As the large problem is broken down into successively less complex ones, those subproblems must eventually become so simple that they can be solved without further subdivision.* **This is the base case:**

    `n! = n x (n−1)!`
    `n! = n x (n−1) x (n−2)!`
    `n! = n x (n−1) x (n−2) x (n−3)!`
    
    `n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3!`
    `n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2!`
    `n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1!`
    
  *Here, 1! is our* **base case**,* and it equals 1.*
    
 ## Opening and Closing a File in Python
  + `file = open('dog_breeds.txt')`
  + `with open('dog_breeds.txt', 'r') as reader`
  + 'r'	Open for reading (default)
  + 'w'	Open for writing, truncating (overwriting) the file first
  + 'rb' or 'wb'	Open in binary mode (read/write using byte data)

