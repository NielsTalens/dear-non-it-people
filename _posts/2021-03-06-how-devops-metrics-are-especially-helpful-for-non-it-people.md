---
title: How DevOps metrics are especially helpful for non-it people
layout: post
author: sal
image: assets/images/dora-metrics/pexels-anna-nekrashevich-header.jpg
description: How can these technical looking metrics help non-IT people?
categories:
- technical practices
- devops
- metrics
featured: true
hidden: false
---

*Picture: Anna Nekrashevich*.
I often see that companies who create their products in an agile way are looking for ways to see how things really are going. From the start of agile software development there was a healthy suspicion in regards to metric, reports and dashboards.

But to be honest we have, despite never ending discussions about velocity and story points, burn up or burn downs often not a great track record of creating predictability and transparency on a product level. We have had years in which the mantra 'bringing value to end users' was enough. But exactly what this value was remained something quite vague often.

So we have things like burn down charts, portfolio walls and happiness metrics. For me it lacked an overall view. How are we doing from start to finish? Are we delivering functionality to real people or are we doing sprints?

So being a guy who embraced the idea and practices of continuous integration and delivery from a quality perspective, I later realised what great value a pipeline could have for a non-it person. He or she could learn to recognise some really crucial metrics which would tell the most honest story about how we really are doing. And the beauty of it is that these metrics  are not technical at all!

I wrote another blog earlier in which I explain more about pipelines which you can read [here]({{ site.baseurl }}/about-pipelines-and-continuous-everything-and-more/).

![Dashboard example]({{ site.baseurl }}/assets/images/dora-metrics/pexels-vinicius-benedit-oven.jpg)

*Picture: Vinicius Benedit*

## Setting the stage

Let's say that you are the owner of a Pizza shop. You make wonderful delicious pizzas and have some scooters and drivers who do the delivery. Business is doing pretty good.

## Lead time

This is the mother of software development measurements. It is the time it takes from an order call until the moment the pizza is on the customer's plate. In software development it translates to 'the time from idea to production'. The longer this time is the longer a customer has to wait and evenly important: the longer we will have to wait for feedback.

In general you will see that lead time will increase over time. A larger codebase, more tests to run and so on. Even badly written user stories or lack of knowledge can affect the lead time. How much it will increase and what is an acceptable time is up to you my dear non-it person. If you need faster throughput we should find out how.

## Deployment frequency

How often do we do a pizza delivery? Do you deliver right away when the pizza comes out of the oven or do you often start a delivery only when you have 6 orders? Both have an effect and both have their uses. From a continuous delivery perspective it is better to have multiple smaller releases than on big one. Imagine the effects of the scooter with the 6 orders breaking down.

![Dashboard example]({{ site.baseurl }}/assets/images/dora-metrics/pexels-norma-mortenson-door.jpg)

*Picture: Norma Mortenson*

## Mean time to restore

Imagine a scooter breaking down, a pizza dropping on the floor, the oven breaking down, phone lines not working. Those are things that probably will happen once. Or, like often in life, happen all at the same time.

But bad things happening are not the issue. The time it takes to get up and running again is what matters. It relates also often to the deployment frequency. If you make many smaller deployments the things you might have to fix when there is something wrong tend also to be smaller.

## Change fail percentage

When 50% of the deliveries end up in an accident or when some pizza's are being dropped off at the wrong addresses the fail rate is something to keep an eye on.

Imagine a spike of bugs after each release. That means something. There can be numerous reasons (no proper testing, complex architecture, dependencies failing, diverging acceptance and production) but it is something worthwhile to investigate.


## Example of a dashboard:

![Dashboard example]({{ site.baseurl }}/assets/images/dora-metrics/dora-metrics.jpg)

*Picture: Niels Talens*

## Metrics as a way to improve

These metrics alone do not mean very much. They merely can help you spot where to look for root causes. Also the delivery is still not the end goal. The end goal is having happy customers who will continue ordering pizza at your shop. The real important validation begins when your products are used and these metrics can help to make sure we deliver consistently and frequently. With easy and a healthy paste.

![Happy customer]({{ site.baseurl }}/assets/images/dora-metrics/pexels-rodnae-productions-happy-customer.jpg)

*Picture: Rodnae Productions*
