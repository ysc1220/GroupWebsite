---
title: "News"
layout: gridlay
sitemap: false
permalink: /news/
---

<p style="font-size:300%; text-align:center;"> News </p>

{% for article in site.data.news %}
<div class="jumbotron">
<b>{{ article.date }}</b>

{{ article.headline }}
</div>
{% endfor %}

