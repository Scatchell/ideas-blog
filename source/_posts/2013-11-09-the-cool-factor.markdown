---
layout: post
title: "The Cool Factor"
date: 2013-11-09 15:37
comments: true
categories: 
- cool
- it-industry
- technology
- psychology
---
*(This post is still an unfinished draft)*

I often find myself wondering about and/or having conversations with others concerning the classic breadth vs depth decision. To explain, let's say you have 100 hours to learn some things - and you could choose either to:

- Learn 15 different things given these 100 hours, but all of them only to a relatively shallow degree
- Learn only 1 or 2 things with these 100 hours, but learning them to an extremely great depth

So, which would you choose? Especially working in the IT industry, one that changes particularly quickly (making information about it seem inherently transient), this question becomes quite interesting.

###The Answer:
If you ask this question to almost anyone, inside or out of the IT industry, you'll likely get the same answer. Can you guess what it is?
<!-- more -->

> "A happy median between depth and breath!"

...or

> "T-Shaped people, who are generalists amongst a wide array of skills but experts in only a few""

Or other such answers of similarly indescribable brilliance and specificity. I would like to make clear that I think this answer is **bullshit**, and that, in most cases, it should be viewed as nothing less.

It's a valid and useful answer in the sense that it's an important thing to strive for - of course we want to make an attempt to achieve perfection. But, I also feel it's a little bit like the president asking his chief economic advisor "What should we do about balancing the budget?" and getting the response "We should make sure we don't waste money on bad things, and spend it only on good things!" It's a nice idea but, how helpful is it, really?

So, let us put aside the obvious answer of "be perfect" and instead consider more realistic concerns.

###The Slightly Less Bullshit Answer:
To try and give a less bull-shitty answer, I will suggest the following.

In the IT industry, I believe there is an unspoken influence which places a stronger focus on depth than on breadth. I will also argue that I think this is wrong, and not only potentially dangerous to the industry as a whole, but also particularly dangerous to consulting firms - the reasoning of which I will try to detail shortly.

I feel safe suggesting such a hard opinion because I don't insult the general ideology of depth being 'better' than breadth, but instead I insult the mechanism that I believe often causes this decision to be made. I believe this mechanism is:

###The Cool Factor
![The Cool Factor](/images/don_draper_is_cool.png)

The cool factor can be explained with a simple example. Take two programming concepts:

**_Concept A_**: Learning basic array manipulation in C, Java, Python, Ruby, JavaScript, etc.

------

**_Concept B_**: Knowing a pointer based programming language well enough to use pointer arithmetic to alter the values of an array tersely
 
*Concept A* is something about any programmer will know, iterating and manipulating arrays in a variety of ways, i.e.
- Mapping an array to add 1 to every element
- Initializing arrays with a set of values
- Iterating and selecting a particular element from an array.

This is just a **good** idea. It's relatively simple, and has incredible utility with almost every aspect of programming.
  
*Concept B* is something that fewer programmers know about. I also think we can safely this concept is much less useful than Concept A. It's a more complex idea, and it's likely you will run into this technique only after working with a pointer based language like C for a relatively long time. Additionally, it will only legitimately be useful in a small number of cases.
   
Now - imagine you ask some fellow developer to tell you about some concept, any concept, concerning programming. What would be a "cooler" response?  If they responded with and explained Concept A, general array manipulation, or Concept B, using pointer arithmetic to manipulate arrays? I think the answer is rather obvious, it would be much cooler to tell someone a lesser known technique like Concept B. 

Thus we describe a "technical coolness" as follows:

![Technical Coolness](/images/technical_coolness.png)

(Admittedly the use of the word 'cool' in this example is a bit ridiculous :-P.)

This elucidates the "cool factor", which is simply the following phenomenon:

###People think it's incredibly cool to know useless things. 

As a matter of fact, the useless things are MUCH cooler to know than the useful things. 

This is clearly illustrated in a few points:

1. The more useless something is, the harder it is to learn and remember (because it is never employed, and is so useless that it is rare to come by).
2. The harder it is to learn, the less people who will know it.
3. The less people who know a concept, the cooler it is to know (because you will be one of the few with this knowledge).

Thus we can conclude: People are infinitely impressed by useless knowledge

Think about it...if an idea is useful - truly useful - it inherently must spread like wildfire through an industry. In the software development industry, mocking and stubbing, writing tests for large code bases, cloud based storage - these concepts spread incredibly easily and quickly. Other concepts though, remain known by only a few. Why? Because for God's sake, they *shouldn't* spread. They are utterly useless in all but an extremely small subset of problems, and are not ubiquitously applicable like the good ideas are. And the shitty part is, this is exactly why they are so damn cool.

The cool factor seems to be particularly ubiquitous in the software industry, and I believe it's one of the reasons we often get people being more desirous of a very depth-full understand of tech, so they can obtain more of this "cool" (useless) knowledge and impress people with that knowledge. I also think this is a serious problem that needs to be solved.

###Why is this an issue?

Oh, lots of reasons. The critical one being it drives people toward spending their valuable time learning useless but impressive technical concepts, and the coolness of these topics leads them to in turn spread much more quickly than they actually should. The waste of time is one issue but, even worse is when people start to use these concepts just because they think they are so cool. Then we have tools and techniques being utilized to solve a problem that have absolutely no place in. I.E. writing a large project in vim with all "refactoring tools" vim macros built by hand. Cool? Definitely. Useful and time saving? Quite the opposite (this coming from someone writing this entire post in vim). 

Imho, the problem is particularly dangerous in the consulting industry because we are not there to show off how many awesome, bad ass tools and techniques we can use. Instead, we're there to solve some problem as quickly, efficiently, and most important: **simply** as possible so that code can be quickly in working order, easy to change, and easily handed over to our clients. Bringing guava into a project and upgrading to Java 8 so we can use a hash whose values are functions to solve a relatively simple sorting problem is cool, but is it really necessary? Is it really the simplest and easiest thing we can do to solve that sorting issue for our clients?

###So, what to do?
Per the norm, exposing and ridiculing a problem is infinitely easier (and less fun :-P) than offering solutions for it. But, let's give it a shot:

1. Control yourself. If some new technology or tool is cool, ONLY use it if it will really offer value in that particular solution. Don't be seduced by the coolness.
2. Have someone review your code. If it takes them more than a few minutes to understand it, it might be unnecessarily complex. This one is dangerous, because the reviewer very well may say "Wow, that is AWESOME!" but, keep in mind, this is NOT GOOD...even though we'd love it to be.
3. Start off with the simplest solution possible. If it works, and keeps the code extensible and easily changeable, avoid at all costs refactoring it to the 'cooler' version.
