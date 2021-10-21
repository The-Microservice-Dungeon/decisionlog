---
type: decision
acronym: game-domainmodel
title: (Sub-)Domain Model for Game Service
decision_type: team
belongs_to: game
status: _1_open
responsible: mba
deadline: 2021-10-22
priority: 1-high
tags: 
    - subdomain-model
history:
    v1:
        date: 2021-10-17
        comment: created initially
    v2:
        date: 2021-10-21
        comment: documenting the decisions
---

## Why is there need for such a decision?

The (sub-)domain model is a prerequisite for planning the development - which entities, value objects, aggregates 
do I have? 

In addition, it needs to be checked if the domain model is consistent with the other teams' (sub-)domain models.
Especially: Are there any conflicts with regard to entity ownership?

## Additional sources for better understanding the background

Evans, E. (2003). Domain-Driven Design: Tackling Complexity in the Heart of Software (1 edition). 
Addison-Wesley Professional.

## Viable Options


### Player
The Player gets commands which are excuted in the game. Money is a composition of Player, 
and Player is part of the Game.

### Round
A Round follows certain conditions which are part of the Game. The conditions are initiated in the Round Phase...?
The timer is a composition of the round.
- potential sub-domain: Round end

### Game
A Game follows certain conditions. The timer is a composition of the round.
- potential sub-domain: Game start
- potential sub-domain: Game end
- potential sub-domain: Game Creation  
    + Are the Game conditions set her?
    + Dungeon master approves map?
    + Costs defined?
    + Where is the map created and modified?
    + Is there a max Player count?
    
### Command
Commands are excuted through th ePlayer in a Round. The command need the information about a certain Robot and which
phase or type is be choosen.
- potential sub-domain: Command input
- potential sub-domain: Command processing

### Admin 
tbd.

### Further potential (sub) domains:
- Authentication
- Outside of Game (getting all player, achievments ...)

## Alternatives not seriously considered

n/a

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details

tbd.

## Reasons for the resolution

tbd.
