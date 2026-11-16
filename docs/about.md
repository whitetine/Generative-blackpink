---
title: 關於本站
layout: default
type: index
permalink: /about/
---

<p class="eyebrow">About</p>

# 關於本站

BLACKPINK ARCHIVE 是一個繁體中文的入門網站，寫給第一次認識 BLACKPINK 的人。你可以從四位成員、團體作品和發行年表開始，再順著連結到官方頁面聽歌、看 MV。

<p class="notice">本網站為非官方粉絲作品，與 BLACKPINK 及其相關公司無隸屬關係。</p>

## 資料來源

站內的日期與藝名以下列官方頁面為準。若與其他資料不同，以官方頁面為主。

| 來源 ID | 官方來源 | 用在哪裡 |
| --- | --- | --- |
| `yg-profile` | [YG 成員資料](https://ygfamily.com/en/artists/blackpink/profile) | 四位成員的藝名與生日 |
| `yg-square-one` | [YG《SQUARE ONE》](https://ygfamily.com/en/artists/blackpink/discography/228) | 出道作品與發行日 |
| `yg-discography` | [YG 作品總表](https://ygfamily.com/en/artists/blackpink/discography) | 作品類別與發行順序 |
| `yg-the-album` | [YG《THE ALBUM》](https://ygfamily.com/en/artists/blackpink/discography/249) | 專輯資料與曲目 |
| `yg-born-pink` | [YG《BORN PINK》](https://ygfamily.com/en/artists/blackpink/discography/255) | 專輯資料與曲目 |
| `yg-deadline` | [YG《DEADLINE》](https://ygfamily.com/en/artists/blackpink/discography/1651) | 迷你專輯資料與曲目 |
| `bp-youtube` | [BLACKPINK 官方 YouTube](https://www.youtube.com/@BLACKPINK) | 官方影片 |

## 圖片與素材

站內的光束、漸層與作品卡都是原創的 CSS 圖形。專輯封面、官方宣傳照與授權不明的圖片不會放上本站。

成員照片只使用允許公開再利用的圖片，並在照片旁與下表註明署名：

<ul class="credit-list">
{% for c in site.data.credits %}
  <li><a href="{{ c.used_on | relative_url }}">{{ c.subject }}</a>：{{ c.author }}，<a href="{{ c.license_url }}">{{ c.license }}</a>，<a href="{{ c.source_url }}">via Wikimedia Commons</a></li>
{% endfor %}
</ul>

MV 一律連到官方 YouTube，不在站內嵌入或自動播放。

## 回報錯誤

如果發現日期、藝名或連結有誤，歡迎到本站的 GitHub 儲存庫開 issue。
