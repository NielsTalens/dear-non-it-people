---
title: Be aware of the 'innovation is key' trap
layout: post
author: sal
image: assets/images/innovation-trap/trap.jpeg
description: This article is about the difference between technical and business innovation. We often focus on tecnical innovation while we, from an IT perspective, need to serve business innovation and first understand the WHY.
categories:
- technical practices simplyfied
- innovation 
featured: true
hidden: true
---

You might have heard about the importance of innovation during company speeches, in blogs or at conferences. "We need to be innovative to remain relevant" is something that is often agreed upon. The examples of the most innovative companies, which often have no similarities whatsoever with your company, are endless.

In this article I will distinguish two types of innovation and explain why the one in most cases should serve the other: business and technical innovation.
- Business innovation solves a problem or adds a whole new opportunity for a target group.
- Technical innovation could be a way to serve the business innovation.

We often seem to mix them up and we end up in a place where technical innovations are the goal and the business goals are not being reached since the waiting is for the promise of the technical innovation. It is a bit like building a shiny state of the art restaurant while the only thing you need is a way for you and your colleagues to drink coffee and thee.

![coffee]({{ site.baseurl }}/assets/images/innovation-trap/coffee.jpeg)
*Picture: Chevanon Photography*

The thing is that most of these innovative companies I mentioned earlier, which we tend to see as examples, did not start because of technical innovations. They first had business ideas and to serve these ideas some technology had to be invented or was not sufficient. They were forced to innovate technically in order to reach their business goals. Often not even in the beginning but in a later stage when they were scaling up. 

And I explicitly say most of these companies since I fully understand that sometimes new technology opens up a world of new business ideas. 

## Start with the why

In order to break this pattern the first step must be defining proper business goals, explicit non-functionals and a way to quantify these. First of all the whole reason for any product needs to be clear: what problem are we solving, for who and what would be a good outcome?

We also need to be able to answer questions like: how many and what kind of users do you target? How fast do you expect to be growing? Is this an application for internal use? Which kind of data is important for you? How much data do you expect to need? Do you expect really big spikes in usage? In which phase of the product are we? 

These business goals and non-functionals dictate whether there is a need for things like fast delivery or scalability, a serverless architecture or a way to gather data through a/b testing. 

![coffee]({{ site.baseurl }}/assets/images/innovation-trap/wwh.png)

If we do not spend enough time getting on the same page, people will tend to already have a suitable technical solution in their head. And this solution does not have to have anything to do with solving your problem. A pattern is that the solution is either something familiar or something shiny and brand new. The sad reality is that often the ‘solution’ is also something that will fill up someone's resume very nicely.

![coffee]({{ site.baseurl }}/assets/images/innovation-trap/why.jpeg)

## Dare to ask

When given proper objectives teams should be able to explain the direct relation between architecture, functionality and non-functional requirements. I think you are in your right to expect an answer on a question like: How is this  'data lake, blockchain, continuous deployment, artificial intelligence or new javascript framework that will have to be implemented, mastered and maintained' going to help me reach my goals?

And the answer 'Because Silicon Valley company x is doing it' should never cut it. It is like commuting to work with a Formula 1 car because 'Red bull is doing it'. 

An argument that 'if you have all the data you have gold' is invalid if we didn't think of practical usage of this data beforehand. And the 'once we have all this in place you will have so much functionality for free' is absolute nonsense if the most important things are not created first. There is no such thing as free functionality.

## Where to start

First off all we all need to have the same understanding of the objectives. We need to understand which goals we want to achieve. And we need to make sure we all talk the same language. And since we are pursuing business goals I would advise in making the business domain terminology leading.

Luckily for us there are many very well documented tools which can help us in defining proper goals, target groups, business events and how to translate these into architecture. For me these three are often life savers to start with:

- Product vision canvas
- Impact mapping
- Event storming
