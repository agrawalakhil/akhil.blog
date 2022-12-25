---
layout: post
title: I-Shaped Learning
---

<div class="message">
  This is a post on I-Shaped learning framework to build expertise
</div>

* Table Of Contents
{:toc}

# Overview
Generally for building technical & engineering expertise, the learning framework which has worked well is something like an I-Shaped Learning where there are three important components of the learning plan which are explained in the diagram below.

There is a lot of debate going on with regards to breadth focus vs depth focus. Even the popular saying “Jack of all trades is a master of none” is misrepresented today as an insult to people who are focusing on the breadth while ignoring the depth but the original full quote “Jack of all trades is a master of none, but often times better than master of one” was in fact a complement.

General guidance for the plan would be to spend equal time on each of the three components (minimum 4 weeks each) in the first iteration & repeat again for deeper learning. The plan is basically a checklist, create a copy & update each of the checklist item with specific details, artifacts like docs, mind-maps etc and individual learning.

<img src="https://akhil.blog/public/images/i-shaped-learning-framework.png" />

# Breadth On Fundamentals
Learning a wide range of fundamentals (computer science, coding, design & language) is very important to build mental muscle to understand different nuances & comfortably handle technical complexity as well as building a good grip on systems.
## CS Fundamentals
This should be covered by any CS fundamentals MOOC course in references, follow one course & complete it, instead of spreading thin across many information sources.
### Data Structures
- [ ] **Basic Data Structures**
> Understanding & practicing problem solving using the basic data structures - arrays, linked lists (singly & doubly), lists, stack/queues, min/max heaps, maps, trees. Also various data structure considerations - space, time complexity (read/write).
- [ ] **Advanced Data Structures**
> Understanding & practicing problem solving using some of the advanced data structures considerations (memory hierarchy with caches, hashing techniques, immutability, large data sets) and examples (priority queues, binary trees, bloom filters)
### Algorithms
- [ ] **Basic Algorithms** 
> Fundamental concepts - space & time complexity, asymptotic notation, basic algorithms - sorting & searching, algorithm design - iterative/recursion, memoization/dp, divide & conquer, greedy, branch & bound, optimizing algorithms (removing bottlenecks, unnecessary operations, duplicated operations)
- [ ] **Advanced Algorithms**
> Understanding & knowledge of a couple of advanced algorithms from any domain like - parallel (matrix multiplication), streaming (count-min sketch), randomized algorithms (quicksort), string (suffix trees), graph (DFS, BFS), mathematical (linear programming).

## Coding Fundamentals
The clean code book & the examples link in references can be a good start as it covers many of these things.
### Code Design
- [ ] **Code Constructs**
>In-depth understanding of common code constructs (variable/constant, conditions, loops, functions, type/class, try/catch, thread safety, annotation) and knowledge of advanced constructs & concepts (macros, currying, trait/aspect, symbolic tree)
- [ ] **Code Structuring**
>Learn various code structuring mechanisms (modular decoupled structure, convention based structure, domain driven design based structure, tech vs functional oriented, frontend/backend structure, framework vs library structure) & list examples for each.
### Coding Practices
- [ ] **Coding Best Practices**
>Learn & list down coding best practices - language independent like general (naming, readability, indentation etc), design (low coupling, don’t repeat yourself) & language specific like syntax (standard linting, using obvious not obscure constructs, nuances of constructs), semantics (exception handling, concurrency, built-in types behavior). 
- [ ] **Code Review Best Practices**
>Learn & list down code review best practices - code review checklist (readability, security, structuring, test coverage, reusability), code review metrics (inspection rate, defect rate, defect density), code review automation (danger.js), code review diligence (400 lines at a time, nitpicks %), code review etiquettes (suggestion instead of command, conversation instead of fault finding)
## Design Fundamentals
### Design Patterns
- [ ] **Solid Principles & OOP Design Principles**
> Go through & practice some of the important design patterns like observer, strategy, adapter, facade by implementing them. Common design principles like SOLID, OOP (composition over inheritance, container structure using core + extensions / modules / plugins - for inversion of control & dependency injection)
- [ ] **Distributed System Patterns**
> Go through and learn various distributed design patterns like single node patterns (side-car pattern, adapter, ambassador), multi-node patterns (discovery, cluster management patterns - consensus algos, leader/master election, data/control plane), batch computational patterns (work queues, event based processing, coordinated workflows), distributed transactionality patterns (2-phase commit, saga pattern etc.) 
### Design Anti-Patterns
- [ ] **Code & Design Anti-Patterns**
> Learn some of the common coding anti-patterns (spaghetti code, god class, cyclic dependencies, copy/paste, golden hammer, dead code, scattered code, boat anchor) and code smells (duplicate code, large functions, lazy/large class, mysterious naming, unsafe type handling, side-effects)
- [ ] **Distributed System Anti-Patterns**
> Learn some of the common distributed system anti-patterns - microservice anti-patterns (distributed monolith, shared database, dependency disorder, entangled data, improper versioning, missing api-gateway) & list down reasons why these result in bad design.
## Language Fundamentals
### Language Independent
- [ ] **Programming Languages Landscape**
> Look at various programming language families (procedural. object oriented, declarative, functional, logic), operating model (interpreted, compiled), abstraction level from machine to humans (machine, assembly, high level), origin (academy, industry)
- [ ] **Programming Languages History**
> Many of the languages have evolution paths where sometimes in the new language, fundamental changes are introduced while other times its only incremental new constructs. Go through a couple of these like c -> c++, java -> scala, erlang -> elixir.
### Language Specific
- [ ] **Constructs & Language Design**
> Language constructs starting from syntax to semantics, then looking at the overall language design. Constructs for different programming paradigms - declarative (macros, annotations), procedural (first order functions, loops, conditions), oop (type, inheritance, polymorphism, generics, reflection), functional programming (closure, higher order functions, pattern matching, list comprehensions) etc. Do this for any one language.
- [ ] **Language Evolution & Philosophy**
> Language evolution and philosophy are important to know and understand, this builds the context in which programming language has been developed. Most being open-source helps in looking at the evolution of the language & learning.
- [ ] **Compiler & Virtual Machine Internals**
> The way language and various constructs operate or are implemented in the VM, this gives a good view of the VM for doing tuning, optimisation and knowing internals like scheduling, memory management helps in debugging & troubleshooting issues.

# Depth On Single Tech Stack
Important thing to keep in mind for this section is to reduce context switching & have deeper thinking to understand the journey of a tech stack well, so that the learnings here can be extrapolated quickly for any tech stack, whenever required on demand.

## Tech Stack
### Stack Selection
- [ ] **Select Tech Stack**
> Based on interest, select one of tech stack for deep dive (like data stack - any sql or nosql data stores or messaging stack - kafka, rabbitmq or functional stack - elasticsearch, neo4j or infra stack - docker container, kubernetes)
- [ ] **Tech Stack Mind-map**
> Mind-map for covering the breadth of the tech stack - pros/cons, high level design, when to use this tech stack, comparative analysis with competition, use-case mapping (popular use cases with understanding of why this tech stack was preferred)
### High Level Design
- [ ] **Component / Block Diagram**
> Create the component or block diagram based on the HLD understanding of tech stack, iterate over it couple of times and then compare with the existing component or block diagram from tech stack developers
- [ ] **Data & System Architecture**
> Create the data & system architecture of the tech stack based on the HLD understanding of tech stack, iterate over it couple of times and then compare with the existing data & system architecture diagram from tech stack developers
## Deep Dive
### Low Level Design
- [ ] **Schema & API**
> Go through & list down the data schema (for meta, master & transaction data models) and various APIs (type - sync/async, protocol - rest/grpc, format - xml/json, security - authn/authz, contract - sla/limits, robustness - idempotency/degradation)
- [ ] **Tech Stack Components**
> Go through & list down the important components like language, base libraries (like lucene for Elasticsearch), abstraction layers - data, logic & api layer, underlying storage mechanism, concurrent processing mechanism (threading vs lightweight processes)
### Code Level Design
- [ ] **Data Structures & Algorithms**
> Go through & list down the important DS/Algo used in the tech stack, need & rationale behind using those, what optimisation (space or time or both) these DS/Algo bring, review the space/time complexity, are there better alternatives & why.
- [ ] **Data/Compute, Code, Read/Write Flows**
> Go through & list down the important flows in the tech stack - from different point of views - data & compute, read & write flow, code flow.  Create the flow diagram for the listed flows along with their inter-relationships like cross-dependencies, pipelines etc.
## Evolution
### Design Tradeoffs
- [ ] **Fundamental Resource Tradeoffs** 
> Go through and list down the fundamental resource tradeoffs (compute, storage, memory, network, time) that are applicable to the tech stack, why these tradeoffs are important for the success of the tech stack
- [ ] **Distributed System Tradeoffs**
> Go through and list down the distributed system tradeoffs (consistency - serializability & linearizability, availability, partition tolerance) that are applicable to the tech stack, why these tradeoffs are important for the success of the tech stack.
### Decision Log
- [ ] **Critical Design Decisions**
> Go through & list down the critical design & architecture decisions from inception, look at the anatomy of each of these decisions (3 fundamental parts for each decision - problem - approaches - solution) and the retrospective of decision - impact, pitfalls etc
- [ ] **Important Design Decisions**
> Go through & list down the important (non-critical) design & architecture decisions, look at the anatomy of each of these decisions (3 fundamental parts for each decision - problem - approaches - solution) and the retrospective of decision - impact, pitfalls etc

# Breadth On Tech Stacks
This section is the last and open-ended, it is more like understanding the landscape of tech stacks based on various needs & use cases, mainly to be able to judiciously choose the appropriate tech stack whenever needed based on various parameters.
## Considerations
### Tech Stack
- [ ] **General**
> Create mind-map for the important things to consider when evaluating any tech stack - pros/cons, high level design, when to use which tech stack, comparative analysis, use-case mapping, functional/non-functional & ecosystem related evaluation criteria
- [ ] **Non-Functional**
> Go through & list down the non-functional considerations (security, robustness, stability, resilience, scalability, performance) which are important for selecting any tech stack for a given problem, why they are important & how to measure each of these considerations.
### Ecosystem
- [ ] **Support, Community & Management**
> Go through & list down the ecosystem considerations like support (sponsors, core contributor activity etc), community (size, involvement) & management (managed service, paid support) which are critical for operability & sustainability of tech stack.
- [ ] **Benchmark & Independent Evaluations**
> Go through & list down the various benchmark & independent evaluations to be reviewed to be able to take more data driven & well researched decisions. For example - https://jepsen.io/ is the de-facto standard for distributed system evaluation.
## Landscape
### Data Stores & Messaging 
- [ ] **SQL & NoSQL Data Stores**
> Go through different sql databases (mysql, mssql, pgsql, oracle) and nosql datastores like key-value stores (redis, aerospike), columnar stores (cassandra), document stores (mongodb, couchdb), graph stores (neo4j, dgraph), search store (elasticsearch, solr)
- [ ] **Generic vs Specialized Data Stores**
> Look at the datastores from generic vs specialized functionality point of view - generic (sql db, in-memory, key-value, columnar, document) or a bit more specialized (graph, search, time-series, analytical). Mind-map for considerations for a few categories.
- [ ] **Messaging Frameworks**
> Look at the popular messaging frameworks (like kafka, pulsar, rabbitmq, activemq), messaging considerations like functional (delivery guarantees), performance (throughput, latency), consumption model (pull, push), storage model (log, index)
### Processing & Application
- [ ] **Stream & Batch Data Processing**
> Go through & list down the open-source stream & batch data processing frameworks like storm, spark, flume, flink, skoop) & commercially available (redshift, athena, snowflake, big-query, synapse)
- [ ] **Application Frameworks & Libraries**
> Go through & list down the application framework & libraries which are relevant for current work - backend(django, flask for python, gin, gorm for go), frontend (react, vue, angular), other framework & libraries (grpc, graphql, rule engine, workflow engine)


<br/><br/><br/>


# References
## Breadth On Fundamentals
- [Clean Code](https://erik-uus.gitbook.io/clean-code/)
- [Learning & Thinking Structure](https://akhil.blog/2022/06/07/individual-development-plan/#learning--thinking-structure)
- Coding Standards - [GitHub - Kristories/awesome-guidelines: A curated list of high quality coding style conventions and standards.](https://github.com/Kristories/awesome-guidelines) 
- Code Review Best Practices - [5 code review best practices - Work Life by Atlassian](https://www.atlassian.com/blog/add-ons/code-review-best-practices) 
- Code Review Best Practices - [Google Engineering Practices Documentation](https://google.github.io/eng-practices/)
- Code Smells - [Code smell - Wikipedia](https://google.github.io/eng-practices/)
- Patterns of distributed system - [Patterns of Distributed Systems](https://martinfowler.com/articles/patterns-of-distributed-systems/)
- Anti-Patterns for distributed systems - [Overcoming the Common Microservices Anti-Patterns - Developer.com](https://www.developer.com/design/solving-microservices-anti-patterns/)
- Anti-Patterns - [What are Software Anti-Patterns? - Lucidchart Blog](https://www.lucidchart.com/blog/what-are-software-anti-patterns)
- Anti-Patterns - [9 Anti-Patterns Every Programmer Should Be Aware Of](https://sahandsaba.com/nine-anti-patterns-every-programmer-should-be-aware-of-with-examples.html)
- Anti-Patterns - [Introduction to Software Engineering,Architecture,Anti-Patterns - Wikibooks, open books for an open world](https://en.wikibooks.org/wiki/Introduction_to_Software_Engineering/Architecture/Anti-Patterns)

## Breadth On Tech Stacks
- [Classification of NoSQL data stores](https://reader.elsevier.com/reader/sd/pii/S1877050916321007?token=5A8E374E8544E44AC517955FB49FA13BD4321BA9D3F39DED30C77E71F65443EDEF0A63863AEEF9B19510ABA78B7F737E&originRegion=eu-west-1&originCreation=20221224104537)
- [Messaging - Kafka vs Pulsar](https://www.conduktor.io/blog/comparing-apache-kafka-apache-pulsar)
- [Open Messaging Benchmark](https://github.com/openmessaging/benchmark)
- [5 top Go web frameworks - LogRocket Blog](https://blog.logrocket.com/5-top-go-web-frameworks/)
- [1. Web Frameworks for Python](https://wiki.python.org/moin/WebFrameworks)
- [Distributed Data Processing Frameworks](https://download.arxiv.org/pdf/2201.01948v1)
- [Streaming Framework Comparison](https://ceur-ws.org/Vol-2170/paper3.pdf)

## Depth On A Tech Stack
### HLD & LLD
- [Companies Using RFCs or Design Docs and Examples of These - The Pragmatic Engineer](https://blog.pragmaticengineer.com/rfcs-and-design-docs/)
- [GitHub - donnemartin/system-design-primer: Learn how to design large-scale systems](https://github.com/donnemartin/system-design-primer)
- [Understanding the architecture | Apache Cassandra 3.0](https://docs.datastax.com/en/cassandra-oss/3.0/cassandra/architecture/archTOC.html)
- [Apache Kafka Architecture Deep Dive: Introductory Concepts](https://developer.confluent.io/learn-kafka/architecture/get-started/)
### Design Tradeoffs
- [Linearizability versus Serializability | Peter Bailis](http://www.bailis.org/blog/linearizability-versus-serializability/)
- [Consistency Models](https://jepsen.io/consistency)
- [CockroachDB's consistency model](https://www.cockroachlabs.com/blog/consistency-model/)
### Decision Log
- [Go Evolution & Go Design Proposals](https://github.com/golang/proposal/tree/master/design)
- [The Evolution of Apache Kafka: From In-House Infrastructure to Managed Cloud Service ft. Jay Kreps](https://developer.confluent.io/podcast/the-evolution-of-apache-kafka-ft-jay-kreps/)

## General
### Books
- [Designing Distributed Systems: Patterns and Paradigms for Scalable, Reliable Services Reviews & Ratings](https://www.amazon.in/Designing-Distributed-Systems-Brendan-Burns/dp/1491983647)
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612)
- [Software Architecture Patterns](https://get.oreilly.com/ind_software-architecture-patterns.html)
### Important Courses
- [CS50's Introduction to Computer Science - edX](https://www.edx.org/course/introduction-computer-science-harvardx-cs50x)
- [Data Structures | Coursera](https://www.coursera.org/learn/data-structures)
- [Divide and Conquer, Sorting and Searching, and Randomized Algorithms - Coursera](https://www.coursera.org/learn/algorithms-divide-conquer)
- [Learn Algorithm with Online Courses, Classes, & Lessons - edX](https://www.edx.org/learn/algorithms) 
- [Advanced Data Structures | Electrical Engineering and Computer Science - MIT OpenCourseWare](https://ocw.mit.edu/courses/6-851-advanced-data-structures-spring-2012/) 
- [Advanced Algorithms and Complexity - Coursera](https://www.coursera.org/learn/advanced-algorithms-and-complexity)
- [Graph Search, Shortest Paths, and Data Structures - Coursera](https://in.coursera.org/learn/algorithms-graphs-data-structures)
- [Introduction to Graduate Algorithms - Udacity Free Courses](https://www.udacity.com/course/introduction-to-graduate-algorithms--ud401)
- [Design of Computer Programs - Udacity Free Courses](https://www.udacity.com/course/design-of-computer-programs--cs212)
