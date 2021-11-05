---
type: decision
acronym: gameLog-api-draft
title: First draft of the REST API for GameLog service (not yet formally specified)
decision_type: must
service: gameLog
status: _3_agreed
responsible: thu;aha
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
        date: 2021-10-22
        comment: >
            Add first API draft
    v3:
        date: 2021-11-05
        comment: >
            Close decision, since there is a first formally specified API draft
---

## Why is there need for such a decision?

This decision will serve as a kickoff for formally specifying the REST APIs.

## Additional sources for better understanding the background

tbd.

## Viable Options

n/a, see resolution.

## Alternatives not seriously considered

n/a, see resolution.

## How is this decision evaluated?

Discussion in workshop on 22.10.

## Resolution Details

Since we're most likely going to consum we don't require many APIs. The main focus will be to provide a leaderboard and grant trophies based on fired events. In addition to that we will expose metrics about the events that can be consumed -- Maybe by other services (e.g. trading prices scale according to the current demand), but mainly to introduce a Live Dashboard during the Hackathon.

Nevertheless we will provide REST APIs regardingt the Leaderboard and Trophies.

**Leaderboard**

- **GET** global leaderboard
- **GET** leaderboard of one specific category

**Trophies**

- **GET** achieved global trophies
- **GET** achieved trophies for a player


## Reasons for the resolution

- see details
