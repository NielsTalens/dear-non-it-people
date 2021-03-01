---
title: Unit testen, code coverage an cucumbers
layout: post
author: sal
image: assets/images/testing/header.jpg
description: What is automated testing and how does it work?
categories:
- quality
- speed of delivery
- what is this thing?
featured: false
hidden: false
---

In this article I will tell you a little more about automatic testing, a very important part of continuous integration. I will explain concepts such as unit testing, integration testing, end to end testing, acceptance testing, TDD, BDD, code coverage.

# From validation afterwards to designing together

There was a time when software development had very tightly defined phases and where testing was the last one . If there was any budget left that is. In practice, this often turned into lengthy 'it's not a bug, it's a feature', 'But the user flow is bad but we build it anyway' discussions. Nowadays, we tend to view testing as an integral part of software development and not a separated topic. Automatic testing is now also an accepted standard way of working.

> Continuous delivery without testing is a bit like switching off your airbags and driving onto a busy highway with a blindfold. You can take your changes and just see what will happen. You might even get pretty far but still..it might not be the best plan. For both cases I just can't think of any good arguments.


As an example for this article, we take a shopping card from a webshop:

![testing]({{ site.baseurl }}/assets/images/testing/testing-01.png)

In principle, we are already looking at at least 4 features (where I leave the footer out of consideration), each of which has its own functionality. All functionality together results in a customer being able to prepare his or her cart and order it in the next step:

![testing]({{ site.baseurl }}/assets/images/testing/testing-02.png)
# Unit testing

![testing]({{ site.baseurl }}/assets/images/testing/testing-03.gif)

Each feature or component has its own specific set of functions. For example adding up when you click on the plus sign next to the shoe or entering and checking a coupon code. We call these units and the testing these functions unit testing. Ideally, a unit only does one thing. Let's take the item price calculations as an example:

![testing]({{ site.baseurl }}/assets/images/testing/testing-04.png)

The first line indicates the total price, so the code for this will be something like:
> Total price items = item price x quantity. So in this case 1 x 299.43.

A unit test is a piece of code that checks, every time the tests are runned, whether the code still does what it should do. That a change did not affect our functionality. In this case the test would look like this:

* Suppose the item price is $ 50 and the quantity 3 then the expected total price of all items is $ 150
* Suppose the item price is $ 3.33 and the quantity 0 then the expected total price of all items $ 0, -

In this example you only pay shipping costs if you order items under $ 300. The unit tests for this are:

* Suppose the item price is $ 50 and the  quantity 3 then the expected shipping costs are $ 40
(so the total price of the items is $ 150. This is less than $ 300 and so there must be shipping costs. paid)
* Suppose the item price is $ 50 and the  quantity 7 then the expected shipping costs are $ 0, -

We also do the same for the import charges and the total of the card. It is very good to know that whatever we change in the code, the calculations will at least be correct.

# TDD

TDD stands for Test Driven Development. It is a way of working where you first write the test and only then the code. In order to be able to write the test initially, a developer must have a very good understanding of what the functionality should do.

The sentence: suppose the item price is $ 50 and the  quantity 3 then the expected total price of all items is $ 150 gives a broader context and an example of what actually needs to be done. Making the functionality is a matter of passing this test.

# Integration testing

![testing]({{ site.baseurl }}/assets/images/testing/testing-05.gif)

With integration testing we examine whether the cooperation between the features / components also works well. For example, we have to make sure that we pass the total amount correctly to the credit card service. But we must also thoroughly test the cooperation between the various components within a feature. You can compare it with a sentence. Every word is spelled correctly, but you will still have to check whether the whole (the sentence) is correct.

If we click on the plus next to the shoe, we expect the prices to be adjusted as well. In this case we test whether we get the correct  quantity and not whether the plus works. After all, we have already covered the operation of the plus sign as a unit test (each click on the plus sign increases the  quantity by one).

![testing]({{ site.baseurl }}/assets/images/testing/testing-06.png)

* Suppose the item price is $ 70 and the quantity is 1, then the expected total price of all items is $ 70
* If the quantity in the top component changes to 2 then the expected total price of all items is $ 140

# End-2- end / acceptance tests / BDD / ATDD

These tests have the most in common with how the user experiences the software. We take a look at the behavior of the application here. Descriptions of these tests are also often written in human language.

![testing]({{ site.baseurl }}/assets/images/testing/testing-07.gif)

# BDD & ATDD

BDD stands for Behavior Driven Development and ATDD for Acceptance Test Driven Development. End-to-end means that we test the application from start to finish.

In all these cases, this means that we can describe the desired behavior in advance and automate its validation as part of the development process.

The great thing about this is that people from every discipline can contribute ideas and describe steps. It is very enlightening to think in advance about which steps a user takes (a user journey) and what choices we can make in advance. It is best to start with a happy path (the ideal user journey without complications) and come up with variants(edge cases):

![testing]({{ site.baseurl }}/assets/images/testing/testing-08.png)

The test to test the coupon functionality:

* Given I have 1 x Nike Zoom blue 1 x Nike Zoom red in the shopping cart put,
* When I click on the heart Icon,
* Then I see that the heart becomes red,
* When I enter the code 'XzOp014524BDZ' in the coupon,
* And I click the Apply button,
* Then I see the message 'Congrats, you receive an 25% discount!'
* And my total price is $ 575.15

And in the case of an incorrect code:

* ...
* When I fill in the code 'BLABLABLA_FOUTE_CODE' in the Coupon field,
* And I click onApply,
* Then I see the error message "Your coupon is not correct,"

# Cucumber

Maybe you've heard your team talk about Cucumber and thought that was strange since it was hours from lunch. Cucumber is simply a tool that has been around for some time with which you can do BDD & ATDD testsing. Although Cucumber is well known, many new automatic testing tools have been created in recent years.

# Code coverage

The code coverage is the number of relevant lines of code that are tested. Often a number like 80% is used, but there are also plenty of teams that want to keep the coverage around 100%. When this coverage becomes too low, you can cause the pipeline to stop. However, coverage does not say anything about the quality of the tests! You can also write bad automatic tests. Something that can help with this (testing your tests) are mutation tests, but that goes too deep for this article.

![testing]({{ site.baseurl }}/assets/images/testing/testing-09.png)
# No guarantee

Bugs can always occur in every application, and often at the most impossible moments. Due to the automation of testing the moment when we talk about what and how to test is now much earlier in the process.  During the development the automatic tests are done continuously by the developers, with every commit on the test and production servers.

In short, it provides the following advantages:

* Thinking earlier about testing ensures a better architecture and user experience,
* If something is difficult to test, the application is often too complex / too dependent on other code,
* Because the code is tested it is easy for new developers to get up and running quickly (any error will be caught quickly by failing tests),
* You can confidently change pieces of code without breaking other parts,
* The tests serve as documentation for how the application should work,
* Fast and high frequency of feedback (The later you get a bug the more expensive it becomes),
* By seeing testing more as a design pattern, it becomes something that can be done by the entire team, including stakeholders,
