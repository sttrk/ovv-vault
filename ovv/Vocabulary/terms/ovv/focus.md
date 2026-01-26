---
id: focus
name: FOCUS
name_ja: フォーカス
category: terms/ovv
aliases:
  - FocusScope
  - 現在のフォーカス
perspectives:
  engineer: |
    現在作業中の Work Item を指す状態変数。
    Discord Thread レベルのスコープに対応。
  pmo: |
    「今、何に取り組んでいるか」を明示する仕組み。
    完了時は `!wc` で閉じる。
related:
  - work_item
  - hierarchical_scope
version: "2.3.3"
created: 2026-01-26
updated: 2026-01-26
---

# FOCUS

## 概要

FOCUS は現在作業中の Work Item を指す状態変数。「今、何に取り組んでいるか」を明示する。

## スコープ階層

```
DomainScope (Discord Category)
    └── ContextScope (Discord Channel)
        └── FocusScope (Discord Thread) ← FOCUS
```

## 状態遷移

| コマンド | 動作 |
|----------|------|
| `!wf <id>` | FOCUS を設定 |
| `!wc` | FOCUS を完了・クローズ |
| `!wd` | FOCUS を詳細表示 |

## FOCUS Closing Rule

- FOCUS が存在する場合、応答は次ステップまたは `!wc` を案内
- 放置禁止

## State Transition Gate

- LLM は FOCUS 変更を提案のみ
- 実際の遷移はユーザ操作

## 関連

- [[work_item]] — FOCUS の対象
- [[hierarchical_scope]] — スコープ階層
