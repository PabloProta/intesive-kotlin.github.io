---
layout: default
parent: Collections
title: Collections Part
nav_order: 6
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>

# 😄 Fun with Collection Operations in Kotlin! 🎉
Retrieve Collection Parts 🕵️‍♀️
Sometimes you just need to fetch specific parts from a collection. Fear not, Kotlin has got your back with some handy operations! Let's take a look at them:

## Slice and Dice! 🍕
Ever wanted to slice a collection like a pro pizza chef? 🍕 Say hello to slice! 🥳 It allows you to extract a range of elements from a collection and create a brand new one. It's like cutting slices of salami from a delicious pizza! 🍕✂️

```run-kotlin
fun main(){
    val pizzaSlices = listOf("Pepperoni", "Margherita", "Hawaiian", "Supreme", "Veggie")
    val tastySlices = pizzaSlices.slice(1..3)
    println(tastySlices) // Output: [Margherita, Hawaiian, Supreme]
}
```

In this example, we have a list of pizza slices. By using the slice function with a range from 1 to 3, we extract the second to fourth elements and store them in the tastySlices list. Yum!

## Take It or Leave It! ✋
Want to grab the first few elements from a collection? Or perhaps limit the number of elements you want to retrieve? The take function is here to help! It lets you take a specified number of elements from the beginning of a collection. It's like grabbing the tastiest chocolate chip cookie from the jar before someone else does! 🍪🙌

```run-kotlin
fun main(){
    val numbers = listOf(1, 2, 3, 4, 5)
    val firstThree = numbers.take(3)

    println(firstThree) // Output: [1, 2, 3]
}
```
Here, we have a list of numbers. By using the take function with an argument of 3, we grab the first three elements and store them in the firstThree list. No one can resist the allure of the first few numbers!

## Drop It Like It's Hot! 🔥
On the flip side, if you want to skip some elements and drop them like a hot potato, drop is your go-to function! It allows you to discard a specified number of elements from the beginning of a collection. It's like saying, "Adios, boring stuff! I'm moving on to the exciting part!" 🚀👋

```run-kotlin
fun main(){
    val fruits = listOf("Apple", "Banana", "Orange", "Mango", "Strawberry")
    val remainingFruits = fruits.drop(2)

    println(remainingFruits) // Output: [Orange, Mango, Strawberry]
}
```

In this example, we have a list of fruits. By using the drop function with an argument of 2, we skip the first two elements and keep the rest in the remainingFruits list. Say goodbye to the initial items and focus on the juicy fruits!

## Chunked and Windowed: Divide and Conquer! 🧩
Sometimes, you want to break down your collection into smaller chunks or windows. Kotlin has got your back with two useful functions: chunked and windowed! Let's take a look:

### Chunked: Divide and Savor! 🧀
The chunked function splits a collection into smaller chunks of a specified size. It's like dividing a delicious cheese wheel into bite-sized pieces! 🧀🍽️

```run-kotlin
fun main(){
    val numbers = listOf(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
    val chunks = numbers.chunked(3)

    println(chunks) // Output: [[1, 2, 3], [4, 5, 6], [7, 8, 9], [10]]
}
```
In this example, we have a list of numbers. By using the chunked function with an argument of 3, we divide the numbers into chunks of size 3 and store them in the chunks list. It's like savoring bite-sized portions of a tasty treat!

### Windowed: Peek-a-Boo! 👀
The windowed function allows you to slide a window over your collection and create sublists. It's like playing peek-a-boo with your elements! 👀

```run-kotlin
fun main(){
    val fruits = listOf("Apple", "Banana", "Orange", "Mango", "Strawberry")
    val windows = fruits.windowed(3)

    println(windows) // Output: [[Apple, Banana, Orange], [Banana, Orange, Mango], [Orange, Mango, Strawberry]]
}
```
Here, we have a list of fruits. By using the windowed function with an argument of 3, we create sliding windows of size 3 and store them in the windows list. It's like revealing a glimpse of the fruits, one window at a time!

Feel free to mix and match these collection operations to suit your needs. Slice, take, drop, chunk, and window your way to collection perfection! 🎉🍕🙌
