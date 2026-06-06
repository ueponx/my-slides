---
theme: seriph
title: Claude Code 入門
info: |
  ## Claude Code 入門
  非エンジニアの大学生向け 15分セッション
class: text-center
transition: slide-left
mdc: true
---

# Claude Code 入門

## 〜 プログラミングが分からなくても、AI に「お願い」してみよう 〜

<div class="pt-8 opacity-80">
非エンジニアの大学生のための 15 分ガイド
</div>

<div class="abs-br m-6 text-sm opacity-50">
所要時間：約15分 / 全10枚
</div>

---
layout: center
---

# 今日のゴール

このスライドが終わるころには、こんな状態を目指します 🎯

- Claude Code が **何をするものか** をイメージできる
- 「**自分にも関係あるかも**」と思える
- 試したくなったときの **始め方** が分かる

<div class="pt-6 opacity-70">

専門用語はできるだけ使わず、出てきたら必ず説明します。<br>
「よく分からない」が普通のスタート地点です。

</div>

---

# Claude Code とは？

ひとことで言うと…

<div class="text-2xl pt-4 pb-6 text-teal-400">
🤖 「文章で指示すると、代わりに作業してくれる AI アシスタント」
</div>

- Anthropic 社が作っている **AI コーディングエージェント**
- 普通のチャット AI と違い、**あなたのパソコンの中のファイルを読んだり書いたりできる**
- 「この資料をまとめて」「このデータを表にして」のように、**日本語でお願いするだけ**

<div class="pt-4 opacity-70">

※「コーディング」= プログラムを書くこと。<br>
でも実は、プログラム以外の文章作業や調べ物にも使えます。

</div>

---
layout: two-cols
---

# 「ターミナル」って何？

Claude Code は主に **ターミナル** という画面で動きます。

<div class="pt-4">

- 黒い画面に文字を打ち込んで<br>パソコンに命令する道具
- マウスでクリックする代わりに<br>**キーボードで言葉を打つ**
- 昔ながらの操作方法だけど<br>今でも開発の現場で大活躍

</div>

<div class="pt-4 opacity-70 text-sm">
最近は <b>マウスで使えるデスクトップアプリ版</b> もあるので、<br>
ターミナルが苦手でも大丈夫です。
</div>

::right::

<div class="pl-4 pt-12">

```bash
$ claude
Welcome to Claude Code!

> このフォルダの中身を
  教えて

調べています...
report.docx  data.csv
memo.txt
```

</div>

---
layout: center
---

# なぜ「非エンジニアの私」に関係あるの？

<div class="grid grid-cols-2 gap-6 pt-4">

<div>

### これまで
プログラミングを使うには…

- 専門の言語を学ぶ必要があった
- 文法を覚え、エラーと戦う
- 「自分には無理」と感じやすい

</div>

<div>

### これから
Claude Code を使うと…

- **日本語でお願いするだけ**
- 細かい文法は AI が担当
- アイデアや「やりたいこと」が主役

</div>

</div>

<div class="pt-8 text-center text-xl text-teal-400">
✨ 大事なのは「コードを書く力」より「やりたいことを言葉にする力」
</div>

---

# 何ができるの？（具体例）

非エンジニアでも役立つ使い方の例 👇

- 📄 **資料の整理**：「このテキストを見出し付きで整理して」
- 📊 **データの加工**：「この CSV を読んで、平均点を計算して」
- 🔍 **中身の説明**：「このファイル、何が書いてあるか説明して」
- 🛠 **ちょっとした自動化**：「複数ファイルの名前をまとめて変えて」
- 🌐 **調べ物の下準備**：「このテーマについて要点をまとめて」

<div class="pt-4 opacity-70">

ポイントは、**「自分の手元のファイルに対して」作業してくれる**こと。<br>
普通のチャット AI より一歩踏み込んだお手伝いができます。

</div>

---

# 使うために必要なもの

始める前のチェックリスト ✅

- 💻 **パソコン**（Windows / Mac / Linux いずれも OK）
- 🔑 **Claude の有料プラン**（Pro など）または API の利用契約
- 🌐 **インターネット接続**

<div class="pt-4 opacity-70">

無料の範囲だけでは使えない点に注意。<br>
まずは「どんなものか知る」だけでも十分価値があります。

</div>

<div class="pt-4 text-sm opacity-60">
最新の対応状況・料金は公式ドキュメントで確認してください。
</div>

---

# インストールはむずかしい？

実は、コマンドを1行打つだけで始められます。

<div class="pt-2">

Mac / Linux の場合（ターミナルに貼り付けて Enter）：

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

</div>

- この方法（**ネイティブインストーラー**）なら、追加の準備はほぼ不要
- Windows でも公式の手順が用意されています
- ターミナルが不安な人は **デスクトップアプリ版**（クリックで操作）から

<div class="pt-4 opacity-70">

「呪文みたい…」と感じても大丈夫。<br>
意味は「公式の準備ツールを取ってきて実行してね」というお願いです。

</div>

---
layout: center
---

# 最初の一歩

インストールできたら、ターミナルで `claude` と打つだけ。

```bash
$ claude

> このフォルダにある memo.txt の内容を
  3行で要約して

memo.txt を読んでいます...
要約：
1. 来週の発表は火曜日
2. スライドは10枚程度
3. 担当は3人で分担
```

<div class="pt-4 text-center opacity-80">
あとは <b>友達に頼むように、日本語で会話するだけ</b>。<br>
うまくいかなければ「もっと短く」「やり直して」と伝えれば OK。
</div>

---
layout: center
class: text-center
---

# まとめ & 次のステップ

<div class="pt-2 text-left max-w-2xl mx-auto">

- Claude Code は **文章で指示すると作業してくれる AI アシスタント**
- 強みは **手元のファイルを直接さわれる**こと
- 大事なのは文法より **「やりたいことを言葉にする力」**
- 始め方はシンプル。まずは小さなお願いから試そう

</div>

<div class="pt-8 opacity-80">

📚 もっと知りたい人へ：<br>
公式ドキュメント → <span class="text-teal-400">docs.claude.com/en/docs/claude-code</span>

</div>

<div class="pt-8 text-2xl text-teal-400">
まずは「ちょっと頼んでみる」ところから 🚀
</div>