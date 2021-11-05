---
type: decision
acronym: robot-seq-blocking
title: Blocking sequence of the robot context
decision_type: team
service: robot
status: _2_draft
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

![Robot blocking sequence](./images/robot-block-seq.png)

## Contexts which interact with this sequence

* game service: issues the command which was received by the player  
* robot service: processes the command and throws event according to the result

## Additional information

No other service needs to know whether a planet is blocked or not so this information is managed within the robot context exclusively.

