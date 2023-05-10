---
layout: default
parent: Collections
title: Iterators
nav_order: 0
---
<script src="https://unpkg.com/kotlin-playground@1" data-selector="code"></script>

# So, what are Iterators in Kotlin? 
### Well, an iterator is like a tour guide that takes you through a collection of data one item at a time. 🚶‍♂️🚶‍♀️

Let's say you have a list of your favorite ice cream flavors. 🍦🍨 You can use an iterator to loop through the list and visit each flavor, one by one. The iterator will keep track of where you are in the list and make sure you don't miss any flavors. 🤤

To use an iterator in Kotlin, you first need to create one. You can do this by calling the iterator() method on your collection. This will return an Iterator object that you can use to loop through your data. 🔄

Here's an example:

```run-kotlin
fun main(){
    val flavors = listOf("Vanilla", "Chocolate", "Strawberry")

    val flavorIterator = flavors.iterator()

    while (flavorIterator.hasNext()) {
        val flavor = flavorIterator.next()
        println(flavor)
    }
}

```

In this example, we create an iterator for our list of ice cream flavors and then loop through the list using a while loop. We call hasNext() to check if there are any more flavors in the list, and then call next() to move the iterator to the next flavor and get its value.

## Now, let's add some humor to this iterator business. 🤣

Think of the iterator as a waiter at a fancy restaurant. 🍴 They bring you one dish at a time, and you savor each one before moving on to the next. The waiter keeps track of which dish you've had and makes sure you don't miss any. 🧐

But what if the waiter gets distracted by a beautiful customer and forgets which dish they brought you last? 😍 That's where the iterator's hasNext() method comes in handy. It reminds the waiter which dish to bring next, so you don't end up with two servings of chocolate ice cream. 🤦‍♂️

And if the waiter brings you a flavor you don't like, you can politely ask for a different one using the iterator's remove() method. 🙏

In summary, iterators are a great way to loop through collections of data in Kotlin. They keep track of where you are in the collection and make sure you don't miss any items. And if you think of them as fancy waiters, they can even add a bit of humor to your code! 😄

#### REFERENCES:
[https://www.geeksforgeeks.org/kotlin-collections/](https://www.geeksforgeeks.org/kotlin-collections/)
[https://kotlinlang.org/docs/iterators.html#mutable-iterators](https://kotlinlang.org/docs/iterators.html#mutable-iterators)
[https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-collection/](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-collection/)
[https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-iterable/](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-iterable/)
