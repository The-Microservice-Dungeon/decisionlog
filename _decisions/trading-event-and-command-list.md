---
type: decision
acronym: trading-event-and-command-list
title: List of Trading business events and commands
decision_type: team
service: trading
status: _3_agreed
responsible: tla;tpa
deadline: 2021-10-22
priority: 2-medium
aspects:
  - eventing
history:
  v1:
    date: 2021-10-17
    comment: created initially
  v2:
    date: 2021-10-21
    comment: added events
  v3:
    date: 2021-10-27
    comment: added stuff
  v4:
    date: 2021-11-22
    comment: informal event specs
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
  - Player Joined 
  - On Player join created -> create bank
  For every player listen to:
  - Spawn Created
  Save spawn planet id

  - Spacestation Created
  Save spacestation planet id

  - All items and price factors (Special Items, Upgrades, Energy/Health Restore) ???
  Save all items and calculate prices
  
  - All resources and prices ???
  Save all resources and calculate prices

#### During Game
  - Round Started (with current round number)
  - Round Ended
  - Game Ended
  - Robot Spawned ??? Need to discuss with robot
  - Robot Destroyed ??? Need to discuss with robot

### Broadcasted Events

#### Init

  - Player Banks created (with amount)
  

### Round Start
  - Current Prices (Resources + Items + Upgrades) 
  ```json
    [{
            "name": "WORMHOLE",
            "price": 100
        },
        {
            "name": "REPAIR_SWARM",
            "price": 10
        },
        {
            "name": "MINING_SPEED_1",
            "price": 100
        },
        {
            ...
        },
    ]
  ```

### On Command
Always with transactionId.

### Buying
#### Success
  ```json
    {
      "transactionId" : "12345",
      "success": true,
      "moneyChangedBy": -50,
      "message": "success"
    }
  ```
#### Failure
  ```json
    {
      "transactionId" : "12345",
      "success": false,
      "moneyChangedBy": 0,
      "message": "Item does not exist"
    }
  ```
### Selling
#### Success
  ```json
    {
      "transactionId" : "12345",
      "success": true,
      "moneyChangedBy": 500,
      "message": "success"
    }
  ```
#### Failure
  ```json
    {
      "transactionId" : "12345",
      "success": false,
      "moneyChangedBy": 0,
      "message": "Robot position is not on a spacestation"
    }
  ```


## Reasons for the resolution

To make the trading service as independent as possible it has to get all avaiable resources/items and upgrades at the start of the game. Thereupon, the service can calculate the prices based on the specified price factor and share them with the players. In this way, the purchasable items can be added dynamically at the start of each game without having to adjust the trading service. Another possibility would be to also offer an event to update these buyable items. This would also allow new items to be added during a game. But this is only the second priority of the service.