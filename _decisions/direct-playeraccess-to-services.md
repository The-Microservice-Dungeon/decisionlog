---
type: decision
acronym: direct-playeraccess-to-services
title: Direct player access to services
decision_type: must
status: _3_agreed
responsible: ngi
deadline: 2021-11-12
priority: 2-medium
aspects: 
    - api
history:
    v1:
        date: 2021-11-12
        comment: created initially
---

## Why is there need for such a decision?

The design of the Microservice Dungeon specifies that the only way for players to communicate with the service during a game is through commands sent to the game service. Therefore during a game it is not allowed for players to have access to the api of services other than the game service.  
However, the players have to implement their interaction possibilities provided by the game service api by their own and listening to results via thrown events. This is the only source of game information for a player and these events are often obfuscated so that only the players who sent the command which triggered an event can map the event with the initial command. This means that during the hackathon on which the players have to be implemented, all the work has to be done without a way to test an implementation because the game data is a black box. If an event is handled incorrectly or ignored the source of error in the implementation of the player is hard to find.

## Additional sources for better understanding the background

[Microservice Dungeon Documentation](https://the-microservice-dungeon.github.io/docs/)

## Viable Options

1. access to services is forbidden for all players (except game service which provides the api to handle player commands)
2. all GET access requests to all services are usable without restrictions but will be forbidden after the implementation phase of the hackathon and therefore be disabled/prevented when the Microservice Dungeon game is actually played
3. every service implements an own authentification option with which player are only allowed to get access to information they could have gathered by themselves through the events
4. implementation of a stand-alone service which handles all authentification in the Microservice Dungeon

## How is this decision evaluated?

### Do we actually need this feature?

#### Arguments pro direct player access:

- players can develop whith the option to test their implementation
- no overcomplicated and doubled implementation of methods because players can directly access the desired service without a middle man

#### Arguments contra direct player access:

- every service has to validate authenticity on its own (which probably only works with the help of the game service, so there would be many requests to / answers from the game service)
- undermindes the specificed communicationstructure between player and Microservice Dungeon (direct access as back door)
- a lot of work to implement correctly and a goal which doesn't apply to the final game 

### Proposal

- authentification is handled by the game service, therefore it stays the only communication interface for the player
- every service gets an extra end point, which isn't part of the fundamental entity which can handle such requests

## Resolution Details

The decision regarding direct player access was evaluated by the cost and benefit it has for the overall project. Due to the short time of one study semester and the optional character of the feature for the final project it is low priority.  
The feature may be implemented in the four stages specified above (viable options) when a team has leftover time:
1. player access forbidden
2. all access open for hackathon, later disabled
3. own authentification feature for every service
4. stand-alone authentification service

## Reasons for the resolution

The group of architecs discussed the benefits of this feature and the costs to implement it. They also took the possible risks in account, e.g. the effort needed to make it safe against exploitation.  
The result is that it would be very time-consuming to implement and the benefit is relatively small due to information being available through events (which means that a player could first implement a working data management and never really need this feature).
