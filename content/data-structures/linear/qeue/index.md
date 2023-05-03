---
layout: default
title: Qeue
parent: Linear
grand_parent: Data Structures
nav_order: 4
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>
# Queue
> A Queue is defined as a linear data structure that is open at both ends and the operations are performed in First In First Out (FIFO) order.

We define a queue to be a list in which all additions to the list are made at one end, and all deletions from the list are made at the other end.  The element which is first pushed into the order, the operation is first performed on that.

We have explained some of the application of queue in data structure below:

- Queues are used to schedule the jobs that are needed to be performed in certain order
- Queues are used in graph algorithms mainly for breadth first search
- Queues are also used for real world systems simulations like customer queues, traffic flow,etc.

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20221213113312/Queue-Data-Structures.png)

## Basic Operations:

We can perform various operations on queues but in this blog section we have explained some of the basic operations on queue.

- Enqueue: This function is used to add an element to the rear end of the queue. If the queue is completely filled, then it will be in an overflow condition. The time complexity of the enqueue is O(1).
- Dequeue: This function is used to remove an element from the front end of the queue. If the queue is empty, then it will be in an underflow condition. The time complexity of the dequeue is O(1).
- Front: This function returns the front element of the queue. The time complexity of this function is O(1).
- Rear: This function returns the last element of the queue. The time complexity of this function is O(1).
- Peek(): This operation is used to get the value of the element from the front of the queue.



## Types:

There are mainly 4 types of queues and we have explained all 4 of them below:

- **Simple Queue:** In a Simple queue, insertion of the element takes place at the rear end i.e. ENQUEUE, and removal of the element takes place at the front end i.e. DEQUEUE. The simple queue is also called a linear queue.
- **Circular Queue:** In a circular queue, the elements act like circular rings. The working of a circular queue is similar to a simple queue but in a circular queue, the element in the last position is connected to the element in the first position. The main advantage of a circular queue is that the memory will be utilized in a better way.
-  **Priority Queue:** In a priority queue, the elements are stored according to their priority, Based on the priority of elements we’ll set our queue accordingly i.e. in ascending order or in descending order.
- **Dequeue:** Dequeue is known as a double-ended queue. In dequeue, the elements can be inserted or removed from both ends.Due to this property, the dequeue may not follow the first in first out property.

I will just give an example using kotlin for the simple/linear queue, but be free to evaluate by yourself how to
structure those above using kotlin.

### Structure:

> For the implementation of queue, we need to initialize two pointers i.e. front and rear, we insert an element from the rear and remove the element from the front, and if we increment the rear and front pointers we may occur error, Due to this, the front pointer may reach the end.
The solution to the above problem is to increase the front and rear pointers in a circular manner.

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20221213111946/fifo-property-in-Queue.png)

``` run-kotlin
package datastructures.queue


class LinearQueue<T>(private val capacity: Int) {
    /**
     * Array list is basically a list, but you can use your own
     * list implementation like one that we already did in the
     * linked list section.
     */
    private val vector = ArrayList<T>(capacity)

    private var _front: T? = null

    val front: T
        get() = _front ?: throw EmptyQueueException()

    val rear: T
        get() = vector[0]

    /**
     * Inserted on rear of queue.
     *
     * @param value the value that will be inserted.
     */
    fun enqueue(value: T) {
        if (queueIsFull())
            throw OverflowConditionException()

        _front = value
        vector.add(value)
    }

    private fun queueIsFull() = vector.size == capacity

    /**
     *  Remove an element from front of queue.
     */
    fun dequeue() {
        if (vector.isEmpty())
            throw UnderflowConditionException()
        vector.removeAt(0)
    }

    /**
     * Print the queue.
     */
    fun printQueue() {
        vector.forEach {
            print(" $it")
        }
    }

    /**
     * Method to get the element at front of the queue.
     */
    fun peek() = vector[vector.size - 1]

    class OverflowConditionException : Exception("Queue reached the max size.")

    class UnderflowConditionException : Exception("Queue is empty unable to dequeue it.")

    class EmptyQueueException : Exception("Queue is empty, cannot access any element")
}


fun main() {
    val queue: LinearQueue<Int> = LinearQueue(5)
    for (i in 1..5) {
        queue.enqueue(i)
    }

    println("The entire queue:")
    queue.printQueue()
    println("\ndequeue 2 items : ")
    queue.dequeue()
    queue.dequeue()
    queue.printQueue()
    println("\nenqueue the element 10: ")
    queue.enqueue(10)
    queue.printQueue()
    println("\nrear: ${queue.rear} | front: ${queue.front} | peek(): ${queue.peek()}")
}

```

#### REFERENCES:
[https://www.geeksforgeeks.org/queue-data-structure/](https://www.geeksforgeeks.org/queue-data-structure/) 
[https://www.prepbytes.com/blog/queues/applications-of-queue-data-structure/#:~:text=When%20any%20resource%20is%20shared,queue%2C%20doubly%20ended%20priority%20queue.](https://www.prepbytes.com/blog/queues/applications-of-queue-data-structure/#:~:text=When%20any%20resource%20is%20shared,queue%2C%20doubly%20ended%20priority%20queue.)
