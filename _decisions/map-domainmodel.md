---
type: decision
acronym: map-domainmodel
title: (Sub-)Domain Model for Map Service
decision_type: team
belongs_to: map
status: _2_draft
responsible: sbe;psc
deadline: 2021-10-29
priority: 1-high
tags: 
    - subdomain-model
history:
    v1:
        date: 2021-10-17
        comment: created initially    
---

## Why is there need for such a decision?

The (sub-)domain model is a prerequisite for planning the development - which entities, value objects, aggregates 
do I have? 

In addition, it needs to be checked if the domain model is consistent with the other teams' (sub-)domain models.
Especially: Are there any conflicts with regard to entity ownership?

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details

### Gameworld

A `Gameworld` exists as a container/map of `Planets`.

### Resource Types

We are going to have 5 `ResourceTypes` and differentiate them by the names `[coal iron gem gold platin]`

#### Planet

A `Planet` belongs to a `Gameworld` and can be of `planet_type` `[default spawn spacestation]`
We will set the `taken_at` timestamp as soon as `Planet` of `planet_type: 'spawn'` has been assigned to a player
A `Planet` can have multiple `neighbours` represented as an array of planets
A `Planet` can have multiple `resources` represented as an array of planets
In addition a planets contains a `recharge_multiplicator` and `movement_difficulty`

#### Resource

A `Resource` belongs to a `Planet` and belongs to a `ResourceType`
In addition a resource contains a `max_amount` and `current_amount` field to handle mining operations

#### Mining

A `Mining` belongs to a `Planet` and contains the `resource_type` and `amount_mined`

We do receive a POST request for an amount of a planet's particular resource_type
After a mining has been done on a given planet we sent out an event of the exact that has been amount mined

#### Replenishment

A `Replenishment` is a type of Event where a planet's `Resource` is replenished

#### Spawn Creation

A `SpawnCreation` is a type of Event where a planet's `planet_type` is switched to `spawn`

## Reasons for the resolution

We seperated the map service as much from the other services as possible, where we are not aware of anything like
the robots, game or trading service.
Communication between those services should happen by events.
