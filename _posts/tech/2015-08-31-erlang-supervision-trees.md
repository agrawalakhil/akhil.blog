---
layout: post
title: Erlang Supervision Trees
---

<div class="message">
  This is a blog post written in the past and brought here with minor changes only.
</div>


*Erlang Supervision Trees* - This presentation was made for the meet up on Erlang supervision trees which was arranged to discuss and understand how Erlang supervision trees helps bring fault tolerance, recovery and robustness to Erlang applications. The presentation covers following

* Basics - A supervisor is responsible for starting, stopping and monitoring its child processes. The basic idea of a supervisor is that it has to keep its child processes alive by restarting when necessary.

* Supervision Trees - Supervisors can supervise workers (leaf nodes) or other supervisors forming supervision tree, while workers should only be positioned under supervisor.

* Supervision Strategy - Supervision strategy consists of two steps - first to form the supervision tree and then providing restart strategy at each level to follow when child dies, which could affect other children as well.

* Complete examples - To look at the complete example of supervision tree from open source projects like rabbitmq and ejabberd to get some understanding of how supervisors are used in real world.

Here is the presentation for the Erlang Supervision Trees

<https://www.slideshare.net/digikrit/erlang-supervision-trees>

Here is the github repository for the basic and advanced examples of Erlang supervision tree

<https://github.com/agrawalakhil/erlang-supervision-trees>
