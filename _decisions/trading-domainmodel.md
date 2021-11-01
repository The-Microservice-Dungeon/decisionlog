---
type: decision
acronym: trading-domainmodel
title: (Sub-)Domain Model for Trading Service
decision_type: team
belongs_to: trading
status: _2_draft
responsible: tla;tpa
deadline: 2021-10-22
priority: 1-high
tags: 
    - subdomain-model
history:
    v1:
        date: 2021-10-17
        comment: created initially    
    v2:
        date: 2021-11-01
        comment: added explanation         
---

## Why is there need for such a decision?

The (sub-)domain model is a prerequisite for planning the development - which entities, value objects, aggregates 
do I have? 

In addition, it needs to be checked if the domain model is consistent with the other teams' (sub-)domain models.
Especially: Are there any conflicts with regard to entity ownership?


## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details
The following describes the proposed structure of the Trading Service.

### Player and Money

Trading has a `Player` which has the `playerId` initially given by the game service. Trading is also the only service which saves the money of the players so `Player` has also an attribute `Money` which is a numeric value.

### Spawns and Spacestations

Even if the trading service is not the owner of spawns and spacestations, their positions of the planets that are a spawn and a spacestation are still needed to match the robot position with the positions of the spacestations/spawns in case of a request to the trading service. It is proposed, that trading has a `Positions` entity which holds the position of every spawn and spacestation. The data initially comes from the map service which has to emit them to the trading service.

### Tradeables (Items/Upgrades/Regeneration)

Tradeables are `Item`, `Upgrade` or `Regeneration`. They have an `ID`, `Name`, `Description`, `Price`, `Type` and `OriginalPrice`. 
Name and Description are needed to make it readble by humans if a players asks the trading service for a list of all items and their prices. All `Item` have an adjustable price which will be changed be the economy algorithm of the trading service, based on multiple factors such as demand, current round, etc.. 

### Resources

Resources can be sold via the trading service. A `Resource` has `ID`, `Price`, `Type` and `OriginalPrice`. 

### Econonomy

`Economy` has an trades history which tracks the trades done by the players/robots and the round numbers to later calculate the prices from.

## Reasons for the resolution

Where possible, we have separated the trading service as far as possible from the other services, so trading just need to check for money of the player and the position of a robot on a spacestation or spawn to be able to confirm or decline a trade. Especially the communication with the robot service was kept as simple as possible and reduced to a request from the trading service with a response from the robot service.

The main focus of the trading service should be the economy part.