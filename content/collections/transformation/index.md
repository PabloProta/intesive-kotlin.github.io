---
layout: default
parent: Collections
title: Transformation
nav_order: 4
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>

# 👋 Hey there, Kotlin enthusiasts! 
If you're working with collections in Kotlin, you'll be happy to know that Kotlin comes with a variety of transformation functions that can make your life a lot easier.

🧪 Transformation functions are used to transform one collection into another by applying a given function to each element in the collection. Here are some of the most commonly used Kotlin collections transformation functions, with some code examples to illustrate their use:

## 🤖 **map**: 
This function transforms each element in a collection by applying a given function to it and returns a new collection with the transformed elements. It's like a magic wand for your collections! 🔮

```run-kotlin
fun main(){
    val numbers = listOf(1, 2, 3, 4, 5)
    val doubledNumbers = numbers.map { it * 2 }
    println(doubledNumbers) // [2, 4, 6, 8, 10]
}
```

**map indexed**: Whether you want a given index for the map list:
```run-main
fun main(){
    val numbers = setOf(1, 2, 3)
    println(numbers.map { it * 3 })
    numbers.mapIndexed {i, value -> 
        println("index: $i  value: $value")
    }
}
```

For non null values:
```run-main
fun main(){
    val numbers = setOf(1, 2, 3)
    println(numbers.mapNotNull { if ( it == 2) null else it * 3 })
    println(numbers.mapIndexedNotNull { idx, value -> if (idx == 0) null else value })
}
```

Furthermore we can transform the values and the keys of the map list:

```run-kotlin
fun main(){
    val numbersMap = mapOf("key1" to 1, "key2" to 2, "key3" to 3, "key11" to 11)
    println(numbersMap.mapKeys { it.key.uppercase() })
    println(numbersMap.mapValues { it.value + it.key.length })
}
```

## 🧰 zip:
The zip function is a transformation function that allows you to combine two collections into a single collection of pairs. It's like a zipper that connects two separate collections together! 🤏

🧵 Here's an example of how to use the zip function to combine two lists of strings:

```run-kotlin
fun main(){
    val list1 = listOf("apple", "banana", "cherry")
    val list2 = listOf("red", "yellow", "purple")
    val combinedList = list1 zip list2
    println(combinedList) // [(apple, red), (banana, yellow), (cherry, purple)]
    val twoAnimals = listOf("fox", "bear")
    println(combinedList.zip(twoAnimals))
}
```

🧰 The zip function is a handy tool in Kotlin collections that allows you to combine two collections into a single collection of pairs. But did you know that you can also apply a transformation function to those pairs as you combine them? That's where the real magic happens! 🤩

🧵 Let's start with a basic example of using the zip function with a transformation function. We'll combine two lists of strings and concatenate each pair with a dash symbol:

```run-kotlin 
fun main(){
    val list1 = listOf("apple", "banana", "cherry")
    val list2 = listOf("red", "yellow", "purple")
    val combinedList = list1.zip(list2) { fruit, color -> "$fruit - $color" }
    println(combinedList) // [apple - red, banana - yellow, cherry - purple]
}
```

When you have a List of Pairs, you can do the reverse transformation – unzipping – that builds two lists from these pairs:

```run-kotlin
fun main(){
    val numberPairs = listOf("one" to 1, "two" to 2, "three" to 3, "four" to 4)
    println(numberPairs.unzip())
}
```

## 📝 Associate:
The associate function is a useful tool in Kotlin collections that allows you to transform a collection into a map by applying a transformation function to each element. It's like having a magic wand that can turn a list into a dictionary! 🧙‍♀️

🗺️ Let's start with a basic example of using the associate function for transformation. We'll transform a list of integers into a map where the keys are the integers themselves, and the values are the square of each integer:

```run-main
fun main(){
    val list = listOf(1, 2, 3, 4, 5)
    val map = list.associate { it to it * it }
    println(map) // {1=1, 2=4, 3=9, 4=16, 5=25}
}
```

🌟 You can also use the associate function to perform more complex transformations. Here's an example where we transform a list of strings into a map where the keys are the length of each string, and the values are the uppercase version of each string:

```run-kotlin
fun main(){
    val list = listOf("apple", "banana", "cherry", "date", "elderberry")
    val map = list.associate { it.length to it.uppercase() }
    println(map) // {5=APPLE, 6=BANANA, 7=CHERRY, 4=DATE, 10=ELDERBERRY}
}
```

Also you can use the **associateWith**:

```run-kotlin
fun main(){
    val numbers = listOf("one", "two", "three", "four")
    println(numbers.associateWith { it.length })
}
```

For building maps with collection elements as values, there is the function associateBy(). It takes a function that returns a key based on an element's value. If two elements' keys are equal, only the last one remains in the map.

associateBy() can also be called with a value transformation function:
```run-kotlin
fun main(){
    val numbers = listOf("one", "two", "three", "four")

    println(numbers.associateBy { it.first().uppercaseChar() })
    println(numbers.associateBy(keySelector = { it.first().uppercaseChar() }, valueTransform = { it.length }))
}
```

## 🫓 Flatten:

Flattening collections in Kotlin is a useful operation when you have nested collections, and you want to merge all the elements into a single collection. Think of it like a giant smushing machine that takes all your nested collections and flattens them into one.

To use the Flatten function, you just need to call the flatten() method on your collection. Easy peasy! 😎

Here's an example:

```run-kotlin
fun main(){
    val nestedList = listOf(listOf(1, 2), listOf(3, 4), listOf(5, 6))
    val flattenedList = nestedList.flatten()
    println(flattenedList) // Output: [1, 2, 3, 4, 5, 6]
}
```

As you can see, the nested list is flattened into a single list with all the elements in order.

But what if you have a collection of collections of collections? 🤔

No problem! Kotlin's flatten() method is smart enough to handle nested collections of any depth.

```run-kotlin 
fun main(){
    val deeplyNestedList = listOf(listOf(listOf(1, 2), listOf(3, 4)), listOf(listOf(5, 6), listOf(7, 8)))
    val flattenedList = deeplyNestedList.flatten()
    println(flattenedList) // Output: [1, 2, 3, 4, 5, 6, 7, 8]
}
```

Boom! The deeply nested list is flattened into a single list, just like magic. 🧙‍♂️
Flattening collections in Kotlin is a great way to merge all the elements of nested collections into a single collection. But sometimes, you want to do more than just flatten a nested collection. That's where FlatMap comes in!

To use the FlatMap function, you just need to call the flatMap() method on your collection. Here's an example:

```run-kotlin 
fun main(){
    val nestedList = listOf(listOf(1, 2), listOf(3, 4), listOf(5, 6))
    val flattenedList = nestedList.flatMap { it.map { num -> num * 2 } }
    println(flattenedList) // Output: [2, 4, 6, 8, 10, 12]
}
```
In this example, we start with a nested list of numbers and use flatMap() to multiply each number by 2 and flatten the resulting list into a single list of doubled numbers.

But what if you have a more complex nested collection structure? 🤔

No problem! FlatMap can handle nested collections of any depth, just like flatten(). Here's an example:

```run-kotlin
fun main(){
        val deeplyNestedList = listOf(
        listOf(listOf(1, 2), listOf(3, 4)),
        listOf(listOf(5, 6), listOf(7, 8))
    )
    val flattenedList = deeplyNestedList.flatMap { it.flatMap { it.map { num -> num * 3 } } }
    println(flattenedList) // Output: [3, 6, 9, 12, 15, 18, 21, 24]
}
```

In this example, we have a deeply nested list of numbers, and we use flatMap() to multiply each number by 3 and flatten the resulting list into a single list of tripled numbers.

## 🎼 String Representation

When working with collections in Kotlin, it's often useful to convert them to a string representation for debugging or printing purposes. Kotlin also provides the joinTo() and joinToString() functions for converting collections to strings.

Let's take a look at an example of how to use joinToString() on a simple list:

```run-kotlin
fun main(){
    val list = listOf("apple", "banana", "cherry")
    val str = list.joinToString(separator = ", ")
    println(str) // Output: apple, banana, cherry
}
```
n this example, we have a list of fruits, and we use the joinToString() function to convert the list to a string representation. The resulting string is a comma-separated list of fruits.

But what if you want to customize the string representation? 🤔

No problem! The joinToString() function allows you to specify various parameters to customize the string representation, such as the separator, prefix, and postfix. Here's an example:

```run-kotlin
fun main(){
    val list = listOf("apple", "banana", "cherry")
    val str = list.joinToString(
    separator = " - ",
    prefix = "Fruits: ",
    postfix = " are delicious!"
)
    println(str) // Output: Fruits: apple - banana - cherry are delicious!
}
```
In this example, we use the joinToString() function to create a string representation of a list of fruits. We specify a custom separator, prefix, and postfix to make the string representation more informative and fun.

Kotlin also provides the joinTo() function, which works similarly to joinToString() but appends the result to a given StringBuilder object. Here's an example:

```run-kotlin
fun main(){
    val list = listOf("apple", "banana", "cherry")
    val sb = StringBuilder()
    list.joinTo(sb, separator = ", ")
    println(sb.toString()) // Output: apple, banana, cherry
}
```
In this example, we use the joinTo() function to append the string representation of a list of fruits to a StringBuilder object.

So the next time you need to convert a collection to a string representation in Kotlin, remember to use the joinToString() or joinTo() function. They're like Swiss Army knives for converting collections to strings! 😂