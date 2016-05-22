---
layout: post
title:  "Beginning my Google Summer of Code Journey"
date:   2016-05-21 17:15:30 +1000
tags: julia, gsoc, software
---

## Road to Summer of Code

I first became aware of Julia about a year ago, and started using it more heavily about 6 months ago.
I've found it an excellent language to work with, and a good fit for machine learning, linear programming, and general 'glue code' work.

I was introduced to and encourage to register for Google Summer of Code by my campus's Google Evangelist (big thanks!), and was my proposal for the Julia Language was accepted.
What follows is an abridged version of that proposal.

## Goals 
My proposal is based on the [Swirl-style tutorial idea][idea]: to create an interactive tutorial system for new Julia users, a framework for these tutorials, and tools to create tutorials.

I aim to build a Julia program for completing interactive tutorials, being available in the REPL and in Juno.
I've taken inspiration from [Swirl][swirl] and a similar tool called [MyPyTutor][mypytutor].
The core paradigm would be question and answer: lessons would consist of a cycle of explanations of concepts, followed by interactive questions, followed by answer checking.
I envisage these questions as being both closed-- and open--ended: questions involving syntax might have only one valid answer, allowing simple checking of the given expression against the correct answer, whereas questions with a broader scope might accept any answer that passes specified tests.

While lessons would be stored in a human-readable format, it'd be far more convenient if tutorial creators could use a program to generate the lessons without having to deal with the storage format.
Inspiration here could be taken from Swirlify.
Ideally, this would take the form of a GUI building upon lower level tools, such that authors could use the level with which they're most comfortable.
At the least, I aim to create a Julia package that represents lessons as native Julia data structures and that offers method to create and edit them.

Another major feature would be integration with the Juno IDE.
Juno is a series of plugins for Atom that aim to provide a stable and productive IDE for Julia users, and is of particular value to new users desiring an experience that works well out-of-the-box.
My proposal could use the existing Julia integration in Juno to provide interactive tutorials within Juno, and potentially allow the creation of tutorials within the IDE.

## Potential

Julia is currently a relatively minor language, but one with a lot of potential for growth.
I believe that with sufficient tooling and good new-user on-boarding, Julia could become the future of scientific computing.
In this context, an interactive tutorial that guides new users through the language basics, and a framework for creating and completing lessons in Julia could be of great value to new users, educators, and the Julia community in general.
Julia is already carving out a place in education, and an interactive tutorial framework like this will likely prove a valuable educational resource.

## Beta

I plan to have a beta out by early July --- please [email me][mail] if you're interesting in doing beta testing.

## Planned Timeline

| --- | ---|
| May 23 - June 6 | Core format, Julia data structures for tutorials, Displaying questions and accepting responses |
| June 6 - June 20 | Validate close-ended and open-ended answers, Begin Juno integration |
| June 20 - July 4 | Juno integration |
| July 4 - July 18 | Beta release, User testing, Bug fixes, Catch up on unfinished work |
| July 18 - August 1 | Methods to create tutorials, GUI for creating tutorials |
| August 1 - August 18 | GUI for creating tutorials, Stretch Goals |
| August 18 - August 23 | Polish, bug-fixing, documentation |


[idea]:			http://julialang.org/soc/ideas-page#swirl-style-tutorial
[swirl]:			http://swirlstats.com/
[mypytutor]:	http://ceit.uq.edu.au/content/mypytutor
[mail]:			mailto:me@mgtlake.com
