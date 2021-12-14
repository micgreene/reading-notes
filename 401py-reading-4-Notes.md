# **Reading Assignment 4 - Classes, Objects, Recursion**
[Home](https://micgreene.github.io/reading-notes/)
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
    
  
  ## Recursive Functions in Python
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
    
  *Here, 1! is our* **base case,** *and it equals 1.*
    
   ### Maintaining State
   **When dealing with recursive functions, keep in mind that each recursive call has its own execution context, so to maintain state during recursion you have to either:**
   1. **Thread the state through each recursive call so that the current state is part of the current call’s execution context**
   1. **Keep the state in global scope**
   
   *Let’s calculate 1 + 2 + 3 ⋅⋅⋅⋅ + 10 using recursion. The state that we have to maintain is (current number we are adding, accumulated sum till now).*

   1. Threading the state through each recursive call:<br />
       `def sum_recursive(current_number, accumulated_sum):`<br />
         &nbsp;&nbsp;&nbsp;&nbsp;`# Base case`<br />
         &nbsp;&nbsp;&nbsp;&nbsp;`# Return the final state`<br />
         &nbsp;&nbsp;&nbsp;&nbsp;`if current_number == 11:`<br />
           &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return accumulated_sum`<br />
         &nbsp;&nbsp;&nbsp;&nbsp;`# Recursive case`<br />
         &nbsp;&nbsp;&nbsp;&nbsp;`# Thread the state through the recursive call`<br />
         &nbsp;&nbsp;&nbsp;&nbsp;`else:`<br />
           &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return sum_recursive(current_number + 1, accumulated_sum + current_number)`
         
         &nbsp;&nbsp;&nbsp;&nbsp;`# Pass the initial state`<br />
         &nbsp;&nbsp;&nbsp;&nbsp;`>>> sum_recursive(1, 0) //55`<br /><br />        
   2. Keeping state in global scope:
       `#Global mutable state`<br />
       `current_number = 1`<br />
       `accumulated_sum = 0`<br /><br />       
       `def sum_recursive():`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;`global current_number`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;`global accumulated_sum`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;`# Base case`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;`if current_number == 11:`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return accumulated_sum`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;`# Recursive case`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;`else:`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`accumulated_sum = accumulated_sum + current_number`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`current_number = current_number + 1`<br />
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return sum_recursive()`<br /><br />         
       &nbsp;&nbsp;&nbsp;&nbsp;`>>> sum_recursive() //55

  ## Naive Recursion is Naive
  **The Fibonacci numbers were originally deﬁned by the Italian mathematician Fibonacci in the thirteenth century to model the growth of rabbit populations. Fibonacci surmised that the number of pairs of rabbits born in a given year is equal to the number of pairs of rabbits born in each of the two previous years, starting from one pair of rabbits in the ﬁrst year.**<br />
    To count the number of rabbits born in the nth year, he deﬁned the recurrence relation:<br /> 
      *Fn = Fn-1 + Fn-2*<br />
      
    The base cases are:
      F0 = 0
      F1 = 1    
  
 *Let’s write a recursive function to compute the nth Fibonacci number:*<br /><br />
     `def fibonacci_recursive(n):`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;`print("Calculating F", "(", n, ")", sep="", end=", ")`<br /><br />
     `# Base case`<br />
     `if n == 0:`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;`return 0`<br />
     `elif n == 1:`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;`return 1`<br />
     `# Recursive case`<br />
     `else:`<br />
     &nbsp;&nbsp;&nbsp;&nbsp;`return fibonacci_recursive(n-1) + fibonacci_recursive(n-2)`<br /><br />
     `>>> fibonacci_recursive(5)`<br />     
     **Terminal Output:**<br />
     **Calculating F(5), Calculating F(4), Calculating F(3), Calculating F(2), Calculating F(1),**<br />
     **Calculating F(0), Calculating F(1), Calculating F(2), Calculating F(1), Calculating F(0),**<br />
     **Calculating F(3), Calculating F(2), Calculating F(1), Calculating F(0), Calculating F(1),**
     
 *Naively following the recursive deﬁnition of the nth Fibonacci number was rather inefficient. As you can see from the output above, we are unnecessarily recomputing values.*   
 
 *Let’s try to improve fibonacci_recursive by caching the results of each Fibonacci computation:*<br /><br />
     `from functools import lru_cache`<br /><br />
     `@lru_cache(maxsize=None)`<br />
     `def fibonacci_recursive(n):`<br />
     `print("Calculating F", "(", n, ")", sep="", end=", ")`<br /><br />
     `# Base case`<br />
     `if n == 0:`<br />
     `return 0`<br />
     `elif n == 1:`<br />
     `return 1`<br /><br />
     `# Recursive case`<br />
     `else:`<br />
     `return fibonacci_recursive(n-1) + fibonacci_recursive(n-2)`<br /><br />
     `>>> fibonacci_recursive(5)`<br /><br />
     **Terminal Output:**<br />
     **Calculating F(5), Calculating F(4), Calculating F(3), Calculating F(2), Calculating F(1), Calculating F(0),**<br />

 *lru_cache is a decorator that caches the results. Thus, we avoid recomputation by explicitly checking for the value before trying to compute it. One thing to keep in mind about lru_cache is that since it uses a dictionary to cache results, the positional and keyword arguments (which serve as keys in that dictionary) to the function must be hashable.*
