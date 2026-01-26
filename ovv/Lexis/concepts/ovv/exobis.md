---
id: exobis
name: EXOBIS
name_ja: EXOBIS
category: concepts/ovv
aliases:
  - EXO-BIS Architecture
perspectives:
  engineer: |
    EXO（External I/O + Persistence）と BIS（Brain Inference System）の分離。
    思考/判断と入出力/永続化を明確に区別。
  pmo: |
    「考える」と「実行する」の責務分離。
    判断の純粋性を保ち、副作用を外部化。
related:
  - tta
  - paf
version: "2.3.3"
created: 2026-01-26
updated: 2026-01-26
---

# EXOBIS — EXO/BIS Architecture

## 概要

EXOBIS は Ovv のアーキテクチャ原則。思考/判断（BIS）と I/O/永続化（EXO）を分離する。

## 構成

```
┌─────────────────────────────────────┐
│              EXOBIS                  │
├─────────────────┬───────────────────┤
│      EXO        │       BIS         │
│  (External)     │  (Brain)          │
├─────────────────┼───────────────────┤
│ - Discord I/O   │ - PAF 推論        │
│ - PostgreSQL    │ - COC オペレータ  │
│ - Obsidian      │ - 判断/決定       │
│ - API 呼び出し  │ - 内部思考        │
└─────────────────┴───────────────────┘
```

### EXO — External

- **I/O**: Discord メッセージ送受信
- **Persistence**: PostgreSQL、Obsidian
- **API**: 外部サービス呼び出し
- 副作用を持つ処理を担当

### BIS — Brain Inference System

- **Reasoning**: PAF プロトコル
- **Operators**: COC（Clarify/Options/Commit）
- **Output**: `reasoning`（内部）と `response_message`（外部）
- 純粋な思考/判断を担当

## 原則

- BIS は副作用を持たない
- EXO は判断を行わない
- 境界を明確に保つ

## 関連

- [[tta]] — TTA と連携
- [[paf]] — BIS で実行
