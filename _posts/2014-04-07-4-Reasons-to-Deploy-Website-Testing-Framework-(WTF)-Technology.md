---
layout: post
title: 4 Reasons to Deploy Website Testing Framework (WTF) Technology
tags: [Lessons Learned,All Things Tech]
image: /public/images/edmunds-technology.png

bio: Daniel Kang is Director of Software Architecture at Edmunds.
 
biopic: 

featured-summary:
    <p> A brief summary of Edmunds' transition to Website Testing Framework (WTF) written by Daniel Kang. </p>

summary: A brief summary of Edmunds' transition to Website Testing Framework (WTF) written by Daniel Kang.

---

At the beginning of 2014, the Software Architecture team at Edmunds.com deployed a new Website Testing Framework (WTF) which enables us to run hundreds of parallel experiments in a reliable manner. Since launching WTF, our company has reached a new level of efficiency and confidence in designing, coordinating and measuring our controlled experiments. We wanted to share our experience building WTF, and go over the motivation for choosing an in-house solution. 

> <b> Motivation 1: Centralize the configuration of all AB tests </b>

We used to have two separate AB testing systems that were tailored specifically for JavaScript and for CMS templates. In both systems, the test configuration was essentially placed around the code block that would generate the AB variants. Since these configuration blocks were not easily visible, it became a tedious exercise to track down all the AB tests. We ran a very large weekly AB test coordination meeting with all Product Owners and Business Analysts to describe, slot, and track all running tests. 

The solution WTF provided was simple. All configuration code for both client and server side experiments are standardized and published from a single source. We also created a WTF Dashboard which shows experiments running in each environment. It contains a description of the test, the expected start and end dates, and the pages and components that are being tested. 

> <b> Motivation 2: Eliminate wait time to run an AB test </b>

One of the biggest bottlenecks we encountered in launching an AB test, was waiting for your test to get slotted to go live. The process for launching an AB test involved asking a Business Analyst to forecast the percentage of visitors required to confidently detect a lift in key metrics during a two week period. If three campaigns each required 33% of visitors, no other campaigns could be slotted. 

WTF changed this approach by allowing each visitor to be part of multiple experiments. Initially there was a lot of resistance to this approach due to concerns of cross contamination between campaigns, but we reinforced the fact that strong interactions between campaigns are rare. We still provide the ability to run a campaign in isolation, but this is strongly discouraged for most experiments since this reduces the number of visitors in our test pool.

With WTF we want developers and product owners to come up with testable ideas, and immediately launch their experiments when ready. This allows us to run more tests than ever.

> <b> Motivation 3: Auto coordinate AB test campaigns </b>

There are certain pages on our site that every team wants to test. WTF detects when experiments are trying to test the same page, and splits traffic evenly between the overlapping experiments. It also notifies the Product Owner of the overlap so that they can decide whether they need additional coordination. WTF also guarantees that no experiments will be starved of traffic since the traffic split between all overlapping campaigns happens at the beginning of the visitorâ€™s session. 

> <b> Motivation 4: Provide end to end audit of our AB testing system <b>

WTF has standardized reports for all live experiments. To ensure that all aspects of the testing system are functioning normally, we regularly run an AA test. Using a 95% confidence interval, we expect no difference in key metrics 95% of the time. This sanity check detects potential issues with the framework as we develop new features.

Conclusion: What's coming

As we increase our reliance on controlled experiments for various layers of our products, we want to accelerate the detection of winning recipes. We will be adding features to increase the sensitivity of our reports for key user segments. We are also formulating our Overall Evaluation Criteria, so that we can introduce Multi-Arm Bandit to dynamically split traffic between the recipe variants.
