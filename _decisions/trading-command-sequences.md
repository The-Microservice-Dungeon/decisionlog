---
type: decision
acronym: trading-command-sequences
title: List of commands and their sequences with other services
decision_type: team
belongs_to: trading
status: _2_draft
responsible: tla;tpa
deadline: 2021-10-28
priority: 2-medium
tags:
history:
  v1:
    date: 2021-10-28
    comment: added sequences for buy and sell
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

tbd

## Alternatives not seriously considered

Treating trading as a sub-service from robot.
Have trading be the owner of items.

## How is this decision evaluated?

Discussion with team. Discussion with robot service and project lead.

## Resolution Details

n/a

## Reasons for the resolution

n/a
