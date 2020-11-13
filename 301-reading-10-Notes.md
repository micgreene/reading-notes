# **Reading Assignment 10 - The Call Stack and Debugging**

1. ## Callstack Overview
  + ### Definition
    + A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.
      + When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
      + Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
      + When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
      + If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.
    + **What causes a stack overflow?**
      + A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.
    + **In summary**
      + The key takeaways from the call stack are:
        1. It is single-threaded. Meaning it can only do one thing at a time.
        2. Code execution is synchronous.
        3. A function invocation creates a stack frame that occupies a temporary memory.
        4. It works as a LIFO — Last In, First Out data structure.
   
   
2. ## Javascript Error Messages and Debugging
  + **Types of error messages**
  + The first thing that indicates you that something is wrong with your code is the (in)famous error message that the one we saw just moments ago, it usually appears on your console (being developer tools of the browser, terminal or whatever else you are using).
    + Reference errors
      + This is as simple as when you try to use a variable that is not yet declared you get this type os errors.
      + `console.log(foo)` // Uncaught ReferenceError: foo is not defined
      + This is also a common thing when using const and let, they are hoisted like var and function but there is a time between the hoisting and being declared so when you try to access them a reference error occurs, the fact that this happens to let and const is called Temporal Dead Zone (TDZ).
    + Syntax errors
      + I know it’s in the name of the errors, but like it says itself, this occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.
      + `JSON.parse( {'foo': 'bar'} )` // Uncaught SyntaxError: Unexpected token o in JSON at position 1
    + Type errors
      + Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable:      
        `var foo = {}`
        `foo.bar` // undefined
        `foo.bar.baz` // Uncaught TypeError: Cannot read property 'baz' of undefined
      + This is probably the most frequent error in JS, trying to access a property/method thinking that bar is of the type object when in reality, since it hasn’t been declared yet, it’s undefined which doesn’t have any baz available.
  + **Debugging**
    + To debug your JS code, the easiest and maybe the most common way its to simply console.log() the variables you want to check or, by using chrome developer tools, open your page with your JS code (press cmd+o in macOS or Ctrl+o in Windows) and choose your file to debug, click the line you wanna debug and refresh your page again (F5).
    + If the line you selected was run you will be able to see what has happened before that point and you can try and evaluate the next lines to check if everything is outputting what you are expecting.
    + The breakpoint can also be achieved by putting a debugger statement in your code in the line you want to break.
Image for post
    + You can also add conditional breakpoints by right-clicking a previous set breakpoint, which will make your program stop at that point only if a condition is met, this is awesome for when you want to debug huge cycles for specific values. In this example the breakpoint will point stop when the index reaches 40.
    
