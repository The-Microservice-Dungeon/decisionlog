---
type: decision
acronym: map-event-and-command-list
title: List of business events and commands from Event Storming, for Map service
decision_type: team
belongs_to: map
status: _2_draft
responsible: sbe;psc
deadline: 2021-10-29
priority: 2-medium
tags: 
    - business-event
history:
    v1:
        date: 2021-10-17
        comment: cr eated initially    
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

n/a

## Alternatives not seriously considered

n/a

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details

### Events we want to publish

```json
{
    "event": "resource_mined",
    "amount_mined": 1000,
    "resource_type": "iron"
}
```

```json
{
    "event": "spawn_created",
    "planet_id": "90b0fe76-f886-4f08-9cbd-5d52b75c7ae8"
}
```

```json
{
    "event": "resource_replenished",
    "planet_id": "90b0fe76-f886-4f08-9cbd-5d52b75c7ae8",
    "resource_type": "iron"
}
```

## Reasons for the resolution

tbd.
