---
type: decision
acronym: robot-seq-mining
title: Mining sequence of the robot context
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
    v2:
        date: 2021-11-17
        comment: moved destribution responsibility to robot
---

## Sequence diagram

![Robot mining sequence](./images/robot-mining-seq.png)

## Contexts which interact with this sequence

* game service: issues the command which was received by the player  
* robot service: processes the command, issues requests to map, processes the results and throws event according to the result  
* map service: handles the amount of available resources

## Additional information

All mining requests issued to the map service have to be processed by them before sending the results back to the robot service.    
The player states which resource should be mined, so the robot service just checks if the specific robot is able to do that (mining level) and if yes, calculates the amount. The robot service then combines all requests for one planet and sends a mining request with the total amount per planet to the map service. Map then returns the amount which can be mined (requested value or below) and robot then distributes the received resources fairly between all participating robots for the planet.

