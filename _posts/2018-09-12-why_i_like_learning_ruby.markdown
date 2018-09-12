---
layout: post
title:      "Why I Like Learning Ruby"
date:       2018-09-12 12:24:26 -0400
permalink:  why_i_like_learning_ruby
---


Hey there.  It's time for the next installment.  I am continuing my journey to becoming a master programmer.  This journey started with Ruby.  First I went through the labs learning the basics of Ruby.  Learning methods, objects, strings, etc. and the proceedures of it all.  Having not taken any coding really in the past it took me longer to understand the proceedures than I would like to admit but I figured it out.  

Next on the journey was object oriented Ruby.  This was nice as it gives you a way to remember information and automate tasks within the class.  Object oriented programming has made the whole world make more sense.  So what do I like about Ruby?

I like Ruby programming thus far for the fact that it is very readable.  When you read the code in Ruby you can truly understand what the code is trying to accomplish.  After learning the basics the code reads like a instruction manual.  Take this following code as an example:  

```
class Test
count = 0

def initialize(name)
    @name = name
		count = count + 1
end
```

This code is creating a class.  The class it is creating is not important at the moment, what is important is what this code is telling us.  It is saying that when we create a new instance of this class we are giving it an argument of `name`.  When that happens we are going to set a variable of `@name = name`.  So far it is very easy to understand.  The next thing we are going to do is add 1 to our `count`.  This means that if we create 5 instances of the `Test` class then our count will equal...............5.

This is extremely easy to read when you are looking at the code.  That is the best part.  The other part of what makes Ruby so nice is that you can do Test Driven Development.  What this means is that when you want to write a program to accomplish anything you first can think of the result that you want to receive.  The next step is write the test for the result that you want to receive.  Then finally you actually write the code to make the tests pass.  

All of these things make me like Ruby as a language.  It also makes life easier for the beginner coder.  This should help me along the way and I can't wait to see what comes next in Ruby magic.
