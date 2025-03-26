---
title: "People"
layout: gridlay
sitemap: false
permalink: /people/
---

## Principal Investigator

{% for member in site.data.pi %}

<div class="jumbotron">
<div class="row">
<div class="col-sm-4">
  <img src="/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-8 col-xs-12">
<h4>{{ member.name }}</h4>
<b>{{member.position}}</b> <br>
{% if member.email %}<a href="mailto:{{ member.email }}" target="_blank">{{ member.email }}</a> {% endif %} 

{% if member.website %}<a href="{{ member.website }}" target="_blank"><i class="fa fa-home fa-2x"></i></a> {% endif %} {% if member.scholar %} <a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-2x"></i></a> {% endif %} {% if member.cv %} <a href="{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-2x"></i></a> {% endif %} {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-2x"></i></a> {% endif %} {% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-2x"></i></a> {% endif %}

<ul style="overflow: hidden">
<li> {{ member.education[0] }} </li>
<li> {{ member.education[1] }} </li>
<li> {{ member.education[2] }} </li>
<li> {{ member.education[3] }} </li>
</ul>
</div>
</div>
</div>

{% endfor %}

## Group Members

<div class='jumbotron'>
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}

<div class="row">
{% endif %}

<div class="col-sm-2">
<img src="/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-4 col-xs-12">
  <h4>{{ member.name }}</h4>
  <b>{{member.position}}</b> <br>
  {% if member.email %}<a href="mailto:{{ member.email }}" target="_blank">{{ member.email }}</a> {% endif %} 
  
<div style="margin-bottom: 10px" markdown="0">
  {% if member.website %}
    <a href="{{ member.website }}" target="_blank"><i class="fa fa-home fa-2x"></i></a>
  {% endif %}
  {% if member.scholar %}
    <a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-2x"></i></a>
  {% endif %}
  {% if member.cv %}
    <a href="{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-2x"></i></a>
  {% endif %}
  {% if member.github %}
    <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-2x"></i></a>
  {% endif %}
  {% if member.researchgate %}
    <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-2x"></i></a>
  {% endif %}
  {% if member.linkedin %}
    <a href="{{ member.linkedin }}" target="_blank"><i class="fa fa-linkedin-square fa-2x"></i></a>
  {% endif %}
</div>

<ul class="edu-list" style="margin-top: 10px; padding-left: 20px;">
  {% for degree in member.education %}
    <li>{{ degree }}</li>
  {% endfor %}
</ul>

<br>

</div>
<!-- </div> -->

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}

</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}

</div>
{% endif %}
</div>


