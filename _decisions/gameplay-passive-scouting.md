---
type: decision
acronym: gameplay-passive-scouting
title: Passive scouting after movement
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

Players need to get information about the planet their robots are located on and which neighbors it has to plan their next move.

## Alternatives not seriously considered

Scouting as a robot ability which has to be used in order to get information about the planet (resources, other robots) and the neighbor planets.

## How is this decision evaluated?

Discussion with the whole project team.

## Resolution Details

After successful movement the respective event contains information about the planet (resources, other robots) and will also return the uuids of the neighbor planets.  
To obfuscate the information, the event will not contain the planet uuid of the target planet. Therefore only the player which issued the movement command will be able to map that information through the transaction id which only that player knows.

## Reasons for the resolution

The first draft was a detailed description of a scouting ability, but for the sake of simplicity and to not go beyond the scope of this project scouting was modeled to be a passive ability which triggers after successful movement.  
In addition, obfuscation and fog of war (which was planned in the initial draft of this project) don't allow precise scouting due to the lack of private events and a authentication service.

