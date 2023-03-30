---
layout: default
title: Tree
parent: Non-Linear
grand_parent: Data Structures
nav_order: 0
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>
# Tree

> A tree data structure is a hierarchical structure that is used to represent and organize data in a way that is easy to navigate and search. It is a collection of nodes that are connected by edges and has a hierarchical relationship between the nodes. The topmost node of the tree is called the root, and the nodes below it are called the child nodes. Each node can have multiple child nodes, and these child nodes can also have their own child nodes, forming a recursive structure.

This data structure is a specialized method to organize and store data in the computer to be used more effectively. It consists of a central node, structural nodes, and sub-nodes, which are connected via edges. We can also say that tree data structure has roots, branches, and leaves connected with one another. 

![](https://media.geeksforgeeks.org/wp-content/uploads/20221124153129/Treedatastructure.png)

## Types:
- Binary Tree
- Binary Search Tree
- AVL Tree
- B-Tree

## Terminologies In Tree Data Structure:
**Parent Node**: The node which is a predecessor of a node is called the parent node of that node. {B} is the parent node of {D, E}.

**Child Node**: The node which is the immediate successor of a node is called the child node of that node. Examples: {D, E} are the child nodes of {B}.

**Root Node**: The topmost node of a tree or the node which does not have any parent node is called the root node. {A} is the root node of the tree. A non-empty tree must contain exactly one root node and exactly one path from the root to all other nodes of the tree.
Leaf Node or External Node: The nodes which do not have any child nodes are called leaf nodes. {K, L, M, N, O, P} are the leaf nodes of the tree.
Ancestor of a Node: Any predecessor nodes on the path of the root to that node are called Ancestors of that node. {A,B} are the ancestor nodes of the node {E}

**Descendant**: Any successor node on the path from the leaf node to that node. {E,I} are the descendants of the node {B}.

**Sibling**: Children of the same parent node are called siblings. {D,E} are called siblings.
Level of a node: The count of edges on the path from the root node to that node. The root node has level 0.
Internal node: A node with at least one child is called Internal Node.
Neighbour of a Node: Parent or child nodes of that node are called neighbors of that node.

**Subtree**: Any node of the tree along with its descendant.

### Properties of a Tree:
**Number of edges**: An edge can be defined as the connection between two nodes. If a tree has N nodes then it will have (N-1) edges. There is only one path from each node to any other node of the tree.

**Depth of a node**: The depth of a node is defined as the length of the path from the root to that node. Each edge adds 1 unit of length to the path. So, it can also be defined as the number of edges in the path from the root of the tree to the node.

**Height of a node**: The height of a node can be defined as the length of the longest path from the node to a leaf node of the tree.
Height of the Tree: The height of a tree is the length of the longest path from the root of the tree to a leaf node of the tree.

**Degree of a Node**: The total count of subtrees attached to that node is called the degree of the node. The degree of a leaf node must be 0. The degree of a tree is the maximum degree of a node among all the nodes in the tree.
Some more properties are:

Traversing in a tree is done by depth first search and breadth first search algorithm.
It has no loop and no circuit
It has no self-loop 
Its hierarchical model.

### Structure:

In this section i will structure just the Binary Tree, for the other ones i suggest you to create one by yourself.

``` run-kotlin
package datastructures.tree

import java.util.*

class Node<T>(var value: T) {
    var level: Int = 0
    var left: Node<T>? = null
    var right: Node<T>? = null
}

class BinaryTree<T : Comparable<T>> {
    private var root: Node<T>? = null


    fun insert(value: T) {
        val node = Node(value)
        if (root == null) {
            root = node
            root!!.level = 0
        } else {
            insertNode(root!!, node)
        }
    }

    /**
     * This a recursive method that inserts a node in the tree hierarchy.
     * @param parentNode is the parent of the current node.
     * @param newNode the node that will be inserted.
     */
    private fun insertNode(parentNode: Node<T>, newNode: Node<T>) {
        if (newNode.value < parentNode.value) {
            if (parentNode.left == null) {
                parentNode.left = newNode
                newNode.level = parentNode.level + 1
            } else {
                insertNode(parentNode.left!!, newNode)
            }
        } else {
            if (parentNode.right == null) {
                parentNode.right = newNode
                newNode.level = parentNode.level + 1
            } else {
                insertNode(parentNode.right!!, newNode)
            }
        }
    }

    fun printTreeHierarchy() {
        val root = root ?: return
        val queue = LinkedList<Node<T>>()
        queue.add(root)

        while (queue.isNotEmpty()) {
            val size = queue.size
            var levelNodes = mutableListOf<Node<T>>()

            for (i in 0 until size) {
                val node = queue.poll()
                levelNodes.add(node)

                if (node.left != null) {
                    queue.add(node.left!!)
                }
                if (node.right != null) {
                    queue.add(node.right!!)
                }
            }

            val line = levelNodes.joinToString(" ") { it.value.toString() }
            println(line)
        }
    }
}

fun main() {
    val tree = BinaryTree<String>()
    tree.insert("apple")
    tree.insert("banana")
    tree.insert("apoja")
    tree.insert("cherry")
    tree.insert("date")
    tree.printTreeHierarchy()
}
```

## For what it's?

Trees are commonly used to represent or manipulate hierarchical data in applications such as:

**File systems for**:
Directory structure used to organize subdirectories and files (symbolic links create non-tree graphs, as do multiple hard links to the same file or directory)
The mechanism used to allocate and link blocks of data on the storage device
Class hierarchy or "inheritance tree" showing the relationships among classes in object-oriented programming; multiple inheritance produces non-tree graphs
Abstract syntax trees for computer languages

**Natural language processing**:
Parse trees
Modeling utterances in a generative grammar
Dialogue tree for generating conversations
Document Object Models ("DOM tree") of XML and HTML documents
Search trees store data in a way that makes an efficient search algorithm possible via tree traversal
A binary search tree is a type of binary tree
Representing sorted lists of data

**Computer-generated imagery**:
Space partitioning, including binary space partitioning
Digital compositing
Storing Barnes–Hut trees used to simulate galaxies
Implementing heaps
Nested set collections
Hierarchical taxonomies such as the Dewey Decimal Classification with sections of increasing specificity.
Hierarchical temporal memory
Genetic programming
Hierarchical clustering

#### REFERENCES:
[https://www.geeksforgeeks.org/introduction-to-tree-data-structure-and-algorithm-tutorials/](https://www.geeksforgeeks.org/introduction-to-tree-data-structure-and-algorithm-tutorials/)
[https://en.wikipedia.org/wiki/Tree_(data_structure)](https://en.wikipedia.org/wiki/Tree_(data_structure))