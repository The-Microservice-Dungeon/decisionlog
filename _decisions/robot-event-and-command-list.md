---
type: decision
acronym: robot-event-and-command-list
title: List of business events and commands from Event Storming, for Robot service
decision_type: team
belongs_to: robot
status: _2_draft
responsible: ngi;cpo
deadline: 2021-10-22
priority: 2-medium
tags: 
    - business-event
    - command
history:
    v1:
        date: 2021-10-17
        comment: created initially
    v2:
        date: 2021-10-21
        comment: added business events    
---

## Why is there need for such a decision?

Each team needs to be clear about the business events (deep yellow stickers) and commands (blue stickers)
from the [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/). They are the blueprint for 
designing the features and API(s) of the service.

In addition, it needs to be checked if the event/command list is consistent with the other teams' lists.
Any conflicts, especially about who should receive which command?

## Additional sources for better understanding the background

tbd.

## Viable Options

- robot used energy for action
- robot regenerated energy
- robot blocked planet
- upgraded robot
- robot moved to another planet
    - movement failed due to a block
- fought other robot
    - robot used item
    - robot was destroyed
    - distributed resources of destroyed robot
- mined resource
    - added item to inventory
- spawned robot


## Alternatives not seriously considered

n/a

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details

tbd.

## Reasons for the resolution

tbd.