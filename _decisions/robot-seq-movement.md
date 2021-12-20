---
type: decision
acronym: robot-seq-movement
title: Movement sequence of the robot context
decision_type: team
service: robot
status: _3_agreed
responsible: ngi;cpo
deadline: 2021-11-08 
priority: 2-medium
aspects:
    - serviceInteraction
todo: 
history:
    v1:
        date: 2021-10-27
        comment: created initially and added contents
---

## Sequence diagram

![Robot movement sequence](./images/robot-movent-seq.png)

## Contexts which interact with this sequence

* game service: issues the command which was received by the player  
* robot service: processes the command, issues request to map, checks if two planets are neighbors, processes the results and throws event according to the result  
* map service: provides neighbors of a planet

## Additional information

A successful result of the move has to incluse all planet data of the new position. This info has to be obfuscated so that not every player can just read the most recent planet data of all visited planets. Therefore the planet info has to be obfuscated via the command uuid.  
After a successful movement two events are thrown. The first one which indicates the success of the movement. It contains the remaining energy of the robot, the planet data of the target planet and the uuids of all robots located there. The second event is mapped to the command uuid and provides all neighbors for the target planet after a successful move.
If a player tries to move a robot which is on a blocked planet, the robot service will just throw an event to report the failure and that round is lost for that specific robot.