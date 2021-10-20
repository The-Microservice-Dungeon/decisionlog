---
layout: default
---

{% include /functions/print-decision-header-and-text.html myInfix="Team" %}

{% assign filtered_decisions = site.decisions | where: "decision_type", "team" %}
{% include /functions/print-decision-filtering.html myFilterType="type" myFilterInstance="T" %}

<p>A <b>Team</b> decision can be taken without consulting anyone outside the team.</p>

{% include /functions/print-sorted-decision-table.html mydecision_list=filtered_decisions %}

