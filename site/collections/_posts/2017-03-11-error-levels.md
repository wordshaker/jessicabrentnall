---
layout: post
title: "Error! Error!"
description: "Getting your error levels right - An assessment of error levels and what they mean."
date: 2017-03-11
image: "/images/posts/2017/03-11.jpg"
tags: ["2017"]
---

<br/>

---

<center>
<h3>An assessment of error levels and what they mean.</h3>
</center>
--- 
<br/>

# Introduction

---

This is an exploration of the different levels of error, what they mean and when they should be used. Before we begin, there is a disclaimer: in my opinion logging is very important - but so is avoiding noise. I prefer logs that have a purpose and are going to be used. If I can't use it or
act on it at any time, it's not getting logged.

This article is based off what I have learnt and my experience using logs as a developer. I'm currently using these levels in C# using Serilog, so this is where they will probably most applicable but the concepts will be made as generic as possible.

<br/>

# Basic Error levels

---

There are many different levels available for logging including:

```
1. FATAL
2. ERROR
3. WARN
4. INFO
5. DEBUG
6. TRACE
7. VERBOSE
```

But what do these mean and when should you use them? For consistent and effective logging this is something that should be agreed on.

#### FATAL

THE WORLD IS ENDING! This is for the worst of the very worst situation. This is for situations which force the application to close. As such their use should be very rare, if used at all.

#### ERROR

This is for something that has gone wrong that will not force the application to close but it will cause issues. These are for logging errors that could cause the operation to close, but can also be used for issues that don't cause an application to close (i.e logging a 500 from a request).
It is for any problems that require immediate intervention.

#### WARN

This is for problems that do not require immediate intervention, but that may cause issues or peculiarities at some point. It provides information but it isn't something to act upon. The application continues even if it's full behaviour isn't quite as expected.

Personally, I wouldn't use this level of logging, as if it's not actionable, people won't pay attention to it. Why not throw an error where the problem occurs, or if possible, guard against the possibility of their being an issue.

It is used however. An example given in [reference 2](http://stackoverflow.com/questions/2031163/when-to-use-the-different-log-levels) is for logging bad login attempts. This could be used to assess problems in user experience. Something to consider is there are other tools that could be used for this purpose effectively. Is logging right for this use case?

#### INFO

The information level of logging is generally used for things you want to know about but that don't cause your application to crash. There is a lot of confusion between the difference between information and debug, the principle I work by is that if it information that would be informative in production, log it as information. There is a careful balance that needs to be achieved however. You want to avoid noise, but be informative. For example, if you receive a 500 from an api, log it. Maybe don't log all the information corresponding to it.

The other thing to consider when logging to production is the content of the information. You do not want to log sensitive or identifying information about customers for instance. Internal ID's would be fine as you can track information without revealing anything you don't intend to. Logs are not a secure place for storage.

The information logs are also important in some systems as centralised logging can be used to build up monitoring. Logs and dashboards can be used to see early signs of different types of issues and for fine tuning. You can base your monitoring off centralised logging, and in a production system, the information logging would appropriate for this. It could be argued again that other tools can be used for such measurements. There are no fixed formula's for how to use these different logging levels. I find this useful, but there are alternative ways of tackling this issue.

#### DEBUG

The Debug level is there to help diagnose issues. Again, some developers choose not to use this level of log at all, or filter it out. In my experience, the debug level has been useful for logging certain information about the application while fixing issues. I have seen it used (and used it myself) for logging information such as the elapsed time of a request or time of storing something to a database. The reason I keep this in the logs is so that it can be used in dashboards to assess performance, potentially help work out issues or see signs that something is going wrong / slowly in a component.

#### TRACE / VERBOSE

The Trace or Verbose level of logging is often used for very detailed level logging. For example it can be used to log user input. Often these logs do not live for long. They are put in to fix an issue and then are removed. This is to reduce the amount of noise thrown into the logs. Its been mentioned many times, but you don't want to log something you don't use as it will just cause fatigue and excess logging.

Again, the Trace level is not a level of logging I personally have used much. I can definitely see how it could be useful if used with discipline.

<br/>

# In Conclusion.

---

As mentioned throughout, how to use logging levels is not something that is completely concrete. In this article, I have explored my interpretation of what the levels mean and how to use them. This is from how I would use them in my job as a developer, but also from reading other peoples usage. Please send me any resources on the topic, or experiences that you have found useful.

## References

1. [https://dave.cheney.net/2015/11/05/lets-talk-about-logging](Lets Talk About Logging - Dave Cheney)
2. [http://stackoverflow.com/questions/2031163/when-to-use-the-different-log-levels](StackOverflow - Logging Levels)
3. [http://stackoverflow.com/questions/7839565/logging-levels-logback-rule-of-thumb-to-assign-log-levels](StackOverflow - Logging Levels 2)

---

<div style="text-align:center" markdown="1">
<img src="{{site.baseurl}}/images/logo.png" alt="Logo">
</div>
