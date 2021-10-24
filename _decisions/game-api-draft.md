---
type: decision
acronym: game-api-draft
title: First draft of the REST API for Game service (not yet formally specified)
decision_type: must
belongs_to: api
status: _2_draft
responsible: fgr;mba
deadline: 2021-10-22
priority: 1-high
tags: 
todo:
history:
    v1:
        date: 2021-10-22
        comment: created initially
    v2:  
        date: 2021-10-24
        comment: added first draft of the decision
---

## Why is there need for such a decision?

This decision will serve as a kickoff for formally specifying the REST APIs.

## Additional sources for better understanding the background

n/a

## Viable Options

n/a, see resolution.

## Alternatives not seriously considered

n/a, see resolution.

## How is this decision evaluated?

Discussion in workshop on 22.10.

## Resolution Details

The game services provides api calls for its different tasks. 
For the user-management: 
* Post Admin/               
    * (Creates a new admin)
* Post Player/              
    * (Creates a new player with uuid)
* Delete Player/            
    * (Deletes a player and removes him from the game)

For the generell game-management: 
* Post Game/                
    * Payload: {number of rounds, number of max players}
    * (Creates a new game, where people can join)
* Get time/                
    * (Showes how long one round is going on)

For the command-management: 
*   Post Command/
    *  Payload: {playeruuid,robotuuid,command,commandtype,item}
    *  (playeruuid,robotuuid,command are not used in game and just get delievered; commandtype says to which service it gets delivered, item says if the command includes the usage of an item and is needed for correct ordering)
    *  Response: CommandUUID for the player
    *  (Creates a new Command, that will get delievered to the fitting service)

API's needed from the game service, that must be provided by the trading- ,robot- and mapservice:
*   PUT Command/
    *   Payload: {List of (CommandUUID,PlayerUUID,RobotUUid,command)} 
    *   Response: Flag, that commands are recieved

## Reasons for the resolution

The given APIs provide all the needed interactions for the other services and the useres, so that the game service can fulfil all its purposes.
