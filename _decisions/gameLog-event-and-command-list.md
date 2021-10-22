---
type: decision
acronym: gameLog-event-and-command-list
title: List of business events and commands from Event Storming, for GameLog service
decision_type: team
belongs_to: gameLog
status: _2_draft
responsible: thu;aha
deadline: 2021-10-22
priority: 2-medium
tags: 
    - business-event
history:
    v1:
        date: 2021-10-17
        comment: created initially
    v2:
        date: 2021-10-20
        comment: add event list
---

## Why is there need for such a decision?

Each team needs to be clear about the business events (deep yellow stickers) and commands (blue stickers)
from the [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/). They are the blueprint for 
designing the features and API(s) of the service.

In addition, it needs to be checked if the event/command list is consistent with the other teams' lists.
Any conflicts, especially about who should receive which command?

## Additional sources for better understanding the background

Miro Board of the Domains (from Event Storming).

## Viable Options

The business events are pretty clear from the miro board:
- request game data from the services
- ALTERNATIVE: let services log events to event queue (Apache Kafka)
- aggregate end results of all rounds
- evaluate end results
- generate final rankings
  - grant trophies
- generate rankings for categorized achievements (not trophies but e.g. amount of money, resources, etc.) (leaderboards)
- store trophies in cross-game personal log

This domain has no commands.

## Alternatives not seriously considered

n/a

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details

Should be discussed in FAE/DDD on October 22th.

## Reasons for the resolution

tbd.
