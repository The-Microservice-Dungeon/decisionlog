---
type: decision
acronym: event-structure
title: Event Structure
decision_type: must
status: _3_agreed
responsible: psc;thu
deadline: 2021-11-10
priority: 2-medium
todo:
aspects:
    - eventing
history:
    v1:
        date: 2021-11-08
        comment: created draft
---

## Why is there need for such a decision?
Events are used in every service. For easy processing by all services and the players, a uniform basis should be created.

## Additional sources for better understanding the background
\-

## Viable Options
- Event scheme inspired by Rewe Digital. (FAE presentation form WS2019)
- [Cloud Event](https://github.com/cloudevents/spec/blob/v1.0.1/spec.md)
- [Cloud Event (Kafka)](https://github.com/cloudevents/spec/blob/v1.0.1/kafka-protocol-binding.md)
- [Cloud Event (JSON)](https://github.com/cloudevents/spec/blob/v1.0.1/json-format.md)


## Alternatives not seriously considered
\-

## How is this decision evaluated?
Complexity of implementation and benefits for the overall project.

## Resolution Details
All events that are published must follow the following scheme.

Header
```properties
eventId = "Generated UUID of the event"
transactionId = "TransactionID if available or UUID of the entity concerned"
version = "Consecutive number for the comparability of the actuality of the event"
timestamp = "timestamp as specified in time-format-decision"
type = "The type of event"
```

Payload
```json
{
    "id": "The UUID of the entity",
    "field": "A field of the entity"
}
```

**Example**:

Header
```properties
eventId = "5bc9f935-32f1-4d7b-a90c-ff0e6e34125a"
transactionId = "0cfc04f1-6df5-42c6-a19a-146128b8a3b4"
version = 42
timestamp = "2020-01-10T12:00:00Z"
type = "event-example-uploaded"
```

Payload
```json
{
    "id": "0cfc04f1-6df5-42c6-a19a-146128b8a3b4",
    "field": "This is a field and it contains a string"
}
```

## Reasons for the resolution
The various solutions from Rewe Digital or Cloud Event are already close. Cloud Event, especially the extended specifics for Kafka or Json require a lot of information that is not needed for the Microservice Dungeon system landscape. Therefore, in terms of the data to be transmitted, the Rewe-Digital schema was followed.

However, the schema was adapted to the project. All metadata was moved to the event header. This makes it easy for the player services to search all events for their own `TransactionsId`s later on.

