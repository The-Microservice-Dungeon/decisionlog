---
type: decision
acronym: gameLog-event-and-command-list
title: List of business events and commands from Event Storming, for GameLog service
decision_type: team
belongs_to: gameLog
status: _3_agreed
responsible: thu;aha
deadline: 2021-10-22
priority: 2-medium
tags: 
    - business-event
history:
    v1:
        date: 2021-10-17
        comment: created initially
    v2:
        date: 2021-10-20
        comment: add event list
    v3:
        date: 2021-10-22
        comment: >
            Decision regarding the required Events
    v4:
        date: 2021-10-22
        comment: >
            Add events we require for our the API draft
---

## Why is there need for such a decision?

Each team needs to be clear about the business events (deep yellow stickers) and commands (blue stickers)
from the [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/). They are the blueprint for 
designing the features and API(s) of the service.

In addition, it needs to be checked if the event/command list is consistent with the other teams' lists.
Any conflicts, especially about who should receive which command?

## Additional sources for better understanding the background

Miro Board of the Domains (from Event Storming).

## Viable Options

The business events are pretty clear from the miro board:
- Let services log events to event queue (Apache Kafka)
- *ALTERNATIVE*: request game data from the services
- aggregate end results of all rounds
- evaluate end results
- generate final rankings
  - grant trophies
- generate rankings for categorized achievements (not trophies but e.g. amount of money, resources, etc.) (leaderboards)
- store trophies in cross-game personal log

This domain has no commands.

## Alternatives not seriously considered

n/a

## How is this decision evaluated?

Evaluation of [Event Storming results](https://miro.com/app/board/o9J_lsQV7ZA=/), and the discussion within the team.
 
## Resolution Details

We're subscribing/consuming events from Kafka. 

We need the following events from the services: 

- Mining event + Resource given event
- Health change event
- Robot spawn event
- Movement event
- Fight Event + Fight Result
- Player registered
- Game started + Game ended

In addition we require the following REST APIs: 
- Wealth / User Balance API 

## Reasons for the resolution

We're going to use asynchronous communication to make it possible using a live-dashboard and do not require synchronous polling.

## Additional Information

One possible idea to display the leaderboards is exposing metrics from the service which get scraped by prometheus and displayed within a Grafana Dashboard   