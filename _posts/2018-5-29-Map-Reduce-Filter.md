---
layout: post
title: Map, Filter & Reduce, Explained Visually
date: 2018-05-29
---

The words "map", "filter" and (*brace yourself*!) "reduce" have a strange mystique among programmers. But they're worth getting to know. In many languages, these techniques offer a concise and straightforward syntax for common data transformations. **The purpose of this post is to demystify map, filter and reduce with some simple visual examples.**

All three techniques are useful when dealing with a data structure with multiple elements, like a list. In this blog post, we'll be playing with this beautiful and oh-so-meaningful series of squares:

![Series of squares](/images/map-filter-reduce/squares.png){: .center-image.small}

We'll also need a way to express rules for transforming elements of the series. We'll use a simple visual syntax to represent input and output:

![Square -> triangle function](/images/map-filter-reduce/map2f.png){: .center-image.small}

{: .caption}
Input: square. Output: triangle.

Let's get started!

## Map
Sometimes, we want to apply a transformation to every item in a set of data. For example, maybe we have a list of squares, and we want to produce a list in which each square is a few shades lighter. To generalize, we want to apply a rule like this...

![Dark -> light function](/images/map-filter-reduce/map1f.png){: .center-image .small}

...to every element. For example:

![Map illustration](/images/map-filter-reduce/map1.png){: .center-image}

{: .caption}
Squares mapped to lighter squares.

Mapping is the process of applying a single rule to every element in a data structure. The resulting data structure has **the same shape and size** as the original: if we start with a list of four items, we know we'll end up with a list of four items.

## Filter
Sometimes, however, we want a version of our data structure with *fewer* elements that the original. Maybe we have a bunch of squares, but we're only interested in the purple ones.

In this case, we need to specify a rule that produces a boolean - either "**true**, keep me" or "**false**, throw me away." In our case, we'll test whether a square is purple:

![Is purple function](/images/map-filter-reduce/filterf.png){: .center-image.small}

With a filter, we can apply this test to every square in the series, and produce a new series with only the squares that passed the test:

![Filter illustration](/images/map-filter-reduce/filter.png){: .center-image}

{: .caption}
Pink & purple squares filtered to purple squares

Filtering **maintains the shape but not necessarily the size** of the original data structure. If we start with a list of 4 items, we will produce a list with 4 *or fewer* items.

## Reduce

Unlike map and filter, reduce provides an opportunity to **change the shape** of the original data structure. Maybe we have a series of squares that we want to turn into a vertical block.

In this case, we need to write a rule that specifies the relationship between **(1)** the new data structure we are building and **(2)** a given element of the list. For example, let's say every time we hit a new element, we want to stick it to the bottom of our vertical block:

![Function for adding square to vertical block](/images/map-filter-reduce/reducef.png){: .center-image.small}

With reduce (also known as *fold*), we can go through our series of squares, repeatedly applying this rule. First, we place a purple square at the bottom of an empty vertical block:

![Reduce illustration step 1](/images/map-filter-reduce/reduce1.png){: .center-image}

Then we move on to the pink square and place it at the bottom of the block we've started building:

![Reduce illustration step 2](/images/map-filter-reduce/reduce2.png){: .center-image}

...and on to the next purple:

![Reduce illustration step 3](/images/map-filter-reduce/reduce3.png){: .center-image}

..until we get our final result!

![Reduce final result](/images/map-filter-reduce/reduce.png){: .center-image}


{: .caption}
Pink & purple squares reduced to vertical line

## Beyond the World of Colorful Squares
Map, filter and reduce are useful for all kinds of real-world data transformations:
* Map a list of user record sets to just usernames!
* Filter a list of users to just active users!
* Reduce a list of users to a dictionary, with ids as keys, for faster lookups!

There are, of course, plenty of other ways to accomplish these transformations, depending on the language: for loops, while loops, recursion, list comprehensions, etc. But map/filter/reduce can offer concise syntax and mental short-cuts for these common programming tasks.
