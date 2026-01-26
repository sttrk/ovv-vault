---
id: tta
name: TTA
name_ja: TTA v2
category: concepts/ovv
aliases:
  - Temporal Triad Architecture
perspectives:
  engineer: |
    PAST (Loader) → PRESENT (Logic) → FUTURE (Effector) の単方向フロー。
    コンテキスト生成、PAF 推論、アクション実行を分離。
  pmo: |
    時間軸に沿った責務分離。
    過去（文脈）→ 現在（判断）→ 未来（実行）の流れを明確化。
related:
  - paf
  - exobis
version: "2.3.3"
created: 2026-01-26
updated: 2026-01-26
---

# TTA v2 — Temporal Triad Architecture

## 概要

TTA は時間軸に基づくアーキテクチャ。PAST → PRESENT → FUTURE の単方向フローで責務を分離。

## 構成

```
PAST (Loader)  →  PRESENT (Logic)  →  FUTURE (Effector)
   ↓                    ↓                    ↓
コンテキスト生成      PAF 推論          アクション実行
```

### PAST — Loader

- 過去のデータを読み込み
- コンテキストを生成
- Fact（PostgreSQL）と Reference（Obsidian）を統合

### PRESENT — Logic

- PAF プロトコルで推論
- 判断・決定を行う
- BIS（思考/判断）層

### FUTURE — Effector

- アクションを実行
- 結果を永続化
- EXO（I/O/永続化）層

## 単方向性

- PAST → PRESENT → FUTURE の順序厳守
- 逆流禁止（FUTURE から PAST への直接参照なし）

## 関連

- [[paf]] — PRESENT で実行
- [[exobis]] — EXO/BIS 分離と連携
