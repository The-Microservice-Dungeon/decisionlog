---
type: decision
acronym: domain-model-for-commands
title: What is the proper domain model for commands - who is owner?
decision_type: must
belongs_to: api
status: _1_open
responsible: 
deadline: 2021-10-22
priority: 1-high
tags: 
    - model-conflict
    - command-entity
todos:
    - fill open parts
history:
    v1:
        date: 2021-10-22
        comment: created initially
---

## Why is there need for such a decision?

Ownership for Command is claimed by more than one service: 
* xxx
* xxx

## Additional sources for better understanding the background

n/a

## Viable Options

* Assign ownershio
* Go for more than one command entity

## Alternatives not seriously considered

tbd 

## How is this decision evaluated?

tbd

## Resolution Details

tbd

## Reasons for the resolution

The whole project is API-driven, as the robot service will have to implement against the APIs. Therefore, the
APIs need to be done first.
