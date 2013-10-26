---
layout: post
title: "Charles Is Watching..."
date: 2013-10-23 18:25
comments: true
categories: ruby thoughtworks t&e
---
##The Problem
It all started on a dark and rainy Tuesday afternoon in San Francisco (though it's nearly always cloudy, so this isn't saying much). I was at work, right in the middle of solving some mildly interesting problem with a colleague, when I decided to glance at my computer to check for some tool we needed. This forced me to accidentally check my E-Mail, which is always a horrible idea. As usual, there was something there that caught my eye in a negative, forcing context switching kind of way - it was an E-Mail from Charles, written in all caps, yelling at me for not turning in my time-sheet yet. Don't get me wrong, Charles is an awesome guy...one of my favorites in the San Francisco office. I don't want to kill the messenger, he just happens to be the one who sends out the E-Mails that force me to worry about my time-sheet :).

The E-Mail specifically detailed all the reasons I was damaging ThoughtWorks' bank account, and its relationship with the client by not turning in my time-sheet on time last week. I was ruining everything....the company was going to collapse if I didn't turn it in that day...and not only that, but this was maybe the 4'th or 5'th time it has happened! It was a miracle ThoughtWorks had managed to survive up until that point with all the damage I had already done, I couldn't jeopardize my beloved company yet again by making my time sheet even LATER! But, I was in the middle of pairing, and I didn't want to suddenly leave the warm embrace of my [loving pair](http://www.youtube.com/watch?v=dYBjVTMUQY0), switching context completely for 10-15 minutes while I thought long and hard about how many hours I worked the week before. Decisions, decisions...

##If Only...
If only I had some way to quickly remember how many hours I worked in the last week! Even when I turn in my time-sheet is on time, think of how many batches of 5-10 minutes are wasted sitting around trying to remember hours worked?

- 10 minutes every 2 weeks - **20 minutes**
- 2 years of working in ThoughtWorks, that's **104 weeks**
- 104 / 2 * 20 = 1040 minutes! That's **17 hours of wasted time**
- 2,500+ employees in ThoughtWorks makes that at LEAST **42,500 hours of wasted time** per year (that's **1,770 days**, or **354 working weeks** of collective time)

And if that still doesn't sound like a lot, keep in mind it isn't including the likely significantly larger portion of time that is wasted switching out of and then back into context when solving a problem, dealing with (and wasting more time thinking about) people badgering us constantly about turning in our time sheets, and all the rest that is involved. They didn't hire us at ThoughtWorks because of our awesome remembering hours worked abilities, but for other, potentially more useful skills they saw in us. So, I wanted a way to be able to quickly get past this issue.

At first, wasn't positive how to accomplish this, but I had a hunch that being connected to the wifi (since we are always on the internet at work) might be a good place to start.

##So, how does it work?
1. Every 5 seconds or so, it checks to see if you're connected to one of the predefined wifi networks (by default, these are 'twdata' and 'twguest' - but can also easily add project specific wifi's.) Every 5 seconds when it checks, if you are detected being on the work networks you have defined (i.e.  you're 'at work' to Charles) one of two things can happen:
    1. If it is the first time Charles has been run for this day, he will create a new day starting at the current time (i.e. if you've just arrived at work and opened your computer at 8:00am, it will mark 8:00am as the "started work" time for today)
    2. If you are detected as no longer being connected to the network, it will mark that time as the ENDING time for the day, replacing whatever the previous ending time was

This means every 5 seconds your 'ending time' for the day is changing to be more up to date. The assumption is, the last time you close your computer and leave the office, that ending time will be accurately saved within 5 seconds.

You can see there may be a problem here, what if you close your computer at the middle of the day (or get disconnected from the wifi) does Charles just give up and assume you're no longer at work? No, he's not that stupid :-P

If you shut down your computer or disconnect from the wifi for a few hours at any time of the day, let's say you do this from 1pm to 2pm - Charles will mark the end of the day at 1pm. But then, as soon as you open it and it connects again, as long as you still have Charles running, he will do this:

1. Are we connected to the network? Yes.
2. OK, is it the first time I've been connected today? Oh look, no it isn't, I've already logged an ending time for today.
3. So that means they are probably still at work for today, let's mark 2pm as the new ending time.

And he will continue along happily until you close your computer and go home for the day. You can connect to your home wifi all you want, because it is not in your "Work SSID's list", so Charles will ignore it. The next day when you come to work, Charles will start a new day, and will remember almost exactly the time you left work on the previous day.


##Where Can I Get It?
On [Git Hub](https://github.com/Scatchell/Charles), of course! 

##The Future
####Automating the Time Entry
What I think would really be cool, is using a browser automation tool (like selenium) to give Charles a function that allows it to log into our T&E web page (if you already have a valid session) and set all the times automatically, taking out an hour for lunch automatically, or something. Then, Charles would allow you to simply glance at the form it has automatically filled out, make sure everything is good and accurately represents what happened that week, and just click the submit button. Hopefully the whole process would take less than 15 seconds like this.

####Going Mobile
Another option is to integrate Charles, or something like it, into a cell phone. They are constantly searching for wifi networks, and since people tend to pretty much ALWAYS have their cell phones on, as long as you had your wifi activated, this would probably be extremely accurate as far as logging exactly how many minutes you were inside of a particular building.

This could be accomplished quite easily, I think, if Charles were ported over to a small and simple web app library like Sinatra, and the cell phone could have an app that checks the wifi, and every time it is connected hit a route online that would log them as "at work", allowing Charles to handle the rest.

####Reasonable Display
Right now, every time you start up Charles, he quickly lists all the previous days he remembers and the hours worked for those days. This could be a lot better, for instance showing the times only for the current week, and allowing movement backwards and forwards by week (maybe through a simple bootstrapped web-app :) )

##Issues With Charles
####Wifi? Really?
I realize wifi connection isn't perfectly accurate, but in my experience it's been surprisingly representative of how long I've been at work. However, forgetting to run the program, or never opening your computer on a certain day (maybe pairing with someone else the whole day? Or running around at meetings all day?) is still an issue. I think the cell phone connection could help with this.

####Just a shitty ruby script? Really?
It would also help a lot to have Charles be a real program, that can run in the background and be quit, instead of a simply ruby script that you have to exit with ctrl-c :-P

####The annoying people that make the rest of us look bad
For you SUPER hard workers, I've also noticed some bugs when staying past midnight for an event or something. When it gets past midnight, Charles gets extremely confused and ends the current day, immediately starting the next one at 12:00:01am, so then when you get to work the next day it thinks you've already worked for 8 hours. I've got some ideas on how to fix this, but it hasn't been a huge problem for me yet so haven't quite gotten around to it.
