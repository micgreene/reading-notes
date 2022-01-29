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
+ The most common way to traverse through a tree is to use recursion:
  + Pre-order:\
    **ALGORITHM preOrder(root)**\
    **// INPUT <-- root node**\
    **// OUTPUT <-- pre-order output of tree node's values**\
    `OUTPUT <-- root.value`\
    `if root.left is not Null`\
      `  preOrder(root.left)`\
    `if root.right is not NULL`\
      `  preOrder(root.right)`\
  + In-order:\
    **ALGORITHM inOrder(root)**\
    **// INPUT <-- root node**\
    **// OUTPUT <-- in-order output of tree node's values**\
        `if root.left is not NULL`\
            `  inOrder(root.left)`\
        `OUTPUT <-- root.value`\
        `if root.right is not NULL`\
            `  inOrder(root.right)`\
  + Post-order:\
    **ALGORITHM postOrder(root)**\
    // INPUT <-- root node**\
    // OUTPUT <-- post-order output of tree node's values**\
        `if root.left is not NULL`\
          `  postOrder(root.left)`\
        `if root.right is not NULL`\
          `  postOrder(root.right)`
        `OUTPUT <-- root.value`\
 
