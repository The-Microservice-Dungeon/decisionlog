---
type: decision
acronym: map-api-draft
title: First draft of the REST API for Map service (not yet formally specified)
decision_type: must
service: map
status: _2_draft
responsible: psc;sbe
deadline: 2021-10-29
priority: 1-high
aspects:
    - api
todo:
history:
    v1:
        date: 2021-10-22
        comment: created initially
    v1:
        date: 2021-10-27
        comment: updated after discussion
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
Discussion in meeting on 26.10.

## Resolution Details

* Create new `Gameworld` (`player_amount` `round_amount`)
* Get all `Gameworlds`
* Get the `Gameworld` with `"status": "active"` including the `Planets`
* Get a single `Planet` including `planet_type`
* Get a planet's `neighbours`
* Get a planet's specific `neighbour` (404 when not found)
* Turn planet into space station / spawn
* Get all `ResourceTypes`
* Get `Resources` for a given planet including it's `resource_type`
* Mine resources (of a certain `resource_type`) from a given planet, for one or several robots (with given transaction IDs)
  * Actual mined amount is sent via event
* Replenish resources (of a certain `resource_type`) on a given planet
  * Resource replenishment is sent via event
* Spawn creation is sent via event

We assume `created_at` and `updated_at` timestamps to exist

## Gameworld

POST `/gameworlds`

**Payload**

```json
{
  "gameworld": {
    "player_amount": 100,
    "round_amount": 1000
  }
}
```

GET `/gameworlds`

```json
[
   {
    "id": "19ae9ee7-d790-44cd-b5fc-8d618cf92ed1",
    "status": "active"
  }
]
```

GET `/gameworlds/:id`

```json
 {
  "id": "19ae9ee7-d790-44cd-b5fc-8d618cf92ed1",
  "status": "active",
  "planets": []
}
```

## Planet

GET `/planets/:id`

```json
 {
  "id": "e0448835-cc2d-40ad-b452-45bd7b7778b7",
  "gameworld_id": "19ae9ee7-d790-44cd-b5fc-8d618cf92ed1",
  "taken_at": "timestamp",
  "planet_type": "spawn",
  "neighbours": [],
  "resources": [],
  "movement_difficulty": 0,
  "recharge_multiplicator": 0
}
```

GET `/planets/:id/neighbours`

```json
{
  "neighbours": [],
}
```

GET `/planets/:id/neighbours/:neighbour_id`

```json
{
  "neighbour": {
    "id": "e0448835-cc2d-40ad-b452-45bd7b7778b7",
    "gameworld_id": "19ae9ee7-d790-44cd-b5fc-8d618cf92ed1",
    "taken_at": "2021-10-27T09:54:55.814Z",
    "planet_type": "spawn",
    "neighbours": [],
    "resources": [],
    "movement_difficulty": 0,
    "recharge_multiplicator": 0
  }
}
```

## Resource Type

GET `/resource_types`

```json
{
    "resource_types": []
}
```

## Resource

GET `/planets/:id/resources`

```json
[
  {
    "id": "f5b34539-4bcd-4a3d-b6f2-da2c580eae1c",
    "planet_id": "e0448835-cc2d-40ad-b452-45bd7b7778b7",
    "resource_type": {
        "id": "7014e90e-7f52-481e-8685-304898348a18",
        "name": "iron",
        "difficulty": 4
    },
    "max_amount": 1000,
    "current_amount": 400
  }
]
```

GET `/planets/:id/resources/:resource_id`

```json
{
  "id": "f5b34539-4bcd-4a3d-b6f2-da2c580eae1c",
  "planet_id": "e0448835-cc2d-40ad-b452-45bd7b7778b7",
  "resource_type": {
      "id": "7014e90e-7f52-481e-8685-304898348a18",
      "name": "iron",
      "difficulty": 4
  },
  "max_amount": 1000,
  "current_amount": 400
}
```

## Minings

POST `/planets/:id/minings`

**Payload**

```json
  {
  "mining": {
    "amount_mined": 1000,
    "resource_type": "iron"
  }
}
```

## Reasons for the resolution

tbd.
