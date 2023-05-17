---
layout: default
parent: Collections
title: Grouping
nav_order: 6
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>

# 📝 Grouping Collections with Kotlin
### Embrace the Power of 🎊 Squads and 🎉 Parties

## Introduction:
Hey there, Kotlin aficionados! Today, we're diving into the exciting world of grouping collections with Kotlin. 🥳 Get ready to become the life of the party as we explore how Kotlin's expressive syntax and supercharged functions can help you create squads of elements in your collections. 🕺💃 So put on your dancing shoes and let's get grooving!

## Grouping Basics
Before we hit the dance floor, let's get familiar with the basics of grouping. Grouping is all about organizing elements in your collection based on a common attribute, like gathering your friends based on their favorite pizza toppings. 🍕 It's like creating mini tribes within your collection, each with its own unique identity.

## Grouping with Kotlin's groupBy()
Kotlin's groupBy() function is your ultimate party planner when it comes to grouping collections. It takes a lambda as input and creates a map where the keys represent the common attribute and the values are lists of elements that share that attribute. 🎩✨ Let's take a look:

```run-kotlin
fun main(){
    val people = listOf("Alice", "Bob", "Charlie", "Dave", "Eve")
    val groups = people.groupBy { it.length }
    println(groups)
}
```
Boom! 💥 We've grouped the people by the length of their names. The result is a map where keys represent name lengths and values contain the corresponding names. It's like dividing the party into tables based on the number of characters in people's names. Let the mingling begin!

## Grouping with Transformations: groupBy() + mapValues()
Now, let's crank up the party vibes by adding a touch of transformation to our groups. With Kotlin's mapValues() function, we can unleash the power of customization on our grouped elements. 🎉💫 Check this out:

```run-kotlin
fun main(){
    val numbers = listOf(1, 2, 3, 4, 5)
    val groups = numbers.groupBy { it % 2 }.mapValues { (_, values) -> values.map { it * 2 } }

    println(groups)
}
```
Woohoo! 🙌 We've not only grouped the numbers by their evenness (0 for even, 1 for odd), but we've also doubled the values within each group. It's like throwing a party where each group has its own unique dance move. Let's see those moves!

## Grouping with Multi-level Keys: groupBy() + Pair
Sometimes, a single attribute isn't enough to capture the complexity of your collection. Fear not, for Kotlin has the perfect solution! By using groupBy() in combination with Pair, we can create multi-level keys for our groups. 🤝✨ Here's an example:

```run-kotlin
fun main(){
    val people = listOf("Alice", "Bob", "Charlie", "Dave", "Eve")
    val groups = people.groupBy { Pair(it.length, it.first()) }
    println(groups)
}
```
Voilà! 🎉 We've created groups based on both the length of the names and the first letter of each name. It's like throwing a party where each group has its own secret handshake. Party on!

## The Power of Grouping: Creating Unforgettable Experiences
Grouping collections with Kotlin isn't just about organization—it's about creating memorable experiences. With the ability to group and transform, you can orchestrate incredible interactions within your collections. It's like being the conductor of a grand symphony, bringing together harmonious elements. 🎵🎻

### REFERENCES:

[https://kotlinlang.org/docs/collection-grouping.html](https://kotlinlang.org/docs/collection-grouping.html)