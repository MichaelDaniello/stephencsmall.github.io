---
layout: post
title: Home NAS with FreeNAS
---

# Introduction

I've accumulated a lot of data.  A rough tally of all my digital data is about 5TB total, spread across a lot of disk drives that are mostly throwaways from old projects.  They've all been folded into either my dedicated server, or they're still connected to my Windows system.

All of this data needs to be brought under one roof.  I have experimented with NAS in various ways for a while, most of the time I've landed on something Linux-y running SAMBA.  I haven't gotten to advanced file systems, backup routines, or even other file sharing services, save for some brief dabbling in AFP.

For some time I have been entertaining the idea of switching my server to FreeNAS.  FreeNAS is a robust project based on FreeBSD that aims to provide a completely free distribution specializing in network attached storage that can run on consumer hardware.  I decided to take the plunge this weekend, and after two days of fiddling, I can say that I'm pretty satisfied with the decision.

# Why FreeNAS?

If you're a glutton for punishment (which I've often found in the *nix community) you might be thinking "Why don't you do all of this on `<insert distribution of choice>` ?".  You probably imagine me firing up something like a Ubuntu 13.04 machine, tweaking some SAMBA settings, and cruising into the network attached sunset.  You would also be exactly correct about all of my previous runs at creating a NAS setup for my apartment.  Most of the time, I fired up a basic distribution, shared some files, and called it a day.  This time is different.

The big thing here is the use of an advanced file system instead of the hum-drum typical desktop FS.  FreeNAS comes with XFS out of the box, and I hear all the time that filesystem performance on BSD systems is extremely good.  Sounds like a good recipe for me.

