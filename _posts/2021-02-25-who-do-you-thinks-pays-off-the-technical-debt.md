---
title: Who do you thinks pays off the technical debt?
layout: post
author: sal
image: assets/images/technical-debt/chevanon.jpg
beforetoc: "Picture: Chevanon"
toc: true
description: In this article I explain what technical debt is and what the reasons to create this debt can be. Who decides to create debt and who will be the one that pays it off?
categories:
- technical debt
- quality
featured: false
hidden: false
---

You have probably heard the term technical debt from time to time. It's often used as an explanation of why we cannot create and deploy as fast and flexible as we want or need. Why the throughput of a new feature is so long.

![debt]({{ site.baseurl }}/assets/images/technical-debt/debt.jpg)

The thing with debt, like taking a loan at the bank, buying stuff on credit or the choice to allow technical debt, is that there is a conscious choice made to create this debt even if it seems the choice is sometimes made by others.

And just like any debt, someone will have to pay off the technical debt. The bigger the debt, the more it hurts. Now the question remains: who is responsible and who will pay off the debt?

> Famous last words: We will improve our quality after this period!

**Let's say you and I are going to start a new company. We are going to deliver goods with drones. We will build and maintain our own fleet of drones and people can just order and pay through their bank app.

**So we now have the shop (the garage in which we will build and maintain our fleet) and we have our business (selling and delivering goods). The game is now to grow as much as possible without spending all funds we have at once. This means we have some choices to make with each their own effect on our technical debt:

## Choice: security

![Security]({{ site.baseurl }}/assets/images/technical-debt/artem-beliaikin-security.jpg)
*Picture: Artem Beliaikin*

We choose to not spend too much on the security of the drones and invest more in new features. We have never had one crash into a customer's house yet and we expect that the chances are not so high. They can be hacked but we think we will be able to get up and running faster without bothering about security too much.

## Choice: maintenance

![Maintenance]({{ site.baseurl }}/assets/images/technical-debt/maintenance.jpg)

We will spend more time on building new drones so we can deliver more goods for more customers and spend less on maintenance of used drones. This means we will invest less on software updates and checks on the moving parts of the machines.

## Choice: manual updates

![Security]({{ site.baseurl }}/assets/images/technical-debt/polina-zimmerman-error.jpg)
*Picture: Polina Zimmerman*

We can either choose to spend some budget on a way to automate the updates of our drones instead of doing it one by one. It will cost us quite some but the other choice is to have one or two engineers updating the manually which often has to be redone since people make mistakes.

## Choice: revise the architecture and refactoring

![Security]({{ site.baseurl }}/assets/images/technical-debt/cottonbro-architecture.jpg)
*Picture: Cottonbro*

We found out that customers want to have a video stream of the drone when delivering their goods so we added a camera on top and we also had to add bigger rotors for the weight. For now we chose to glue the camera and used duct tape for the wires but then we added an extra rotor because of the weight of the tape but we also needed a bigger battery for the extra rotor which we needed for the tape and we glued that one…..

The thing with building stuff is that after adding new features we sometimes end up having other dependencies and needs than when we started. We can make things more complex by working around the challenges which often results in more complexity.

## Choice: quality

![Security]({{ site.baseurl }}/assets/images/technical-debt/drone-wars.jpg)

Well, we found out that however the industry standard is to check whether the bolts are tightened properly, we can save time by assuming we alway do a good job (yes people who do not write automated tests. I really refer to you right now).

So we are one and a half years later and we had some hacked drones that delivered the goods to the wrong address, some that caught on fire and crashed in buildings and there is a small nuclear threat from Germany which we cannot say for sure we didn't inflict.

So the question remains: who pays off the technical debt?
Well if we do not structurally change things it is all of us. But sadly we are not even paying off the debt but only the interest.

* It is the engineering department since their work is mostly fixing stuff that is already broke and they never seem to do some work they love. A lot of work is done manually and takes much time. Also they need to hire more and more engineers to be able to create stability. Overtime is also pretty common.
* It is you since you won't be able to ship as many deliveries as you would like and the rating of the service is decreasing. You have more great ideas but with the current state you are glad if the rate of complaints decrease. The costs of overdue maintenance are increasing.
* It is the customer who was very delighted to become one but saw that the quality of service went down. It makes them sad because they want to love the product but the product doesn't seem to love them.


I can imagine it is hard for you, a non-drone engineer, to make think about these choices since you cannot oversee the consequences properly. If we inject some highly complicated sounding tech words during our discussions we can be sure it doesn't make the overseeing any easier. If we really want to prevent more debt we should agree on some standards. I personally hold on to the following:

* Quality is non-negotiable
* Security is non-negotiable
* Maintenance is a structural part of our work
* Refactoring is a structural part of our work
* Automation is key

Consciously making small temporary technical debt can be a good choice sometimes. But in general there are not so many reasons for choosing tech debt. We have the knowledge, the tools and the people to build the right thing the right way. If you choose it, do it consciously and never ever forget that every debt needs to be paid off.
