---
type: decision
acronym: eventing-solution
title: Apache Kafka is used as Eventing Solution
decision_type: must
aspects: 
    - eventing
    - devOps
    - techStack
status: _3_agreed
responsible: sbe;psc    
deadline: 2021-10-22
priority: 2-medium
todos:
history:
    v1:
        date: 2021-10-08
        comment: created initially  
    v2: 
        date: 2021-11-04
        comment: finalized
---

## Resolution Details

See title.

## Reasons for the resolution

Kafka is market leader, so this is an appropriate decision for a teaching project (that is supposed to be realistic.
And we have already experience with it. 

## Why is there need for such a decision?

A multitude of possible eventing solutions exist on the market. While most solutions have very similar
functionality at their core, the different services of course need to use the same solution.

## Additional sources for better understanding the background

* [Sebastian Gauder - Eventing Presentation](https://www.doag.org/formes/pubfiles/9948769/2018-NN-Sebastian_Gauder-Eventing_mit_Apache_Kafka__Haben_ist_besser_als_Brauchen-Praesentation.pdf)
* [Apache Kafka](https://kafka.apache.org/)
* [RabbitMQ](https://www.rabbitmq.com/)
* [Spring Events](https://www.baeldung.com/spring-events)

## Viable Options

* Apache Kafka
    * Market Leader
    * Eventing solution with the highest adoption

* RabbitMQ
    * Lighter Version of Kafka
    * Functional very similar but lacking the in-depth analysis and monitoring tools

* Spring Eventing
    * Rather unknown eventing solution
    * Might be useful to avoid using additional software besides Spring, which we already use 

## Alternatives not seriously considered

* Amazon Kinesis?
* IBM Event Streams / Cloud Pak for integration
* Google Cloud Dataflow

None of these are open-source solutions which would limit us in our own open-source project.
Additionally, all of these are specialized for use in their respective cloud environments or need a paid license.

## How is this decision evaluated?

n/a
 
