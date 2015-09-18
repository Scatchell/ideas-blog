---
layout: post
title: "The Cool Factor"
date: 2013-11-09 15:37
comments: true
categories: 
- IT industry
- technology
- psychology
---
*(This post is still an unfinished draft)*

I often find myself having conversations with colleagues around the classic breadth vs depth conundrum. To explain it with a quick example, let's say you have 100 hours to learn some things - and you could choose to either spend the entire 100 hours:

- Learning 15 different things, but only to a relatively shallow degree
- Learn only 1 or 2 things, but to an much richer depth

So, which would you choose? Especially working in the IT industry, one that changes particularly quickly (making the industry specific information seem inherently transient), this question becomes quite interesting.

###The "Answer":

Just to get this out of the way: If you ask this question to almost anyone, inside or out of the IT industry, you'll likely get the same answer. Can you guess what it is?
<!-- more -->

> "A happy median between depth and breath!"

...or

> "T-Shaped people, who are generalists amongst a wide array of skills but experts in only a few"

Or other such answers of equal brilliance and specificity. I would like to make clear that these are not answers to the original question, but are simply clever ways to avoid answering a difficult question.

It is valid and useful in the sense that perfection is an important ideology to *strive* for... But, it's also a bit like the president of some country asking their chief economic advisor "What should we do about balancing the budget?" and getting the response "We should make sure we don't waste money on bad things, and spend it only on good things!"

Cute statements like that are very easy to agree with but, without detail and a touch of realism, are they really helpful?

So, putting aside the answer of "be perfect"...

###The Slightly Less Bullshit Answer:

In the IT industry, I believe there is an unspoken cultural norm which places a stronger focus on depth than on breadth. Below, I will argue why I think this is not only wrong, but potentially dangerous to the IT industry as a whole (particularly so for software consulting firms.)

That sentence made use of a pretty black and white word: ‘*wrong*’. However, I don't feel bad suggesting such a hard opinion because I don't insult the general ideology of knowledge depth being 'better' than breadth, but instead I want to insult the mechanism I believe often causes people to choose depth.

This mechanism is...

<div style="text-align: center;">
  <img style="width: 400px;" src="/images/don_draper_is_cool.png" alt="The Cool Factor">
  
  <p style="text-align: center; font-size: 1.2em;">The Cool Factor</p>
</div>

The cool factor can be explained with a simple example. Take two programming concepts:

-----

**_Concept A_**: Knowing basic array manipulation in C++, Java, Python, Ruby, JavaScript, etc.

**_Concept B_**: Knowing a low level pointer based programming language well enough to use pointer arithmetic to alter the values of an array tersely

-----

*Concept A* is something just about any programmer will know, iterating and manipulating arrays in a variety of ways, i.e.

- Initializing arrays with a set of values
- Iterating and selecting a particular elements
- Mapping over a list to add 1 to every element

These are damn good ideas. They're simple, and have incredible utility with almost every piece of software you might want to write.

*Concept B* is something that fewer programmers know inside and out. I also think we can safely say it is less useful than Concept A to the average developer. It's a more complex idea, and it's likely you will run into this technique only after working with very specific types of languages for quite some time.

Maybe most critically, it will only be legitimately useful (i.e. no other good, simple way to solve the problem) in a comparatively tiny number of cases.

Now - imagine you ask some fellow developer to tell you about some concept, any concept, concerning programming. What would be a "cooler" response?  If they responded with and explained *Concept A*, basic array manipulation, or *Concept B*, using pointer arithmetic to manipulate arrays? Of course, it would be **much** cooler to tell someone a lesser known trick like Concept B.

Thus we describe a "technical coolness" of the two topics as follows:

![Technical Coolness](/images/technical_coolness.png)

This elucidates the "cool factor", which is simply the following phenomenon:

###It's incredibly cool to know useless things.

Clearly illustrated in a few points:

1. The more useless something is, the **harder it is to learn** and remember (it is seldom employed, and is so useless that it is rare to come by).
2. The **harder it is to learn**, the **less people who know it**.
3. The **less people who know** a concept, the **cooler** it is to know (you will be one of the few with this knowledge).
4. Thus we conclude: People are infinitely impressed by useless knowledge.

Think about it...if an idea is useful - truly useful - it inherently must spread like wildfire through an industry. In the software development industry things like mocking and stubbing, writing tests for large code bases, cloud based storage - these concepts spread incredibly easily and quickly because they are so awesome.

Other concepts though, remain known by only a few. Why? Because for God's sake, they *shouldn't* spread. Usually they have been long replaced by much better ideas, and are useless in all but an extremely small subset of problems. Most annoying of all, this seems to be exactly why they are so cool.

The cool factor seems to be particularly pervasive in the software industry, and I believe it's one of the reasons we often get people being more desirous of a very depth-full understanding of tech, so they can obtain more of this deep, "cool" (useless) knowledge and impress others with that "expertise."

I also feel this is a pretty serious problem.

###Why would this be an issue?

The critical reason simply being: It drives people toward spending their valuable (and limited) time learning useless but impressive technical concepts. There is a great opportunity cost, here. Additionally, the coolness of these topics leads them in turn to spread via conversation much more quickly and efficiently throughout the industry than they actually should.

Wasting time learning this useless knowledge is one thing but, much worse is when people start to actually **use** these concepts because they think they are so cool. This leads us to employ tools and techniques to solve problems they have no place in. I.E. writing a large project in vim with all the "refactoring tools" vim macro's built by hand. Cool? Definitely. Useful and time saving? Quite the opposite (from someone writing this post in vim :) ).

Think of how destructive this would be in a team of 10 people where only 5 are vim ninja's and the other 5 are unfamiliar with the tool. And that’s a problem that won't be spoken about, of course, because the 5 who are weaker with vim will be disincentivized from speaking up...given the incredibly uncool nature of suggesting a fat, memory intensive IDE alternative...how dare they!

The problem is particularly dangerous in the consulting industry. As much as we hate it, we are not there to show off how many awesome, bad ass tools and tricks we can use in a project. Instead, consultants are usually hired to solve some problem as quickly, efficiently, and (maybe most important) **simply** as they can. Bringing [guava](https://code.google.com/p/guava-libraries/wiki/FunctionalExplained) into a project, and upgrading to Java 8 so we can use a hash whose values are functions to solve a relatively simple sorting problem is cool, but is it really the best thing we can do to solve that sorting issue for our clients?

###So, what to do?

Per the norm, exposing and ridiculing a problem is infinitely easier (and more fun) than offering any solutions for it. But to give it a shot:

1. When you come across an idea that seems incredibly cool - stop yourself from exploding in excitement and telling everyone around you how awesome it is. Instead:
    - Try to think of two good ways to use the idea to solve problems you've had before in a way that's significantly better than other methods
    - Consider how easily you would be able to understand the concept if you had never seen or heard of it before, but saw it in code

   If you can't easily do both of the above - then no matter how cool it is, don't use it.
2. Have someone review your code from time to time. If it takes them too long to understand a certain part, it might be due to the unnecessary complexity of something "cool" you are using there.
   - If the reviewer says "Wow, that is AWESOME!" once they finally figure out what the hell is happening, this is **not** good - it is the opposite of good and is instead an indicator you should look more closely and make sure the coolness didn't blind your better judgement.
3. If someone tells you of a new technology or tool that is cool as hell, don't get all excited and start using it everywhere. Don't be seduced by the coolness.

So then, go off into the world and fearlessly be uncool!
