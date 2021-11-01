---
type: decision
acronym: trading-event-and-command-list
title: List of business events and commands from Event Storming, for Trading service
decision_type: team
belongs_to: trading
status: _2_draft
responsible: tla;tpa
deadline: 2021-10-22
priority: 2-medium
tags:
  - business-event
history:
  v1:
    date: 2021-10-17
    comment: created initially
  v2:
    date: 2021-10-21
    comment: added events
  v3:
    date: 2021-10-27
    comment: added sequence diagrams
---

## Why is there need for such a decision?

Each team needs to be clear about the business events (deep yellow stickers) and commands (blue stickers)
from the [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/). They are the blueprint for
designing the features and API(s) of the service.

In addition, it needs to be checked if the event/command list is consistent with the other teams' lists.
Any conflicts, especially about who should receive which command?

## Additional sources for better understanding the background

tbd.

## Viable Options

## All Trading Commands/Actions

#### Buy - Robot

- Receive buy command
- Check player money (needs player info)
- Check robot count (needs player info)
- Reduce player money
- Spawn robot for player (Spawn only after money reduction confirmed)
- Confirm bought
- Return error

#### Buy - Upgrade

- Receive buy command
- Check player money (needs player info)
- Check robot current upgrade level (needs robot info)
- Reduce player money
- Tell robot-service to upgrade robot (Upgrade only after money reduction confirmed)
- Confirm bought
- Return error

#### Buy - Item

- Receive buy command
- Check player money (needs player info)
- Check item available, check item price (needs item)
- Reduce player money
- Tell game service to tell robot-service to put item in robot inventory (item only after money reduction confirmed)
- Confirm bought
- Return error

#### Sell - Resources

- Receive sell command
- Check Robot Inventory for Resources (needs robot info)
- Calculate receive money
- Reduce resources in robot inventory (needs robot info)
- Reduce player money (needs player info)
- Confirm sold
- Return error

#### Restore - Health

- Receive restore hp command
- Check player money (needs player info)
- Reduce player money
- Tell robot service to add health to robot
- Confirm success
- Return error

#### Restore - Energy

- Receive restore energy command
- Check player money (needs player info)
- Reduce player money
- Tell robot service to add energy to robot
- Confirm success
- Return error

Other functions we did not speak about:

    Get shop list (get all items, upgrades, heals + prices)

Questions:

- Can you sell a specific amount of resources or everything at once?
- Can you sell multiple times per round? Can you sell different types of resources per ‘sell’ command?
- Can you buy multiple robots per round?
- Can you sell items?
- Can you sell robots?
- Can you buy multiple things per round? Multiple items? One item and one upgrade? Multiple upgrades?
- Upgrade from 1 - 5 in one step? One round?
- If you try to buy an upgrade which is not possible, will it cost you? Or just return an error?
- Does trading has to have a connecting to the robot service (see “need robot info” above)
- Initialisieren?

### Inital API Draft

    GET /trading/item
      Get item list with prices
    POST /trading/item
      Buy item
    GET /trading/resource
      Get resources list with prices
    POST /trading/resource
      Sell all resources of robot
    GET /trading/upgrade
      Get upgrade list with prices
    POST /trading/upgrade
      Buy specific upgrade (unsure wether it is an item now)
    GET /trading/health
      Get health price (to be discussed)
    POST /trading/health
      Buy health for robot
    GET /trading/energy
      Get energy price (to be discussed)
    POST /trading/energy
      Buy energy for robot
    GET /trading/robot
      Get robot prices
    POST /trading/robot
      Buy new robot
    GET /trading/balance
      Get players current balance (security?)
    GET /trading/balances
      Get all players current balances (security?)
    

## Ongoing Discussions

- It is not sure if upgrade are items now and if we still need a seperate route
- It is not sure if health/energy are items and if we need a seperate route
- Do we need security on balances routes? Which security?
- How do we get the inital resources? From planet service?

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.

## Resolution Details

tbd.

## Reasons for the resolution

tbd.
