---
type: decision
acronym: gameLog-domainmodel
title: (Sub-)Domain Model for GameLog Service
decision_type: team
belongs_to: gameLog
status: _2_draft
responsible: thu;aha
deadline: 2021-10-22
priority: 1-high
tags: 
    - subdomain-model
history:
    v1:
        date: 2021-10-17
        comment: created initially
    v2:
        date: 2021-10-20
        comment: add domain model
---

## Why is there need for such a decision?

The (sub-)domain model is a prerequisite for planning the development - which entities, value objects, aggregates 
do I have? 

In addition, it needs to be checked if the domain model is consistent with the other teams' (sub-)domain models.
Especially: Are there any conflicts with regard to entity ownership?

## Additional sources for better understanding the background

Miro Board of the Domains (from Event Storming).

## Viable Options

The entities Gamelog, Leaderboard and Trophy are exclusive to the Gamelog service.

## Alternatives not seriously considered

n/a

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details

No resolution required, as there are no conflicts with other services.

## Reasons for the resolution

n/a
