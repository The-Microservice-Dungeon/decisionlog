---
type: decision
acronym: gameloop_changes
title: Changes of the gameloop and its phases for the commands
decision_type: must
service: game
status: _3_agreed
responsible: fgr;mba
deadline: 
priority: 2-medium
aspects: 
    - api
todo:
history:
    v1:
        date: 2021-12-23
        comment: created initially
---

## Why is there need for such a decision?

During the development of the gameloop it turned out, that there are more phases needed as given in the original gameloop. Espacially for commands with item-usage. Also Scouting is no longer an own command type, but happens passive after the movement.

## Additional sources for better understanding the background

n./a.

## Viable Options

Commands with items are sent togehter with commands that  have same cause (e.g. fighting), but dont use items.

## Alternatives not seriously considered

Other services get all their commands at the same end must handle them for themself.

## How is this decision evaluated?

In the Sprint planning with the Team and supervisor.

## Resolution Details

Items are handled seperantly, to make it easier forthe other services. <br>
The original gameloop was changed from 1. Blocking -> 2. Trading -> 3. Moving -> 4. Fighting -> 5. Mining -> 6. Scouting to <br>
1. Blocking -> 2. Trading -> 3. Moving (with an item) -> 4.Moving (without an item) -> 5. Repairing -> 6. Battleing (with an item) -> 7. Battleing(without an item) -> 8. Mining -> 9. Regenerating
