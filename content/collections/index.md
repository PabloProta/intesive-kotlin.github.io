---
layout: default
title: Collections
has_children: true
nav_order: 2
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>

# Kotlin Collections: From Empty Lists to Full Hearts 💕

If you're a Kotlin developer, chances are you're familiar with the concept of collections. Collections are one of the most useful features in Kotlin, providing a convenient way to store and manipulate groups of related data. In this doc, we'll explore the various types of collections available in Kotlin and give you some practical examples of how you can use them to make your code more efficient and enjoyable. 🚀

## Lists
Let's start with the most basic type of collection: lists. Lists are ordered collections of elements, which means you can access them by their index. In Kotlin, lists are created using the **listOf** function. For example:

``` run-kotlin
val names = listOf("Alice", "Bob", "Charlie")
```


With a list of names like this, you can easily iterate over them, filter them, or transform them using functions like map and filter. Lists are great for situations where you need to maintain the order of your data.

### Usages:

- **Iterating Over a List:**
Lists can be used to store a collection of elements that can be accessed using an index. Here's an example of how you can iterate over a list:

```run-kotlin
fun main(){
    val myList = listOf("apple", "banana", "orange")
    for (item in myList) {
        println(item)
    }
}
```

- **Searching for Elements:**
You can search for elements in a list using various functions like contains, indexOf, lastIndexOf, and more. Here's an example:

```run-kotlin
fun main(){
    val myList = listOf("apple", "banana", "orange")
    if (myList.contains("banana")) {
        println("We have bananas!")
    }
    val index = myList.indexOf("orange")
    println("The index of orange is $index")
}
```

- **Sorting a List:**
Lists can be sorted using various sorting algorithms like quicksort, mergesort, and more. You can also sort a list using the sorted and sortedBy functions. Here's an example:

``` run-kotlin
fun main(){
    val myList = listOf(3, 2, 1, 4)
    val sortedList = myList.sorted()
    println(sortedList) // Output: [1, 2, 3, 4]

    val myList2 = listOf("apple", "banana", "orange")
    val sortedList2 = myList2.sortedBy { it.length }
    println(sortedList2) // Output: [apple, orange, banana]
}
```

## Sets
Sets, on the other hand, are collections of unique elements that have no order. In Kotlin, sets are created using the setOf function. For example:

``` run-kotlin
val uniqueNames = setOf("Alice", "Bob", "Charlie")
```

With a set like this, you can easily check if a specific element exists, add new elements, or remove existing ones. Sets are great for situations where you need to maintain uniqueness of your data.

### Usages:

- **Removing Duplicates:**
Sets are a great way to remove duplicates from a list or an array. You can convert the list to a set and then back to a list to remove duplicates. Here's an example:

```run-kotlin
fun main(){
    val myList = listOf(1, 2, 3, 2, 4, 1)
    val mySet = myList.toSet()
    val myNewList = mySet.toList()
    println(myNewList) // Output: [1, 2, 3, 4]
}
```
- **Checking for Membership:**
Sets can be used to check if an element is present in a collection efficiently. Here's an example:

```run-kotlin
fun main(){
    val mySet = setOf("apple", "banana", "orange")
    if ("banana" in mySet) {
        println("We have bananas!")
    }
}
```

- **Set Operations:**
You can perform various set operations like union, intersection, difference, and more using sets. Here's an example:

```run-kotlin
    fun main(){
    val set1 = setOf(1, 2, 3)
    val set2 = setOf(2, 3, 4)
    val union = set1.union(set2)
    val intersect = set1.intersect(set2)
    val diff = set1.subtract(set2)
    println(union) // Output: [1, 2, 3, 4]
    println(intersect) // Output: [2, 3]
    println(diff) // Output: [1]
}
```

## Maps (Dictionary)
Maps are collections of key-value pairs, where each key is unique. In Kotlin, maps are created using the mapOf function. For example:

``` run-kotlin
val ages = mapOf("Alice" to 28, "Bob" to 32, "Charlie" to 25)
```

With a map like this, you can easily retrieve values by their keys, check if a key exists, or add new key-value pairs. Maps are great for situations where you need to associate data with specific keys.

## Putting It All Together
Now that we've covered the basics, let's see how you can use Kotlin collections in practice. Say you have a list of people and their ages, and you want to filter out anyone under 18. You could do it like this:

```run-kotlin
val people = listOf("Alice" to 28, "Bob" to 32, "Charlie" to 16, "Dave" to 45)
val adults = people.filter { it.second >= 18 }.toMap()
```
In this example, we start with a list of people and their ages. We use the filter function to remove anyone who is under 18, and then convert the resulting list to a map using the toMap function. The end result is a map of adults and their ages.

## Wrapping Up
And there you have it! Kotlin collections may seem daunting at first, but once you get the hang of them, they're a powerful tool that can help you write clean, efficient code. Whether you're working with lists, sets, or maps, Kotlin collections are sure to put a smile on your face. 😊