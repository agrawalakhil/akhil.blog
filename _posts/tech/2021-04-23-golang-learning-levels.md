---
layout: post
title: Golang Learning Levels
---

<div class="message">
  This is a post for helping developers to go deeper into golang
</div>

* Table Of Contents
{:toc}

## Background

To build deep expertise on any programming language, one needs to study the language at three levels (increasing in depth) and then only the nuances of the language are understood well to effectively use the language & have good grip on the language.

Coming from Erlang background, it's very interesting to see some of the features in golang being inspired from Erlang or some evolving towards those in Erlang like
* Scheduling in golang has moved from cooperative to preemptive scheduling from v1.2
* Message passing and process distribution - this is still not as flexible as erlang 
* Supervision trees for fault tolerance

During discussions with the team, I thought it would be useful to list down links to learn golang at each level.

## Constructs & Language Design
This is the first and basic level where focus is on learning the constructs provided by language starting from syntax to semantics and then looking at the overall language design. Some of the constructs may be for declarative programming (macros, annotations), procedural programming (first order functions, loops, conditions), oop (type, inheritance, polymorphism, generics, reflection), functional programming (closure, higher order functions, pattern matching, list comprehensions), concurrent programming (light weight processes, message passing, process distribution), fault tolerance (supervision, hot reloading). Some useful links to start on Golang constructs & language design learning.

* [Golang Syntax](https://medium.com/cloud-security/golang-syntax-afc1ce1a356)
* [Go - Good, Bad & Ugly](https://bluxte.net/musings/2018/04/10/go-good-bad-ugly/)
* [Go - Pike Abstract](https://web.stanford.edu/class/ee380/Abstracts/100428-pike-stanford.pdf)
* [Go Koans](https://github.com/cdarwin/go-koans)
* [Some Thoughts On Library Design](https://blog.gopheracademy.com/advent-2019/pkgapi/)
* [Domain Driven Design in Go](https://www.calhoun.io/moving-towards-domain-driven-design-in-go/)
* [Functional Go](https://medium.com/@geisonfgfg/functional-go-bc116f4c96a4)
* [Golang Developer Roadmap](https://github.com/Alikhll/golang-developer-roadmap)

## Evolution & Philosophy
Language evolution and philosophy are important to know and understand, this builds the context in which programming language has been developed which then helps to understand in depth the correct way of using language as well as its limitations and strengths. Golang being opensource helps in looking at the evolution of the language & learn from various design decisions taken.

* [Golang Design History](https://github.com/golang-design/history)
* [Go at Google - Language Design](https://talks.golang.org/2012/splash.article)
* [Towards Go 2](https://blog.golang.org/toward-go2)
* [The laws of reflection](https://blog.golang.org/laws-of-reflection)
* [The value in Go's simplicity](https://benjamincongdon.me/blog/2019/11/11/The-Value-in-Gos-Simplicity/)
* [Message passing designs - Actor/Light Weight Process vs CSP (Communicating Sequential Process) vs MPI](https://spcl.inf.ethz.ch/Teaching/2020-pp/lectures/PP-l24-MessagePassingII.pdf)

## Compiler & VM Internals
The way language and various constructs operates or are implemented in the VM, this gives good view of VM for doing tuning, optimisation and knowing internals like following
* **Go concurrency using goroutines** - scheduling, sandboxing, message passing, distribution across nodes, csp (communicating sequential process)
* **Go memory management** - garbage collection, stack vs heap memory, manual memory management, immutable vs mutable, shared memory
* **Go io management** - various io management features like buffered io, non-blocking io
* **Go grammar and compiler** - looking at the grammar (syntax and semantics), compilation and symbolic tree

Few links to start on the golang internals

* [Golang Garbage Collection](https://blog.golang.org/ismmkeynote)
* [Golang Internals](https://www.altoros.com/blog/golang-internals-part-6-bootstrapping-and-memory-allocator-initialization/)
* [Memory Management In Golang](https://deepu.tech/memory-management-in-golang/)
* [Journey of Go's Garbage Collector](https://blog.golang.org/ismmkeynote)
* [Scheduling In Go](https://www.ardanlabs.com/blog/2018/08/scheduling-in-go-part1.html)
* [Go Scheduler](https://www.cs.cmu.edu/afs/cs/academic/class/15740-s18/www/report/go_scheduler)
* **Cooperative to preemptive scheduling** - [Non-Cooperative Preemption](https://github.com/golang/proposal/blob/master/design/24543-non-cooperative-preemption.md), [Manual Memory Management In Golang](https://dgraph.io/blog/post/manual-memory-management-golang-jemalloc/)

## General
Few links below have very good content across all levels

* [Great depth in Go](https://dave.cheney.net/category/golang)
* [Go : A Documentary](https://github.com/golang-design/history)
* [Design proposals](https://github.com/golang/proposal/tree/master/design)
