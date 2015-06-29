---
layout: post
title: Thoughts from the Gradle Summit
---

# Introduction

*Hello California! You are crazy, we are Scorpions! Rock You Like a HURRICANEEEE!*

I've never been to California before.  I've always thought of it as this wonderful liberal playground on the far side of the country where all my favorite tech comes from.  I consume Silicon Valley documentaries and stories like Pez.  I relished in learning the history of Intel, Apple, and others forged in the fires of venture capitol.  When I discovered the Gradle Summit was in Santa Clara, I was excited for the chance to visit the home of some of my favorite stuff.  I was lucky enough to have some time to visit some landmarks in "The Valley", including the Computer History Museum which I'll be writing another post about soon.

# Summit Day 1

I was lucky this morning, within minutes of reaching the breakfast buffet I spotted Andrey Hihlovskiy, who created a Gradle plugin that I'm closely following with hopes of applying at work.  I flagged him down and introduced myself, we immediately started chatting about the Wuff plugin, which is his answer to the fact that building Eclipse/RCP applications absolutely blows.  I immediately realized why attending conferences is so important: no matter how many emails, forum posts, or pull requests you participate in, nothing is as valuable as a face to face meeting.  One tennant of Agile that I can truly support.

Following breakfast, Hans Dockter gave his keynote address introducing the new "Gradle Inc.".  Gradleware goes away, the company becomes Gradle, they change logos, and there was much rejoicing... *Yaaay!*  This stuff was kinda superficial, but soon he started getting into the cool stuff: drastically improved build performance, and the new "gradle.com" offering.

Gradle.com is going to help answer the age old question: It works on my local box, why doesn't it work in CI? Imagine that every build in the entire enterprise, local or CI, gets recorded and tracked by a centralized system.  A buildmaster can review all the builds and quickly diagnose problems without having to go through the old "send me your logs" rigamarole.  I can see a lot of value here, provided that Gradle finishes it and makes it available as a self-hosted application.  I'd love to have that much insight to what people are building, and to have a much simpler way to share strange build results.

We were also treated to some previews of Buildship, the new Eclipse integration for Gradle.  I'm particularly excited about this, because it may finally make Gradle feel like a first class citizen in Eclipse.  The current implementation made by Pivotal isn't terrible, but it also isn't that awesome.  Buildship and Eclipse Mars come at a good time for me, since it's now that I'm most likely to facilitate adoption.  I want to get while the getting is good.

# Day 2

## Special Topic: Project Layout -> Ur doin' it wrong.

Gradle has some opinions about how to lay things out, and you probably ought to listen, but I'm not completely convinced.  First of all, if you want a flat file structure, you have to suck it up and have some loose files in the root.  Second, you have to have the entire project checked out. There's no two ways about it, Gradle expects you to treat all your projects in a repo as citizens, nobody gets left out.  If you don't need to work with it, then don't. I can accept this from the angle of trying to have a complete software model, it's not *just* a build system anymore. Plus, if you really hate having every project in front of you, then there's Prezi Pride.
