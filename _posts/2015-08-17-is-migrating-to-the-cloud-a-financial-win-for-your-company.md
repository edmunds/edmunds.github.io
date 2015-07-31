---
layout: post
title: Is Migrating to the Cloud a Financial Win for Your Company?
tags: [Lessons Learned,All Things Tech]
image: /public/images/migration-to-the-cloud-graphic.png

bio: Brad Tawa is Executive Director of Sourcing and Project Management and has been with Edmunds for 7 years.  He has held numerous finance, accounting, sourcing and technology leadership positions throughout his career and played a key role in developing and executing on Edmunds' cloud migration strategy.

biopic: Brad-Tawa-bio-pic.png

featured-summary:
    <p>We will save 70% by migrating to the cloud.  There, we said it.  Every post or article on public cloud migration experiences seems to contradict the one I just read.  For every company that claims to have saved money by switching to the cloud, there is another that just moved back to on-premise for the very same reason.  What gives?  For background, Edmunds is a privately-held, profitable and growing company.  As 100% of Edmunds’ revenue is derived online, uptime and performance of the website is critical.  We have operated from co-located data centers for 10 years and have lived through multiple build-outs, so we know what it takes to build and run a data center both operationally and financially.</p>
    <p>This is still the featured summary.  You can add markup to make it look extra pretty, if that's what you want to do.</p>

summary: We will save 70% by migrating to the cloud.  There, we said it.  Every post or article on public cloud migration experiences seems to contradict the one I just read. 

---
We will save 70% by migrating to the cloud.

There, we said it.  Every post or article on public cloud migration experiences seems to contradict the one I just read.  For every company that claims to have saved money by switching to the cloud, there is another that just moved back to on-premise for the very same reason.  What gives?

For background, Edmunds is a privately-held, profitable and growing company.  As 100% of Edmunds’ revenue is derived online, uptime and performance of the website is critical.  We have operated from co-located data centers for 10 years and have lived through multiple build-outs, so we know what it takes to build and run a data center both operationally and financially. 

<img src="{{site.baseimagesurl}}/migration-to-the-cloud-graphic.png" />

<h2 class="question-heading">What steps are involved in preparing to migrate to the cloud?</h2>

A prerequisite to any automation effort is to ensure the underlying processes are sound and sustainable.  Poor choices compound quickly in the cloud.  Many of Edmunds’ applications had to be refactored in order to operate in the cloud.  We took advantage of this work to scrutinize our existing technology stack, down to the OS and database level and questioned whether our choices were extendable to the cloud.  We pursued open source alternatives where practical, and carefully vetted any commercial software to ensure portability and sustainability.

<h2 class="question-heading">What are some things to keep in mind before migrating to the cloud?</h2>

Find the bodies that are buried in your data center.  When contemplating a migration to the cloud, take the time to accurately assess your current data center costs.  If you are taking an “all-in” approach, as Edmunds did, this exercise is fairly straightforward.  If not, your challenge is to find an accurate method of allocating your data center costs to the applications you will be migrating.  Work closely with your finance team to help develop this cost allocation, but don’t cede the responsibility to them.  Allocations based on revenue or other business metrics will lead you to false conclusions.  It is important that you identify a method to allocate your data center costs by compute resources.

I have also seen models where data center costs are derived from typical server configurations, which are projected across business segments.  This doesn’t take into account failed configurations, memory upgrades, and the slick new PDUs that your data center manager had to have.

It (almost) goes without saying, but account for all of your data center costs - including monitoring and asset management software, racking and stacking, (re)cabling, even parking costs for your people to spend the day at the data center.  

<h2 class="question-heading">How do I set up my plan for success?</h2> 

Plan for failure.  I’ve heard multiple stories where companies pulled the plug on their cloud strategy due to a surprise monthly bill from their provider.  It is important that you allow your people to experiment in the cloud; set aside a discrete budget and establish accountability measures - these do not need to be hyper-detailed goals, as they will change often.  Identify a single person responsible for tracking and managing your cloud costs (again, don’t outsource this to your finance people). 

Once you have developed a model to forecast your cloud computing spend that has been presented to your executives and accepted by your CFO, don’t let it collect dust.  Constantly update your forecast as your migration plan evolves and as the market (i.e. pricing) adjusts.  Models that incorporate a blended rate for all of your cloud instances are worthless - take the time to sweat the details.

<h2 class="question-heading">What is the final step in deciding whether or not I should migrate to the cloud?</h2>   
Ask yourself if you’re ready to commit.  Depending on which cloud provider you select, you may have to decide whether committing to a set configuration makes economic (and operational) sense for your organization.  As we learned early on, committing prematurely could cost you more than pay-as-you-go options.  We quickly ruled out longer term commitments as cloud computing, as well as our own business, is evolving far too quickly to place any bets to the contrary.

There are other/unpublished ways to negotiate cloud costs lower, however, these generally entail some type of revenue commitment and/or prepayment, which will take you further away from the utility-based model that attracted us in the first place.  As cloud providers are still experimenting with pricing strategies and the market is still searching for its equilibrium, Edmunds values flexibility.  The price wars don’t hurt either.

<h2 class="question-heading">How has Edmunds’ experience been in migrating to the cloud?</h2> 
We are in the home stretch of our migration, and so far, so good.  We run 100% of our production traffic through the cloud, which is now part of our normal environment rotation.  We have retrofitted most of our back-end applications and as we get closer to decommissioning our data center, we will spin-up redundancies in the cloud as well.

We’d love to hear from others on how their experiences have been in migrating to the cloud.  




