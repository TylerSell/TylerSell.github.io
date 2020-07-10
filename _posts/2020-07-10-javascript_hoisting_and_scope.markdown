---
layout: post
title:      "JavaScript Hoisting and Scope"
date:       2020-07-10 19:40:38 +0000
permalink:  javascript_hoisting_and_scope
---


A couple of concepts we all wrestle with in Javascript are Hoisting and Scope.  If you do not fully understand these 2 different aspects of JavaScript you can easily drive yourself mad trying to find a bug in your code that you don't see because you don't understand what is going on under the hood.  Today we will look at Hoisting and Scope and try to demystify them both so you have a better understanding of what is going on so you can avoid issues in the future.

## Hoisting

Basically what Hoisting is, is simple.  When your JS code is compiled (read) it lifts (or Hoist) all the `var` declarations to the top of their scope whether it be local or global.  But lets be clear here it only lifts the declaration or name of the `var` to the top of the scope and not the value of the `var`.  Let's see an example:

```
console.log(myVar);
var myVar = 2;
```

We expect this to return an error on the `concole.log` that `myVar` is not defined and give us a reference error.  Instead we get back `undefined` when we run this code since JavaScript hoists the name `myVar` to the top but not its value thus we get undefined.  Wow that seems simple to say but it is hard to visualize so let's look at what it is essentially doing when we run the above code.

This code:
```
console.log(myVar);
var myVar = 2;
```

Compiles or is Read as:
```
var myVar;
console.log(myVar); //undefined
myVar = 2;
```

That makes more sense.  This makes it easier to understand how and when our variable declararations are used with their value.   This is why we want to always use `let` and `const` whenever possible.  They will give a Reference Error if we try to call them before their value is assigned.  This also brings us to the topic of scope that goes hand in hand with hoisting.

## Scope

In JavaScript there are two scopes:

1. Global Scope

2. Local Scope 

### Global Scope

Global Scope means that a `var` `let` or `const` declaration made outside of any function or class is accessable to all functions and classes in the document.  

So in short if you have a `var` `let` or `const` that you want to be available everywhere in the document you would want to declare it outside of any function or class and ideally you would want to declare it at the top of the document so that your code is easier to read and maintain.  It also leaves no doubt as to which scope it is in.  And comments do not hurt to make your life easier in the future when something breaks or you need to add more funcitonality.  

```
let myVar = 2; //global variable(defined outside any function)

function myFunction() {
   console.log(myVar)
}

myFunction(); //returns 2
```

### Local Scope

Local scope is any variable that is declared within a function is limited to the local scope only and not outside of that function.  So basically if you declare a `var` `let` or `const` inside a function the only way to get the value of that variable to do anything with it would be to call the function you could not call variable directly.

```
function myFunction() {
   let myVar = 2; //local variable(defined inside a function)
	 return myVar;
}

console.log(myFunction()); //returns 2
console.log(myVar); //returns Uncaught ReferenceError: myVar is not defined
```

Do you see the difference.  When you see how the code is interperated and compiled it makes it easier to understand where and how your variable are used.

I hope this gives you some insight also into some errors you may run into.  I know that this subject took me a moment to understand and I fought through some brutal errors to learn this and truth be told when writing this post I gained an even better understanding of the concepts while trying to explain it to somebody else.  
