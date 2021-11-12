---
title: Can you even DevOps?
layout: post
author: sal
image: assets/images/can-you-devops/tima-miroshnichenko.jpeg
beforetoc: "Picture: Tima Miroshnichenko"
description: This article explaines the essence of DevOps and that DevOps is nothing more than an organisational structure where teams are responsible for creating products and making sure that products are performing properly in order to pursue maximal customer satisfaction.
categories:
- technical practices simplyfied
- innovation
featured: true
hidden: true
---

You might have heard the term DevOps mentioned or even work with teams that are DevOps teams. Sometimes people say they do DevOps, other times they say they are DevOps and you even hear people say that according to DevOps there is only one way of doing things. 

Often it is connected to many new tools, possibilities and ways to create better software in a faster way. Even organisational transformations. It could seem pretty extensive this way I expect. But let’s have a look at what it is in its essence. 

## Clock company

Imagine the two of us starting a professional clock company. We make and sell all types of clocks and have them both delivered and installed at the customer’s. We also take care of the maintenance. One of us designs and creates the clocks while the order drives to the customers and installs them on location. That last person will also take care of the maintenance:

![non-devops-clock-delivery]({{ site.baseurl }}/assets/images/can-you-devops/non-devops.jpeg)

If you look at this from the perspective of the maker/designer, what are the situations that are out of their scope but have a major impact on how the products are perceived and experienced? What information could they possibly miss that could be really beneficial for the products while working this way?

And what about the delivery/maintenance colleague? What are the things that are out of scope that can influence customer satisfaction for them?


In this setup, often referred to as silos, there is a lack of overall shared understanding and experiences that might have an effect on the quality of products. A couple of examples: 

- Only the deliverer/maintainer knows the possible annoyance of maintenance while the maker/designer might choose for the fastest and cheapest material and constructions.
- Only the deliverer/maintainer knows the possible challenges while delivering and only the maker/designer knows all challenges of redesigning the products.
- Whenever either the deliverer/maintainer or the maker/designer is sick, either production or delivery stops. 
- Only the deliverer/maintainer gets the first hand feedback from customers when the product is installed while the maker/designer makes the product.
- Feedback on the delivery, installation and maintenance only reaches the maker if the deliverer tells it.
- ...

![devops-clock-delivery]({{ site.baseurl }}/assets/images/can-you-devops/tima-miroshnichenko-2.jpeg)
*Photo: tima-miroshnichenko*

In order to mitigate all of the above it could be a solution that we do not distinguish between making, designing, delivering and maintaining anymore. You and me, as a team, are responsible for everything that is needed to bring the customer requests to our customers. 
So from now on we design, make and deliver clocks together and are also both responsible for the maintenance. 

That means that both of us have fast feedback on all aspects from design to maintenance. It also means that we both work on eliminating waste in the whole process. We both understand the challenges of the delivery, maintenance and the joy of getting positive customer feedback.

![devops-clock-delivery]({{ site.baseurl }}/assets/images/can-you-devops/devops-clock.jpeg)

## DevOps

So this is basically how DevOps works also. It is an organisational structure where you make the whole team responsible for both the creation and making sure everything is running properly of a product. Removing yet another wall (between dev and ops teams) to make sure we can deliver the right products as fast as needed with the quality that is needed.

![devops]({{ site.baseurl }}/assets/images/can-you-devops/devops.png)

You could view DevOps as an umbrella concept like Agile is to Scrum, Kanban or Xp. 
While often mentioned in one breath, things like automated testing, continuous deployment, containerising those are not part of the structure we call DevOps. However, since DevOps aims to shorten the systems development life cycle and provide continuous delivery with high software quality it makes much sense to invest in these.

If well implemented, DevOps can have great benefits for a quicker, safer, frequent delivery of small increments and faster user feedback. There are some things to consider when transforming an organisation to a structure like this. More on that in <a href="https://nielstalens.nl/2021/11/09/why-devops/" target="_blank">Why DevOps?</a>
