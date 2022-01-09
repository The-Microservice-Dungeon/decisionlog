---
type: decision
acronym: robot-api-current
title: Current version of the REST API for Robot service
decision_type: must
service: robot
status: _3_agreed
responsible: ngi;cpo
deadline: 2021-11-21
priority: 1-high
aspects: 
    - api
todo:
history:
    v1:
        date: 2021-11-07
        comment: created initially  
    v2:
        date: 2021-12-03
        comment: added link to api spec
---

## Why is there need for such a decision?

This decision serves as explanation and reasoning of the formally specifyed REST API of the robot service.

## Link to the specified API

[API of the robot service](https://the-microservice-dungeon.github.io/docs/openapi/robot)

## DEPRECATED please see [API spec](https://the-microservice-dungeon.github.io/docs/openapi/robot)

### Robot and its data

The API provides GET for all attributes of a robot:  
- general: id, player, planet, alive  
- max stats of robot according to current upgrade status: maxHealth, maxEnergy, energyRegen, attackDamage, miningSpeed  
- current status of the robot: health, energy  
- current upgrade level: healthLevel, damageLevel, miningSpeedLevel, miningLevel, energyLevel, energyRegenLevel, storageLevel
- object "inventory" with attributes: maxStorage, usedStorage, storedCoal, storedIron, storedGem, storedGold, storedPlatin

### POST a robot

This is responsible for spawning a new robot. It should only be used by the trading service.  

The expected properties are:  
- transaction_id
- player
- planet  

All expected properties are UUIDs. The robot service then creates the new robot with a newly generated uuid for the robot, the three received properties and standard values.

### PATCH robot data

This is the way to go if the game service converts commands to API calls and controls the actions. May be subject to chance depending on whether we get the respective command directly or reformed as API call.  

Is used to change attributes of a specific robot. Used for trading, upgrading, mining, movement.  
Expected properties are:
- For movement: planet uuid
- For upgrading: healthLevel, damageLevel, miningSpeedLevel, miningLevel, energyLevel, energyRegenLevel, storageLevel as integer
- For mining and trading: storedCoal, storedIron, storedGem, storedGold, storedPlatin

TODO: Check if this is a viable option.

### Commands

The path "/commands" is a endpoint to receive commands which are no specific API calls. These are all commands which the player issues to the game service which then will be forwarded to us together with a transaction id. They are received as a batch consisting of all commands of a phase.  
Valid commands are:
- block
- move
- fight
- mine
- regenerate
- use-item-fighting
- use-item-movement

TODO: Discuss if different commands are needed for item usage, robot just has to receive a batch of commands from one phase and is not involved in scheduling.

### Errors

- integer for https-codes (example 404)
- string for "Not found"
- string for specific error messages (example: "couldn't find robot with id=xy")
