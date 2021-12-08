# **Reading Assignment 2 - Testing and Modules**

 ## Unit tests and TDD
  + *Test-Driven Development* -  is a strategy to write tests first.
  + *Test Name* - should be descriptive as to the type of test taking place, this will be used similar to commenting or documentation.
  + *Arrange, Act and Assert*:
   + **Arrange -** you need to organize the data needed to execute that piece of code (input).
   + **Act -** here you will execute the code being tested (exercise the behaviour).
   + **Assert -** after executing the code, you will check if the result (output) is the same as you were expecting..
  + *The Cycle*:
   + The cycle is made by three steps:
    1. Write a unit test and make it fail.
    2. Write the feature and make the test pass!
    3. Refactor the code.

 ## What does the `if __name__ == “__main__”:` do?
   + Before executing code, Python interpreter reads source file and define few special variables/global variables.
    + If the python interpreter is running that module (the source file) as the main program, it sets the special __name__ variable to have a value “__main__”. 
    + If this file is being imported from another module, __name__ will be set to the module’s name.
   +  **Module** - a file containing Python definitions and statements. The file name is the module name with the suffix .py appended. 
    1. Every Python module has it’s __name__ defined and if this is ‘__main__’, it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.
    2. If you import this script as a module in another script, the __name__ is set to the name of the script/module.
    3. Python files can act as either reusable modules, or as standalone programs.
    4. if __name__ == “main”: is used to execute some code only if the file was run directly, and not imported.

 ## Recursion
  + The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function.
  + **What is base condition in recursion?**
   + In the recursive program, the solution to the base case is provided and the solution of the bigger problem is expressed in terms of smaller problems:
    + `int fact(int n)
{
    if (n < = 1) // base case
        return 1;
    else    
        return n*fact(n-1);    
}`
   + **Arrange -** you need to organize the data needed to execute that piece of code (input).
   + **Act -** here you will execute the code being tested (exercise the behaviour).
   + **Assert -** after executing the code, you will check if the result (output) is the same as you were expecting..
  + *The Cycle*:
   + The cycle is made by three steps:
    1. Write a unit test and make it fail.
    2. Write the feature and make the test pass!
    3. Refactor the code.
