# Trees

**Trees are structures comprised of a "Root" node which has a reference to child nodes. These children nodes will in turn have references to their own set of child nodes. The number of children a node might hav depends on the type of tree you are implementing. For example, Binary Trees have both "left" and "right" child nodes. Each child node also contains a reference to its own "left" and "right" child nodes. All types of Tree nodes contain no reference to their parent nodes typically, but in some cases will.**
<br />
![image](https://user-images.githubusercontent.com/66289456/151674004-c15e5a23-9a77-4b85-a9ad-4d61426672f9.png)
<br />
## Common Terminology
+ **Node** - A Tree node is a component which may contain it’s own values, and references to other nodes
+ **Root** - The root is the node at the beginning of the tree
+ **K** - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
+ **Left** - A reference to one child node, in a binary tree
+ **Right** - A reference to the other child node, in a binary tree
+ **Edge** - The edge in a tree is the link between a parent and child node
+ **Leaf** - A leaf is a node that does not have any children
+ **Height** - The height of a tree is the number of edges from the root to the furthest leaf

## Traversals

**An important aspect of trees is how to traverse them. Traversing a tree allows us to search for a node, print out the contents of a tree, and much more! There are two categories of traversals when it comes to trees:**
+ *Depth First*
+ *Breadth First*

### Depth First

+ Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the root. Here are three methods for depth first traversal:
  + Pre-order: root >> left >> right
  + In-order: left >> root >> right
  + Post-order: left >> right >> root

**Sample Tree**
<br />
![image](https://user-images.githubusercontent.com/66289456/151674136-38cf2a3d-73dd-4458-b18f-0b279301d447.png)
<br />
+ Given the sample tree above, our traversals would result in different paths:
  + Pre-order: A, B, D, E, C, F
  + In-order: D, B, E, A, F, C
  + Post-order: D, E, B, F, C, A
  + Breadth First: A, B, C, D, E, F
+ The most common way to traverse through a tree is to use recursion:
  + **Pre-order:**\
    *ALGORITHM preOrder(root)*\
    *// INPUT <-- root node*\
    *// OUTPUT <-- pre-order output of tree node's values*\
    `OUTPUT <-- root.value`\
    `if root.left is not Null`\
      `  preOrder(root.left)`\
    `if root.right is not NULL`\
      `  preOrder(root.right)`\
  + **In-order:**\
    *ALGORITHM inOrder(root)*\
    *// INPUT <-- root node*\
    *// OUTPUT <-- in-order output of tree node's values*\
        `if root.left is not NULL`\
            `  inOrder(root.left)`\
        `OUTPUT <-- root.value`\
        `if root.right is not NULL`\
            `  inOrder(root.right)`\
  + **Post-order:**\
    *ALGORITHM postOrder(root)*\
    *// INPUT <-- root node*\
    *// OUTPUT <-- post-order output of tree node's values*\
        `if root.left is not NULL`\
          `  postOrder(root.left)`\
        `if root.right is not NULL`\
          `  postOrder(root.right)`\
        `OUTPUT <-- root.value`\
  + **Breadth-First:**\
    + *Breadth First traversal is accomplished by pushing each node into a queue as they are encountered.*
    + 1) **This is done by first enqueuing the root node:**
    + ![image](https://user-images.githubusercontent.com/66289456/151677499-213498a3-990e-4a0d-86c4-2cf4d9b23f5a.png)
    + 2) **Begin by dequeuing the root node and outputting its value, then enqueuing its children in order of left to right (if binary):**
    + ![image](https://user-images.githubusercontent.com/66289456/151677510-c81cae60-8f30-435e-a391-e85b409d5686.png)
    + ![image](https://user-images.githubusercontent.com/66289456/151677515-d6a58651-b2a8-4aaf-a5d0-8084c8a0526a.png)
    + 3) **Once all child nodes are enqueued, dequeue the next node and output its value, then enqueue its children in order once again:**
    + ![image](https://user-images.githubusercontent.com/66289456/151677604-04c2507a-7537-4fcf-8376-c206c1ce234d.png)
    + 4) **Continue this process until the tree is empty (there is nothing left to dequeue):**
    + ![image](https://user-images.githubusercontent.com/66289456/151677646-ff77fc6c-817e-4a1f-b104-4cb9b8ca2aa0.png)
    + ![image](https://user-images.githubusercontent.com/66289456/151677656-a82dee2f-2759-438e-868b-d233155ff3af.png)
    + ![image](https://user-images.githubusercontent.com/66289456/151677652-9a030f39-620b-4e68-bc84-58c2ae76b579.png)
    + ![image](https://user-images.githubusercontent.com/66289456/151677666-9a65e6cb-83bb-4dac-af66-76a476361506.png)





