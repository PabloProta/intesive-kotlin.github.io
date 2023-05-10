---
layout: default
title: Graph
parent: Non-Linear
grand_parent: Data Structures
nav_order: 1
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>

# Graph

> A Graph is a non-linear data structure consisting of vertices and edges. The vertices are sometimes also referred to as nodes and the edges are lines or arcs that connect any two nodes in the graph. More formally a Graph is composed of a set of vertices( V ) and a set of edges( E ). The graph is denoted by G(V, E).

![](https://media.geeksforgeeks.org/wp-content/uploads/20200630111809/graph18.jpg)
Graph data structures are a powerful tool for representing and analyzing complex relationships between objects or entities. They are particularly useful in fields such as social network analysis, recommendation systems, and computer networks. In the field of sports data science, graph data structures can be used to analyze and understand the dynamics of team performance and player interactions on the field.

Imagine a game of football as a web of connections, where players are the nodes and their interactions on the field are the edges. This web of connections is exactly what a graph data structure represents, and it’s the key to unlocking insights into team performance and player dynamics in sports.

## Types:
**Null Graph**:
A graph is known as a null graph if there are no edges in the graph.

**Trivial Graph**:
Graph having only a single vertex, it is also the smallest graph possible.
![](https://media.geeksforgeeks.org/wp-content/uploads/20200630113942/null_graph_trivial.jpg)

**Undirected Graph**:
A graph in which edges do not have any direction. That is the nodes are unordered pairs in the definition of every edge. 

**Directed Graph**:
A graph in which edge has direction. That is the nodes are ordered pairs in the definition of every edge.

![](https://media.geeksforgeeks.org/wp-content/uploads/20200630114438/directed.jpg)

**Connected Graph**:
The graph in which from one node we can visit any other node in the graph is known as a connected graph. 

**Disconnected Graph**:
The graph in which at least one node is not reachable from a node is known as a disconnected graph.

![](https://media.geeksforgeeks.org/wp-content/uploads/20200630121400/connected1.jpg)

**Regular Graph**:
The graph in which the degree of every vertex is equal to K is called K regular graph.

**Complete Graph**:
The graph in which from each node there is an edge to each other node.

![](https://media.geeksforgeeks.org/wp-content/uploads/20200630122008/regular.jpg)

**Cycle Graph**:
The graph in which the graph is a cycle in itself, the degree of each vertex is 2. 

**Cyclic Graph**:
A graph containing at least one cycle is known as a Cyclic graph.

![](https://media.geeksforgeeks.org/wp-content/uploads/20200630122225/cyclic.jpg)

**Directed Acyclic Graph**:
A Directed Graph that does not contain any cycle. 

**Bipartite Graph**:
A graph in which vertex can be divided into two sets such that vertex in each set does not contain any edge between them.

**Weighted Graph**:
A graph in which the edges are already specified with suitable weight is known as a weighted graph. 
Weighted graphs can be further classified as directed weighted graphs and undirected weighted graphs. 


## Tree v/s Graph

Trees are the restricted types of graphs, just with some more rules. Every tree will always be a graph but not all graphs will be trees. Linked List, Trees, and Heaps all are special cases of graphs. 

![](https://media.geeksforgeeks.org/wp-content/uploads/20200630123458/tree_vs_graph.jpg)


## Basic Operation: 
>- Insertion of Nodes/Edges in the graph – Insert a node into the graph.
- Deletion of Nodes/Edges in the graph – Delete a node from the graph.
- Searching on Graphs – Search an entity in the graph.
- Traversal of Graphs – Traversing all the nodes in the graph.


## Structure:

``` run-kotlin
package datastructures.graph

class Graph<T> {
    private val adjacencyList = mutableMapOf<T, MutableList<T>>()

    fun addVertex(vertex: T) {
        adjacencyList[vertex] = mutableListOf()
    }

    fun addEdge(from: T, to: T) {
        adjacencyList[from]?.add(to)
        adjacencyList[to]?.add(from)
    }

    fun removeVertex(vertex: T) {
        adjacencyList[vertex]?.let { adjVertices ->
            adjVertices.forEach { adjVertex ->
                adjacencyList[adjVertex]?.remove(vertex)
            }
            adjacencyList.remove(vertex)
        }
    }

    fun removeEdge(from: T, to: T) {
        adjacencyList[from]?.remove(to)
        adjacencyList[to]?.remove(from)
    }

    fun getAdjacencyList(): Map<T, List<T>> {
        return adjacencyList.toMap()
    }

    fun printGraph() {
        println("Graph:")
        for ((vertex, adjVertices) in adjacencyList) {
            println("$vertex -> ${adjVertices.joinToString(", ")}")
        }
    }
}


fun main(){
    val graph = Graph<String>()
    graph.addVertex("A")
    graph.addVertex("B")
    graph.addVertex("C")
    graph.addEdge("A", "B")
    graph.addEdge("B", "C")
    graph.printGraph()
}

```
## For what it's:

- Graph data structures can be used to represent the interactions between players on a team, such as passes, shots, and tackles. Analyzing these interactions can provide insights into team dynamics and areas for improvement.
Commonly used to represent social networks, such as networks of friends on social media.
- Graphs can be used to represent the topology of computer networks, such as the connections between routers and switches.
- Graphs are used to represent the connections between different places in a transportation network, such as roads and airports.
- Neural Networks: Vertices represent neurons and edges represent the synapses between them. Neural networks are used to understand how our brain works and how connections change when we learn. The human brain has about 10^11 neurons and close to 10^15 synapses.
- Compilers: Graphs are used extensively in compilers. They can be used for type inference, for so-called data flow analysis, register allocation, and many other purposes. They are also used in specialized compilers, such as query optimization in database languages.
Robot planning: Vertices represent states the robot can be in and the edges the possible transitions between the states. Such graph plans are used, for example, in planning paths for autonomous vehicles.

#### REFERENCES:
[https://www.geeksforgeeks.org/introduction-to-graphs-data-structure-and-algorithm-tutorials/?ref=rp](https://www.geeksforgeeks.org/introduction-to-graphs-data-structure-and-algorithm-tutorials/?ref=rp)
[https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/)
[https://www.programiz.com/dsa/graph](https://www.programiz.com/dsa/graph)