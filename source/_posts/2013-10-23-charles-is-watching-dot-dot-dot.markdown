---
layout: post
title: "Charles Is Watching..."
date: 2013-10-23 18:25
comments: true
categories: ruby thoughtworks t&e
---
##The Problem
It was a dark and rainy Tuesday afternoon in San Francisco (always being cloudy, this isn't saying much). I was at work, pairing with a colleague, when I decided to glance at my computer to check for something we needed. This forced me to unintentionally check my E-Mail...something that always causes trouble. As usual, there was a message there which frustrated me - an E-Mail from Charles, caps-locked, screaming for me to turning in my time sheet. Not to kill the messenger, Charles is a great guy, he just happens to be the one who has the job of dealing with the irritating employees that miss their time sheets.

The E-Mail detailed all the reasons I was damaging ThoughtWorks' profit margins and bank account, and how it was detrimental to the client relationship. I was ruining everything! The company was in danger of falling apart! I couldn't jeopardize my beloved company yet again by making my time sheet even later. But, as we often are, I was in the middle of doing some work, and didn't want to suddenly leave, switching context to think long and hard about how many hours I worked the week before, as it is equally immoral to type in random numbers for 30 seconds and call it done. Decisions, decisions...

##If Only...
...I had some way to quickly remember how many hours I worked in the last week!
<!-- more -->
Even when we manage to turn in time sheets on time, think of how many batches of 5-10 minutes are wasted sitting around trying to remember hours worked?

- 10 minutes every 2 weeks or **20 minutes every month**
- 1 year working in ThoughtWorks, **12 months**
- 12 * 20 = 240 minutes a year, or that's **4 hours of wasted time** per year
- 2,500+ employees in ThoughtWorks makes that at least **10,000 hours of wasted time** (**83 working weeks** of collective time per year)

Or worse still, how many mistakes are made due to failing at the task of remembering our hours?

If that still doesn't sound like enough time, keep in mind it doesn't include the likely larger portion of time that is wasted switching out of and then back into context when trying to solve a problem. During the hiring process at any company, they don't look for top-notch 'remembering hours worked' abilities, but likely for other skills. So, I wanted some way to be able to quickly get past this annoyance.

Having a hunch that being connected to the wifi (since we are nearly always on the internet at work) might be a good place to start, I ended up making a small script that keeps track of your time based on when you're connected to work wifi networks, and it's been working quite well so far.

##So, how does it work?
1. Every 5 seconds or so, it checks to see if you're connected to one of the predefined wifi networks (by default, these are 'twdata' and 'twguest' - but users can easily add project specific ssid's.) When it checks, if you are detected being on the work networks you have defined (i.e.  you're 'at work' to Charles) one of two things can happen:
    1. If it is the first time Charles has detected you at work for this day, he will create a new day starting at the current time (i.e. you've just arrived at work and opened your computer at 8:00am letting it connect to the wifi, it will mark 8:00am as the "started work" time for today.)
    2. If Charles has already logged a starting time for that day, 'he' will mark that time as the ENDING time for the day, replacing whatever the previous ending time was, if one existed.

This means every 5 seconds your 'ending time' for the day is changing to be more up to date. The assumption is, the last time you close your computer and leave the office, that ending time will be accurately saved within 5 seconds.

He will continue logging the time happily until you close your computer and go home for the day. You can connect to your home wifi all you want, because it is not in your "Work SSID's list", so Charles will ignore it. The next day when you come to work, Charles will start a new day, and will remember almost exactly the time you left work on the previous day.

A second component of Charles is the webapp component, hosted for free on Heroku, that receives posts from the locally running script every 5 seconds and logs the time. You can visit http://charles-time.herokuapp.com/ and log in through the (extremely sparse) UI to then see your hours worked.

##Where Can I Get It?
[Git Hub](https://github.com/Scatchell/Charles)

##The Future
####Automating the Time Entry
In my opinion, icing on the cake would be some simple browser automation tool (like selenium) to give Charles a feature that allows it to log into our T&E web page and set all the times automatically, taking out a preset time out for lunch. Then, Charles would allow you to simply glance at the form it has filled, make sure everything is good and accurately represents what happened that week, and just click the submit button, making the process much more accurate and taking less than 10-15 seconds.

####Going Mobile
An alternative to the script on your mac which several people have suggested is to integrate Charles into a mobile app. They are constantly searching for wifi networks, and people tend always have their phones on, so as long as you had wifi activated on your mobile, this would be exceptionally accurate as far as logging exactly how many minutes you were inside of a particular building.

This could be accomplished quite easily, I think, if Charles were ported over to a mobile app that does the same as the current ruby script does.

##Known Issues
####Why Wifi?
Wifi connection may not sound accurate at a first glance, but I've been using charles for a while now and it's been surprisingly representative of how long I've been at work. Forgetting to run the program, or never opening your computer (pairing on a different machine? Running around from meeting to meeting all morning and never having a chance to open your computer until the afternoon?) is still an issue. The cell phone integration mentioned above could be a solution to this.

####Just a simple script...
It would help a lot to have Charles be a real mac application, one that can be run more easily through the GUI and run in the background with a taskbar icon.

####The people that make the rest of us look bad
For you SUPER hard workers, there are some bugs when staying past midnight. When it passes through to the next day, Charles gets confused and ends the current day, immediately starting the next one at 12:00:01am, so then when you get to work the next day it thinks you've already worked for 8 or 9 hours as soon as you walk in the door. No one likes dealing with time, so I haven't sorted this out yet.

####Interested?
Feel free to contact me with suggestions, ideas, interest in working on this mini project, or questions in general. Definitely interested to hear both the good and bad comments :)
