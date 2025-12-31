---
type: decision
decision_id: DEC-2024-001
related_deliverable: Pre-PAF System
date: 2024-12-28
decided_by: human
---

# Pre-PAF 導入決定

## Decision

推論前の構造安全ゲートとして Pre-PAF を導入する。

## Background

LLM 推論が不安定な状態で実行されると、誤った WorkItem 追加や矛盾した応答が発生していた。

## Rationale

- 機械判定で安定性を事前チェック
- 不安定なら推論をブロック
- 曖昧さを次工程に持ち込まない

## Impact

- DeliverableSpec 未定義時は推論ブロック
- Focus 未設定 + pending 複数の場合もブロック
