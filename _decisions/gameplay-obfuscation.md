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
todos: discuss the suggested changes on the fog of war
history:
    v1:
        date: 2021-11-24
        comment: created initially
    v2:
        date: 2021-11-24
        comment: added results of discussion with gameplay team
---

## Why is there need for such a decision?

The initial draft of the Microservice Dungeon included a gameplay decision for obfuscation of information. In the gaming context this is called a "fog of war".  
In the architecture of this project an authentification service to ensure private events would be required to achieve this.

## Alternatives not seriously considered

1. Implementing an authentification service in every microservice to keep the independency of each service and prevent that the game service becomes some kind of god service.
2. Implementing a stand-alone authentification service which handles all authentification and ensures that players can only read their events and general events.
3. All events are openly readible and contain all information. Therefore all players have access to the same information regardless of robot ownership.

These options are related to the decision [direct player access to services](./direct-playeraccess-to-services.md).

## How is this decision evaluated?

Discussion within the architecture team. Later the whole team of all responsibilites discussed this together.

## Resolution Details

Due to the time constraint of this project neither an authentification service as part of each service nor a stand-alone authentification service is feasible.  
Therefore the solution is a transaction id which obfuscates all events. If possible an event should contain as much information as possible and generally contain the whole aggrgegate in question without revealing the crucial information to map it. 

### Example of obfuscation
After movement of a robot an event is thrown which contains the transaction id, success/failure of the command and the neighbors of the target planet. The planetdata of the target planet itself is thrown in a different event which contains the whole planet data (id, id of robots located there, resource).contained in this event.  
This means that players who can track this information well can work with the events of all planets which uuids the respective player knows. Hiding the neighbor planets with the help of the transaction id ensures that every player has to discover the planet uuids by themselves. (Tracking movement of enemy robots without knowledge of the planet uuids could still be possible but is hard to achieve and therefore not relevant.)
<br>
<br>
TODO: This decision has to be discussed in the whole team with game masters, architects and developers from all contexts.


## Reasons for the resolution

The scope of this project is already very big for the amount of time and people we have. Therefore a simple and time efficient solution is preferred. Using obfuscation with the help of a transaction id is a good compromise between openly showing all data and verifying authenticity.

