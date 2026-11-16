---
title: 成員
layout: default
type: index
permalink: /members/
---

{% assign members = site.pages | where: "type", "member" | sort: "order" %}

<p class="eyebrow">Members</p>

# 四位成員

BLACKPINK 由 JISOO、JENNIE、ROSÉ、LISA 四人組成，2016 年由 YG Entertainment 推出。點選成員，看她的生日、簡介與官方連結。

<ul class="member-grid">
  {% for m in members %}
  <li>
    <a class="member-card" href="{{ m.url | relative_url }}">
      <span class="member-initial" aria-hidden="true">{{ m.title | slice: 0 }}</span>
      <span class="member-name">{{ m.title }}</span>
      <span class="member-meta">生日 {{ m.birth_date | date: "%Y.%m.%d" }}</span>
    </a>
  </li>
  {% endfor %}
</ul>

<p class="source-note">藝名與生日來源：<a href="https://ygfamily.com/en/artists/blackpink/profile">YG 官方成員資料</a></p>
