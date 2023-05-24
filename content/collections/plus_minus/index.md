---
layout: default
parent: Collections
title: Plus and Minus operators
nav_order: 6
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>
## 😄📝 Minus and Plus Operators 😄📝

## 1️⃣ The Minus Operator:
====================

Ah, the Minus operator, the magician of Kotlin Collections! With a flick of its wand, it can make elements disappear from our collections like they're in an invisible cloak! 😲🔮

Let's take a peek at its magical syntax:

```run-kotlin
fun main(){
    val myCollection = listOf("Harry", "Hermione", "Ron", "Luna")
    val updatedCollection = myCollection - "Ron"

    println(updatedCollection)
}
```
Voila! 🎩✨ In just one line of code, "Ron" is gone from our collection, leaving us with a renewed and Ron-free collection! 💪🚫

Oh, but that's not all! The Minus operator isn't just a one-trick pony. It can perform its vanishing act with multiple elements at once! Just look at this enchanting example:

```run-kotlin
fun main(){
    val troublesomeTrio = setOf("Fred", "George", "Percy")
    val peacefulTrio = troublesomeTrio - setOf("Fred", "Percy")

    println(peacefulTrio)
} 
```
Abracadabra! ✨🐇 Our troublesome trio now becomes a peaceful duo with just one swipe of the Minus operator! Isn't that simply magical? 🎩🔥

## 2️⃣ The Plus Operator:
==================

Ah, now it's time to meet the Plus operator, the master of union in Kotlin Collections! This operator knows how to bring different collections together, like a social gathering of elements! 🎉🤝

Let's unravel the mystery of its syntax:

```run-kotlin
fun main(){
    val collection1 = listOf("apple", "banana", "orange")
    val collection2 = listOf("grape", "kiwi")
    val combinedCollection = collection1 + collection2

    println(combinedCollection)
}
```
Ta-da! 🎉🌟 By using the Plus operator, we've merged collection1 and collection2, resulting in a delightful fruit salad of elements in combinedCollection! 😋🍇🍌🍊🥝

And guess what? The Plus operator is not limited to just two collections. It can handle multiple collections with ease, creating a grand symphony of elements! Here's a charming example:

```run-kotlin
fun main(){
    val collectionA = setOf("sun", "moon")
    val collectionB = setOf("stars", "comets")
    val collectionC = setOf("galaxy", "nebula")
    val universeCollection = collectionA + collectionB + collectionC
}
```
Voilà! 🌌🌟 Our universe collection is formed by merging collectionA, collectionB, and collectionC. Now we have a celestial amalgamation of elements, creating a cosmic masterpiece! 🪐✨

With the Plus operator, the possibilities are endless. It's like a magical potion that can blend collections together, resulting in marvelous combinations! 🧪🔮

So, go ahead, embrace the power of the Plus and Minus operators, and let your Kotlin Collections flourish with their enchanting abilities