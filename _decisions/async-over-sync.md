---
type: decision
acronym: async-over-sync
title: Asynchronous communication takes precedence over synchronous communication
decision_type: must
status: _3_agreed
responsible: sbe
deadline: 2021-10-22
priority: 1-high
aspects:
    - api
    - principle
todos:
    - ausformulieren
history:
    v1:
        date: 2021-10-08
        comment: created initially
---

## Resolution details

We build an (as far as possible ...) loosely coupled architecture, where each service team has a maximum of 
"local" freedom for decisions. This means that **synchronous** calls should be used as little as possible - basically
only to issue commands. 

If a service needs additional information on an entity it doesn't own, it should **NOT** do a synchronous REST call 
to the owning service. Instead, it should subscribe to events produced by the owning service, thus building a 
redundant information base on the entity in question.

## Reasons for the resolution

Synchronous calls mean:
* consultations and agreements about API structure - disturbing the own development flow by inducing waiting times,
    feedback/question iterations, etc.
* a dependency on the other service.

Therefore, async communication with an own, redundant data base is easier to handle and avoids a direct dependency 
(as far as possible).

## Why is there need for such a decision?

This is a fundamental architecture style choice, influencing the whole development process.

## Additional sources for better understanding the background

See ...
* DDD concepts like bounded contexts 
* Microservice architecture principles

## Viable Options

* Async over sync
* no async communication, all synchronous calls


## Alternatives not seriously considered

-

## How is this decision evaluated?

Based on the choice for the general architecture style.

