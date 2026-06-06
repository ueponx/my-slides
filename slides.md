---
theme: seriph
title: Slidev + Vercel で「Markdownで書いて即公開」
info: |
  Markdown で書いて git push したら勝手に公開される、
  生成AIと相性抜群のスライド環境のつくり方。
class: text-center
transition: slide-left
mdc: true
---

# Markdownで書いて即公開する<br>スライド環境のつくり方

## Slidev + Vercel + 生成AI

<div class="pt-8 opacity-75">
@uepon ｜ 技術勉強会 LT ｜ 2026
</div>

<!--
発表メモ:
今日は「スライド作成を、ブログを書く労力まで下げる」話をします。
所要15分。ハンズオンの全手順は別途資料にあるので、ここでは流れと勘所だけ。
-->

---
layout: center
class: text-center
---

# スライド作成、地味につらくないですか？🥲

<v-clicks>

PowerPoint を立ち上げて、テンプレ選んで、フォント揃えて、配置いじって…

**で半日が溶ける**

毎週スライドを作る人にとって、これが生産性のボトルネック

</v-clicks>

<!--
共感フェーズ。会場に「あるある」と思ってもらう。
特に大学講義・勉強会で毎週作る人を想定。
-->

---

# 今日つくる環境

3つのうれしさを満たす仕組みを作ります。

<v-clicks>

- 📝 **Markdown だけ**でスライドが書ける
- 🤖 **生成AI との連携が超ラク**(テキスト1ファイルで完結)
- 🚀 **git push したら勝手に公開**される

</v-clicks>

<div v-click class="mt-8">

使う道具はたった2つ ——
**Slidev**(スライド本体)と **Vercel**(ホスティング)

</div>

<!--
ゴール提示。「明日のスライドが、編集→push の数分で公開URLまで届く」状態。
-->

---
layout: center
---

# 全体像 — できあがるワークフロー

```mermaid {scale: 0.85}
flowchart LR
    A[slides.md を編集] --> B[git push]
    B --> C[Vercel が自動build]
    C --> D[公開URL 完成]
    AI[生成AI に依頼] -.中身を作る.-> A
```

<div v-click class="mt-6 text-center text-xl">

あなたがやるのは <span class="text-teal-400 font-bold">「slides.md を編集して push」</span> だけ。<br>
それ以外は全部自動です。

</div>

<!--
このフロー図がこの発表の背骨。以降のステップは全部この図のどこかの話。
-->

---

# 事前準備

ハンズオン前に、これだけ揃っていればOK。

<div class="grid grid-cols-3 gap-4 mt-8">

<div v-click class="p-4 border rounded-lg">

### ① Node.js

```bash
$ node -v
v20.18.0
```

**18以上**が必要。<br>WSL でも Windows でもOK。

</div>

<div v-click class="p-4 border rounded-lg">

### ② GitHub

アカウントを持っていればOK。<br>なければ github.com で作成。

</div>

<div v-click class="p-4 border rounded-lg">

### ③ Vercel

これから作る。<br>**GitHubアカウントでログイン**できるので追加登録不要。

</div>

</div>

<!--
Node 18未満の人だけ nvm でアップデートしてもらう、と一言添える。
-->

---

# Step 1 — Slidev プロジェクト作成

作業ディレクトリに移動して、1コマンド。

```bash {all|2}
$ cd ~/projects
$ npm init slidev@latest
```

<div v-click>

対話形式で3つ聞かれるだけ。

| 質問 | 回答 |
|---|---|
| Project name | 任意(例: `slides-claude-code`) |
| Package manager | `npm` |
| Install and start it now | `Yes` |

</div>

<div v-click class="mt-4">

→ 依存インストールが走り、**ブラウザにデモスライドが自動で開けば成功** 🎉

</div>

<!--
「Welcome to Slidev」が出たらOK。矢印キーで進む、Fでフルスクリーン、を実演できると良い。
次に進む前に Ctrl+C でサーバーを止めておくと混乱しない。
-->

---

# Step 2 — 中身は `slides.md` 1ファイルだけ

これが Slidev 最大の特徴。**毎日触るのはこのファイルだけ。**

```markdown {all|1-4|6|8|10}
---
theme: seriph
title: Welcome to Slidev
---

# Welcome to Slidev

Presentation slides for developers

---
```

<v-clicks>

- 冒頭の `---` で囲んだ部分 = **Frontmatter**(全体設定)
- 本文中の `---` = **スライドの区切り**
- HTMLタグや独自セクションタグは不要(reveal.js との違い)

</v-clicks>

---
layout: center
class: text-center
---

# 編集 → 保存 → 即反映

<div class="text-2xl my-8">

`npm run dev` した状態で `slides.md` を保存すると…<br>
**その瞬間にブラウザがリロードされて反映**🥰

</div>

```bash
$ npm run dev
```

<div v-click class="opacity-75">

PowerPoint にはないリアルタイム反映の快感。<br>
ここが「ブログを書く感覚」の正体。

</div>

<!--
できればここでライブデモ。タイトルを書き換えて保存→即反映を見せる。
-->

---

# Step 3 — Git で管理を始める

ローカルで初期化して、最初のコミット。

```bash {all|1-3|5-7}
$ git init
$ git add .
$ git commit -m "Initial commit: Slidev プロジェクト作成"

$ git remote add origin https://github.com/<you>/slides-claude-code.git
$ git branch -M main
$ git push -u origin main
```

<div v-click class="mt-4 p-3 bg-amber-500 bg-opacity-10 rounded border-l-4 border-amber-500">

⚠️ **push でパスワードを聞かれたら**<br>
2021年以降パスワード認証は廃止 → **Personal Access Token** か `gh` CLI を使う

</div>

<!--
GitHub 側で New repository を作るときは README/.gitignore を追加しない(衝突回避)。
.gitignore は Slidev テンプレに同梱済み。
-->

---

# Step 4 — Vercel でデプロイ 🎉

一番楽しいパート。

<v-clicks>

1. vercel.com に **Continue with GitHub** でログイン
2. **Add New → Project** で `slides-claude-code` を **Import**
3. Build 設定を1点だけ確認 → **Deploy**

</v-clicks>

<div v-click class="mt-4 p-3 bg-amber-500 bg-opacity-10 rounded border-l-4 border-amber-500">

⚠️ **Output Directory が `dist` になっているか必ず確認**<br>
`build` や `public` だとデプロイ後に404。Slidev は `dist/` に吐く。

</div>

<div v-click class="mt-4">

1〜3分で `https://....vercel.app` が割り当てられ、**世界に公開** 👏

</div>

<!--
リポジトリが一覧に出ないときは GitHub App の権限を許可(Public でも明示許可が要る)。
-->

---
layout: center
---

# Step 5 — これ以降の更新フロー

<div class="text-xl mb-4">セットアップは一度きり。あとは超シンプル。</div>

```bash {all|2|4-5}
# slides.md を編集する
$ code slides.md

$ git add slides.md && git commit -m "Update: 内容を更新"
$ git push
```

<div v-click class="mt-6 text-center text-2xl text-teal-400 font-bold">

push した瞬間、Vercel が自動でビルド&デプロイ。<br>
あなたは何もしない。

</div>

<div v-click class="mt-4 text-center opacity-75">

※ 反映は即時ではない。push の2〜3分後にリロードを。

</div>

---
layout: section
---

# 応用 — 生成AIとの連携 🤖

ここからが本題。<br>中身が `slides.md` 1ファイルなので、AIへの渡し方が極限までシンプル。

---

# 生成AI連携 — 3つのパターン

<div class="grid grid-cols-1 gap-3 mt-4">

<div v-click class="p-3 border rounded-lg">

**① ゼロから生成**<br>
「テーマ / 対象 / 時間 / 枚数 / 出力形式= Slidev Markdown」を指定して投げる → コピペで完成

</div>

<div v-click class="p-3 border rounded-lg">

**② ブログ記事を変換**<br>
「この記事を Slidev用15分プレゼンに再構成して」→ 既存記事を勉強会用に転用 🤩<br>
<span class="opacity-60 text-sm">(まさにこのスライドがその実例)</span>

</div>

<div v-click class="p-3 border rounded-lg">

**③ Claude Code で半自動運用**<br>
リポジトリに `CLAUDE.md` を置き運用ルールを記述 →<br>
「MCPの概要スライドを5枚追加して」だけでルール準拠の更新

</div>

</div>

<!--
パターン2が一番刺さる。「テキスト1個渡せば終わる=AIへの説明コストほぼゼロ」を強調。
-->

---

# `CLAUDE.md` の例 — 運用ルールを置く

```markdown {all|4-6|8-12}
# このリポジトリのルール

## ファイル構成
- スライド本体は slides.md
- 画像は public/images/ 以下に配置

## スタイルルール
- テーマは seriph で固定
- タイトルスライドに @uepon と日付を入れる
- 1スライド 1トピックを原則とする
- コード例は言語を明示する
```

<div v-click class="mt-4">

→ レビューして問題なければ `git push` するだけ。

</div>

---

# 便利機能 — PDF / PPTX エクスポート

LMS への配布や「.pptx じゃないとダメ」な提出に対応。

```bash {all|2-3|6|9}
# 初回だけ: Chromium と依存ライブラリを入れる
$ npm install -D playwright-chromium
$ npx playwright install-deps chromium

# PDF 出力
$ npx slidev export          # → slides-export.pdf

# PowerPoint 出力
$ npx slidev export --format pptx
```

<div v-click class="mt-4 p-3 bg-amber-500 bg-opacity-10 rounded border-l-4 border-amber-500">

⚠️ PPTX は **完璧な再現ではない**。Vueコンポーネントやアニメは失われる。<br>
「テキストと構造を残す変換」と割り切るのがおすすめ。

</div>

<!--
install-deps を省くと libnspr4.so エラーで失敗する、と一言。
-->

---

# 詰まりやすいポイント

<div class="grid grid-cols-1 gap-2 mt-4 text-sm">

<div v-click>

**Q. 画像が表示されない**<br>
→ `public/images/` に置き、`![](/images/foo.png)`(先頭スラッシュ)で参照。相対パスはビルド後に壊れる。

</div>

<div v-click>

**Q. テーマを変えたい**<br>
→ Frontmatter の `theme:` を変更。`seriph` / `default` / `apple-basic` ほか、`npm i -D slidev-theme-名前` でコミュニティテーマも。

</div>

<div v-click>

**Q. プレゼンターモードを使いたい**<br>
→ URL 末尾に `/presenter`。発表者ノート付きの画面が別ウィンドウで開く。

</div>

</div>

---
layout: two-cols
---

# 使ってみての実感

::left::

### 想定以上に良かった 😊

<v-clicks>

- 着手の**心理的コストが激減**(ブログ感覚)
- **生成AIとの相性が圧倒的**
- Git 履歴で**去年との差分**が見える
- Vercel 自動デプロイの体験が良すぎる

</v-clicks>

::right::

### ちょっと気になる 🫠

<v-clicks>

- 凝ったアニメは **Vue知識が必要**
- 原則 **1リポジトリ = 1スライド**
- PPTX エクスポートは万能でない

</v-clicks>

<div v-click class="mt-4 text-sm opacity-75">

普段 Markdown でブログを書く人なら、<br>ほぼノーコストで導入できる。

</div>

---
layout: center
class: text-center
---

# まとめ

<div class="text-2xl my-8">

良さは1点に尽きる ——<br>
<span class="text-teal-400 font-bold">「ブログを書く労力でスライドが作れる」</span>

</div>

<v-clicks>

AIと相性が良いのも、結局は<br>「テキスト1ファイルで完結する」シンプルさから。

**次の一歩:** 自分テーマの作成 / 独自ドメイン接続 / `CLAUDE.md` で半自動運用

</v-clicks>

---
layout: center
class: text-center
---

# ありがとうございました 🚀

<div class="mt-8 text-left inline-block opacity-80">

参考リンク

- Slidev 公式ドキュメント — sli.dev
- Vercel ドキュメント — vercel.com/docs
- Slidev テーマギャラリー — sli.dev/themes/gallery.html
- Slidev サンプル集 — sli.dev/showcases.html

</div>

<div class="abs-br m-6 opacity-60 text-sm">
@uepon
</div>