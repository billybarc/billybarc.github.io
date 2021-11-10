---
layout: default
title: Research
---
<div class="container" id="research">
<h3>Working Papers</h3>
<ul>
{% assign wp_sorted = site.data.wp | sort: 'date' | reverse %}
{%- for paper in wp_sorted %}
  <li><b>
  {%- if paper.filename != null -%}
    <a target="_blank" href="/assets/{{ paper.filename }}">{{ paper.title }}</a>
  {%- else if paper.href != null -%}
    <a target="_blank" href="{{ paper.href }}">{{ paper.title }}</a>
  {%- else -%}
    {{ paper.title }}
  {%- endif -%}
  </b>, with
  {%- if paper.authors.size==1 -%}
    {{ paper.authors.first }}
  {%- else -%}
    {%- for author in paper.authors -%}
      {%- if author == paper.authors.last -%}
        and {{ author }}
      {%- else -%}
        {{ author | prepend: " " | append: ", "}}
      {%- endif -%}
    {%- endfor -%}
  {%- endif -%}
  .</li>
{%- endfor %}
</ul>

<h3>Works in Progress</h3>
<ul>
{%- for paper in site.data.wip %}
  <li><b>
  {%- if paper.filename != null -%}
    <a href="/assets/{{ paper.filename }}">{{ paper.title }}</a>
  {%- else -%}
    {{ paper.title }}
  {%- endif -%}
  </b>, with
  {%- if paper.authors.size==1 -%}
    {{ paper.authors.first }}
  {%- else -%}
    {%- for author in paper.authors -%}
      {%- if author == paper.authors.last -%}
        and {{ author }}
      {%- else -%}
        {{ author | prepend: " " | append: ", "}}
      {%- endif -%}
    {%- endfor -%}
  {%- endif -%}
  .</li>
{%- endfor %}
</ul>

<h3>Research Assistance</h3>
<ul>
{%- for paper in site.data.ra %}
  <li>{{ paper.citation }}</li>
{%- endfor %}
</ul>
</div>
