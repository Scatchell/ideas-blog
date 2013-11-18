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

I often find myself wondering about and/or having conversations concerning the classic breadth vs depth conundrum. To explain it with a quick example, let's say you have 100 hours to learn some things - and you could choose either to:

- Learn 15 different things given these 100 hours, but all of them only to a relatively shallow degree
- Learn only 1 or 2 things with these 100 hours, but learning them to an extremely deep depth

So, which would you choose? Especially working in the IT industry, one that changes particularly quickly (making the industry specific information seem inherently transient), this question becomes quite interesting.

###The Answer:

If you ask this question to almost anyone, inside or out of the IT industry, you'll likely get the same answer. Can you guess what it is?
<!-- more -->

> "A happy median between depth and breath!"

...or

> "T-Shaped people, who are generalists amongst a wide array of skills but experts in only a few""

Or other such answers of equally indescribable brilliance and specificity. I would like to make clear that I think this answer is **bullshit**, and that, in most cases, it should be viewed as nothing less.

It is valid and useful in the sense that perfection is an important ideology to *strive* for - of course we want to make an *attempt* to achieve the best possible solution. But, I also feel it's a bit like the president asking his or her chief economic advisor "What should we do about balancing the budget?" and getting the response "We should make sure we don't waste money on bad things, and spend it only on good things!" It's a nice idea that's really easy to agree with but, how helpful is it, really?

So, let us put aside the answer of "be perfect" and instead consider slightly more realistic concerns.

###The Slightly Less Bullshit Answer:

In the IT industry, I believe there is an unspoken influence which places a stronger focus on depth than on breadth. I will also argue that I think this is wrong, and not only potentially dangerous to the industry as a whole, but also *particularly* dangerous to consulting firms - the reasoning of which I will try to detail shortly.

I feel safe suggesting such a hard opinion because I don't insult the general ideology of depth being 'better' than breadth, but instead I insult the mechanism that I believe often causes this decision to be made <a onclick="$('#hidden-coolness').show()" style="cursor:pointer;">click to see:</a>

<div id="hidden-coolness" style="
display: none;
padding: 15px;
border: 4px dashed black;
">
    <h3>The Cool Factor</h3>

    <img src="/images/don_draper_is_cool.png" alt="The Cool Factor">
</div>
</br>
The cool factor can be explained with a simple example. Take two programming concepts:

**_Concept A_**: Learning basic array manipulation in C, Java, Python, Ruby, JavaScript, etc.

------

**_Concept B_**: Knowing a low level pointer based programming language well enough to use pointer arithmetic to alter the values of an array tersely
 
*Concept A* is something about any programmer will know, iterating and manipulating arrays in a variety of ways, i.e.

- Mapping an array to add 1 to every element
- Initializing arrays with a set of values
- Iterating and selecting a particular element from an array.

This is a damn **good** idea. It's relatively simple, and has incredible utility with almost every program you might want to write.
  
*Concept B* is something that fewer programmers know about. I also think we can safely say it is much less useful than Concept A. It's a more complex idea, and it's likely you will run into this technique only after working with a pointer based language for quite some time. Maybe most critically, it will only be legitimately useful (i.e. no other good way to solve the problem) in a comparatively minuscule number of cases.
   
Now - imagine you ask some fellow developer to tell you about some concept, any concept, concerning programming. What would be a "cooler" response?  If they responded with and explained *Concept A*, basic array manipulation, or *Concept B*, using pointer arithmetic to manipulate arrays? I think the answer is pretty obvious, it would be **much** cooler to tell someone a lesser known technique like Concept B. 

Thus we describe a "technical coolness" of the two topics as follows:

![Technical Coolness](/images/technical_coolness.png)

(Admittedly not the best use of the word 'cool' :-P)

This elucidates the "cool factor", which is simply the following phenomenon:

###It's incredibly cool to know useless things. 

This is clearly illustrated in a few points:

1. The more useless something is, the harder it is to learn and remember (it is seldom employed, and is so useless that it is rare to come by).
2. The harder it is to learn, the less people who will know it.
3. The less people who know a concept, the cooler it is to know (because you will be one of the few with this knowledge).

Thus we can conclude: People are infinitely impressed by useless knowledge.

Think about it...if an idea is useful - truly useful - it inherently **must** spread like wildfire through an industry. In the software development industry things like mocking and stubbing, writing tests for large code bases, cloud based storage - these concepts spread incredibly easily and quickly.

Other concepts though, remain known by only a few. Why? Because for God's sake, they *shouldn't* spread. They are utterly useless in all but an extremely small subset of problems, and are not even close to ubiquitously applicable like the good ideas are. The frustrating part is, this seems to be exactly why they are so damn cool.

The cool factor seems to be particularly pervasive in the software industry, and I believe it's one of the reasons we often get people being more desirous of a very depth-full understand of tech, so they can obtain more of this deep, "cool" (useless) knowledge and impress others with that expertise. I also feel this is a serious problem that needs to be solved.

###Why is this an issue?

Lots of reasons! The critical one being it drives people toward spending their valuable (and limited) time learning useless but impressive technical concepts, and the coolness of these topics leads them to in turn spread via conversation throughout the industry much more quickly and efficiently than they actually should. The waste of time learning useless knowledge is one issue but, even worse is when people start to actually **use** these concepts just because they think they are so cool. This leads us to employ tools and techniques to solve problems they have absolutely no place in. I.E. writing a large project in vim with all the "refactoring tools" vim macro's built by hand. Cool? Definitely. Useful and time saving? I think quite the opposite (coming from someone writing this post in vim).

Further, this would be especially destructive in a team of 10 people where only 5 are vim ninja's and the other 5 are just 'pretty good' with the editor. A problem that won't be spoken about because, of course, the 5 who are weaker at vim will be disincentivized from speaking up...due to the incredibly uncool nature of suggesting a fat, memory intensive IDE. 

I also think the problem is particularly dangerous in the consulting industry. As much as we hate it, we are not there to show off how many awesome, bad ass tools and techniques we can use in a project. Instead, we're there to solve some problem as quickly, efficiently, and most important: **simply** as possible. This is in an effort to get code quickly in working order, easy to change, and easily handed over to our clients. Bringing [guava](https://code.google.com/p/guava-libraries/wiki/FunctionalExplained) into a project, and upgrading to Java 8 so we can use a hash whose values are functions to solve a relatively simple sorting problem is cool, but is it really necessary? Is it really the simplest and easiest thing we can do to solve that sorting issue for our clients?

###So, what to do?

Per the norm, exposing and ridiculing a problem is infinitely easier (and more fun :-P) than actually offering solutions for it. But, to give it a shot:

1. When you hear about an idea that seems incredibly cool - stop yourself from exploding in excitement and:
  - Try to think of two good ways to use the idea to solve problems you've had before in a way that's significantly better than using other tools
  - Consider if you would be to understand the concept if you had absolutely no idea what it was, but saw it in the code
  - If you can't do both of the above (think of two ways or understand the concept directly when seeing it) - then no matter how cool it is, don't use it :-P 
2. Have someone review your code from time to time. If it takes them more than a few minutes to understand a certain part, it might be due to the unnecessary complexity of some tool or technique you are using there. This one is dangerous, because the reviewer very well may say "Wow, that is AWESOME!" once they figure out what the hell is going on but, keep in mind, this is NOT GOOD - it is actually an indicator you should look more closely and make sure the coolness didn't blind your better judgement.
3. Start off with the simplest solution possible. If it works, and keeps the code extensible and easily changeable, avoid at all costs refactoring it to the 'cooler' version.
4. Control yourself. If someone tells you of a new technology or tool that is cool as hell, for God's sake ONLY use it if it will really offer irreplaceable value in a particular situation. Don't be seduced by the coolness :).

###Common arguments against this idea

1. Won't this reduce our ability to learn new tools and techniques?
  - I didn't say don't learn them....learning is awesome! Just don't use them on a project unless they need to be used.
2. Things get cool because they are useful, not the other way around
  - Frankly, I think this is a rationalization for someone who has been seduced by the cool many times and doesn't want to admit their mistakes. There are many historical examples of this idea - i.e. I suppose in the 30's in Germany, it was pretty damn cool to be a Nazi.
3. Avoid the extremes of depth or breadth, and don't concern yourself with this complain. A happy median is what's really best!
  - Please see the first header in this post "The Answer:" for a response to this.


