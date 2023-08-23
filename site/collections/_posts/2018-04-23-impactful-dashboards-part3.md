---
layout: post
title: Danger Signs of Dashboarding
description: "Part Three of Creating & Maintaining Impactful Dashboards. Keeping dashboards useful."
date: 2018-04-23
image: "/images/posts/2018/04-23.jpg"
tags: ['2018']
---

----
<center>
<h3> Creating & Maintaining Impactful Dashboards Part Three </h3>
</center>
--- 
<br/>


We have covered what needs to be covered on a day-to-day aspect of working with dashboards. This series so far has explored the conversations in creation and maintenance of dashboards. What we haven't explored are the signs that a dashboard may need a bit of clearing up or re-work. Here we will go through a few of them, why they might happen and what to do when they do.

### "I don't know what the metrics are for"

_"I don't know what these metrics mean"_, _"Which dashboard should I be using"_, _"I don't know what the metrics are for"_...

All of these statements point to the same issue, and it's a very common problem. Monitoring isn't being treated like a first class citizen and the dashboards are stale, out of date, out of context and probably no longer useful. The systems and projects we work on and care about are ever evolving. We want them to grow and change, as it shows progress, but often monitoring, in particular dashboarding, gets left behind. 

Not knowing what your metrics mean or are for anymore is a symptom of numerous problems:

- _Stale / obsolete information_

    Your dashboards and other forms of monitoring aren't being updated with the systems / projects that they are monitoring. In terms of your dashboards, this can mean that some of the metrics shown are no longer measured or present or may be stable now.  All in all - your dashboards are crowded with metrics that should have been deprecated.

    This is a problem for numerous reasons. Firstly, how are you supposed to know which of the metrics displayed are useful to you or not? Especially as a newer person to the company that might be using the dashboards to aid them trace or debug (though log analytics are better for this purpose if available) this can be confusing.

    Secondly, we are supposed to be able to react to the metrics on our dashboards. There should be a purpose to them. you cannot react to stale or obsolete data. Also, if that is present it suggests the boards haven't been updated in a while and may be missing information you need to know about.

- _Problems with communication_ 
   
    The previous posts have had emphasis on the importance of communication when producing and maintaining dashboards. If the metrics have been put on this board without conversations being had about the purpose and audience of the board, what needs measuring and why, and how long it needs measuring for - you will be lucky to be making the most out of it. 

    Dashboards should always have a purpose and there should be a suitable reaction to the metrics displayed on a dashboard.

    This is even more of a issue if the person making the dashboard is separate from the work the dashboard is responsible for. If you aren't working on the system or project, it's unlikely you will know if the information is relevant or needs changing. I'll come back to this later.

- _Bad annotation_ 

    Dashboards should be clear. Whether its by using titles, panels or what ever feature you think is beneficial it should be possible for someone working in the area the dashboard is covering to look at it and work out what is what relatively quickly.

    If you can't do this clearly on the display - make sure that those who will need to be using the boards are trained on the stats that are displayed, what they mean, and what to do when it's gone Pete Tong.

- _"This might be interesting"_

    There are many things in life that are interesting. Unfortunately, these things aren't always useful and don't have a reaction that needs to be taken against them. 

    Dashboards are used to inform us of the current state of play. The metrics displayed on them should be things we can react to, even if it is to plan improvements to our systems. By adding information without a purpose for it, leads to busy, cluttered dashboards. This will include metrics which were once added out of interest, but nobody knows what they are for or what should be done with them.


#### What can I do?

The reason this is listed as a danger sign is that the dashboards are now not easy to read or understand, there is not a strong purpose to them and it is hard to react to the metrics. As they become harder to use, they become more of a hindrance than a help.

In my opinion, if a dashboard is in this state the only thing to do is to go back to basics. Delete the board. Have the necessary discussions to determine if anything needs to be monitored in relation to this are of the system or project. If there is, talk to the stakeholders / audience of the dashboard and start fresh.


### "Dashboards are a tick box exercise"

I can fully empathise with this, but it causes so many issues. 

Sometimes in the effort to make monitoring a first class citizen, tasks will be added to developers work to "add logging and instrumentation" or to "make a dashboard. It's added as a tick box.

There are a number of problems that can arise from this. Firstly, those making the dashboards might not necessarily be instructed to what the dashboard is for or who is using it. The critical conversations can be missed out to gather the requirements for what should be on the dashboard, who it is for, why the information is needed etc. 

As such the dashboard can be made up with what that person thinks might go on it. Dashboards are used not only to display information in a clear way that you need to react to - but also to improve communication, transparency and demonstrate purpose. Communication is needed as part of constructing dashboards. Having a _tick box exercise_ culture can lead to metrics people don't understand the purpose of.

Another point to this is if a dashboard is being changed as what it is covering is changing - that's great. You can think about what in the current environment is changing, what you might need to keep an eye on. If you can, you can put telemetry in first to observe the impact of these changes. Sometimes, when monitoring is treated like another tick box, this is neglected. It's doing changes for the sake of it, instead of having it as part of the change.

There will _always_ be some aspects of monitoring that feel like a tick box exercise. Many places have consistent things they monitor for services or API's for example. That is fine - I encourage patterns like <a href="https://peter.bourgon.org/blog/2016/02/07/logging-v-instrumentation.html" rel="noreferrer" target="_blank">R.E.D</a>for API's, <a href="http://www.brendangregg.com/usemethod.html" rel="noreferrer" target="_blank">U.S.E.</a> for services. I encourage following the <a href="https://landing.google.com/sre/book/chapters/monitoring-distributed-systems.html" rel="noreferrer" target="_blank">Four Golden Signals</a> from the Google SRE book. All these are great. All I'm saying is the entire act of monitoring for each project and task shouldn't feel like a tick box with no reason or guidance.

#### What can I do?

First of all, get buy in to treat monitoring like a first class citizen. When considering a change, have the conversations of what may need to be monitored, why and how. Put in the telemetry you need early so that you can see the baseline before you make your changes. Include monitoring as part of your team discussions.

This is a difficult one to solve as it is more of a cultural one than a technical one. The only this to be done is to change the attitudes towards monitoring.

### "We have one person responsible for our dashboards"

Strangely common and there are, again, a few issues that can arise from this.

Firstly, the person making these dashboards is going to be too far removed from the things that are being monitored. If their job is to create and manage dashboards, they will not have the context of the projects or systems being monitored. As such how will they be able to have the necessary conversations, be able to push back on unrequired metric or put in the needed telemetry from the start.

Further, it goes back to communication. This person is a bottleneck for all those dashboarding needs. The conversations that need to be had between teams, with stakeholder, all of these can't be had if one person is responsible for putting these metrics in place.

We are told in software and infrastructure that single points of failure are a bad thing - this holds true for many things including monitoring. Having one person who can create, react to and be responsible for dashboards, even having one team being responsible for this is stopping those using them get the most out of them and feel invested in them.

Finally, it's a dull job to do. To monitor projects and systems that you don't have an active influence or interest in can't be fun.

#### What can I do?

Bring the responsibilities back into the team. Usually the teams or people who have the job of creating and maintaining dashboards or the other teams have other responsibilities. Let them concentrate on those responsibilities.

### "Vanity Metrics"

These metrics will sneak up on you. You'll do it without even realising it. 

I'm probably repeating myself - but metrics need a purpose. Something that you can react to (and no I don't mean react with a sigh and _"oooo that's pretty"_). Monitoring something out of interest is a big one for this. Vanity metrics are things that are monitored just for the sake of it, or to make you look good. It doesn't include when results go well. That's great and you can have reactions to good as well as bad results. Don't display measurements without reason.

### Busy Boards / Too many boards

For busy boards / dashboards with too much information on - split the information up. Find out why you are measuring the metrics are. Group the purpose. Make several boards. There is no reason why you can't rotate through several dashboards on a screen if it results in them being easier to read and understand.

For too many boards (which some may worry can be a symptom of the above) - prioritise them. Many companies have banks of screens covered in boards and metrics - no one is going to be taking all that information in. The problems you are having will be hidden, a tree in a forest. 

Instead consider what you need to monitor right now. Is there a project you are working on? Is there a particular bit of the system being changed? If so do you have dashboards for these? If not - create them. If you do put those dashboards on screen as these are the least stable / most informative part of the business and systems right now. The screen can cycle through these boards but until the work is done and these areas are stable again - these dashboards have the most relevant information to you right now. Dashboarding tools normally have a means of storing your dashboards which means you can access and display them when they are needed. They will not be needed all the time.

If there's something you are worried about breaking in the background, put an alert around it. That's what alerts are for.

### I Hate Pie

_This section is more a personal point than the others - but I really dislike pie charts_. 

A question for the world - when has a pie chart on a dashboard been clear, representative and useful?

It might be a personal thing, but pie charts on dashboards are in themselves a danger sign for me. The data is demonstrated in a way that is near incomprehensible. A few degrees change on a pie chart, which no one will notice, can mean huge change for the thing being monitored. The percentages displayed on a pie chart can also be misrepresentative and that would be difficult to spot.

I would love to hear of a pie chart that people can react to on a dashboard that displays the data in a clear format, better than any form of graph - but until then I consider pie charts a dangerous thing to have on a dashboard. 

## To tie things up..

These are but a few danger signs that can signify that something is going awry with dashboards. There are more, but I have tried to cover a few of the more common ones I have seen.

It is **REALLY** difficult to get to the stage where your dashboards are everything you need them to be; especially for a big, established business or system. There are no quick fixes. A solution that will work for one company won't necessarily work for another (a common rule with monitoring). Any solution will take time to get buy in for and implement.

The pay off is great though. To be able to see the effects of the work being done, the progress towards those business goals. To be able to spot where problems are and whether you can improve them. Do see the direct impact work is having. Monitoring in all its forms is powerful, when done well.

---

<div style="text-align:center" markdown="1">
<img src="{{site.baseurl}}/images/logo.png" alt="Logo">
</div>