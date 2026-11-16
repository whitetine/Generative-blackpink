# BLACKPINK ARCHIVE

一個繁體中文的非官方 BLACKPINK 入門網站。從四位成員、團體作品和精選年表認識 BLACKPINK，再順著連結到官方頁面聽歌、看 MV。

- 上線網址：（部署後補上，形如 `https://<帳號>.github.io/<儲存庫>/`）
- 網站規格與編輯規則：[`AGENTS.md`](AGENTS.md)
- 來源索引：[`sources/index.md`](sources/index.md)
- 更新紀錄：[`CHANGELOG.md`](CHANGELOG.md)

## 結構

```
AGENTS.md            規格（給協作者與 AI）
CHANGELOG.md         更新紀錄
sources/             來源索引與查核筆記（不會發布）
docs/                網站本體（GitHub Pages 從這裡發布）
  _config.yml
  _layouts/default.html
  index.md           首頁
  members/           成員索引與四位成員頁
  discography/       作品索引與三張精選作品頁
  timeline.md        精選年表
  about.md           關於本站
  assets/css/style.css
```

## 部署到 GitHub Pages

1. 在 GitHub 建立新儲存庫，例如 `blackpink-archive`。
2. 打開 `docs/_config.yml`，把 `baseurl` 改成 `"/<儲存庫名稱>"`，例如 `"/blackpink-archive"`。
3. 推送程式：
   ```bash
   git init
   git add .
   git commit -m "First version of BLACKPINK Archive"
   git branch -M main
   git remote add origin https://github.com/<帳號>/<儲存庫>.git
   git push -u origin main
   ```
4. 到儲存庫的 **Settings → Pages**，Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/docs`，按 Save。
5. 等一兩分鐘，打開 Pages 顯示的網址，檢查首頁、內頁與樣式，再把網址補到本檔上方。

## 本機預覽（選用）

需要 Ruby 與 Bundler：

```bash
cd docs
bundle install
bundle exec jekyll serve --baseurl ""
```

打開 <http://localhost:4000>。

## 聲明

本網站為非官方粉絲作品，與 BLACKPINK 及其相關公司無隸屬關係。
