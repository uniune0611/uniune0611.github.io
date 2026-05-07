# uniune0611.github.io

Jekyll を使った GitHub Pages リポジトリです。  
各 `.md` ファイルは GitHub Copilot Coding Agent で調査・作成する前提で、以下のルールでインデックス整理を行います。

## Markdown 配置ルール

- 調査記事は `notes/YYYY/slug.md` に配置する
  - 例: `notes/2026/jekyll-indexing.md`
- `slug` は英小文字・数字・ハイフンのみを使う
- 1トピックにつき1ファイルを原則とする

## 各 Markdown の必須 front matter

```yaml
---
layout: page
title: "記事タイトル"
summary: "1行要約"
category: "jekyll"
tags:
  - github-pages
  - copilot
updated: 2026-05-07
---
```

## インデックス整理ルール

- ルートの `index.md` を「総合インデックス」とする
- インデックスは `category` ごとに見出しを分ける
- 各リンクは以下フォーマットで統一する

```md
- [記事タイトル](./notes/YYYY/slug.md) - 1行要約（更新日: YYYY-MM-DD）
```

- 同一カテゴリ内は `updated` の降順（新しい順）に並べる
- 新規記事を追加したら、必ず `index.md` にリンクを追加する

## index.md 更新チェックリスト

1. 追加した記事のパスが `notes/YYYY/slug.md` になっている
2. front matter に `title`, `summary`, `category`, `updated` がある
3. `index.md` にリンクと要約を追加した
4. `index.md` のカテゴリ並び・日付順が崩れていない
