---
layout: page
title: Archive
permalink: /archive/
---

{%- assign issues = site.pages | where_exp: "p", "p.path contains 'archive/'" | sort: "path" | reverse -%}
{%- assign years = issues | group_by_exp: "p", "p.path | slice: 8, 4" -%}

{%- for year in years %}

## {{ year.name }}

<ul>
  {%- for issue in year.items %}
  <li><a href="{{ issue.url | relative_url }}">{{ issue.title | escape }}</a></li>
  {%- endfor %}
</ul>

{%- endfor %}
