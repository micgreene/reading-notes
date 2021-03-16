Linked Lists

I have learned that a linked list is similar to a conga line, each element or "Node" in the linked list would represent a person in the conga line.

Each Node contains 2 properties:

'value': could be any data
'next': the next Node in the list
Example, in a 3 person Conga Line:

1st Dancer                       -->               2nd Dancer                            -->                             3rd Dancer

value: who is this                                value: who is this                                                      value: who is this

next: 2nd Dancer                                next: 3rd Dancer                                                      next: null (they are at the end of the line)

 

If this was a linked list it would be the same:

 

Example, in a 3 person Linked List: [3, 7, 10]

1st Node            -->          2nd Node                   -->                      3rd Node

value: 3                              value: 7                                                  value: 10

next: 2nd Node                 next: 3rd Node                                     next: null (this is the last node)

 

The 1st node is always called the 'Head', the last node is always called the 'Tail'.

So far, the above info describes a 'Singly Linked List', meaning there is only a pointer to the next node contained in each node. 

Doubly Linked List

A 'Doubly Linked List' would ALSO contain pointers to the PREVIOUS node in the list:

Example, in a 3 person DOUBLY Linked List: [3, 7, 10]

1st Node                   -->                 2nd Node                   -->                      3rd Node

value: 3                                            value: 7                                                  value: 10

next: 2nd Node                               next: 3rd Node                                     next: null (this is the last node)

previous: null (this is the 1st)         previous: 1st Node                              previous: 2nd Node
