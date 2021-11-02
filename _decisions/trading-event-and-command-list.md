---
type: decision
acronym: trading-event-and-command-list
title: List of business events and commands from Event Storming, for Trading service
decision_type: team
belongs_to: trading
status: _2_draft
responsible: tla;tpa
deadline: 2021-10-22
priority: 2-medium
tags:
  - business-event
history:
  v1:
    date: 2021-10-17
    comment: created initially
  v2:
    date: 2021-10-21
    comment: added events
  v3:
    date: 2021-10-27
    comment: added sequence diagrams
---

## Why is there need for such a decision?

Each team needs to be clear about the business events (deep yellow stickers) and commands (blue stickers)
from the [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/). They are the blueprint for
designing the features and API(s) of the service.

In addition, it needs to be checked if the event/command list is consistent with the other teams' lists.
Any conflicts, especially about who should receive which command?
    
## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.

## Resolution Details

### Needed Events

#### Init
  - Game Started with all players
  - Map initalized with all spacestations and spawn positions
  - All available resources and price factors
  - All available items and price factors
  - All available upgrades and price factors

### Broadcasted Events

#### Init
  - Prices Initally Calculated (Resources + Items + Upgrades)
  - Player Banks created (with amount)

### During Game
  - Prices updated (start of trading phase)
  - Player bought something (Regen/Upgrade/Item/Robot)
  - Player sold something (Resources)
  - Player money changed

## Reasons for the resolution

To make the trading service as independent as possible it has to get all avaiable resources/items and upgrades at the start of the game. Thereupon, the service can calculate the prices based on the specified price factor and share them with the players. In this way, the purchasable items can be added dynamically at the start of each game without having to adjust the trading service. Another possibility would be to also offer an event to update these buyable items. This would also allow new items to be added during a game. But this is only the second priority of the service.