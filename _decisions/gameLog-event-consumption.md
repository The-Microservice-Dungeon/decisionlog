---
type: decision
acronym: gameLog-event-consumption
title: Event Consumption within the GameLog service
decision_type: team
service: gameLog
status: _2_draft
responsible: thu;aha
priority: 1-high
deadline: 2021-11-05
aspects:
    - eventing
history:
    v1:
        date: 2021-11-02
        comment: created initially    
---

## Why is there need for such a decision?

In order to have a well-structured, maintainable and reliable service for a game log it is crucial 
to have a well-defined strategy for event consumption.

## Additional sources for better understanding the background

- [Event Sourcing (Martin Fowler)](https://martinfowler.com/eaaDev/EventSourcing.html)
- [Event Sourcing (Microservices.io)](https://microservices.io/patterns/data/event-sourcing.html)
- [Event Sourcing (Greg Young)](https://www.youtube.com/watch?v=8JKjvY4etTY)

## Viable Options

- Using Event Sourcing by building a custom event store
- Using Event Sourcing by utilizing Kafka as an event store 
- Consume Events and updating the point score according to the consumed events

## Alternatives not seriously considered

- Purely using Kafka Streams to process the events
    - Although this way would probably work and would seamless integrate into kafka
      it is not considered as a valid approach, since we would break previously defined 
      constraints. 

## How is this decision evaluated?

- Discussion in Team
- In the first sprint it is planned to develop a proof-of-concept of a custom event store using Kafka

## Resolution Details

- We decide to use event sourcing as our backbone of score calculation
- Technically it would be possible to use Kafka as our event store, but since we all don't have much experience using Kafka and don't have the time tou gather experience, we try to stick to the custom event store and use kafka as a simple message queue 
    - This way we also have more control
- tbd.

## Reasons for the resolution

- Using event sourcing we are more error-prone and can relatively easy adapt to changes
- In addition the point calculation is transparent and can be reproduced at any point of time
- We are more likely match the "Log" aspect of "Game Log"