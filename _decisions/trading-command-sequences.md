---
type: decision
acronym: trading-command-sequences
title: List of commands and their sequences with other services
decision_type: team
service: trading
status: _2_draft
responsible: tla;tpa
deadline:
priority: 2-medium
tags:
history:
  v1:
    date: 2021-10-28
    comment: added sequences for buy and sell
  v1:
    date: 2021-10-28
    comment: added sequence for initialization
---

## Why is there need for such a decision?

To better understand how the trading service communicates with other services. And to have a model of all functions that need to be in the trading service.

## Additional sources for better understanding the background

tbd.

## Viable Options

### Buy Command

![Buy Command Sequence Diagram](./images/trading-service-sequence-buy-command.png)

### Sell Command

![Sell Command Sequence Diagram](./images/trading-service-sequence-sell-command.png)

### Initialize

![Initialization Sequence Diagram](./images/trading-service-sequence-initialization.png)

## Alternatives not seriously considered

Treating trading as a sub-service from robot.
Have trading be the owner of items.

## How is this decision evaluated?

Discussion with team. Discussion with robot service and project lead.

## Resolution Details

Trading just checks position and money. Then requests the action from robot service. If robot responds with success, reduce money and confirm command. If robot responds with error, cancle command and emit error.

## Reasons for the resolution

Main discussed reason was to reduce the amount of communication between robot and trading service.