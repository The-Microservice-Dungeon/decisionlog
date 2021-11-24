---
type: decision
acronym: robot-event-and-command-list
title: List of business events and commands from Event Storming, for Robot service
decision_type: team
service: robot
status: _2_draft
responsible: ngi;cpo
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
        comment: added business events 
    v3:
        date: 2021-11-24
        comment specified events
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
- robot was upgraded
- bought item was added to the robots inventory
- robot moved to another planet
    - robot used item for movement
    - movement failed due to a block
    - movement failed due to not enough energy
- robot fought other robot
    - robot used item
    - robot was destroyed
    - resources of destroyed robot were distributed
- robot mined resource
    - resources were added to the robots inventory
- robot was spawned
- scouting? :)


## Alternatives not seriously considered

n/a

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details

### Needed Events

### Broadcasted Events

### Robot spawn
Spawn new robots
#### Success
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"success",
   "robots":[
      {
         "id":"497f6eca-6276-4993-bfeb-53cbbbba6f08",
         "player":"ae2cfcf0-e870-4360-a41e-3b3bb3312234",
         "planet":"2faf337d-d8d1-40fc-983e-5f130540496b",
         "alive":true,
         "maxHealth":10,
         "maxEnergy":20,
         "energyRegen":4,
         "attackDamage":1,
         "miningSpeed":2,
         "health":10,
         "energy":20,
         "healthLevel":0,
         "damageLevel":0,
         "miningSpeedLevel":0,
         "miningLevel":0,
         "energyLevel":0,
         "energyRegenLevel":0,
         "storageLevel":0,
         "inventory":{
            "maxStorage":20,
            "usedStorage":0,
            "coal":0,
            "iron":0,
            "gem":0,
            "gold":0,
            "platin":0
         },
         "items":{
            "rocket":0,
            "wormhole":0,
            "longRangeBombardement":0,
            "selfDestruction":0,
            "repairSwarm":0,
            "nuke":0
         }
      },
      {
        ...      
      }   

   ]
}
```
#### Failure
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"failure"
}
```

### Movement
Successful movement
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"success",
   "energyChangedBy": -10,
   "remainingEnergy": 15,
   "planet":{
      "id":"497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "movement_difficulty":0,
      "recharge_multiplicator":0,
      "taken_at":"2019-08-24T14:15:22Z",
      "gameworld_id":"5bd7c16e-97a9-49f5-974e-307be5fc576d",
      "created_at":"2019-08-24T14:15:22Z",
      "updated_at":"2019-08-24T14:15:22Z"
   },
   "otherRobots":[
      
   ],
   "neighbours":[
      
   ]
}
```
Failure
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"Failure",
   "reason":"Planet is being blocked",
   "energyChangedBy": "-10",
   "remainingEnergy": 15
}
```

Publish Neighbour Planets??
```json

```

### Blocking
Successful
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"success",
   "energyChangedBy": -10,
   "remainingEnergy": 15
}
```
Failure
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"failure",
   "reason":"Not enough energy"
}
```
### Upgrade
By Trading


### Mining
Successful
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"success",
   "ressourceType":"gem",
   "amount": 3,
   "energyChangedBy": -10,
   "remainingEnergy": 15
}
```
Failure
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"failure",
   "reason":"Not enough energy"
}
```
### Fighting
Successful
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"success",
   "damageDealt":5,
   "remainingHealth":15,
   "targetRobot":"cb9eb21d-1238-4e10-b5b0-52247f750bf0",
   "enemyAlive": true,
   "energyChangedBy": -10,
   "remainingEnergy": 15
}
```
Failure
```json
{
   "transactionId":"07421f12-5354-4462-a31b-eba71f634585",
   "message":"failure",
   "reason":"target not on planet"
}
```

### Instant-Restoration

```json
{
"transactionId": "07421f12-5354-4462-a31b-eba71f634585",
"message": "success"
}
```

failure: Trading bei zuwenig geld

## Reasons for the resolution

tbd.
