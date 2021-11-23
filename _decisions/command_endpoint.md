---
type: decision
acronym: command_endpoint 
title: endpoint_to_recieve_commands
decision_type: must
service: game;trading;robot
status: _3_agreed
responsible: fgr;mba
deadline: 2021-10-22
priority: 2-medium
aspects: 
    - api
todo:
history:
    v1:
        date: 2021-11-23
        comment: created initially
---

## Why is there need for such a decision?

The game api must have endpoints, where they can deliever the commands they recieved from the players to the correct services.

## Additional sources for better understanding the background

n/a

## Viable Options

Every service that wants to recieve commands must provide an endpoint named post/commands.
This endpoints gets an stack of commands, that contain the transactionuuid, playerid,robotid and an commandobject:

[
  { 
  "transactionId" : uuid 

  "playerid" :uuid 
  
  "robotid": uuid, 
  
  "commandobject"
  
           { "commandtype": string

           "robotid": uuid

           "planetid": uuid

           "itemname": String}
   }   
   { 
  "transactionId" : uuid 

  "playerid" :uuid 
  
  "robotid": uuid, 
  
  "commandobject"
  
           { "commandtype": string

           "robotid": uuid

           "planetid": uuid

           "itemname": String}
   } 
   ...
]

Planetid an itemname can be null, if they are not needed in the command
If an error oncours the service can invoke an error with the transactionuuid.

## Reasons for the resolution

Only when this decision is fullfilled the commands from the players can reach there intended destiny.
