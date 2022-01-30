---
layout: post
title: Erlang TDD Example
---

<div class="message">
  This is a post written in the past and brought here with minor changes only.
</div>

Test driven development is truly a very different and useful approach towards development in which you think of the result and define the tests first which gives you clarity not only about the expectation from your program but also the different scenarios that needs to be handled.

Generally test driven development is easy if you have well defined API or contract, so that the tests written are stable throughout the development timeframe. Like the design pattern recommendation to prefer interface over implementation, test driven development also needs to be against the interface as much as possible.

To see it in action, here is an example of test driven development for Erlang - simple movie reservation system which has the following 3 API requirement - register movie, reserve seat and retrieve reservation. Apart from these simple API, support for basic auth is also required for API calls, but no authorisation requirement is there.

### Requests
<pre>
Request type   | Key            | Description
========================================================================
               | imdbId         | IMDB movie identifier
 register      | availableSeats | Total seats available for this movie
               | screenId       | Externally managed identifier of
               |                | when and where the movie is screened
---------------+----------------+---------------------------------------
               | imdbId         | IMDB movie identifier
 reserve       | screenId       | Externally managed identifier of
               |                | when and where the movie is screened
---------------+----------------+---------------------------------------
               | imdbId         | IMDB movie identifier
 retrieve      | screenId       | Externally managed identifier of
               |                | when and where the movie is screened 
---------------+----------------+---------------------------------------
</pre>

### Responses
<pre>
Request type | Response                       | Description
==============================================================================
             | ok                             | Registration was successful
             | {error, missing_fields}        | Fields missing in the request
 register    | {error, not_allowed}           | Registration is not allowed
             | {error, exists}                | Movie already exists
             | {error, Error}                 | Registration failed
-------------+--------------------------------+-------------------------------
             | ok                             | Reservation was successful
             | {error, missing_fields}        | Fields missing in the request
 reserve     | {error, not_exists}            | Movie was not registered
             | {error, not_allowed}           | Reservation is not allowed
             | {error, not_available}         | Seat not available for movie
             | {error, Error}                 | Reservation failed
-------------+--------------------------------+-------------------------------
             | {ok,                           | Retrieval was successful
             |  {"imdbId": "tt0111161",       | IMDB movie identifier
             |   "screenId": "screen_123456", | Externally managed identifier
             |   "movieTitle": "The Movie",   | Movie title
             |   "availableSeats": 100,       | Total seats available
             |   "reservedSeats": 50          | Total seats reserved
             |  }                             |
             | }                              |
             | {error, missing_fields}        | Fields missing in the request
 retrieve    | {error, not_exists}            | Movie was not registered
             | {error, not_allowed}           | Retrieval is not allowed
             | {error, Error}                 | Retrieval failed
-------------+--------------------------------+-------------------------------
</pre>

To implement this reservation system, when you use test driven development, it will require you to first write tests for API which is the functional aspect. It also requires you to provide tests for your non-functional aspects like fault tolerance using supervisor.

From implementation point of view, following functionalities are implemented
* REST API using cowboy web server
* Data storage using mnesia

Here is the complete code for this example of test driven development - https://github.com/agrawalakhil/erlang_movies
