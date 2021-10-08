---
layout: default
---

# Documentation

This page contains some rudimentary documentation for the decision process used in FAE for
the EVATool prototype.


## Decision Types

These are the decision types used in the architectural decision process.

| Symbol | Type | Explanation |
|-----|-----|-----|
| <img src="{{ site.url }}{{ '/assets/error-4-24.png' | relative_url }}" alt="Error"> | Error | There are __errors__ in the decision description; please fix immediately. |
| <img src="{{ site.url }}{{ '/assets/clipboard-4-24.png' | relative_url }}" alt="Todos"> | Todo | There are __todos__ in the decision; must be fixed before closing. |
| <img class=_0_neutral src="{{ site.url }}{{ '/assets/letter-m-16.png' | relative_url }}" alt="Must"> | Must | A decision (principle, solution, technology etc.) that is binding for **all** teams. Icon color indicates decision status (see tables below).  | 
| <img class=_0_neutral src="{{ site.url }}{{ '/assets/letter-s-16.png' | relative_url }}" alt="Must"> | Should | A decision that is a **recommendation** for all teams, e.g. a technology that seemingly works well; teams can still deviate if they have good reasons to do so. Deviations must be reasoned by a team decision (see below).  Icon color indicates decision status (see tables below).   | 
| <img class=_0_neutral src="{{ site.url }}{{ '/assets/letter-t-16.png' | relative_url }}" alt="Team"> | Team | Team decision; can be taken without consulting anyone outside the team.  Icon color indicates decision status (see tables below). | 



## Possible Status 

All decisions can go through the following status (explained for "Must", but "Should" and "Team" has the same status names and color codes).

| Symbol | Keyword in Decision Log | Status | Explanation |
|-----|-----|-----|-----|
| <img class=_1_open src="{{ site.url }}{{ '/assets/letter-m-16.png' | relative_url }}" alt="open"> | _1_open | Open | An open decision has been created, but no resolution is available yet | 
| <img class=_2_draft src="{{ site.url }}{{ '/assets/letter-m-16.png' | relative_url }}" alt="draft"> | _2_draft | Draft | A resolution is available and documented, but there has not yet been a discussion about it. | 
| <img class=_3_agreed src="{{ site.url }}{{ '/assets/letter-m-16.png' | relative_url }}" alt="draft"> | _3_agreed | Agreed | The resolution has been discussed and agreed upon in the group where the decision belongs. | 
