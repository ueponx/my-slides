---
theme: seriph
title: Claude Code 入門
fonts:
  sans: IBM Plex Sans JP
  serif: IBM Plex Sans JP
  mono: IBM Plex Mono
  weights: '300,400,500,600,700'
info: |
  ## Claude Code 入門
  非エンジニアの大学生向け 15分セッション
layout: default
class: 'text-[#f3ece2]'
transition: slide-left
mdc: true
---

<div class="absolute inset-0 z-[-1] bg-[#15110d]">
  <div class="absolute inset-0 bg-gradient-to-br from-[#241a10] via-[#15110d] to-[#0c0a07]"></div>
  <div class="absolute -top-24 -right-24 w-[28rem] h-[28rem] rounded-full bg-[rgba(224,135,94,0.18)] blur-[130px]"></div>
  <div class="absolute -bottom-20 left-0 w-80 h-80 rounded-full bg-[rgba(194,85,47,0.12)] blur-[120px]"></div>
</div>

<div class="h-full flex flex-col justify-center">
  <div class="font-mono text-sm tracking-[0.35em] text-[#e0875e] uppercase mb-6">$ claude --help</div>
  <h1 class="!text-6xl !font-700 !leading-[1.1] !mb-0 !text-[#f7f1e8] !border-none">Claude Code<br>入門</h1>
  <div class="w-24 h-[3px] bg-[#e0875e] my-7"></div>
  <p class="text-xl text-[#cbbcab] !mb-1 !leading-relaxed">プログラミングが分からなくても、<br>AI に「お願い」してみよう。</p>
  <p class="font-mono text-sm text-[#897b6c] mt-10">非エンジニアの大学生のための 15 分ガイド ・ 全 10 枚</p>
</div>

---
layout: default
class: 'text-[#f3ece2]'
---

<div class="absolute inset-0 z-[-1] bg-gradient-to-br from-[#1b1510] via-[#15110d] to-[#0c0a07]"></div>

<div class="h-full flex flex-col justify-center max-w-4xl">

<div class="font-mono text-sm tracking-[0.3em] text-[#e0875e] uppercase mb-3">01 — GOAL</div>
<h2 class="!text-4xl !font-600 !text-[#f7f1e8] !mb-10 !border-none">今日のゴール</h2>

<div class="space-y-5">
<v-clicks>

<div class="flex items-start gap-4 p-5 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="font-mono text-[#e0875e] text-xl">→</span>
  <div>Claude Code が <span class="text-[#f0b48a] font-600">何をするものか</span> をイメージできる</div>
</div>

<div class="flex items-start gap-4 p-5 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="font-mono text-[#e0875e] text-xl">→</span>
  <div>「<span class="text-[#f0b48a] font-600">自分にも関係あるかも</span>」と思える</div>
</div>

<div class="flex items-start gap-4 p-5 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="font-mono text-[#e0875e] text-xl">→</span>
  <div>試したくなったときの <span class="text-[#f0b48a] font-600">始め方</span> が分かる</div>
</div>

</v-clicks>
</div>

<p class="text-sm text-[#897b6c] mt-10">専門用語は出てきたら必ず説明します。「よく分からない」が普通のスタートです。</p>

</div>

---
layout: default
class: 'text-[#f3ece2]'
---

<div class="absolute inset-0 z-[-1] bg-gradient-to-br from-[#1b1510] via-[#15110d] to-[#0c0a07]"></div>

<div class="h-full flex flex-col justify-center max-w-4xl">

<div class="font-mono text-sm tracking-[0.3em] text-[#e0875e] uppercase mb-3">02 — WHAT IS IT</div>
<h2 class="!text-4xl !font-600 !text-[#f7f1e8] !mb-8 !border-none">Claude Code とは？</h2>

<div class="p-6 rounded-2xl bg-[rgba(224,135,94,0.08)] border-l-4 border-[#e0875e] mb-8">
  <p class="!text-2xl !text-[#f7f1e8] !leading-relaxed !m-0">🤖 文章で指示すると、<span class="text-[#f0b48a] font-600">代わりに作業してくれる</span> AI アシスタント</p>
</div>

<div class="space-y-3 text-[#cbbcab]">
<v-clicks>

<p class="!my-0">・Anthropic 社が作る <span class="text-[#f3ece2]">AI コーディングエージェント</span></p>
<p class="!my-0">・普通のチャット AI と違い、<span class="text-[#f3ece2]">手元のファイルを読んだり書いたりできる</span></p>
<p class="!my-0">・「この資料をまとめて」のように <span class="text-[#f3ece2]">日本語でお願いするだけ</span></p>

</v-clicks>
</div>

<p class="text-sm text-[#897b6c] mt-8">※「コーディング」＝プログラムを書くこと。でも文章作業や調べ物にも使えます。</p>

</div>

---
layout: default
class: 'text-[#f3ece2]'
---

<div class="absolute inset-0 z-[-1] bg-gradient-to-br from-[#1b1510] via-[#15110d] to-[#0c0a07]"></div>

<div class="h-full grid grid-cols-2 gap-10 items-center">

<div>
<div class="font-mono text-sm tracking-[0.3em] text-[#e0875e] uppercase mb-3">03 — TERMINAL</div>
<h2 class="!text-4xl !font-600 !text-[#f7f1e8] !mb-6 !border-none">「ターミナル」<br>って何？</h2>

<div class="space-y-4 text-[#cbbcab] text-lg">
<p class="!my-0">・黒い画面に文字を打って<br>パソコンに命令する道具</p>
<p class="!my-0">・クリックの代わりに<br><span class="text-[#f0b48a]">キーボードで言葉を打つ</span></p>
<p class="!my-0">・開発の現場では今も大活躍</p>
</div>

<p class="text-sm text-[#897b6c] mt-6">マウスで使える<span class="text-[#cbbcab]">デスクトップアプリ版</span>もあるので、苦手でも大丈夫。</p>
</div>

<div class="rounded-xl overflow-hidden border border-[#3a2e22] bg-[#0d0b08] shadow-2xl shadow-black/60">
  <div class="flex items-center gap-2 px-4 py-3 bg-[#221b14] border-b border-[#3a2e22]">
    <span class="w-3 h-3 rounded-full bg-[#e0875e]"></span>
    <span class="w-3 h-3 rounded-full bg-[#d8b46a]"></span>
    <span class="w-3 h-3 rounded-full bg-[#7fae8a]"></span>
    <span class="ml-3 font-mono text-xs text-[#897b6c]">claude — terminal</span>
  </div>
  <div class="p-5 font-mono text-sm leading-7 text-[#d8ccbd]">
    <span class="text-[#7fae8a]">$</span> claude<br>
    <span class="text-[#897b6c]">Welcome to Claude Code!</span><br><br>
    <span class="text-[#e0875e]">&gt;</span> このフォルダの中身を教えて<br><br>
    <span class="text-[#897b6c]">調べています...</span><br>
    report.docx&nbsp;&nbsp;data.csv&nbsp;&nbsp;memo.txt
  </div>
</div>

</div>

---
layout: default
class: 'text-[#f3ece2]'
---

<div class="absolute inset-0 z-[-1] bg-gradient-to-br from-[#1b1510] via-[#15110d] to-[#0c0a07]"></div>

<div class="h-full flex flex-col justify-center">

<div class="font-mono text-sm tracking-[0.3em] text-[#e0875e] uppercase mb-3">04 — WHY ME</div>
<h2 class="!text-4xl !font-600 !text-[#f7f1e8] !mb-8 !border-none">なぜ「非エンジニアの私」に関係あるの？</h2>

<div class="grid grid-cols-2 gap-6">

<div class="p-6 rounded-2xl bg-[rgba(255,255,255,0.02)] border border-[#332a20]">
  <div class="font-mono text-xs tracking-widest text-[#897b6c] uppercase mb-4">これまで</div>
  <div class="space-y-3 text-[#a99a89]">
    <p class="!my-0">・専門の言語を学ぶ必要があった</p>
    <p class="!my-0">・文法を覚え、エラーと戦う</p>
    <p class="!my-0">・「自分には無理」と感じやすい</p>
  </div>
</div>

<div class="p-6 rounded-2xl bg-[rgba(224,135,94,0.08)] border border-[#a8552f]">
  <div class="font-mono text-xs tracking-widest text-[#e0875e] uppercase mb-4">これから</div>
  <div class="space-y-3 text-[#ecdfd0]">
    <p class="!my-0">・<span class="text-[#f0b48a] font-600">日本語でお願いするだけ</span></p>
    <p class="!my-0">・細かい文法は AI が担当</p>
    <p class="!my-0">・アイデアや「やりたいこと」が主役</p>
  </div>
</div>

</div>

<p class="text-center text-xl text-[#f0b48a] mt-10">✨ 大事なのは「コードを書く力」より「やりたいことを言葉にする力」</p>

</div>

---
layout: default
class: 'text-[#f3ece2]'
---

<div class="absolute inset-0 z-[-1] bg-gradient-to-br from-[#1b1510] via-[#15110d] to-[#0c0a07]"></div>

<div class="h-full flex flex-col justify-center">

<div class="font-mono text-sm tracking-[0.3em] text-[#e0875e] uppercase mb-3">05 — USE CASES</div>
<h2 class="!text-4xl !font-600 !text-[#f7f1e8] !mb-8 !border-none">何ができるの？</h2>

<div class="grid grid-cols-2 gap-4">
<v-clicks>

<div class="flex items-center gap-4 p-4 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="text-2xl">📄</span><div><span class="text-[#f0b48a] font-600">資料の整理</span><br><span class="text-sm text-[#a99a89]">見出し付きで整理して</span></div>
</div>
<div class="flex items-center gap-4 p-4 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="text-2xl">📊</span><div><span class="text-[#f0b48a] font-600">データの加工</span><br><span class="text-sm text-[#a99a89]">この CSV の平均を計算して</span></div>
</div>
<div class="flex items-center gap-4 p-4 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="text-2xl">🔍</span><div><span class="text-[#f0b48a] font-600">中身の説明</span><br><span class="text-sm text-[#a99a89]">何が書いてあるか説明して</span></div>
</div>
<div class="flex items-center gap-4 p-4 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="text-2xl">🛠</span><div><span class="text-[#f0b48a] font-600">ちょっとした自動化</span><br><span class="text-sm text-[#a99a89]">ファイル名をまとめて変えて</span></div>
</div>

</v-clicks>
</div>

<p class="text-sm text-[#897b6c] mt-8">ポイントは <span class="text-[#cbbcab]">「自分の手元のファイルに対して」作業してくれる</span>こと。</p>

</div>

---
layout: default
class: 'text-[#f3ece2]'
---

<div class="absolute inset-0 z-[-1] bg-gradient-to-br from-[#1b1510] via-[#15110d] to-[#0c0a07]"></div>

<div class="h-full flex flex-col justify-center max-w-3xl">

<div class="font-mono text-sm tracking-[0.3em] text-[#e0875e] uppercase mb-3">06 — REQUIREMENTS</div>
<h2 class="!text-4xl !font-600 !text-[#f7f1e8] !mb-10 !border-none">使うために必要なもの</h2>

<div class="space-y-4">
<div class="flex items-center gap-4 p-5 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="text-2xl">💻</span><div><span class="text-[#f3ece2] font-600">パソコン</span> <span class="text-[#a99a89]">（Windows / Mac / Linux いずれも OK）</span></div>
</div>
<div class="flex items-center gap-4 p-5 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="text-2xl">🔑</span><div><span class="text-[#f3ece2] font-600">Claude の有料プラン</span> <span class="text-[#a99a89]">（Pro など）または API の利用契約</span></div>
</div>
<div class="flex items-center gap-4 p-5 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20]">
  <span class="text-2xl">🌐</span><div><span class="text-[#f3ece2] font-600">インターネット接続</span></div>
</div>
</div>

<p class="text-sm text-[#897b6c] mt-8">無料の範囲だけでは使えない点に注意。最新の料金・対応状況は公式ドキュメントで確認を。</p>

</div>

---
layout: default
class: 'text-[#f3ece2]'
---

<div class="absolute inset-0 z-[-1] bg-gradient-to-br from-[#1b1510] via-[#15110d] to-[#0c0a07]"></div>

<div class="h-full flex flex-col justify-center max-w-4xl">

<div class="font-mono text-sm tracking-[0.3em] text-[#e0875e] uppercase mb-3">07 — INSTALL</div>
<h2 class="!text-4xl !font-600 !text-[#f7f1e8] !mb-8 !border-none">インストールはむずかしい？</h2>

<p class="text-lg text-[#cbbcab] mb-5">実は、コマンドを 1 行打つだけで始められます（Mac / Linux）。</p>

<div class="rounded-xl overflow-hidden border border-[#3a2e22] bg-[#0d0b08] shadow-2xl shadow-black/60 mb-8">
  <div class="flex items-center gap-2 px-4 py-3 bg-[#221b14] border-b border-[#3a2e22]">
    <span class="w-3 h-3 rounded-full bg-[#e0875e]"></span>
    <span class="w-3 h-3 rounded-full bg-[#d8b46a]"></span>
    <span class="w-3 h-3 rounded-full bg-[#7fae8a]"></span>
    <span class="ml-3 font-mono text-xs text-[#897b6c]">terminal</span>
  </div>
  <div class="p-5 font-mono text-base text-[#d8ccbd]">
    <span class="text-[#7fae8a]">$</span> curl -fsSL https://claude.ai/install.sh | bash
  </div>
</div>

<div class="space-y-2 text-[#cbbcab]">
  <p class="!my-0">・この方法なら追加の準備はほぼ不要（Windows でも公式手順あり）</p>
  <p class="!my-0">・ターミナルが不安なら <span class="text-[#f0b48a]">デスクトップアプリ版</span>（クリック操作）から</p>
</div>

</div>

---
layout: default
class: 'text-[#f3ece2]'
---

<div class="absolute inset-0 z-[-1] bg-gradient-to-br from-[#1b1510] via-[#15110d] to-[#0c0a07]"></div>

<div class="h-full flex flex-col justify-center max-w-4xl">

<div class="font-mono text-sm tracking-[0.3em] text-[#e0875e] uppercase mb-3">08 — FIRST STEP</div>
<h2 class="!text-4xl !font-600 !text-[#f7f1e8] !mb-6 !border-none">最初の一歩</h2>

<p class="text-lg text-[#cbbcab] mb-5">ターミナルで <span class="font-mono text-[#f0b48a]">claude</span> と打つだけ。あとは会話するだけです。</p>

<div class="rounded-xl overflow-hidden border border-[#3a2e22] bg-[#0d0b08] shadow-2xl shadow-black/60">
  <div class="flex items-center gap-2 px-4 py-3 bg-[#221b14] border-b border-[#3a2e22]">
    <span class="w-3 h-3 rounded-full bg-[#e0875e]"></span>
    <span class="w-3 h-3 rounded-full bg-[#d8b46a]"></span>
    <span class="w-3 h-3 rounded-full bg-[#7fae8a]"></span>
    <span class="ml-3 font-mono text-xs text-[#897b6c]">claude — terminal</span>
  </div>
  <div class="p-5 font-mono text-sm leading-7 text-[#d8ccbd]">
    <span class="text-[#7fae8a]">$</span> claude<br><br>
    <span class="text-[#e0875e]">&gt;</span> memo.txt の内容を 3 行で要約して<br><br>
    <span class="text-[#897b6c]">memo.txt を読んでいます...</span><br>
    <span class="text-[#f0b48a]">要約：</span><br>
    1. 来週の発表は火曜日<br>
    2. スライドは 10 枚程度<br>
    3. 担当は 3 人で分担
  </div>
</div>

<p class="text-sm text-[#897b6c] mt-6">うまくいかなければ「もっと短く」「やり直して」と伝えれば OK。</p>

</div>

---
layout: default
class: 'text-[#f3ece2]'
---

<div class="absolute inset-0 z-[-1] bg-[#15110d]">
  <div class="absolute inset-0 bg-gradient-to-tr from-[#241a10] via-[#15110d] to-[#0c0a07]"></div>
  <div class="absolute top-10 right-10 w-96 h-96 rounded-full bg-[rgba(224,135,94,0.15)] blur-[130px]"></div>
</div>

<div class="h-full flex flex-col justify-center max-w-4xl">

<div class="font-mono text-sm tracking-[0.3em] text-[#e0875e] uppercase mb-3">09 — WRAP UP</div>
<h2 class="!text-4xl !font-600 !text-[#f7f1e8] !mb-8 !border-none">まとめ & 次のステップ</h2>

<div class="space-y-3 text-lg text-[#cbbcab] mb-8">
  <p class="!my-0">・<span class="text-[#f3ece2]">文章で指示すると作業してくれる AI アシスタント</span></p>
  <p class="!my-0">・強みは <span class="text-[#f0b48a]">手元のファイルを直接さわれる</span>こと</p>
  <p class="!my-0">・大事なのは文法より <span class="text-[#f0b48a]">「やりたいことを言葉にする力」</span></p>
  <p class="!my-0">・始め方はシンプル。まずは小さなお願いから</p>
</div>

<div class="p-5 rounded-xl bg-[rgba(255,255,255,0.03)] border border-[#332a20] font-mono text-sm text-[#a99a89] mb-8">
  📚 もっと知りたい人へ → <span class="text-[#f0b48a]">docs.claude.com/en/docs/claude-code</span>
</div>

<p class="text-2xl text-[#f0b48a]">まずは「ちょっと頼んでみる」ところから 🚀</p>

</div>