---
layout: default
parent: Collections
title: Filtering
nav_order: 5
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>

# 📝 Filtering Collections with Kotlin
### Unleashing the Power of 🧹 and 🎯

## Introduction:
Hey there, fellow Kotlin enthusiasts! Today, we're diving into the awesome world of filtering collections with Kotlin. 🎉 With its powerful features and expressive syntax, Kotlin makes filtering a breeze, allowing you to unleash your inner data ninja while having some fun along the way. 🐱‍👤 So, grab your favorite beverage and get ready to filter like a pro! ☕️

## Filtering Basics
To start our filtering adventure, let's first understand the basics. Filtering is all about finding the elements in a collection that match certain criteria and excluding the rest. 🕵️‍♀️ Think of it as separating the wheat from the chaff, the diamonds from the rough, or the 🍕 toppings from the crust. You get the idea!

## Filtering with Kotlin's Lambdas
Now, let's dive into the juicy part: filtering with Kotlin's powerful lambdas. Lambdas allow you to express your filtering criteria concisely, like a ninja slicing through data with precision. ⚔️ Here's an example:

```run-kotlin
fun main(){
    val numbers = listOf(1, 2, 3, 4, 5)
    val evenNumbers = numbers.filter { it % 2 == 0 }

    println(evenNumbers)
}
```
Boom! 💥 We've just filtered out all the odd numbers, leaving only the even ones. It's like filtering out the non-cat pictures from your camera roll. 📸 Feel the power?

## Chaining Filters with Kotlin
Filtering isn't limited to just one pass; you can chain filters together to refine your results. 🧬 It's like applying a series of Instagram filters to your photos until they're picture-perfect. Here's an example:

```run-kotlin
fun main(){
    val people = listOf("Alice", "Bob", "Charlie", "Dave", "Eve")
    val filteredPeople = people.filter { it.length > 3 }
                          .filter { it.startsWith("A") }
    
    println(filteredPeople)
}
```

Voila! 🎩 We've filtered out the people with names longer than 3 characters and then narrowed it down to those starting with an "A." It's like finding the rarest Pokémon in a crowded Pokédex. Gotta catch 'em all!

## Filtering with Predicates
Sometimes, you need more complex filtering logic that goes beyond simple lambdas. That's where predicates come in. Think of predicates as the Sherlock Holmes of filtering—they can crack the trickiest cases! 🔍

```run-kotlin
fun main(){
    val numbers = listOf(1, 2, 3, 4, 5)
    val divisibleByThree = numbers.filter(::isDivisibleByThree)
}

fun isDivisibleByThree(number: Int): Boolean {
    return number % 3 == 0
}
```
Elementary, my dear Watson! 🧐 We've filtered out the numbers divisible by three using a dedicated function. It's like finding a needle in a haystack using a magnifying glass.

## Supercharged Filtering Techniques

### Filter IsInstance for Type-specific Filtering
Hey, guess what? Kotlin has a hidden superpower called filterIsInstance<T>(). It's like having X-ray vision for your collections, allowing you to filter elements based on their specific type. 🦸‍♂️💪

```run-kotlin
fun main(){
    val mixedList = listOf("Alice", 42, "Bob", 3.14, "Charlie")
    val stringsOnly = mixedList.filterIsInstance<String>()

    println(stringsOnly)
}
```
Whoosh! ✨ With a single line of code, we've filtered out all the non-string elements, leaving only the sweet strings behind. It's like sorting through a pile of clothes to find only your favorite t-shirts. So cool, right?

### Filter Not-So-Null with filterNotNull()
Nulls, oh, nulls. They can be a real headache when filtering collections. But fear not! Kotlin comes to the rescue with the mighty filterNotNull() function. It's like a reliable bouncer at the entrance, making sure only non-null elements get through. 🚫🙅‍♂️

```run-kotlin
fun main(){
    val nullableList = listOf("Alice", null, "Bob", null, "Charlie")
    val nonNullList = nullableList.filterNotNull()   
}
```
Abracadabra! 🎩💫 We've magically eliminated all the nulls, leaving behind a pristine list of non-null values. It's like going through your inbox and filtering out all those annoying spam emails. Bliss!

### The Dynamic Duo: Partition and Conquer
Sometimes, filtering isn't enough. You need to divide and conquer! That's where the dynamic duo of partition comes in. It's like having Batman and Robin team up to tackle the trickiest challenges. 🦇🦸‍♂️

```run-kotlin
fun main(){
    val numbers = listOf(1, 2, 3, 4, 5)
    val (evenNumbers, oddNumbers) = numbers.partition { it % 2 == 0 }
}
```
Bam! 💥 We've partitioned the numbers into two groups: even numbers and odd numbers. It's like splitting your friends into Hogwarts houses. Gryffindor or Slytherin, anyone?

### Test Predicates: Let the Games Begin!
Are you ready for a challenge? Kotlin's got your back with the all, any, none, and count functions. These powerhouses let you test predicates against collections to see if they pass or fail. It's like hosting an Olympic event for your data! 🏋️‍♀️🏅

```run-kotlin
fun main(){  
    val numbers = listOf(1, 2, 3, 4, 5)
    val allEven = numbers.all { it % 2 == 0 }
    val anyEven = numbers.any { it % 2 == 0 }
    val noneNegative = numbers.none { it < 0 }
    val countEven = numbers.count { it % 2 == 0 }

    println("allEven - $allEven")
    println("anyEven - $anyEven")
    println("noneNegative - $noneNegative")
    println("countEven - $countEven")
}
```
Game on! 🎮✨ We can determine if all numbers are even, if any number is even, if none of the numbers are negative, and even count how many even numbers there are. It's like judging your favorite reality show with a panel of judges. You're in control!

## The Power of Filtering: More Than Meets the Eye
Filtering isn't just about getting rid of unwanted elements—it's about unleashing the true potential of your data! With Kotlin's filtering prowess, you can transform collections into precisely tailored subsets. It's like sculpting a masterpiece out of clay! 🎨

### REFERENCES: 
[https://kotlinlang.org/docs/collection-filtering.html](https://kotlinlang.org/docs/collection-filtering.html)