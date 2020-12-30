---
layout: default
title: Research
---
<div class="container" id="research">
<h3>Working Papers</h3>
<ul>
{% for paper in site.data.wp %}
<li><b>{% if paper.filename != null %}<a href="/assets/{{ paper.filename }}">{{ paper.title }}</a>{% else %}{{ paper.title }}{% endif %}</b>, with {% if paper.authors.size==1 %}{{paper.authors.first}}{% else %} {% for author in paper.authors %}{% if author == paper.authors.last %}and {{author}}{% else %}{{ author }}, {% endif %}{% endfor %}{% endif %}.</li>
{% endfor %}
</ul>

<!-- <h3>Works in Progress</h3>
<ul>
{% for paper in site.data.wip %}
<li><b>{{ paper.title }}</b>, with {% if paper.authors.size==1 %}{{paper.authors.first}}{% else %} {% for author in paper.authors %}{% if author == paper.authors.last %}and {{author}}{% else %}{{ author }}, {% endif %}{% endfor %}{% endif %}.</li>
{% endfor %}
</ul> -->

<h3>Research Assistance</h3>
<ul>
{% for paper in site.data.ra %}
<li>{{ paper.citation }}</li>
{% endfor %}
</ul>
</div>
