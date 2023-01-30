---
title: "Getting Started With Ruby Arrays For Beginners"
layout: post
post-image: "https://mikechilson-blog-assets.s3.amazonaws.com/ruby.jpeg"
description: An introduction to Ruby arrays
tags:
- Ruby
- Rails
- Programming
---

### What exactly is an Array? ###

Arrays are objects (remember everything is an object in Ruby) that can store multiple values such as numbers or strings. Simplified, an array is a collection or list of things. Arrays are generally used to hold a collection of data that needs to be displayed or manipulated by your program. Their data can come from any source, user input, databases, or computed values. In Ruby (like many other languages), arrays are ordered, integer-indexed collections of any type object. This means that each element in an array is associated with and referred to by an index value within the array. Oh, and Ruby arrays are Zero-based so the first element is index 0, not 1.

![array example](https://mikechilson-blog-assets.s3.amazonaws.com/array_1.png)


### Creating an Array ###

There are two ways to create an array in Ruby. Literal Constructor and a Class Constructor. 

![array literal](https://mikechilson-blog-assets.s3.amazonaws.com/array_2.png)
The literal constructor is an array that we literally create as the square brackets denote an array.

![array class](https://mikechilson-blog-assets.s3.amazonaws.com/array_3.png)
The class constructor also creates a new array, but by using the Ruby Array class. 

It should be noted that both of these methods of creating an array produce an empty array.

### Working with Ruby Arrays ###

There are several methods you use to do basic manipulation of an array. Let's cover a few of them here.

**Adding to an Array**
After your Array is created, you can add additional items to your array in the following ways:

**push**
The push method is used to push the given element at the end of the given array and returns the array itself with the pushed elements.

![push method](https://mikechilson-blog-assets.s3.amazonaws.com/array_4.png)

You can also use the shovel method << to add an element to an array.

![shovel method](https://mikechilson-blog-assets.s3.amazonaws.com/array_5.png)

The string 'Lenny' is pushed into the end of the array by both of these methods.

**unshift**
This method is used to insert the given element into the array but at the beginning of the array (index[0]).

![unshift method](https://mikechilson-blog-assets.s3.amazonaws.com/array_6.png)

**length**
The length method will count the elements in the array and return you that number. The length method will count all the elements in the array and return that number.
![length method](https://mikechilson-blog-assets.s3.amazonaws.com/array_7.png)

**reverse**
This method will reverse the elements in the array that it is being called on. The last element in the array will now be the first, the first will be the last and so on until the whole array is reversed.
![reverse method](https://mikechilson-blog-assets.s3.amazonaws.com/array_8.png)

**clear**
This method empties the array. It removes all elements.

![reverse method](https://mikechilson-blog-assets.s3.amazonaws.com/array_9.png)

These are what I consider to be the "bare-bone" methods you will use with arrays in Ruby. For more methods be sure to check out the Ruby documentation at Ruby-Doc.org. I have linked to the 2.6.5 version, but other versions are available there.

[Link To Array Class in Ruby Docs.](https://ruby-doc.org/core-2.6.5/Array.html)

Good luck!
Mike