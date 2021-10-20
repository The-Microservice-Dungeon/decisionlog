---
layout: default
---

{% include /functions/print-decision-header-and-text.html  %}
{% assign filtered_decisions = site.decisions | where: "decision_type", "should" %}
{% include /functions/print-decision-filtering.html myFilterType="type" myFilterInstance="S" %}

<p>A <b>Should</b> decision is a <i>recommendation</i> for all teams, e.g. a technology that seemingly works well; 
teams can still deviate if they have good reasons to do so. Deviations must be reasoned by a team decision.</p>

{% include /functions/print-sorted-decision-table.html mydecision_list=filtered_decisions %}

