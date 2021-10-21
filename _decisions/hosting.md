---
type: decision
acronym: hosting
title: >
    Choice of Hosting provider
decision_type: must
belongs_to: devOps
status: _2_draft
responsible: psc
deadline: 2021-10-22
priority: 2-medium
history:
    v1:
        date: 2021-10-08
        comment: created initially
    v2:
        date: 2021-10-21
        comment: adapted justification
---

## Why is there need for such a decision?

The application will provide functionality that should be publicly accessible.
It has to be run by some kind of machine.
These are supposed to be provided somehow.
There are many ways in which this can be done.

## Additional sources for better understanding the background
* [Hosting Spring Boot Standalone and Clustered Java Applications with Jelastic Cloud](https://jelastic.com/blog/hosting-spring-boot-java-applications/)
* [Tutorial: Build a Java Spring Boot web app with Azure App Service on Linux and Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/app-service/tutorial-java-spring-cosmosdb)

## Viable Options

* To rent a server
    * Linux V-Server by [Strato](https://www.strato.de/server/linux-vserver/)
    

* To use some cloud platforms, and the services they offer 
    * [Azure App Service](https://docs.microsoft.com/en-us/azure/app-service/overview-hosting-plans)

    
* To use server provided by [ADV-Lab](https://www.gm.th-koeln.de/advlabor/aufgaben.shtml)
    * Linux Server


## Alternatives not seriously considered

* To rent a sever provided by big players like Google, Amazon, Microsoft

## How is this decision evaluated?

* Simplicity of setup
* Price
* Backup options
 
## Resolution Details
It was decided to use the TH internal solution.
An Ubuntu server will be provided.
The development team should be able to connect and to control the server using SSH.

## Reasons for the resolution

Availability and easy access are the main criteria. Availability is also indirectly dependent on the cost factor.
High costs entail a procurement process.
The VM provided by the ADV lab is free of charge, comes with a two-day three-generation backup and is provided with the latest version of Ubunutu.


The setup of Strato's servers in comparison to TH should be very similar. (not checked in practice)\
As can be seen from the sources, setting up an application on a cloud platform has its own complexity. (not checked in practice)

Backups come with extra price by rented solutions.
