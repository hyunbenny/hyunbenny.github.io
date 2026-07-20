---
layout: home
title: Home
nav_order: 1
permalink: /
---

# hyunbenny's blog

공부한 내용을 끄적거리는 낙서장입니다. 왼쪽 카테고리에서 주제별로 글을 찾아보거나, [태그]({{ '/tags/' | relative_url }})로 모아볼 수 있습니다.

## 최근 글

{% assign posts = site.pages | where: "layout", "post" | sort: "date" | reverse %}
<ul class="recent-list">
{% for p in posts limit: 10 %}
  <li>
    <span class="recent-date">{{ p.date | date: "%Y-%m-%d" }}</span>
    <a href="{{ p.url | relative_url }}">{{ p.title }}</a>
    {% for tag in p.tags %}<a class="tag-pill" href="{{ '/tags/' | relative_url }}#{{ tag | slugify }}">{{ tag }}</a>{% endfor %}
  </li>
{% endfor %}
</ul>
