---
layout: default
title: 我的数学笔记首页
---

# 学无止境

{% assign notes = site.pages | where: "is_note", true | sort: "sort_order" %}

{% if notes.size > 0 %}
<ul>
  {% for note in notes %}
    <li>
    <a href="{{ site.baseurl }}{{ note.url }}">
                {{ note.title }}
            </a>
    </li>
  {% endfor %}
</ul>
{% else %}
    <p>抱歉，目前还没有任何笔记。</p>
{% endif %}