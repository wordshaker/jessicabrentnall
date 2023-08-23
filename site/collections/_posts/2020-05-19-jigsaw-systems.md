---
layout: post
title: Pre-loved Systems Are Like Second Hand Jigsaw Puzzles
description: "Working out domains when working with pre-existing systems. How to put together the full picture of a system."
date: 2020-05-19
image: "/images/posts/2020/05-19.jpg"
tags: ['2020']
---

----
<center>
<h3> Putting together the bigger picture </h3>
</center>

---
<br/>

Recently, we have all been stuck indoors. To keep entertained, some of us have taken up putting together jigsaw puzzles. 

A lot of my career has involved working with pre-loved systems, and it's come to mind how similar working out a system and it's domain(s) is to having bought a second-hand jigsaw puzzle and putting those pieces together. 

There are two approaches to solving a jigsaw puzzle or learning about a domain. Working from the pieces up or from the full picture down. Using this analogy I will go through why I think the later has more benefits.

## Putting The Pieces Together Without The Picture

There are a number of scenarios that can happen when we try to solve our jigsaw puzzle without the picture on the lid.

### 1. There are two jigsaw puzzles mixed in the box

It might not be clear that you have more than one jigsaw until you have struggled putting similar pieces together and found they don't look quite right. It's a lot of wasted effort and can be incredibly frustrating.

In terms of pre-loved systems, this is what can happen when you try to figure out a system from components up, when it turns out there are two domain areas you are responsible for. In these systems these domains might not be clearly separated. It can be much harder to separate than two jigsaw puzzles and really hard to see clearly.

### 2. There are missing pieces

For a second hand jigsaw puzzle, missing pieces can mean not finishing the full picture. 

For pre-loved systems a missing piece can happen from a number of situations. There might be parts of your domain that haven't been handed over or documented. It may be that, for some historical reason, another team has that missing piece of your domain. It could just be that there is a piece of the system that hasn't been thought of or created yet that could enhance your domain as a whole.

### 3. There are extra pieces

You might not have a full extra puzzle but you might have a few extra pieces that don't fit. You wouldn't find out until the majority of the puzzle was done that this was the case.

Again, with your systems if there are extra parts of the system that don't seem to fit, there could be numerous reasons for this. It may be that you've been handed a piece that fits in someone elses domain. It might be the extra components aren't used or aren't finished, in which case you might be able to deprecate them. We all love deleting code and saving money after all! But, like with the jigsaw puzzle, you won't have a clear view that these are "extra" until you've managed to put together a full picture of what you have. This can take time when you are building your view from the components up.

### 4. You can fit pieces together, but they don't look quite right.

Whether it's part of the above, or as part of figuring out one jigsaw, sometimes pieces almost fit together but don't look right. You end up moving pieces around and eventually working out how they fit.

For systems, this can also happen. It can take time and energy to figure out how parts of the system fit together in which order. We can get it wrong multiple times before getting to that final picture.

<br/>

## Starting With The Picture On the Box

When working on a second-hand jigsaw puzzle it's easier when you have the picture on the lid. You know what you are building toward. This will highlight early if you have more than one jigsaw, missing pieces or extra pieces. It is much easier to figure out how the pieces should fit together.

This is the same for pre-loved systems. By working with the full picture of the domain(s) you've been handed, you can then work out how the components fit together.

When working with pre-loved systems, there is no magic picture on a box. Instead we get the full picture through discussions with the different users and stakeholders.

### Product Owners

Arrange a meeting with the the product owners that have cared for this domain before it was handed to you. This meeting, in person or remote, isn't to got through the details of the system but instead to go through the journeys at a high level. 

Ask them to walk through a good customer/client/consumer experience using your domain, and then the error scenarios. This can be done with a whiteboard (virtual or physical), post-its, a Trello board or bullet points. Walk through and list the interactions with the domain and the experiences (from a customer or consumer point of view) that it is responsible for.

This helps to build a picture of your domain and what features are important. You can talk through how this ties to Key Performance Indicators for the business. What is important to the business about this domain: is it throughput of customers, speed, how much it makes financial or something else. If you have your KPIs as well as a picture of your domain, you will have measurements of what success looks like, and what you are building towards.

This walk through will help build the picture of what your system should be responsible for and how it should be working at the highest level.

### Consumers

Also talk to the consumers of your services. These could be internal or external consumers. By this I mean they can be teams inside the same company/department (internal), or teams belonging to a third party (external).

Here, my examples are angled towards backend systems as that's what I know, but talking to consumers can give you a really good idea about the boundaries of your system and it's interactions.

When having these discussions I often ask for their documentation. When integrating with this domain or on-boarding a new member to work on interaction with this domain, what is the documentation they refer to? 

If there are any available, it is also good to ask about any service level agreements that are in place. These are agreements about behaviour that are in place, where if they are not met, there are consequences to the business. <a href="{{site.baseurl}}/blog/slo-sli-sla-post" rel="noreferrer" target="_blank">More can be read about Service Levels in this blog post.</a>

By having information about the behaviours your consumers expect and how they integrate with your domain, you can better understand the external boundaries of your domains. This, again, is useful for measuring success and building a picture of your domain. It is also good for testing and metrics. Now you know what the experience expected is, later down the line you can ensure there are procedures in place to ensure you are meeting those expectations.

### Users

Another group that can help give you the full picture of how your system should work is your users. This may be harder to achieve than the other two, depending on the system you are working with and where you work. Users can come in many forms, but probably the ones we are most familiar with are the people who use your product by integrating with a user interface. Whether this is an expected user of your website, a person working in customer servicing who is using an internal program or otherwise.

Whether you talk directly to your users, record their interactions with your system or run focus groups, this will help highlight how they work with your system and what is important to them. 

Seeing this interaction will not only help with understanding domain, but what features of it are important. Often users won't use your system as intended by product, and doing this will highlight which parts of the system are valued by your users. As well as building a picture of how your system, and the product it supports is useful to your end user and building up a picture of your domain(s), this can also help with prioritisation of future fixes or features. A greater understanding of your user is also beneficial to work as a whole. The more you have an idea of how a product is interacted with and used, the better you can tailor it and empathise with the end user while working on it.

<br/>

---

## Working From The Picture To The Pieces

Once you have the picture of the responsibilities of your system and how it works, you can figure out the domain(s). What I mean by this is you can map out the responsibilities of your system. This can be done in an informal manner or there are many user mapping techniques that can also be applied.

If you map out the journeys through your system, the input and outputs and the key responsibilities of these, you'll build up a full picture. This gives you that jigsaw puzzle box lid that you need to fit your pieces to.

From there, each component can be assessed to see how it fits against this picture. Pull down the code to evaluate it at a high level, examine the tests and read the documentation. You may find the documentation is out of date. You might have missing or extra components. At least by having conversations with those who know about and use the domain, if any of this happens it will be clear as you try to understand the details of how your system hangs together and lines up to its purpose.

Figure out the shape of each of your jigsaw puzzle pieces. As you build up a picture of each piece, you'll more easily be able to see where they fit in the picture you've built up with your conversations. It will be clearer how they fit together. All those issues we mentioned in the beginning will be spotted earlier and be more simple to resolve.

In the end, from my personal experience, it will save a lot of time and heart-ache working from the picture down. 

_Enjoy your puzzles_

---

<div style="text-align:center" markdown="1">
<img src="{{site.baseurl}}/images/logo.png" alt="Logo">
</div>