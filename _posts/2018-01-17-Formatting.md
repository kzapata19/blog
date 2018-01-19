---
layout: post
title:  "Formatting"
date:   2018-01-17 14:10:23 -0800
categories: formatting, clean code
---

"Code formatting is about communication, and communication is the professional developer’s first order of business."

### Vertical Formatting: Like a Newspaper

I found the newspaper metaphor Uncle Bob uses to describe how the ideal file should be organized: like a newspaper article with the highest level summary at the top and more details as the reader moves down the article. Functions called from the top function should come directly below it. This pattern should be followed all the way down the file until hitting the lowest level where the most detailed functions reside at the bottom of the file. According to Uncle Bob, this is a good way to organize code because the reader does not have to struggle to mentally juggle the location of all the different pieces in order to make sense of the program as a whole.

## File Size

The size of the source file should ideally be closely related to the size of the class (more will be explained in a later chapter). The typical number of lines in a file are between 200 and 500 though this range is not set in stone. Basically try to keep the files as concise and small as possible.

## Vertical Openness Between Concepts

Use a blank line to separate different concepts/groups of code. For example, use a blank line to separate declarations, imports, and each function. Each blank line will serve as a visual cue to the reader that will identify a new and separate concept.

## Vertical Density

Use vertical density to suggest close association of similar concepts.

## Vertical Distance

Concepts that are related to one another should be kept vertically close:
- variable declarations: should be declared close to their usage (e.g. local variables, control loop variables)
- instance variables: shold be declared at the top of the class (or in your language's well-known place)
- dependent functions: functions that call helper functions should all be vertically close

### Horizontal Formatting

## Line Size

The width of a line should not be so long that the reader must scroll right. However, Uncle Bob acknowledges that nowadays monitors are wider and younger programmers will sometimes shrink the font to fit more characters on the screen. He suggests a limit of about 120 characters per line.

## Openness and Density

Use horizontal white space to group things that are closely related or to separate those that are loosely related. For example, assignment operators can utilize white space to separate the variable name from its assigned value. While the lack of white space between a function name and the parentheses that surrounds its arguments suggests both are closely related.

## Alignment

Use horizontal alignment to accentuate the true intent of the code. For example, if a list of declarations is aligned in such a way to obscure their types, reduce the horizontal spacing.

## Indentation

Use indentation like you would to structure an outline: create a hierarchy of scopes that easily identifies the classes, methods within those classes, blocks within those methods, blocks within those blocks, etc. Programmers rely on indentation to figure out which scope they are in and allows them to easily travel through scopes as needed. Uncle Bob suggests not breaking the identation for small statements

### Team Rules

Follow the agreed upon formatting by your team over your preferences. This will ensure a single, uniform formatting style.
