---
term: FOCUS
en: FOCUS
ja: 現在の集中対象
category: terms/ovv
---

## Engineer View

- **meaning**:  
  現在の Execution Context において、唯一アクティブとみなされる Work Item。

- **implication**:  
  - `update_item_status` や進捗更新の暗黙的ターゲットになる  
  - FOCUS 以外の Work Item を操作する場合、明示的な切替が必要  
  - 並列実行を防ぐための構造的ガードとして機能する

- **reversible**:  
  true（FOCUS は切替可能。ただし履歴は TRACE に残る）

## PMO View

- **meaning**:  
  「いま何に取り組んでいるか」を明確に示す合意上の集中点。

- **implication**:  
  - 脱線・話題拡散・マルチタスク化を防ぐ  
  - 進捗確認や説明時の基準点になる  
  - FOCUS 外の話題は「後でやること」として切り分けられる

- **reversible**:  
  true（優先順位変更として切替可能）

## Meta

- **collision_risk**: high
- **notes**:
  - Engineer は「実行ターゲット」として扱う
  - PMO は「優先順位の固定点」として扱う
  - FOCUS が未定義のまま作業を進めると、迷走・スコープ逸脱が起きやすい
  - FOCUS の切替は判断であり、単なる操作ではない