---
type: decision
acronym: robot-event-and-command-list
title: List of business events and commands from Event Storming, for Robot service
decision_type: team
service: robot
status: _3_done
responsible: ngi;cpo
deadline: 2021-10-22
priority: 2-medium
aspects: 
    - eventing
todos:
history:
    v1:
        date: 2021-10-17
        comment: created initially
    v2:
        date: 2021-10-21
        comment: added business events
    v3:
        date: 2021-11-24
        comment: specified events
    v3:
        date: 2021-12-03
        comment: added link to latest event list & finalized decision
---

## Why is there need for such a decision?

Each team needs to be clear about the business events (deep yellow stickers) and commands (blue stickers)
from the [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/). They are the blueprint for 
designing the features and API(s) of the service.

In addition, it needs to be checked if the event/command list is consistent with the other teams' lists.
Any conflicts, especially about who should receive which command?

## Additional sources for better understanding the background

Video guides provided by the Archilab-Team:  
[Asynchron communication with Apache Kafka](https://www.youtube.com/watch?v=9LZegMnABAA)  
[Apache Kafka essentials](https://www.youtube.com/watch?v=wbhyB9nBR4E)

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


## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 

## Resulution - latest version of events

[Events of the robot service](https://the-microservice-dungeon.github.io/docs/asyncapi/robot/)  

A complete list of all events of the robot service is provided [here](https://the-microservice-dungeon.github.io/docs/asyncapi/robot/). It includes the async specification of all possible events of the robot service.
