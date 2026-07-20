---
title: 태그
nav_order: 2
permalink: /tags/
---

# 태그

태그를 누르면 해당 태그가 걸린 게시글 목록으로 이동합니다.

{% assign posts = site.pages | where: "layout", "post" %}
{% assign all_tags = "" | split: "" %}
{% for p in posts %}{% for t in p.tags %}{% assign all_tags = all_tags | push: t %}{% endfor %}{% endfor %}
{% assign all_tags = all_tags | uniq | sort_natural %}

<div class="tag-cloud">
{% for t in all_tags %}{% assign tagged = posts | where_exp: "p", "p.tags contains t" %}<a class="tag-pill" href="#{{ t | slugify }}">#{{ t }}<span class="tag-count">{{ tagged | size }}</span></a>{% endfor %}
</div>

---

{% for t in all_tags %}
{% assign tagged = posts | where_exp: "p", "p.tags contains t" | sort: "date" | reverse %}
## #{{ t }}
{: #{{ t | slugify }} }

<ul class="tag-post-list">
{% for p in tagged %}
  <li><a href="{{ p.url | relative_url }}">{{ p.title }}</a><span class="tag-post-date">{{ p.date | date: "%Y-%m-%d" }} · {{ p.parent }}</span></li>
{% endfor %}
</ul>
{% endfor %}
