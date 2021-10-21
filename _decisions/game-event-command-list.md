---
type: decision
acronym: game-event-command-list
title: List of business events and commands from Event Storming, for Game service
decision_type: team
belongs_to: game
status: _2_draft
responsible: fgr
deadline: 2021-10-22
priority: 2-medium
tags: 
    - business-event
    - command
history:
    v1:
        date: 2021-10-17
        comment: cr eated initially   
    v2:
        date: 2021-10-21
        comment: documenting the decisions    
---

## Why is there need for such a decision?

Each team needs to be clear about the business events (deep yellow stickers) and commands (blue stickers)
from the [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/). They are the blueprint for 
designing the features and API(s) of the service.

In addition, it needs to be checked if the event/command list is consistent with the other teams' lists.
Any conflicts, especially about who should receive which command?

## Additional sources for better understanding the background

-
## Viable Options

-

## Alternatives not seriously considered

-

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details

The game includes the following events in chronological order: <br>
Game Created <br>
Player <em> name </em> joined the game. <br>
Game started <br>

Round <em> x </em> started <br>
Command execution Phase: Passive Scouting started <br>
Phase: Command Input started <br>
Phase: Command execution started <br>
Command execution Phase: Blocking started <br>
Command execution Phase: Blocking ended <br>
Command execution Phase: Trading started <br>
Command execution Phase: Trading ended <br>
Command execution Phase: Movement started <br>
Command execution Phase: Movement ended <br>
Command execution Phase: Battle started <br>
Command execution Phase: Battle ended <br>
Command execution Phase: Mining started <br>
Command execution Phase: Mining ended <br>
Command execution Phase: Active Scouting started <br>
Command execution Phase: Active Scouting ended <br>
Phase: Command Input ended <br>
Phase: Command execution ended <br>
Round <em> x </em> ended <br>

Game ended <br>
Player <em> name </em> left the game <br> 

The game service doesent have his own commands. Instead it manages the commands coming from the admins, the players and the other services.
## Reasons for the resolution

To get the game running it first must be created. Then the players must join, so that their commands can get delivered. When the players have joined, the rounds for the players start, with an event for every execution phase, where the commands of he robots start the events from  the other services in the right order. After an given time the command execution phase end, so that no more commands for this phase can be executed. The events between game started and game ended are executed in a circle until the endcondition for the game is reached. 
