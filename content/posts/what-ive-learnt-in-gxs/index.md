---
weight: 1
title: "What I've learnt in GXS?"
date: 2023-09-02T09:00:00+07:00
lastmod: 2023-09-02T09:00:00+07:00
draft: false
description: "What I've learnt in GXS?"
images: []
resources:
- name: "featured-image"
  src: "featured-image.jpg"

tags: ["mindset"]
# categories: ["documentation"]

lightgallery: true

toc:
  auto: false
---

<!--more-->

Wow, time is flying fast. My one-year journey with GxS has come to an end. 
I'm very proud to be a part of GxS where I work and contribute to building one of the first digital banking in Singapore.    

During this time, I've learned a lot, especially the mindset when working - which was very different from what I've experienced before in my career.
Believe that these mindsets are crucial to help us - as an engineer to go further, I wrote this article to share about it.

Firstly, let's introduce a bit about GxS.

## What is GxS?
https://www.gxs.com.sg/

Founded by Grab and Singtel, GXS Bank is one of the first two digital banks to serve retail customers.
So, what makes GxS different from other banks?

In GxS, we not only focus on releasing features to users but we also truly care about how to bring the best experience to users or solve user's painpoint when using banking apps. 
And since GxS was founded by Grab, we can inherit their lessons, their technologies, also some really good engineers from Grab 😛 (of course GxS's engineer are really good too), which allow us to move even faster.

Without further ado, let's jump right into the main part of the article.

## Project
### Automation test is essential

> If you want your project better, write unit test

I've joined some projects before GxS, and none of them requires to write automation tests. Of course, I've read about why tests are important, but since my previous projects never required me to write automation tests, so I just ignored it.

Since we didn't have tests at that time, all the things we did were about building new features, fixing bugs, fixing bugs and fixing bugs. It was painful when we changed some logic to fix a bug, but that change broke other parts of the project without our acknowledgment 🥲 Things are even worse when the project is too big over time and ***it's become really hard to make changes because of a lack of tests*** 🥲  

***Human makes mistake***. And even with the help of QAs, sometimes we still release critical bugs to end users.   
(I remember once I released an e-commerce application to Appstore, then later PM told me the payment features didn't work and users can't buy anything 😂)

In GxS, automation testing is 1 of the important parts. At the time I wrote this post, we had over 3000 unit tests & UI tests with the coverage is almost 90%. We also discuss a lot to make sure each unit test has its own value for the codebase.  

Eventually, ***it reduces a lot of work for QAs & prevents hidden bugs, which means we're saving a lot of money and bringing a better experience to users***.

### Constantly measure customer impact

> If you want your project better, keep measuring it overtime

We successfully released new features to our customers. Now what?
As you can see in the image, we need to measure & improve. 

Before joining GxS, the projects I did were all about integrating some 3rd party Crashlytics (normally Firebase), and then we waited if there were new crashes & bugs reported by users. Sometimes we forget to check the Firebase's dashboard so maybe there are crashes that we didn't even know about 🤧

So, what are big tech companies doing differently?   
They have an ***automation process that continuously measures various kinds of metrics***: app size, build time, hangs, crashes, and CPU usage, ... and if a crash happens, we will receive a trigger automatically via Slack.   
***These metrics are also essential for tracking bugs or when we want to optimize performance in the future***.

So I suggest you should have some basic metrics for your app. If your app doesn't have it, then it will be your chance to implement it, and you will learn a lot during the journey.   
(I've implemented features to automatically gather app size & build time and generate a dashboard for visualization. It was a fun stuff to do. Now I'm really into building tools 🤩)

## Individual
### Be responsible & proactive

> If you want to go further in your career, be responsible and proactive.

When I joined GxS, I was amazed by the attitude of GxS's engineers. Each one of them is highly responsible & proactive.   

For the task each engineer committed to, he/she will try his/her best to deliver the best outcome, not just some temporary solution that works only under some specific conditions

Besides feature tasks, we also try to note all the ***problems of the existing codebase to a dashboard*** (which is a cool idea itself), and proactively do it whenever we have freetime.

### Be open

> If you want to go further in your career, be open.

Previously in Vietnam, I often struggled when I wanted to give some feedback to older engineers. Some of them don't want to listen to younger people, I guess.   
In GxS, everyone is open to learning. I can give feedback to senior engineers, or I can get feedback from junior engineers. That's normal. 

> “In every man there is something wherein I may learn of him, and in that I am his pupil.” - Ralph Waldo Emerson”

## Team
### Working as a team, not individual

> If you want your team become more effective, start working as a team, not coding "heroes"

In those projects I've been through, each project heavily relied on 2 or 3 core engineers, while other engineers in the team just did not-so-important tasks.
These core engineers **did all the hard work, reviewed every MRs, and took responsibility for every feature of the project**. Even worse, when other engineers implemented the features not good, these core engineers **re-implemented the features themselves**.

Looking back, this is painful. These core engineers **will become the bottleneck of the project, and we also take the chance to learn from junior/middle engineers**, ...

In GxS, we work as a team. We support each other and learn from each other. ***Even a junior engineer can take responsibility for a core feature, review MRs of middle/senior engineers or take on-call responsibility***. We trust each other.
Example: I reviewed MRs for engineers who are better than me frequently, and sometimes I noticed things they didn't notice.

> A good post that my ex-leader shared before: [How to prevent coding "heroes" from destroying the team](https://hackernoon.com/thoughts-on-software-development-heroes-5ec656c2e31a)

Another thing is that in my previous projects, engineers only cared about their features. We didn't even know what features others were doing, which means we never fully understood the application.   

In GxS, we had team meetings once every 2 weeks. In the meeting, each will show the team what features he's doing, the pain he has been through, or the lesson he has learned. So we learn new things, we understand the project and we can jump right in to support other features whenever the team needs us.

### Sharing culture

> Sharing is learning

Whenever we see some issues, we bring it up, not to blame the one who made the issue but to discuss, find the solution, and learn the lesson together.
Sometimes when we learn something new that can be applied to the project, we can share it with the team and discuss it.   

Don't be afraid that your idea is wrong or you ask a dumb question. As long as you learn something from it, just ask (but please make sure you have researched carefully about it before 😉)
