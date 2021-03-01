---
title: About pipelines and continuous everything and more
layout: post
author: sal
image: assets/images/pipelines/pipes-MichaelGaida.jpg
description: What are al these continuous things nowadays? Does it really matter?
categories:
- continuous delivery
- technical practices
- quality
- speed of delivery
- what is this thing?
featured: true
hidden: false
---

Continuous integration, delivery and deployment are a couple of concepts that you have probably heard more and more often in recent years. They are not entirely new topics and have actually become the industry standard for software development over the last 10 years.

# Continuous integration
In [this article]({{ site.baseurl }} /why-are-they-talking-about-trunk-based-development-for-the-last-couple-of-weeks/) I described the basics of version management. Continuous integration is triggered by the version control system. Every time a piece of code is sent to the version control server, the continuous integration server also gets to work. We then say that the pipeline is running. This pipeline is no different than a number of scripts that tell the server to build the code, then do the automatic test, then check the code for security and code quality and then put this code somewhere. If something is wrong in one step, the whole process stops.

# Continuous delivery
Putting software on the server was often a difficult and annoying job. On one hand it was a repetitive thing, but there were often scripts that you had to adhere to. If you were lucky. If you were unlucky, there was one person who always did it and knew how to do things. You know, the person who could never go on vacation.
![continuous delivery]({{ site.baseurl }}/assets/images/pipelines/cd-all.png)

The continuous delivery process automatically puts the software on the server. It ensures that database changes or migrations are implemented, configuration in the network is correct, stops and starts the server if necessary, etc. Then it runs the acceptance tests to see if everything is okay.

# Continuous deployment
The difference between continuous delivery and continuous deployment is that in the case of continuous delivery you decide for yourself when to deploy to production, but with continuous deployment this automaticly happens. So every change goes directly to the end user:
![continuous deployment]({{ site.baseurl }}/assets/images/pipelines/deployment.png)

What problems are we actually solving?
* Elimination repetitive and manual work, 
* Fast feedback (if something is not right, we will immediately receive a notification),
* No more 'It works on my machine'. After all, the software is passed through various checks on different systems. 
* Reliable delivery and fewer disruptions during and after deployments,
* Little / no time spent on deployment (time that can be invested in development),
* A nice overview of bottlenecks (lead time pipelines, number of errors after deployment, number of deployments, ...),
* Possibility for thresholds. By including the quality checks we can ensure that the pipeline fails if we are below these criteria,
* ...

# Gold plating
Creating and using a good pipeline is not only extremely useful and costs / time saving, but is for many people also very nice to do. Sometimes it is like Lego. This is automation in the purest sense of the word. There is also a lot of great tooling and integrations with other systems. There is a small risk here if we are not careful: continuous delivery is a way of working that is often very useful but never a goal in itself.
![Gold faucet Gerber pixabay.com]({{ site.baseurl }}/assets/images/pipelines/faucet-Gerber-Pixabay.jpg)

Compare it with a kitchen faucet. The tap is there to get water. Newer and nicer taps will always be made, but the thing that matters, water, just has to come out. And always! And as soon as possible.

For someone who is not directly in the development team, there are some actions or behaviour that you can watch out for:
* A pipeline that fails very often. This can of course have hundreds of reasons, but somewhere there must be a concrete cause. If there are a number of causes (or there is no clear answer to the question of what the cause is) then I recommend doing a value stream mapping with the team. This is a very nice and fast way to see where the most profit can be made. [https://en.wikipedia.org/wiki/Value-stream_mapping]
* A pipeline that has been broken for a longer period of time. You often have to deal with a lack of shared knowledge and no DevOps mindset. One of the mantras of continuous delivery is: 'if you break it, you fix it'. In principle, fixing the pipeline comes first.
* A lot of time is spent on the pipeline. Although, like all infrastructure matters, time must be spent, it is also necessary to consider what it is worth to you. Sometimes we are optimizing with regard to continuous delivery, while an end user will never see that millisecond gain in the automatic tests in the application. In fact, all the time we invest in this sub-optimization we are not spending on improving the user experience! In order to optimize the right things, a value stream mapping can also offer a proper starting point here.
* No visibility / dashboards and alerts. The essence of continuous integration is fast feedback. The pipeline works in such a way that whenever something is wrong, we will know immediately. After all, the pipeline is failing. You should therefore be able to see this at all times by means of dashboards and alerting.  
* …

![Value stream mapping]({{ site.baseurl }}/assets/images/pipelines/better-faster-vsm.png)

A continuous deployment pipeline is therefore nothing more than a number of scripts that are executed in a logical order. We used to run the scripts ourselves and now Jenkins, Azure DevOps, GitLab or Bamboo does this for us. Nothing more and nothing less. The essence is to get feedback on the quality of the software and the process to get it to the user asap. This way of working can therefore ensure that we now spend that time on making our products more beautiful and better.
