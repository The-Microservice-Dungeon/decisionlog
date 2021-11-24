---
type: decision
acronym: gameplay-obfuscation
title: Obfuscation of information (fog of war)
decision_type: must
status: _3_agreed
responsible: ngi
deadline:  2021-11-24
priority: 2-medium
aspects:
    - gameplayrule
history:
    v1:
        date: 2021-11-24
        comment: created initially
---

## Why is there need for such a decision?

The initial draft of the Microservice Dungeon included a gameplay decision for obfuscation of information. In the gaming context this is called a "fog of war".  
In the architecture of this project an authentification service to ensure private events would be required to achieve this.

## Alternatives not seriously considered

1. Implementing an authentification service in every microservice to keep the independency of each service and prevent that the game service becomes some kind of god service.
2. Implementing a stand-alone authentification service which handles all authentification and ensures that players can only read their events and general events.

These options are related to the decision [direct player access to services](./direct-playeraccess-to-services.md).

## How is this decision evaluated?

Discussion within the architecture team.

## Resolution Details

Due to the time constraint of this project neither an authentification service as part of each service nor a stand-alone authentification service is feasible.  
Therefore the solution is a transaction id which obfuscates all events. If possible an event should contain as much information as possible and generally contain the whole aggrgegate in question without revealing the crucial information to map it. 

### Example of obfuscation
After movement of a robot an event is thrown which contains success/failure of the command, planetdata of the target planet and its neigbors. To obfuscate this the transaction id which is only known to the player who issued the command maps the data instead of the planet id which will not be contained in this event.

## Reasons for the resolution

The scope of this project is already very big for the amount of time and people we have. Therefore a simple and time efficient solution is preferred. Using obfuscation with the help of a transaction id is a good compromise between openly showing all data and verifying authenticity.

