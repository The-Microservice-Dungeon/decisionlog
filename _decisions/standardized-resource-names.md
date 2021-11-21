---
type: decision
acronym: standardized-resource-names
title: Resources names that are of strategic importance for players
decision_type: must
status: _2_draft
responsible: tla
deadline: 2021-11-19
priority: 2-medium
aspects:
    - convention
history:
    v1:
        date: 2021-11-05
        comment: created initially
---

## Why is there need for such a decision?

The decision is important for Players implementing their Strategies. Having changing IDs or Names for the same Items whould make it hard to implement consistent Strategies.

## Additional sources for better understanding the background

n/a

## Viable Options

- Standardized Names
- No Standardized Names using UUIDs only

## Alternatives not seriously considered

n/a

## How is this decision evaluated?

In a Group discussion with part of the DDD/FAE team.

## Resolution Details

### Standardized Item Names

| **Name**                   | **Item**                            |
|----------------------------|-------------------------------------|
| **ROBOT**                  | Robot                               |
| **HEALTH**                 | Health Regeneration                 |
| **ENERGY**                 | Energy Regeneration                 | 
| **ROCKET**                 | Rocket Item                         | 
| **WORMHOLE**               | Wormhole Item                       |
| **LONG_RANGE_BOMBARDMENT** | Long range Bombardment Item         |
| **SELF_DESTRUCTION**       | Self Destruction Item               |
| **REPAIR_SWARM**           | Repair Swarm Item                   |
| **NUKE**                   | Nuke Item                           |
| **STORAGE_N**              | Storage Level N=1-5 Upgrade         |
| **MINING_SPEED_N**         | Mining Speed Level N=1-5 Upgrade    |
| **MINING_STRENGTH_N**      | Mining Strength Level N=1-5 Upgrade |
| **ENERGY_CAPACITY_N**      | Energy Capacity Level N=1-5 Upgrade |
| **ENERGY_REGEN_N**         | Energy Regen Level N=1-5 Upgrade    |
| **SCOUNTING_N**            | Scouting Level Level N=1-5 Upgrade  |
| ...                        | ...                                 |

This Naming-Convention goes on for all [avaliable Upgrades](https://the-microservice-dungeon.github.io/docs/rules/gameplay#robot-upgrades).

### Standardized Resource Names

| **Name** | **Resource**  |
|----------|---------------|
| COAL     | Coal          |
| IRON     | Iron          |
| GEM      | Gem           |
| GOLD     | Gold          |
| PLATIN   | Platin        |

## Reasons for the resolution

Players can rely on set Names for certain Items/Resources etc. when implementing their Services. These can be used to buy Items from the Trading-Service etc..
