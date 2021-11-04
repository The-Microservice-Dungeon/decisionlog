---
type: decision
acronym: service-cut
title: Service cut
decision_type: must
belongs_to: principle
status: _2_draft
responsible: sbe;psc
deadline:
priority: 1-high
tags: 
todo:
history:
    v1:
        date: 2021-11-04
        comment: created initially
---

## Why is there need for such a decision?
The service cut divides the entire business process into individual contexts that are as independent as possible. This separation creates clear responsibilities that can be reflected in individual microservices. 

## Additional sources for better understanding the background
What is a [bounded context](https://martinfowler.com/bliki/BoundedContext.html)?

## Viable Options
\-

## Alternatives not seriously considered
\-

## How is this decision evaluated?
The service cut was created on the results of the event storming, which can be viewed in the [Miro-Board](https://miro.com/welcomeonboard/d3A0T3duaVhuRzhVbjc1eFBWRWxVQnR5UkNQZWRqY2hpeW1TRVBsWkRRbUFJNThwZ2h2c3ZtcmNsQWlQWWdOenwzMDc0NDU3MzYzNjI4NDEyODM4?invite_link_id=504632100485).

## Resolution Details
The following services will be developed:
- Map
- Robot
- Trading
- Game
- Gamelog

## Reasons for the resolution
As a first approximation, event storming resulted in the following bounded contexts:
- Map
- Robot
- Trading
- Game
- GameLog
- Player

After further consideration of the context sizes, the context player was resolved. In the process, the entities were split between Game and Trading.

This results in the following distribution of tasks among the services:


| Service  | Description  |
|---|---|
| Map  | Map manages the gameworld and is responsible for generating and linking planets and their resources.  |
| Robot  |  Robot is the largest service, because it manages and controls all features triggered by robots. This includes, for example, minig rates, life points, attack values, inventory, etc. |
| Trading  | The Trading service manages a player's money. All transactions, i.e. buying and selling resources, upgrades, etc. are managed by Trading.   |
| Game  | The game service provides the interface between players and other services. It takes care of the registration and authorization of players, the order of commands and the round time. |
| Gamelog  |  The Gamelog service is responsible for the game results. Gamelog listens to all the information in the entire network and thus tries to build a complete version of the events. |
