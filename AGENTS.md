# BLACKPINK Archive｜網站設計與維護規格

> 一個繁體中文的非官方 BLACKPINK 粉絲網站。讓第一次認識 BLACKPINK 的人，能從四位成員、團體作品和發行年表入門，再順著連結找到官方音樂與影片。
>
> **目前進度**：設計階段。這份 `AGENTS.md` 是給開發者與 AI 閱讀的專案規格，不是公開首頁。本階段不建立網站、不推送 GitHub、不部署。

## 1. 兩篇 Gist 怎麼用在這個專案

| 參考 | 採用的做法 | 在這個網站的用法 |
| --- | --- | --- |
| Karpathy 的 LLM Wiki | 原始資料、整理頁面與維護規則分層，並維護索引和更新紀錄 | `sources/` 放來源筆記，`docs/` 放網站，`AGENTS.md` 定義編輯規則，`CHANGELOG.md` 記錄更新 |
| farzaa 的 Personal Knowledge Wiki | 以主題整合新資料，使用結構化欄位、來源 ID 和頁面連結 | 每位成員與每張重點作品有自己的 Markdown 頁。新增資料時更新既有頁面，順手檢查相關的索引與年表 |

這是公開的入門網站，不是私人知識庫。第一版不需要自動匯入、向量搜尋、資料庫或即時新聞。站內連結也不使用 Obsidian 專用的 `[[wikilinks]]`，改用 GitHub Pages 可以正常處理的連結。

## 2. 首頁與導覽

首頁構想是一本黑粉配色的數位音樂誌。首屏只放大字標題、短介紹和一個主要按鈕。往下先看到四位成員，再看到作品入口。即使沒有團體照，也能用黑粉光束與排版完成首屏。

**主標** · BLACKPINK ARCHIVE  
**副標** · 從四位成員與代表作品，認識 BLACKPINK。  
**首頁文案草稿** · 2016 年，JISOO、JENNIE、ROSÉ 和 LISA 帶著首張單曲專輯《SQUARE ONE》出道。從這裡認識四位成員，沿著作品年表回顧她們的團體發行。  
**主要按鈕** · 認識四位成員  
**次要連結** · 瀏覽團體作品

| 公開頁面 | 讀者在這裡能做什麼 | 第一版內容 |
| --- | --- | --- |
| 首頁 | 快速認識團體，選擇從人物或音樂開始 | 出道簡介、四位成員入口、三張精選作品卡 |
| 成員 | 從索引進入每位成員的介紹頁 | JISOO、JENNIE、ROSÉ、LISA 各一頁。放藝名、生日、一段可查證的簡介與官方連結 |
| 音樂作品 | 認識發行作品，轉到官方頁看曲目或 MV | 《SQUARE ONE》、《THE ALBUM》、《BORN PINK》各一頁。《DEADLINE》列入年表並連到官方資料 |
| 年表 | 依年月回顧團體發行，點回作品詳頁 | 2016 年《SQUARE ONE》、2020 年《THE ALBUM》、2022 年《BORN PINK》、2026 年《DEADLINE》。清楚標示為「精選發行」，不是完整紀錄 |
| 關於 | 確認網站定位，找到資料與圖片來源 | 非官方說明、引用來源、圖片授權與署名 |

每篇詳頁應有可回到對應索引的入口。年表事件若已有站內作品頁，就優先連到該頁。尚未建立頁面的事件直接連官方來源，避免死連結。成員頁上的個人作品與團體作品分開標示。

## 3. 視覺與互動

| 項目 | 設計決定 |
| --- | --- |
| 配色 | 背景 `#0D0A0D`、卡片 `#1C161D`、重點粉 `#FF78AD`、正文 `#F8F2F7`。粉色按鈕搭深色字 |
| 版面 | 深底、細粉框、粗體英文標題，搭配寬鬆的繁中內文。作品卡用大字年份與原創漸層，不依賴專輯封面 |
| 響應式 | 成員卡大螢幕四欄、中等寬度兩欄、窄手機一欄。手機導覽可換行，不靠滑鼠懸停才顯示資訊 |
| 動效 | 只用短暫的亮框或淡入，遵守 `prefers-reduced-motion`。不自動播歌或影片 |
| 可讀性 | 使用繁中語系 `zh-Hant`，連結文字說清楚去向，鍵盤焦點清楚可見。有意義的圖片加替代文字 |

## 4. 未來的 GitHub 專案結構

第一版用 **GitHub Pages + Jekyll + CSS**。Markdown 直接作為公開內容的來源，Jekyll 將內容套入同一版型。不必另做一套 HTML 資料，也不用維護後端。

| 路徑 | 用途 |
| --- | --- |
| `AGENTS.md` | 本規格。放在儲存庫根目錄，供 AI 和協作者使用 |
| `README.md` | 之後建立。放專案簡介、用法與上線網址 |
| `sources/index.md` | 來源索引。記錄來源 ID、網址、查核日期與採用欄位 |
| `sources/notes/` | 來源摘記或歷次查核筆記。不覆寫前次紀錄 |
| `CHANGELOG.md` | 簡記修改日期、來源 ID、影響頁面與原因 |
| `docs/_config.yml` | Jekyll 設定 |
| `docs/_layouts/default.html` | 共用導覽、主內容與頁尾 |
| `docs/index.md` | 公開首頁 |
| `docs/members/index.md`、`docs/members/jisoo.md` 等 | 成員索引與四位成員頁 |
| `docs/discography/index.md`、`docs/discography/born-pink.md` 等 | 作品索引與精選作品頁 |
| `docs/timeline.md`、`docs/about.md` | 年表與網站說明 |
| `docs/assets/css/style.css`、`docs/assets/img/` | 樣式與可公開素材 |

`docs/` 是網站發布目錄。不把編輯筆記放進 `docs/`。若 GitHub 儲存庫設為公開，即使資料不在 `docs/` 也能在儲存庫看到，所以來源筆記同樣不可包含私密資料或未獲准公開的素材。

## 5. Markdown 頁面的格式

每頁使用 YAML front matter。固定小寫英文檔名與 slug，以連字號分隔，如 `square-one`。藝名維持官方拼寫，如 ROSÉ。範例是未來的 `docs/discography/born-pink.md`。

```markdown
---
title: "BORN PINK"
layout: default
type: release
slug: born-pink
permalink: /discography/born-pink/
release_date: "2022-09-16"
source_ids: [yg-born-pink]
---

# BORN PINK

《BORN PINK》是 BLACKPINK 的第二張正規專輯，於 2022 年 9 月 16 日發行，收錄主打歌〈Shut Down〉。

- [查看 YG 官方作品資料](https://ygfamily.com/en/artists/blackpink/discography/255)
- [回到作品列表]({{ '/discography/' | relative_url }})
```

成員頁用 `type: member`，可加 `birth_date: "YYYY-MM-DD"`。各頁只存需要公開顯示或追溯的欄位。日期與身分資訊應能在 `source_ids` 對應到來源，頁尾也要有讀者能直接點開的連結。站內導覽、CSS 與圖片路徑用 Jekyll 的 `relative_url`，避免網站放在 `/<repo>/` 下時指到網域根目錄。

## 6. 來源與更新方式

| 來源 ID | 官方來源 | 支援內容 |
| --- | --- | --- |
| `yg-profile` | [YG 成員資料](https://ygfamily.com/en/artists/blackpink/profile) | 四位成員的藝名與生日 |
| `yg-square-one` | [YG《SQUARE ONE》](https://ygfamily.com/en/artists/blackpink/discography/228) | 韓國出道作品與發行日 2016-08-08 |
| `yg-discography` | [YG 作品總表](https://ygfamily.com/en/artists/blackpink/discography) | 作品類別與發行順序 |
| `yg-the-album` | [YG《THE ALBUM》](https://ygfamily.com/en/artists/blackpink/discography/249) | 專輯資料與曲目 |
| `yg-born-pink` | [YG《BORN PINK》](https://ygfamily.com/en/artists/blackpink/discography/255) | 專輯資料與曲目 |
| `yg-deadline` | [YG《DEADLINE》](https://ygfamily.com/en/artists/blackpink/discography/1651) | 迷你專輯資料與曲目 |
| `bp-youtube` | [BLACKPINK 官方 YouTube](https://www.youtube.com/@BLACKPINK) | 官方影片連結 |

1. **記下證據**。新增作品或事件時，在來源索引登記網址、查核日期及採用欄位。保留原始資料與編輯摘要的區別。
2. **更新相關頁**。優先更新既有條目，再同步受影響的首頁卡片、索引或年表。相同內容不用在各頁重寫整段。
3. **處理衝突**。同一個日期若有不同說法，先確認事件是否相同。出道日採 YG 出道作品頁的 2016-08-08，成員資料頁只用來核對藝名和生日。仍有疑問就先留在筆記，不當成事實發布。
4. **檢查再發布**。確認日期、藝名、作品分類、引用、站內連結與素材許可，並在 `CHANGELOG.md` 簡記變更。

**素材預設**：先用原創圖形和文字設計。團照、專輯封面或官網圖片只有在確認可公開使用後才加入，並記錄授權與署名。第一版的 MV 使用官方外連。頁尾註明「本網站為非官方粉絲作品，與 BLACKPINK 及其相關公司無隸屬關係。」

## 7. 第一版實作與部署

- [ ] 建立 `docs/` 的共用版型、首頁與手機版導覽。
- [ ] 加上四位成員頁、三張精選作品詳頁、精選年表與關於頁。
- [ ] 確認在手機與桌機可閱讀，鍵盤可以操作所有連結，並檢查正式網址下的 CSS、圖片和站內連結。
- [ ] 網站完成後再將程式推到 GitHub。到儲存庫的 **Settings → Pages** 選擇 **Deploy from a branch**，指定 `main` 與 `/docs`，儲存並等待部署。
- [ ] 打開 Pages 顯示的公開網址，逐項核對首頁、內頁和樣式。一般專案站網址形如 `https://<帳號>.github.io/<儲存庫>/`。確認後再把網址補到 `README.md`。

## 設計參考

- [farzaa · Personal Knowledge Wiki](https://gist.github.com/farzaa/c35ac0cfbeb957788650e36aabea836d)
- [Andrej Karpathy · LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- [GitHub Docs · 設定 GitHub Pages 的發布來源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
