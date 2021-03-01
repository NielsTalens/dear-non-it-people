---
title: Why have they been talking about Trunk based development for the last couple
  of weeks?
layout: post
author: sal
image: assets/images/tbdevelopment/trunk- khari-hayden.jpg
description: What is trunk based development and why is it so important? Does it really
  matter?
categories:
- technical practices
featured: false
hidden: false
---

This article is about something we call versioning. It is one of the basic things you have to set up when developing software. You've probably heard the word Git before. This is one of the most widely used version control systems. Other names you may sometimes hear are: SVN, Mecurial, GitLab, GitHub, BitBucket, Azure devops or AWS code commit.

# Version control
Most of us have to deal with Office365 and OneDrive or Google Docs and Drive. The source file is somewhere on a server (often in the cloud) and anyone who has the right access can see it and make changes to it. If you and me work on the same documents and you make a change locally (on your computer), I will eventually see this reflected in the document on my computer. We can open the document in an editor (Word) but also in the browser if we want.

While I'm typing this blog, I can see that it is also immediately saved to Google Drive:
![saving]({{ site.baseurl }}/assets/images/tbdevelopment/01-saved.png)

That's great because now I know for sure that my file is safe in the cloud and that my colleagues will see the changes. 

Another very nice feature of this way of working is version management. I can see all the saved changes and can even revert versions if I would like to:
![versions]({{ site.baseurl }}/assets/images/tbdevelopment/02-versions.png)

Basically this is how version control on code also works. But why on earth would you argue about this for weeks?

# Trunk based development vs feature branches
You can deal with version control in different ways and how you subsequently get this software to production. Let's say we're making a document together and there's someone else who will read along (like a reviewer).

**Trunk based development** (TBD) means that we agree to use one source document, which is on a server, in which we can both make changes locally. The great thing about it is that the person reading along can see all the changes immediately. However, we must be sure that there is a very good spell check, otherwise the chances of the reader seeing errors are high.

If we agree to use **feature branches** we both create our own version of the file, this is called a branch, (document_version_niels.doc and document_version_your_name.doc) and both commit our changes. When you are done with your part, you can upload your version to the server and submit a pull request. I review your changes and discuss how things can be improved if necessary. If everything is OK, I merge your version into the source document and your changes are in the source file. The co-reader can only see your changes after merging.

![Veeterzy]({{ site.baseurl }}/assets/images/tbdevelopment/tree-veeterzy.jpg)

Now version control is a bit more advanced than this but hopefully I have been able to explain the essence. Then we can now go back to the initial question: *Why have they been talking about Trunk Based Development for weeks now?*

In practice, there are many IT professionals who have strong opinions about which ways of working is best. Sometimes this opinion is based on the firm belief that the one way is the only true way and that can go quite far. Certain people or teams are so convinced that they are right and it can difficult to move in another direction. That is even more difficult if they work for the same company.

However, the cause of long discussions about the version control strategy is often a mix of conviction and underlying matters.

Possible underlying issues that make teams want to use feature branches may include:
* Trust in each other / seniority of team members: Because every change must be viewed through the pull request, we ensure that the code is written according to the team's standard. The four eyes principle applies here.
* Trust in the quality of the infrastructure: If the environment on which the software is to be installed does not work properly or often breaks down, it is difficult to use it often. Choosing branches in this case is a case of trying to work around the problems.
* Lack of tests: if there is not enough quality built in by automatic tests (the example's spell checker), it is very risky to put every version live. 

Possible reasons that make teams want to do trunk based development are:
* Speed of delivery: branches (branches) sometimes cause the changes that go to production to be much larger (and often cause more problems). This means that feedback from the end user will not come back until later.
* Quality and trust: Installing, testing and putting the software on the server is a fully automated process which is very predictable. Fixing any errors is something that is quick. Why delay delivery in this case?
* Deliver small changes quickly: Each feature is cut into the smallest possible working software that can go directly to production.

# No snake oil.
Also with regard to version management there is no solution that is perfect for every team, company or product and a team has to think carefully about the right set-up. However, it is a supportive process and not worth spending a lot of time and money on. The main goal is always to develop a good end product. Not to make mediocre products with the perfect version control strategy.

I often use the same tactic as I use in the agile processes for new teams. Let's start with the simplest setup possible and see what else we need from there. Inspect and adapt!


### Extra: a number of version control terms
**Repository**
The folder containing the project (and therefore all code) within a version control system is called the repository.

**Merge conflict**
It can happen with both TBD and feature branches that we have both modified the same rule. This is called a merge conflict, and we'll have to tell Git which version we want to keep in the source file.

**Push**
By means of a push command you send the changed files to the server. Version control generally does not auto-save and upload to the server. You decide when your work is finished and it needs to be uploaded.

**Pull**
To make sure you always have the latest version of the files, with the changes made by others, download them regularly using the pull command.
