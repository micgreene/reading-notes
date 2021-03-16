# **Reading Assignment 5 - Linked Lists**

  ## Summarize Linked List functionality
  + I have learned that a linked list is similar to a conga line, each element or "Node" in the linked list would represent a person in the conga line.

  + Each Node contains 2 properties:

   + **'value'**: could be any data
   + **'next'**: the next Node in the list   
    + *Example, in a 3 person Conga Line*:
     + 1st Dancer             --> 2nd Dancer             --> 3rd Dancer
     + 1st value: who is this --> 2nd value: who is this --> 3rd value: who is this
     + 1st next: 2nd Dancer   --> 2nd next: 3rd Dancer   --> 3rd next: null (they are at the end of the line)    

  + If this was a linked list it would be the same:
    + *Example, in a 3 person Linked List: [3, 7, 10]*:
     + 1st Node               --> 2nd Node               --> 3rd Node
     + 1st value: 3           --> 2nd value: 7           --> 3rd value: 10
     + 1st next: 7            --> 2nd next: 10           --> 3rd next: null (they are at the tail of the list)
 

  + The 1st node is always called the **'Head'**, the last node is always called the **'Tail'**.

  + So far, the above info describes a 'Singly Linked List', meaning there is only a pointer to the next node contained in each node. 

 + Doubly Linked List

  + A 'Doubly Linked List' would ALSO contain pointers to the PREVIOUS node in the list:
    + *Example, in a 3 person **DOUBLY** Linked List: [3, 7, 10]*:
         + 1st Node                 --> 2nd Node               --> 3rd Node
         + 1st value: 3             --> 2nd value: 7           --> 3rd value: 10
         + 1st next: 7              --> 2nd next: 10           --> 3rd next: null (tail)
         + 1st previous: null(head) --> 2nd previous: 3        --> 3rd previous: 7
   
