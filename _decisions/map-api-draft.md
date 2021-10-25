---
type: decision
acronym: map-api-draft
title: First draft of the REST API for Map service (not yet formally specified)
decision_type: must
belongs_to: api
status: _1_open
responsible: 
deadline: 2021-10-22
priority: 1-high
tags: 
todo:
history:
    v1:
        date: 2021-10-22
        comment: created initially
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

* Create new map (number of players, number of rounds)
* Print out the complete map
* Turn planet into space station / spawn
* Get: is planet a space station / spawn?
* Get resources (of a certain type) for a given planet
* Put resources (of a certain type) on a given planet
* Mine resources (of a certain type) from a given planet, for one or several robots (with given transaction IDs)
  * actual mined amount is sent via event
* Get list of resource categories for the complete map
* Get all adjacent planets for a given planet
* Get: Is Planet X adjacent to planet y?


## Reasons for the resolution

tbd.
