---
type: decision
acronym: trading-buy-semantics
title: Semantics of all trades
decision_type: team
service: trading
status: _2_draft
responsible: tla;tpa
deadline:
priority: 2-medium
aspects:
  - eventing
history:
  v1:
    date: 2021-11-22
    comment: created initially
---

## Why is there need for such a decision?

To standardize communication with the trading service, it is necessary to clearly define which purchases are valid and which are not. 
    
## How is this decision evaluated?

This decision mainly relates to game play related topics. Discussion with team. 

## Resolution Details

### Special Items
#### How many? 
    1 per robot per round.
#### Why?
    To prevent price manipulation through a single robot.


### Robots
#### How many? 
    Multiple robots per round.
#### Why?
    Buying a robot should not be bound to an existing robot. You can buy as many robots as you have money. 


### Regeneration
#### How many? 
    1 per robot per round
#### Why?
    You get max health/energy with one purchase. So you do not need to buy multiple.


### Upgrades
#### How many? 
    1 per robot per round
#### Restrictions
    Only next upgrade level (1-5)
#### Why?
    Upgrading a robot is seen as an action. The overall game is designed for only a single action per round. You can only buy the next higher upgrade level for each category.
    E.g. a robot with MINING_2 can only buy MINING_3. Any other upgrade to MINING will result in an error. This design takes into account the loose coupling of the trading service and avoids saving robot informations.
