# Trees 

## Common Terminology

- Node - A Tree node is a component which may contain its own values, and references to other nodes

- Root - The root is the node at the beginning of the tree
K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.

- Left - A reference to one child node, in a binary tree

- Right - A reference to the other child node, in a binary tree

- Edge - The edge in a tree is the link between a parent and child node

- Leaf - A leaf is a node that does not have any children

- Height - The height of a tree is the number of edges from the root to the furthest leaf

tree sample:

![tree sample](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)

## Traversals

- Traversing a tree allows us to search for a node, print out the contents of a tree, and much more!

- There are two categories of traversals when it comes to trees:

1. Depth First

- Here are three methods for depth first traversal:

1. Pre-order: root >> left >> right
2. In-order: left >> root >> right
3. Post-order: left >> right >> root

![depth](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/tree-example.png)

- Given the sample tree above, our traversals would result in different paths:

1. Pre-order: A, B, D, E, C, F
2. In-order: D, B, E, A, F, C
3. Post-order: D, E, B, F, C, A


2. Breadth First

- Breadth first traversal iterates through the tree by going through each level of the tree node-by-node. So, given our starting tree one more time:

![breadth](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/tree-example.png)

- Our output using breadth first traversal is now:

`Output: A, B, C, D, E, F`

## K-ary Trees

![k-ary](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/KaryTree1.png)

- If we traversed this tree Breadth First we should see the output:

`Output: A, B, C, D, E, F, G, H`

- We will still start at the root Node, and we will add it to our queue:

- With every Node we dequeue, we check its list of childre and enqueue each one:

![children enqueue](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthKary3.png)

You can read more about trees [here](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)



