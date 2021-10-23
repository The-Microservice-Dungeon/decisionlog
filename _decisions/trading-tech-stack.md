---
type: decision
acronym: trading-tech-stack
title: Technology stack for Trading service
decision_type: team
belongs_to: trading
status: _3_agreed
responsible: tla;tpa
deadline: 2021-10-22
priority: 1-high
tags: 
    - tech-stack
todos:
    - (sb) Spring is understood, but with which language?
    - (sb) please fill the remaining parts of the decision
history:
    v1:
        date: 2021-10-17
        comment: created initially
    v2: 
        date: 2021-10-21
        comment: added first decisions
    
---

## Why is there need for such a decision?

No development can start before the technology stack (esp. programming language) has been chosen by the team.

## Additional sources for better understanding the background

n/a

## Viable Options

 - C#
 -- Good Documentation from Microsoft [Link1](https://docs.microsoft.com/de-de/dotnet/architecture/microservices/multi-container-microservice-net-applications/integration-event-based-microservice-communications) [Link2](https://docs.microsoft.com/de-de/azure/architecture/guide/architecture-styles/event-driven)
 - Java (Spring)
--Tought in various modules
--Easy to set up project with spring
 - Java [(Quarkus)](https://quarkus.io/guides/kafka)
 - Node.js (with nestjs)
 --Tought in various modules
 --Nestjs wraps around express and has prebuild emplementation for kafka microservices

## Alternatives not seriously considered
There are various alternatives though in this project scope it is best to focus on the tech that is known by most of the team. 

## How is this decision evaluated?

Discussion in Discord and looking at similar projects done with other technologies.
 
## Resolution Details

We are going to use Java as programming language.
We are going to use Spring as application framework.
We are going to use mySQL as database service.


## Reasons for the resolution
Everyone agreed on using Java because thats the best known language for everyone in the team and we can get easy support from others.
