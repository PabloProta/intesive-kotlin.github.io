---
layout: default
parent: Collections
title: Ranges & Progressions
nav_order: 1
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>


# 🧐 What are Ranges in Kotlin?

Ranges in Kotlin are a simple and effective way of defining a set of values. They are represented by the .. operator and consist of a start and end value separated by this operator. For example, 1..10 defines a range from 1 to 10 inclusive.

💡 **Pro tip:** Ranges are often used in for loops to iterate over a sequence of values. They can also be used in conditional statements and other places where you need to define a range of values.

## 🚀 What are Progressions in Kotlin?

Progressions are a type of range that represent a sequence of values with a constant step. They are defined using the rangeTo() function or the step property. For example, 1..10 step 2 defines a progression with a step of 2 between each value.

💡 **Pro tip:** Progressions are useful when you need to generate a sequence of values with a consistent pattern, such as every other number.

## 👨‍💻 How to use Ranges and Progressions in Kotlin?

Using ranges and progressions in Kotlin is easy. Here are a few examples:

```run-kotlin
fun main(){
    // Define a range
    val range = 1..10

    // Iterate over the values in the range
    for (i in range) {
        println(i)
    }

    // Define a progression
    val progression = 1..10 step 2

    // Iterate over the values in the progression
    for (i in progression) {
        println(i)
    }

    // Check if a value is in a range
    val value = 5
    if (value in range) {
        println("$value is in the range!")
    }
}
```
🎉 Congratulations, you now know the basics of using ranges and progressions in Kotlin! 🎉

🤖 One last thing: Did you know that Kotlin also has a downTo operator? This allows you to define ranges that decrease in value, such as 10 downTo 1. Cool, huh? 😎

As I mentioned earlier, progressions are a type of range that represent a sequence of values with a constant step. They are defined using the rangeTo() function or the step property.

In addition to the basic syntax I showed earlier, there are a few other things you can do with progressions in Kotlin.

👉 **Custom Steps**

One useful feature of progressions is the ability to specify a custom step value using the step property. This allows you to create progressions with steps other than 1.

For example, here's how you could create a progression of even numbers from 2 to 10:

```run-kotlin 
fun main(){
    val evenProgression = 2..10 step 2
    for(value in evenProgression){
        println(value)
    }
}
```
This will create a progression that starts at 2, increments by 2, and stops at 10. The resulting progression will be 2, 4, 6, 8, 10.

👉 **Reversed Progressions**

Another handy feature of progressions is the ability to reverse them using the reversed() function. This returns a new progression with the same values but in reverse order.

For example, here's how you could create a reversed progression of odd numbers from 9 to 1:

```run-kotlin
fun main(){
    val oddReversedProgression = 9 downTo 1 step 2
   for(value in oddReversedProgression){
        println(value)
    }
}
```
This will create a progression that starts at 9, decrements by 2, and stops at 1. The resulting progression will be 9, 7, 5, 3, 1.

👉 **Converting Progressions to Lists**

If you need to work with a progression as a list, you can easily convert it using the toList() function. This returns a list of all the values in the progression.

For example:

```run-kotlin
fun main(){
    val progression = 1..10 step 2
    val list = progression.toList()
    println(list)
}
```
This will create a progression of odd numbers from 1 to 9, and then convert it to a list. The resulting list will be [1, 3, 5, 7, 9].

👉 **Summing Progressions**

If you need to sum the values in a progression, you can use the sum() function. This returns the sum of all the values in the progression.

For example:

```run-kotlin
fun main(){
    val progression = 1..10 step 2
    val sum = progression.sum()
}
```
This will create a progression of odd numbers from 1 to 9, and then calculate the sum of all the values. The resulting sum will be 25.


#### REFERENCES:

[https://kotlinlang.org/docs/ranges.html](https://kotlinlang.org/docs/ranges.html)