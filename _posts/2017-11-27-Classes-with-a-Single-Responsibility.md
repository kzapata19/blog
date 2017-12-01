---
layout: post
title:  "Classes with a Single Responsibility"
date:   2017-11-27 19:36:36 -0700
categories: POODR, Ruby, Classes, OO, SRP
---

Most applications, once created, will evolve at least once (unless you have a barebones static [site](http://www.cnn.com/US/OJ/) that hasn't changed since 1996). New features will be added, removed, or re-designed to keep up with the current demands of the users or business. Since future changes can't be precisely anticipated, the codebase should be easy to change, flexible, and re-usable.

Enter the SOLID principles by Robert C. Martin. Single Responsibility (SRP), Open/Close, Liskov's Substitution, Interface Segregation, and Dependency Inversion. These are the five principles that should guide programmers every time they produce code. This post will focus on the first principle: Single Responsibility Principle (SRP).

SRP's definition is pretty simple: a class should only have one reason to change, in other words, only one responsibility. Y tho?

Well from a non-programming perspective, trying to multitask usually yields lack-luster results. Any time I try to divide my focus among different activities, I end up either half-starting things or taking longer than expected to accomplish all the tasks. Recently, I've especially noticed that even trying to juggle multiple thoughts at once isn't very efficient and usually leaves me more confused and with a headache. Nightly meditation is helping with this. Learning to organize your thoughts is a huge mental workout but the benefits are enormous. It's even helping me get a handle on my chronic insomnia.

Just like giving your mind one single reponsibility to tackle at a time, the benefits of giving your class a single responsibility abound. Subjecting your class to SRP ensures that:
- any changes made to the class won't have unexpected side effects
- small changes in requirements will have corresponding small code changes
- the existing code is easy to reuse
- the easiest way to make a change is to *add* code

Applying SRP doesn't just stop at the class level. You should apply it to your class methods as well. The goal should be to extract the extra responsibilities within each method (for example the loop and the action performed to each item).

The model we use to design an application becomes it's foundation. If we focus on creating a seperation between the logic and the data passed into our application, it will be easy to add, remove, and redefine features regardless of how complex the codebase becomes in the future.

