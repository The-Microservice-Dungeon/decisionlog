---
layout: default
---

{% include /functions/print-decision-header-and-text.html myInfix="Must" %}

{% assign filtered_decisions = site.decisions | where: "decision_type", "must" %}
{% include /functions/print-decision-filtering.html myFilterType="type" myFilterInstance="M" %}

<p>A <b>Must</b> decision (principle, solution, technology etc.) is binding for <i>all</i> teams.</p>

{% include /functions/print-sorted-decision-table.html mydecision_list=filtered_decisions %}

