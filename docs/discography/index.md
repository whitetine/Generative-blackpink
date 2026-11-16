---
title: 音樂作品
layout: default
type: index
permalink: /discography/
---

{% assign releases = site.pages | where: "type", "release" | sort: "release_date" %}

<p class="eyebrow">Discography</p>

# 團體作品

這裡收錄 BLACKPINK 的精選團體發行，依發行時間排列。每張作品頁附有 YG 官方資料連結，可以在那裡查看完整曲目。

<ul class="release-grid">
  {% for r in releases %}
  <li>
    <a class="release-card release-{{ r.slug }}" href="{{ r.url | relative_url }}">
      <span class="release-year" aria-hidden="true">{{ r.release_date | date: "%Y" }}</span>
      <span class="release-kind">{{ r.release_kind }}</span>
      <span class="release-title">{{ r.title }}</span>
      <span class="release-meta">{{ r.release_date | date: "%Y.%m.%d" }} 發行</span>
    </a>
  </li>
  {% endfor %}
</ul>

## 尚未建立作品頁

- 《DEADLINE》，第三張迷你專輯，2026 年 2 月 27 日發行。[查看 YG 官方作品資料](https://ygfamily.com/en/artists/blackpink/discography/1651)

完整的發行列表請看 [YG 官方作品總表](https://ygfamily.com/en/artists/blackpink/discography)。
