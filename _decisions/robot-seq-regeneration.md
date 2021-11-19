---
type: decision
acronym: robot-seq-regeneration
title: Regeneration sequence of the robot context
decision_type: team
service: robot
status: _3_agreed
responsible: ngi;cpo
deadline: 2021-11-08
priority: 2-medium
aspects:
    - serviceInteraction
todo: 
    - discuss special cases with Game Masters
history:
    v1:
        date: 2021-10-27
        comment: created initially and added contents
---

## Sequence diagram

![Robot regeneration sequence](./images/robot-regenerate-seq.png)

## Contexts which interact with this sequence

game service: issues the command which was received by the player  
robot service: processes the command and throws event according to the result

## Additional information

Special case "regenerate twice the amount of energy on own spawn point" is probably out of scope because the robot service does not know the initial spawn location of the player - maybe there isn't one at all (game init: player has to buy his first robot and therefore has no designated personal spawn)

