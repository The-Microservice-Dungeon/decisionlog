---
type: decision
acronym: robot-api-draft
title: First draft of the REST API for Robot service (not yet formally specified)
decision_type: must
service: robot
status: _2_draft
responsible: ngi;cpo
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
        date: 2021-10-23
        comment: created first draft    
---

## Why is there need for such a decision?

This decision will serve as a kickoff for formally specifying the REST APIs.

## Additional sources for better understanding the background

tbd.

## Viable Options

### /robot/
- is used to create (spawn) robots
- if you post a robot, you need to include playerUUID in the payload

### /robot/{robotUUID}
- GET all th information about the specified robot

### /robot/{robotUUID}/upgrades
- GET the current update status of the specified robot and its possible upgrades
- the trade-service can UPDATE a specific upgrade to the next level
- (may need further discussion)

### /robot/{robotUUID}?attribute=att1,att2,att3,…,attN
- request only the specified attributes of the robot
- (needs to be further discussed)

### /robot/command
- this is for posting player commands and will be used by the game-service
- commands can be posted as a list
- every command has to include the commandUUID
- result of a command will be accessible by the commandUUID
- when a command has been executed, an event with the corresponding commandUUID will be posted

#### commands:
- block [playerUUID] [robotUUID]
- move [playerUUID] [robotUUID] [targetPlanetUUID]
- fight [playerUUID] [robotUUID] [targetRobotUUID]
- mine [playerUUID] [robotUUID]
- regenerate [playerUUID] [robotUUID]
- use_item [playerUUID] [robotUUID] [itemType] [targetUUID]
    - targetUUID is either a planet or a robot, depending on the itemType
- robot_info [playerUUID] [playerAuthToken]
    - allows a player to get the info of all their robots. Only used for the testing phase, will not be available in the final game
    - implementation is low priority


## Alternatives not seriously considered

n/a, see resolution.

## How is this decision evaluated?

Discussion in workshop on 22.10.

## Resolution Details

tbd.

## Reasons for the resolution

tbd.
