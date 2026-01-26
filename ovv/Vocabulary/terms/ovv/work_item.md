---
id: work_item
name: Work Item
name_ja: ワークアイテム
category: terms/ovv
aliases:
  - WI
  - タスク
perspectives:
  engineer: |
    1-2時間で完了可能な作業単位。title, type, done_criteria を持つ。
    PostgreSQL に格納、threadWBS で階層化。
  pmo: |
    実行可能な最小作業単位。
    完了条件を明確に定義し、曖昧さを排除。
related:
  - focus
  - thread_wbs
  - deliverable_spec
version: "2.3.3"
created: 2026-01-26
updated: 2026-01-26
---

# Work Item (WI)

## 概要

Work Item は Ovv における実行可能な最小作業単位。1-2時間で完了可能なサイズに分解される。

## 構造

```yaml
title: "API エンドポイント実装"
type: "implementation"
done_criteria: "GET /api/users が 200 を返す"
```

### 必須フィールド

| フィールド | 説明 |
|------------|------|
| `title` | 作業内容の簡潔な説明 |
| `type` | 作業種別（implementation, research, etc.） |
| `done_criteria` | 完了条件（検証可能な形式） |

## 分解原則

- **1-2時間ルール**: それ以上は分解対象
- **完了条件必須**: 曖昧な終了条件は禁止
- **Deep Decomposition**: Clarification トリガーと自動分解

## 関連コマンド

| コマンド | 機能 |
|----------|------|
| `!wf <id>` | Work Item にフォーカス |
| `!wc` | Work Item を完了 |
| `!wd` | Work Item 詳細表示 |

## 関連

- [[focus]] — 現在の Work Item
- [[thread_wbs]] — WI の階層構造
- [[deliverable_spec]] — WI の上位概念
