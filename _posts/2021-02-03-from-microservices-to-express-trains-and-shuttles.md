---
title: From microservices to express trains and shuttles
layout: post
author: sal
image: assets/images/microservices/header-sergio-souza.jpg
description: Who will be the one that pays off the technical debt? To be honest it
  will be all of us!
categories:
- technical debt
- buzzwords
- what is this thing?
- microservices
- architecture
featured: false
hidden: false
---

*Picture: Sergio Souza*.
In recent years, we have put a lot of effort into making software products better and in a faster paste. We often state that we need a low time-to-market in order to quickly obtain feedback from end users. On one hand by adapting some processes (agile), but the biggest effect is still due to technical developments such as server virtualization, containers, continuous integration / delivery, new frameworks, development supporting tools etc.

This day there is better supporting tooling to create applications that are made up of small pieces, also called microservices, so that in theory you can make adjustments quickly with multiple teams or you have a lot of users who want to use certain functionality. You know, just like Netflix! In some specific cases this yields a lot, but people sometimes forget that it can also cost a lot.

![Mono vs micro]({{ site.baseurl }}/assets/images/microservices/mono-micro.png)

When talking about microservices, a system is divided into independent services that have only one goal such as search, calculation, rating, shopping cart, recommendation engine, etc.

If you really want to know a lot more in depth about microservices, I recommend the blog series by Uwe Friedrichsen where you can find the first part [here](https://www.ufried.com/blog/microservices_fallacy_1/){:target="_blank"}.

## Monolith
![Monolith]({{ site.baseurl }}/assets/images/microservices/long-train-1.jpg)

Let's assume an existing application. This already has a number of logical modules but is usually delivered in its entirety. We can compare this with a long train that also takes part of the freight transport and mail with it.

The planning of the train is not very flexible, but it is reliable. Once a week to the destination and back. If you are late or if goods have not been delivered on time, you have to wait a week. If there is a defect or there is a tree on the rails, this has a lot of impact and there is a good chance that the planning issues will continue for a few weeks.

In terms of infrastructure, we need one track and a number of stations.

## Modular
![Modulair]({{ site.baseurl }}/assets/images/microservices/combined-train.png)

There comes a time when passenger transport requires a different frequency than freight transport. People want to be able to go up and down daily while it is fine for the mail and the goods once a week. 

We will continue to use the same track with the same stations, but will ensure that we take passengers from A to B for passenger transport in specially made trains with our own schedule. The planning is already a bit more difficult, but there is also a bit more flexibility for passenger trains specifically. We also have to invest in the infrastructure because we are going to take people to stations in the cities and the mail and goods just outside the center. We now have to lay two tracks on the shared pieces.

The next step is to recognize that mail also needs a different frequency than both the people and the goods and we can also split them up.

The planning is now also becoming a step more complex and the infrastructure must also be adjusted again.

## Microservices

![Microservices]({{ site.baseurl }}/assets/images/microservices/micro-train.png)
*Picture: The ParkShuttle in Rotterdam, the Netherlands*

In theory we can differentiate much further. In reality we already have sprinters, intercity trains and intercity direct trains. All with fixed times and lines.

A comparison with microservices would be a kind of train-on-demand. A kind of Uber pool but on the track. 

In order to be able to deliver people, goods and mail as quickly and flexibly as possible, we make a large number of different trains, each with their own specific goals:

* Rotterdam - Gouda with only 1st class passengers,
* Maastricht - Nijmegen for domestic mail,
* Amsterdam - Paris for dangerous goods,
* Amsterdam - Paris for 2nd class passengers, etc.

The moment we adjust a wagon so that more people can enter it or that you can now also transport dangerous goods in another, that wagon can immediately go 'live'. If there are passengers or goods, they can go directly to the final destination. Each train does one thing. We no longer have to wait for a certain time or until the wagon is full, but we go when we can. The perfect user experience.

![Shunting]({{ site.baseurl }}/assets/images/microservices/header-sergio-souza.jpg)
*Picture: Sergio Souza*

This brings additional complexity with it and it is certainly not free. Although we can now deliver (to production) whenever we want, we do need a very good monitoring system to ensure that no accidents happen. Partly because the pressure can increase enormously at certain times without it always being predictable. Where we previously had a limited number of trains, we now need an advanced shunting yard. We probably also need more rails. And security wise we might have to update the sensors of the crossings.

## Complexity
With regard to IT architecture, it is often the case that if something simplifies on the one hand, complexity increases elsewhere. And complexity often simply takes effort and money and the choice for it must be carefully weighed. This is also the case with microservices. Where a monolith is sometimes labeled as unwieldy, it also has fewer dependencies where a microservices architecture does strongly.

On the one hand, it becomes much easier to deliver smaller adjustments quickly, on the other hand it becomes an art to ensure that all other services continue to work properly and in certain cases end-to-end testing becomes very difficult.

Complexity is shifting from Dev to Ops in DevOps. Fortunately, there are solutions such as service contracting versioning and new monitoring systems, etc, but the fact remains that this must be properly set up and maintained.

![Shunting]({{ site.baseurl }}/assets/images/microservices/aleks-magnusson-rails.jpg)
*Picture: Aleks Magnusson*

In practice, in most cases you are okay if you choose to build the things that you want to deliver quickly and often or those that will have an extreme load often as services. The rest of your application can then often go through life as a monolith or as a modulite. However, the tendency within IT is often to 'do everything completely differently with a new revolutionary technology'. This results in a number of companies that have gone to a 100% microservices architecture but eventually came back from that and slowly find the balance again [as you can hear in this talk](https://www.infoq.com/presentations/microservices-monolith-antipatterns){:target="_blank"}. A very costly lesson for these companies, and a good lesson for us.

## Who are you and what do you need?
The question to ask yourself is whether you should actually scale up that fast or extremely. Do you really need so many teams to work on the same product? Are the banks and insurers f.i. in the Netherlands really going to amaze us with new features every week? Or are we going to ask ourselves, just like with parcel delivery, whether it is really necessary to have everything at home immediately the next day?
