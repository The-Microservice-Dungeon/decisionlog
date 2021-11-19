---
type: decision
acronym: standardized-resource-names
title: Resources names that are of strategic importance for players
decision_type: must
status: _3_agreed
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

| **Name**                   | **Item**                     |
|----------------------------|------------------------------|
| **ROBOT**                  | Robot                        |
| **HEALTH**                 | Health Regeneration          |
| **ENERGY**                 | Energy Regeneration          |
| **ROCKET**                 | Rocket Item                  |
| **WORMHOLE**               | Wormhole Item                |
| **LONG_RANGE_BOMBARDMENT** | Long range Bombardment Item  |
| **SELF_DESTRUCTION**       | Self Destruction Item        |
| **REPERATION_SWARM**       | Reperation Swarm Item        |
| **NUKE**                   | Nuke Item                    |
| **STORAGE_1**              | Storage Level 1 Upgrade      |
| **STORAGE_2**              | Storage Level 2 Upgrade      |
| **STORAGE_3**              | Storage Level 3 Upgrade      |
| **STORAGE_4**              | Storage Level 4 Upgrade      |
| **STORAGE_5**              | Storage Level 5 Upgrade      |
| **MINING_SPEED_1**         | Mining Speed Level 1 Upgrade |
| ...                        | ...                          |

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
