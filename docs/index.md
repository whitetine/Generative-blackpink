---
title: BLACKPINK ARCHIVE
layout: default
full_width: true
permalink: /
---

{% assign members = site.pages | where: "type", "member" | sort: "order" %}
{% assign releases = site.pages | where: "type", "release" | sort: "release_date" %}

<section class="hero" aria-labelledby="hero-title">
  <div class="hero-beams" aria-hidden="true"></div>
  <div class="wrap hero-inner">
    <p class="eyebrow">非官方入門誌 · Since 2016</p>
    <h1 id="hero-title">BLACKPINK<br><span>ARCHIVE</span></h1>
    <p class="hero-lead">從四位成員與代表作品，認識 BLACKPINK。</p>
    <p class="hero-text">2016 年，JISOO、JENNIE、ROSÉ 和 LISA 帶著首張單曲專輯《SQUARE ONE》出道。從這裡認識四位成員，沿著作品年表回顧她們的團體發行。</p>
    <div class="hero-actions">
      <a class="button" href="{{ '/members/' | relative_url }}">認識四位成員</a>
      <a class="text-link" href="{{ '/discography/' | relative_url }}">瀏覽團體作品 →</a>
    </div>
  </div>
</section>

<section class="wrap section" aria-labelledby="members-title">
  <div class="section-head">
    <p class="eyebrow">01 · Members</p>
    <h2 id="members-title">四位成員</h2>
  </div>
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
</section>

<section class="wrap section" aria-labelledby="releases-title">
  <div class="section-head">
    <p class="eyebrow">02 · Discography</p>
    <h2 id="releases-title">精選作品</h2>
  </div>
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
  <p class="section-more"><a class="text-link" href="{{ '/timeline/' | relative_url }}">看完整的精選年表 →</a></p>
</section>
