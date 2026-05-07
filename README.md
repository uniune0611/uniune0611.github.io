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
category: "jekyll"   # 本リポジトリは「1記事=1カテゴリ」の設計のため単数形を採用
tags:
  - github-pages
  - copilot
updated: 2026-05-07  # Jekyll 標準の date とは別の手動更新日
---
```

> Note: `category` は Jekyll 標準の `categories`（複数形）ではなく、本リポジトリ独自に単数で運用します。  
> `layout: page` は `_config.yml` で指定している `minima` テーマが提供するレイアウトです。

## インデックス整理ルール

- ルートの `index.md` を「総合インデックス」とする
- インデックスは `category` ごとに見出しを分ける
- 各リンクは Jekyll の `{% link %}` タグを使い、以下フォーマットで統一する  
  （`.md` 直リンクだと Jekyll ビルド後に 404 になるため）

```md
- [記事タイトル]({% link notes/YYYY/slug.md %}) - 1行要約（更新日: YYYY-MM-DD）
```

- 同一カテゴリ内は `updated` の降順（新しい順）に並べる
- 新規記事を追加したら、必ず `index.md` にリンクを追加する

## index.md 更新チェックリスト

1. 追加した記事のパスが `notes/YYYY/slug.md` になっている
2. front matter に `title`, `summary`, `category`, `updated` がある
3. `index.md` にリンクと要約を `{% link %}` タグ形式で追加した
4. `index.md` のカテゴリ並び・日付順が崩れていない
