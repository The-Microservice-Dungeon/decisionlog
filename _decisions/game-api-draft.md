---
type: decision
acronym: game-api-draft
title: First draft of the REST API for Game service (not yet formally specified)
decision_type: must
service: game
status: _3_agreed
responsible: fgr;mba
deadline: 2021-10-22
priority: 1-high
aspects: 
    - api
todo:
history:
    v1:
        date: 2021-10-22
        comment: created initially
    v2:  
        date: 2021-10-24
        comment: added first draft of the decision
    v3:  
        date: 2021-12-31
        comment: Updated draft to the final form   
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
* Post player/              
    * (Creates a new player with uuid)

For the generell game-management: 
* Post games/                
    * Payload: {number of rounds, number of max players}
    * (Creates a new game, where people can join)
* Get games/{gameid]/time/                
    * (Showes how long one round is going on)
* Post games/{gameId}/gameCommands/start
    * (Starts a game with given gameid)
* Post games/{gameId}/gameCommands/end
    * (Ends a game with given gameid)
* Put games/{gameId}/players/{playerToken}/
    * (Registers a player to the game)      
* Patch games/{gameId}/roundDuration/{newDuration}/
    * (Changes the duration of the given game)   
* Patch games/{gameId}/maxRounds/{maxRounds}/
    * (Changes the maximal amount of rounds for the given game) 
    
For the command-management: 
*   Post command/
    *  Payload: {gameid,playerid,robotid,commandObject,commandtype}
    *  (gameid,playerid,robotid,commandObjec are not used in game and just get delievered; commandtype says to which service it gets delivered)
    *  Response: Transactionid for the player
    *  (Creates a new Command, that will get delievered to the fitting service)
*   Get command/
    *  (Gives all the commands, that where sent to the other services)

API's needed from the game service, that must be provided by the trading- and robotservice:
*   Post commands/
    *   Payload: {List of (transactionid,playerid,robotid,commandobject)} 
    *   Response: Flag, that commands are recieved

## Reasons for the resolution

The given APIs provide all the needed interactions for the other services and the useres, so that the game service can fulfil all its purposes.
