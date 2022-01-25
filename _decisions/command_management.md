---
type: decision
acronym: command_management
title: Management of the commands
decision_type: must
service: game
status: _3_agreed
responsible: fgr;mba
deadline: 2021-11-12
priority: 2-medium
aspects: 
    -  convention
todo:
history:
    v1:
        date: 2021-11-12
        comment: created initially
    v1:
        date: 2022-01-25
        comment: changed status to agreed
---

## Why is there need for such a decision?

It must be clarified, who manages the commands from the players, because otherwise otherwise every service would have to manage their own commands and try to verify them.

## Additional sources for better understanding the background

n/a

## Viable Options

Game service manages the commands and gets list off all robots or creates one with the information from the robot_create_events.

## Alternatives not seriously considered

Robot service  manages all commands or every service manages its own commands. 

## How is this decision evaluated?

Discussion in workshop on 5.11.

## Resolution Details

The game service must manage the commands from the player, because it owns the information about the round timer and can send the commands at the right time to the right services. 

It ownes a list of all robots, to verify, that players dont sent commands for robots of other players. 

The list is created by the information of the robot-create-events, so the service knows all the robots, that are owned by the players.

The commands from the players are stored in the game service and are sent to the other services, that fit the command-type during the execution phase.

The players recieves an id, to find the right event, that informs him of the outcome of his command.

## Reasons for the resolution

The robotlist is not given from the robot service, to decrease the amount of traffic and overhead. The self-created-list includes all robots during the time of the command-execution. 
So it can be used for the verification.
