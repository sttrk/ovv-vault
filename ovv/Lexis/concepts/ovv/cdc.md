---
id: cdc
name: CDC
name_ja: CDC
category: concepts/ovv
aliases:
  - Change Decision Cycle
perspectives:
  engineer: |
    Draft → Review → Approve/Reject → Apply の4段階。
    PAF とは別レイヤーで動作。変更意図を記録し、承認後に実行。
  pmo: |
    変更管理のガバナンス機構。
    「何を変えるか」を明示し、承認プロセスを経て適用。
related:
  - paf
  - deliverable_spec
version: "2.3.3"
created: 2026-01-26
updated: 2026-01-26
---

# CDC — Change Decision Cycle

## 概要

CDC は変更管理のガバナンス機構。PAF とは別レイヤーで動作し、変更意図の記録と承認プロセスを管理する。

## フェーズ

### 1. Draft

- 変更意図を記録
- LLM がサマリーを生成

### 2. Review

- ユーザが変更内容を確認
- `!cdc show` で表示

### 3. Approve / Reject

- ユーザが承認または却下
- `!cdc approve` / `!cdc reject`

### 4. Apply

- 承認後、変更意図をコンテキストに再注入
- LLM が `set_deliverable_spec` を提案

## コマンド

| コマンド | 機能 |
|----------|------|
| `!cdc show` | 保留中の変更を表示 |
| `!cdc approve` | 変更を承認 |
| `!cdc reject` | 変更を却下 |

## DS Execution Lane

- 承認後、DeliverableSpec コンテキストを会話レーンと実行レーンで共有
- `delete_deliverable_spec` で明示的リセット

## 関連

- [[paf]] — CDC は PAF とは別レイヤー
- [[deliverable_spec]] — CDC で変更対象
