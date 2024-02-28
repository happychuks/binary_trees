# binary_trees

# Binary Trees Documentation

## Overview

Binary trees are hierarchical data structures composed of nodes, where each node contains a value and references to two child nodes, typically called the left child and the right child. These trees are widely used in computer science for various applications such as representing hierarchical data, implementing binary search trees, and more.

## Terminology

- **Node**: Each element or object in a binary tree containing a value and references to its children (if any).
- **Root**: The topmost node in a binary tree, serving as the entry point for traversal.
- **Parent**: A node that has one or more child nodes.
- **Child**: A node directly connected to another node when moving away from the root.
- **Leaf**: A node that has no children.
- **Height**: The maximum number of edges from the root to a leaf node.
- **Depth**: The level of a node in the tree, with the root being at depth 0.
- **Binary Search Tree (BST)**: A binary tree in which the left child of each node is less than the parent node, and the right child is greater.

## Operations

### Traversal

- **Inorder**: Visit left subtree, visit root, visit right subtree.
- **Preorder**: Visit root, visit left subtree, visit right subtree.
- **Postorder**: Visit left subtree, visit right subtree, visit root.

### Common Operations

- **Insertion**: Adding a new node to the tree while maintaining the binary search tree property.
- **Deletion**: Removing a node from the tree while maintaining the binary search tree property.
- **Search**: Finding a specific value within the tree.
- **Minimum/Maximum**: Finding the node with the smallest/largest value in the tree.

## Implementation

Binary trees can be implemented in various programming languages, utilizing classes or structures to represent nodes and their relationships. Here's a basic example in Python:

```python
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

class BinaryTree:
    def __init__(self):
        self.root = None

    def insert(self, value):
        if not self.root:
            self.root = Node(value)
        else:
            self._insert_recursive(self.root, value)

    def _insert_recursive(self, current, value):
        if value < current.value:
            if current.left is None:
                current.left = Node(value)
            else:
                self._insert_recursive(current.left, value)
        elif value > current.value:
            if current.right is None:
                current.right = Node(value)
            else:
                self._insert_recursive(current.right, value)
```

### Other methods (e.g., search, traversal) would be implemented similarly.

```python
# Creating a binary tree
tree = BinaryTree()

# Inserting elements
tree.insert(5)
tree.insert(3)
tree.insert(7)
tree.insert(1)
tree.insert(4)
tree.insert(6)
tree.insert(9)

# Perform operations such as traversal, search, deletion, etc.
```
