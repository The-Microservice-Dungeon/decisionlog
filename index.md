---
layout: default
---
{% include /functions/print-decision-header-and-text.html  %}
{% include /functions/print-decision-filtering.html myFilterType = "all" %}
<p/>
{% include /functions/print-sorted-decision-table.html mydecision_list = site.decisions %}
