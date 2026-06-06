---
# 'default' でもOK。今回は seriph を使用
theme: seriph
# 表紙の背景（Unsplash のキュレーション画像）
background: https://cover.sli.dev
title: Claude Code 入門
info: |
  ## Claude Code 入門
  非エンジニアの大学生向け 15分セッション
class: text-center
transition: slide-left
fonts:
  sans: 'Noto Sans JP'
  serif: 'Noto Serif JP'
  mono: 'Fira Code'
drawings:
  persist: false
duration: 15min
mdc: true
---

# Claude Code 入門

プログラミングが分からなくても、AI に「お願い」してみよう

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  <kbd>Space</kbd> で次へ <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-sm opacity-50">
非エンジニアの大学生のための 15 分ガイド ・ 全 10 枚
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
冒頭のつかみ。「プログラミング＝難しい」という先入観を、最初の一言で軽くしておく。
-->

---
transition: fade-out
---

# 今日のゴール 🎯

このスライドが終わるころには、こんな状態を目指します。

<v-clicks>

- Claude Code が **何をするものか** をイメージできる
- 「**自分にも関係あるかも**」と思える
- 試したくなったときの **始め方** が分かる

</v-clicks>

<br>

<v-click>

専門用語は出てきたら必ず説明します。<span v-mark.underline.orange>「よく分からない」が普通のスタート</span>です。

</v-click>

<!--
全体像とゴールを先に共有して、安心して聞ける状態をつくる。
-->

---
transition: slide-up
---

# Claude Code とは？

ひとことで言うと——

<div class="text-2xl my-6">
🤖 文章で指示すると、<span v-mark.circle.orange>代わりに作業してくれる</span> AI アシスタント
</div>

<v-clicks>

- Anthropic 社が作る **AI コーディングエージェント**
- 普通のチャット AI と違い、**手元のファイルを読んだり書いたりできる**
- 「この資料をまとめて」のように **日本語でお願いするだけ**

</v-clicks>

<div class="text-sm opacity-60 mt-8">

※「コーディング」＝プログラムを書くこと。でも文章作業や調べ物にも使えます。

</div>

<!--
チャットAIとの違い＝「手元のファイルをさわれる」点を強調する。
-->

---
layout: two-cols
layoutClass: gap-12
---

# 「ターミナル」って何？

Claude Code は主に **ターミナル** という画面で動きます。

<v-clicks>

- 黒い画面に文字を打って<br>パソコンに命令する道具
- クリックの代わりに<br>**キーボードで言葉を打つ**
- 開発の現場では今も大活躍

</v-clicks>

<div class="text-sm opacity-60 mt-6">

マウスで使える **デスクトップアプリ版** もあるので、苦手でも大丈夫。

</div>

::right::

```bash
$ claude
Welcome to Claude Code!

> このフォルダの中身を教えて

調べています...
report.docx  data.csv  memo.txt
```

<!--
「黒い画面」への抵抗感を和らげる。アプリ版があることも添える。
-->

---

# なぜ「非エンジニアの私」に関係あるの？

<div class="grid grid-cols-2 gap-6 mt-6">

<div v-click class="p-4 rounded-lg border border-gray-400/30">

### これまで

- 専門の言語を学ぶ必要があった
- 文法を覚え、エラーと戦う
- 「自分には無理」と感じやすい

</div>

<div v-click class="p-4 rounded-lg border border-primary/40 bg-primary/10">

### これから

- **日本語でお願いするだけ**
- 細かい文法は AI が担当
- アイデアや「やりたいこと」が主役

</div>

</div>

<v-click>

<div class="text-center text-xl mt-8">
✨ 大事なのは「コードを書く力」より <span v-mark.orange>「やりたいことを言葉にする力」</span>
</div>

</v-click>

<!--
ここが今日のいちばん伝えたいメッセージ。ゆっくり話す。
-->

---

# 何ができるの？

非エンジニアでも役立つ使い方の例 👇

<div class="grid grid-cols-2 gap-4 mt-4">
<v-clicks>

<div class="p-3 rounded border border-primary/20 bg-primary/5"><b>📄 資料の整理</b><br><span class="text-sm opacity-70">見出し付きで整理して</span></div>
<div class="p-3 rounded border border-primary/20 bg-primary/5"><b>📊 データの加工</b><br><span class="text-sm opacity-70">この CSV の平均を計算して</span></div>
<div class="p-3 rounded border border-primary/20 bg-primary/5"><b>🔍 中身の説明</b><br><span class="text-sm opacity-70">何が書いてあるか説明して</span></div>
<div class="p-3 rounded border border-primary/20 bg-primary/5"><b>🛠 ちょっとした自動化</b><br><span class="text-sm opacity-70">ファイル名をまとめて変えて</span></div>

</v-clicks>
</div>

<div class="text-sm opacity-60 mt-6">

ポイントは <span v-mark.underline.orange>「自分の手元のファイルに対して」作業してくれる</span> こと。

</div>

---

# 使うために必要なもの

始める前のチェックリスト ✅

<v-clicks>

- 💻 **パソコン**（Windows / Mac / Linux いずれも OK）
- 🔑 **Claude の有料プラン**（Pro など）または API の利用契約
- 🌐 **インターネット接続**

</v-clicks>

<div class="text-sm opacity-60 mt-8">

無料の範囲だけでは使えない点に注意。最新の料金・対応状況は公式ドキュメントで確認を。

</div>

---
layout: image-right
image: https://cover.sli.dev
---

# インストールはむずかしい？

実は、コマンドを **1 行** 打つだけ（Mac / Linux）。

```bash [install.sh] {all|1}
curl -fsSL https://claude.ai/install.sh | bash
```

<v-clicks>

- 追加の準備はほぼ不要（Windows でも公式手順あり）
- ターミナルが不安なら **デスクトップアプリ版** から

</v-clicks>

<div class="text-sm opacity-60 mt-6">

意味は「公式の準備ツールを取ってきて実行してね」というお願いです。

</div>

<!--
コマンドの「呪文っぽさ」を、平易な言葉に翻訳して安心させる。
-->

---

# 最初の一歩

ターミナルで <code>claude</code> と打つだけ。あとは会話するだけです。

```bash {all|1|3|5-8}
$ claude

> memo.txt の内容を 3 行で要約して

要約：
1. 来週の発表は火曜日
2. スライドは 10 枚程度
3. 担当は 3 人で分担
```

うまくいかなければ <kbd>もっと短く</kbd> <kbd>やり直して</kbd> と伝えれば OK。

<!--
「友達に頼むのと同じ」という感覚を持って帰ってもらう。
-->

---
layout: center
class: text-center
---

# まとめ & 次のステップ

<div class="text-left inline-block">

- Claude Code は **文章で指示すると作業してくれる** AI アシスタント
- 強みは **手元のファイルを直接さわれる** こと
- 大事なのは文法より **「やりたいことを言葉にする力」**
- 始め方はシンプル。まずは小さなお願いから

</div>

<div class="mt-10 opacity-80">
📚 もっと知りたい人へ → [docs.claude.com/en/docs/claude-code](https://docs.claude.com/en/docs/claude-code)
</div>

<div class="text-2xl mt-8">
まずは「ちょっと頼んでみる」ところから 🚀
</div>

<!--
最後はハードルを下げる一言で締める。
-->