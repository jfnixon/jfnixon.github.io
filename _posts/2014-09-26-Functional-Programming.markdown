---
layout: post
title: Functional Programming and Concurrency
---

<div class="message">
Concurrency is the downfall of Imperative Programming.
</div>

## Why is Concurrent Programming so hard?

I think [this article](https://www.fpcomplete.com/blog/2012/04/the-downfall-of-imperative-programming) is on to something.
There is a big future for taming concurrency with Functional Programming.

> Programmers are scared of concurrency, and rightly so. Managers are scared of concurrency even more. If programmers
were electricians, parallel programmers would be bomb disposal experts. Both cut wires. Except that, when the latter 
cut the wrong wire, mayhem ensues. We make mistakes in coding and we have systems for debugging and testing 
programs -- there is no such system for [testing for] concurrency bugs.

> So why are data races so much harder to detect and fix than regular bugs? It all has to do with non-determinism.
Every time a multi-threaded program is run, its threads may interleave differently. The number of possible interleavings
is astronomical. If your program has a data race, it usually manifests itself only in a very small subset of possible 
interleavings. To discover a bug, two threads must access the same memory location at exactly the same time, and 
one of the threads must **modify that location**. I have written programs with deliberate data races and I couldn't trigger 
buggy behavior even with extensive testing.

I think this is exactly right:

>Imperative programs will always be vulnerable to data races because they contain mutable variables.
