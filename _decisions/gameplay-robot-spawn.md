---
type: decision
acronym: gameplay-robot-spawn
title: spawn of robots
decision_type: must
status: _2_draft
responsible: tpa;ngi;cpo
deadline:  2021-12-07
priority: 2-medium
aspects:
    - gameplayrule
history:
    v1:
        date: 2021-11-23
        comment: created initially
    v2:
        date: 2021-12-03
        comment: added decision for randomized spawn location
---

## Why is there need for such a decision?

To set uniform rules for the start of the game. It is also important to keep the scope reachable and therefore a simple solution is prefered.  

An efficient way to handle robot spawns is needed. Extra features with the help of designated spawn locations for every player would enhance the overall gameplay and provide further depth. However, this comes at a cost. 

## Alternatives not seriously considered

- One service (game service) is responsible for initially spawing one robot for each player.
- Separate spawn locations for every player which provide extra gameplay features such as spawn protection (movement on foreign spawnlocations is prevented), better energy regeneration rate and using the own spawn location as space station.
- Players can buy robots regardless of the position of their other robots as long as they have enough money. Owning a robot is no requirement. The newly bought robots spawn on a designet spawn planet. Every player has its own spawn location.

## How is this decision evaluated?

Discussion with all project members - iteratively.  

## Resolution Details

No robots are provided for players at the start of the game. The players get a starting budget and can decide for themselves how many robots they want to buy (spawn).  
The newly bought robot will spawn at a random space station. If a player decides to buy more than one robot at once, the spawning location for every robot is randomized seperately.

## Reasons for the resolution

This decision was made mainly to simplify the initialization process of the game. It also leaves the player free to choose how to start the game and opens up possibilities for even more different strategies.  
Furthermore, all seperate spawning logic was scrapped due to the time investment it would cost and the player spawn would therefore just be a trap for the player. (no protection versus spawn camping, etc.)
