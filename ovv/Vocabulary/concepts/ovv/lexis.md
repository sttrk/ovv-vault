---
id: lexis
name: LEXIS
name_ja: LEXIS
category: concepts/ovv
aliases:
  - Layered EXpert Interpretation System
  - Vocabulary Dictionary
perspectives:
  engineer: |
    4カテゴリ構造（terms/concepts × common/ovv）の語彙辞書。
    Markdown + YAML frontmatter 形式。起動時に _index.json を生成。
  pmo: |
    PMO/Engineer の二重視点で用語を定義。
    NL2SQL やコンテキスト生成時に参照。
related:
  - nl2sql
version: "2.3.3"
created: 2026-01-26
updated: 2026-01-26
---

# LEXIS — Layered EXpert Interpretation System

## 概要

LEXIS は Ovv の語彙辞書アーキテクチャ。PMO と Engineer の二重視点で用語・概念を定義。

## 名前の由来

| Component | 意味 |
|-----------|------|
| Layered | terms/concepts × common/ovv の多層構造 |
| EXpert | PMO/Engineer の専門視点 |
| Interpretation | 同一語彙の異なる解釈を保持 |
| System | Ovv アーキテクチャの一部として統合 |

## 構造

```
Vocabulary/
├── terms/           # 単語レベル
│   ├── common/      # 業界共通
│   └── ovv/         # Ovv 固有
├── concepts/        # 概念レベル
│   ├── common/      # 一般概念
│   └── ovv/         # Ovv 概念
└── _index.json      # 自動生成
```

## ファイル形式

- Markdown + YAML frontmatter
- Obsidian で編集可能
- `_index.json` は起動時に自動生成

## 同期フロー

```
iPhone (Obsidian + Fit) → GitHub → Pi (jj)
```

## 用途

- NL2SQL テンプレートから参照
- コンテキスト生成時の用語解決
- ユーザ/開発者の共通言語

## 関連

- [[nl2sql]] — LEXIS を参照
