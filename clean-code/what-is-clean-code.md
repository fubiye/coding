# What is clean code?

*Note of ***Clean Code****

## Code Quality - WTFs/Minute
![WTF](http://www.osnews.com/images/comics/wtfm.jpg)

## Craftsmanship - knowledge and work
Knowledge - principles and patterns

Work - case study

Summary - smell of code


## What is clean code
>
> I like my code to be ***elegant*** and ***efficient***. The logic should be straightforward to make it hard for bugs to hide, the dependencies minimal to ease maintenance, error handling complete according to an articulated strategy, and performance close to optimal so as not to tempt people to make the code messy with unprincipled optimizations. Clean code does one thing well.  
>
>  -- ***Bjarne Stroustrup***, *inventor of C++ and author of The C++ Programming Language*
>
>Key Points: ***elegant, efficient***.

>
> Clean code is ***simple*** and ***direct***. Clean code reads like well-written prose. Clean code never obscures the designer’s intent but rather is full of crisp abstractions and straightforward lines of control.
>
> -- ***Grady Booch***, *author of Object Oriented Analysis and Design with Applications*   
> 
>Key Points: ***Readability***

> Clean code can be read, and enhanced by a developer other than its original author. It has unit and acceptance tests. It has meaningful
names. It provides one way rather than many ways for doing one thing. It has minimal dependencies, which are explicitly defined, and provides a clear and minimal API. Code should be literate since depending on the language, not all necessary information can be expressed clearly in code alone.
>
> -- ***“Big” Dave Thomas***, *founder of OTI, godfather of the Eclipse strategy*
>
> Key Points: ***Readability，Easy for other people to enhance it, Test, literate***


> I could list all of the qualities that I notice in clean code, but here is one overarching quality that leads to all of them. Clean code always looks like it was written by someone who cares. There is nothing obvious that you can do to make it better. All of those things were thought about by the code’s author, and if you try to imagine improvements, you’re led back to where you are, sitting in appreciation of the code someone left for you — code left by someone who cares deeply about the craft
>
> -- ***Michael Feathers***, *author of Working Effectively with Legacy Code*
>
> Key Points: ***Care***


> In recent years I begin, and nearly end, with Beck’s rules of simple code. In priority order, simple code:
> + Runs all the tests;
> + Contains no duplication;
> + Expresses all the design ideas that are in the system;
> + Minimizes the number of entities such as classes, methods, functions, and the like.
>
> Of these, I focus mostly on duplication. When the same thing is done over and over,it’s a sign that there is an idea in our mind that is not well represented in the code. I try to figure out what it is. Then I try to express that idea more clearly.
>
> Expressiveness to me includes meaningful names, and I am likely to change the names of things several times before I settle in. With modern coding tools such as Eclipse, renaming is quite inexpensive, so it doesn’t trouble me to change. Expressiveness goes beyond names, however. I also look at whether an object or method is doing more than one thing. If it’s an object, it probably needs to be broken into two or more objects. If it’s a method, I will always use the Extract Method refactoring on it, resulting in one method that says more clearly what it does, and some submethods saying how it is done.
>
> Duplication and expressiveness take me a very long way into what I consider clean
code, and improving dirty code with just these two things in mind can make a huge difference. There is, however, one other thing that I’m aware of doing, which is a bit harder to explain.
>
> After years of doing this work, it seems to me that all programs are made up of very similar elements. One example is “find things in a collection.” Whether we have a database of employee records, or a hash map of keys and values, or an array of items of some kind, we often find ourselves wanting a particular item from that collection. When I find that happening, I will often wrap the particular implementation in a more abstract method or class. That gives me a couple of interesting advantages.
>
> I can implement the functionality now with something simple, say a hash map, but
since now all the references to that search are covered by my little abstraction, I can change the implementation any time I want. I can go forward quickly while preserving my ability to change later.
>
> In addition, the collection abstraction often calls my attention to what’s “really” going on, and keeps me from running down the path of implementing arbitrary collection behavior when all I really need is a few fairly simple ways of finding what I want.
>
> Reduced duplication, high expressiveness, and early building of simple abstractions. That’s what makes clean code for me.
>
> -- ***Ron Jeffries***, *author of Extreme Programming Installed and Extreme Programming Adventures in C#*
>
> Key Points: ***No duplication, one thing, expressiveness, tiny abstractions.***

## The Boy Scout Rule

***Leave the campground cleaner than you found it.***
