---
layout: post
title:  "Google Summer of Code Update 1"
date:   2016-06-24 10:00 +1000
tags: julia, gsoc, software
---

## Progress so far

Most of the core features are more--or--less implemented:

- Question, Lesson, and Course data--structures
- Editing and packaging of the above
- Question display
- Answer checking (with the exception of Function Questions --- see below)

I'm currently working on Juno integration, but current support is very good, with most of the remaining issues purely visual.

### Difficulties

The major difficulty I'm currently working on is how to handle Function Questions.
My original plan was for the answers simply to be written in the REPL.
This has significant drawbacks, however, because it's inconvenient to edit a function when pressing enter might either submit or create a newline.
This is especially difficult because in this regard the terminal REPL and Juno behave differently: the terminal (at least on my machine) will insert a newline if the statement is incomplete, while Juno will always submit.
Additionally, this is difficult if the user gets it wrong and has to retry --- I have not been able to determine an easy way for them to edit their previous attempt.
This also results in the REPL quickly filling up with spam.

An alternative is to create a file specific to the user and question in which the user writes their answer.
This has the benefit of aligning with normal programming practice (at least in my view), and also allows for pre--filling boilerplate.
The downsides are that the submission mechanism (I'm currently thinking `!submit`) are awkward and disconnected from the editing, and that this may be confusing for new programmers.

Juno presents a third option, whereby code in the editor can be loaded into the terminal.
This has the benefits of being easy to use and intuitive (at least for me), and of aligning with Juno best practice.
On the other hand, this is only a partial solution at best, since Juliet is designed to work without Juno, and I'm concerned it may not be intuitive to people who haven't used Juno before.

My current thinking to to try to implement all three options, and determine the best one through user testing.
I'm personally leaning towards the second option, but may change my mind based on feedback.
I've already done small proofs--of--concept for each, but haven't yet integrated any into Juliet itself.

### A name

After weeks of agonising brainstorming, I decide to name my project Juliet, which is an acronym for**Jul**ia **I**nteractive **E**ducational **T**utor.
It's short, memorable, and easy to pronounce, and is --- as far as I can tell --- otherwise unused in the Julia space (there are a couple of 'Julietta's', but they seem abandoned anyway).

## JuliaCon Video

I put together a short video presentation for JuliaCon 2016, where I'll be giving a short talk on my project (unfortunately I cannot attend in person).

Here's my talk:
<video class="centre" id="test" src="/assets/Matthew-Lake-JuliaCon2016-Talk.mp4" controls></video>

And the slides I used.
<iframe class="centre" src="//slides.com/mgtlake/juliet/embed" width="576" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

## Beta

I plan to have a beta out by early July --- please [email me][mail] if you're interesting in doing beta testing.
I have about half a dozen local beta testers signed up, most of whom are new Julia users.
I'm planning up using their feedback to determine how effect Juliet is, and what improvements can be made.

## Planned Timeline

| --- | ---|
| May 23 - June 6 | Core format, Julia data structures for tutorials, Displaying questions and accepting responses |
| June 6 - June 20 | Validate close-ended and open-ended answers, Begin Juno integration |
| June 20 - July 4 | Juno integration |
| July 4 - July 18 | Beta release, User testing, Bug fixes, Catch up on unfinished work |
| July 18 - August 1 | Methods to create tutorials, GUI for creating tutorials |
| August 1 - August 18 | GUI for creating tutorials, Stretch Goals |
| August 18 - August 23 | Polish, bug-fixing, documentation |

[mail]:			mailto:me@mgtlake.com
