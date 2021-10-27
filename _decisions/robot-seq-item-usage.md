---
type: decision
acronym: robot-seq-item-usage
title: Blocking sequence of the robot context
decision_type: team
belongs_to: robot
status: _2_draft
responsible: ngi;cpo
deadline: 
priority: 2-medium
tags: 
todo: define the contents of the thrown event with results for the movement item (see "Problem" below)
history:
    v1:
        date: 2021-10-27
        comment: created initially and added contents
---

## Sequence diagram

![Robot combat item usage sequence]()

![Robot movement item usage sequence]()

## Contexts which interact with this sequence

game service: issues the command which was received by the player  
robot service: processes the command, requests random planet from map and throws event according to the result
map service: provides a random existing planet

## Additional information

### Movement item (wormhole)
The robot service needs the possibility to ask the map for a random valid planet uuid, get all planet data (analog to regular movement) and then throw the result as event with command uuid (to obfuscate) and planet info. This is very close to the movement but doesn't happen with the batch of regular movement commands. 

### Fighting item
The received item type determines if a robot uuid or a planet uuid is expected.

## Problem with movement item (wormhole)

After a successful move the player gets the new planet data obfuscated while not sending the planet uuid. Therefore the player can map the info with the help of the command uuid he got (he knows the planet uuid he sent his robot to so he can easily map). BUT: If movement happens with a randomized target planet the same method to obfuscate the planet info of the new planet doesn't work anymore because the event then has to contain the planet uuid to tell the player where this robot is. The solution would be to never tell the player which uuid a planet has, just giving him the info that there are neighbors "norht, east, south, west" and handling movement with that. (While considering this, don't forget about the validation done by the trading service whether a given planet uuid is a spacestation to check if trading in general is allowed - and other uses of the planet uuid)



