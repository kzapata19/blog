---
layout: post
title:  "Why Reading Old Code is Hard"
date:   2017-12-18 19:36:36 -0700
categories:
---

> What I cannot create, I do not understand

- Richard Feynman

As software engineers, when given a choice, our impulse is to build something from the ground up rather than make adjustments to existing code. You think that the latter choice would seem more appealing because generally making adjustments or adding on to an existing thing is less labor intensive. However, with code it is harder to read and understand an existing code base than to write code from scratch.

I had to step away from my Tic-Tac-Toe project for about a week because of a recent family emergency. When I opened up my project's directory, it took me a while to retrace where I had left off the last time I worked on the project. As I retraced my steps, I noticed small bugs (ex. the board was unevenly displayed when it is 4x4 because the size of the 0-9 digits differ from the 10-16 digits) and saw that I had violated some of the SOLID principles (ex. methods had more than one responsibility).

I had a burning urge to delete all the code and start over. HA! I thought, "Well this is a mess. If I start over, I'm sure I'll create a better version of this game." The issue with that train of thought is that it's most likely wrong. Re-visiting code is hard but starting over from scratch will erase all the lessons learned up to that point. The old code has been used and tested. Bugs came up along the way and they were fixed. So yes there are some methods that have more than one responsibility but that doesn't automatically mean that the whole code base should be demolished. Instead the best approach is to make adjustments piece by piece with the help of the existing tests (or modifying them if necesssary).

Although my learning style includes creating things in order to undestand them, I think that in this case, re-creating the code base is not necessary to re-gain an understanding of my code.
