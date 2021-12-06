# **Reading Assignment 1 - Intro to Big O and Python**
 ## Big O notation- Notation which marks the amount and time and memory an algorithm takes to complete.
  + *O(1)* - algorithm that correlates 1 to 1 with the input data, as data grows Big O grows linearly.
  + *O(N)* - algorithm that uses some kind of variable amounts of data, this could mean an array or list must be iterated over.
  + *O(N^2)* -  represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set.
  + *O(2^N)* - an algorithm whose growth doubles with each addition to the input data set.
  + *O(logN)* - means that the time grows linearly while the input size n is growing exponentially.
 ## Python
   + **Names** - refer to values, Python does not require you to label the typing of your values
   +  **Values** - live until there are no more references to them, in Python values have no scope to them.
   +  **Mutable Values** - values which can be changed or reassigned with no issue.
   +  **Immutable values** - can't be changed in place, like a Const.
   +  **Assignment** - creates pointers to data, it does not copy it.
   +  **Mutable aliasing** - This is when we have one name that refers to another name that holds an original value. Both names refer to the same value and changing one will change the other.
