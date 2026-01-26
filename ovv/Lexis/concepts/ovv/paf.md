---
id: paf
name: PAF
name_ja: PAF
category: concepts/ovv
aliases:
  - Proposal-Audit-Final
  - PAF Thinking Protocol
perspectives:
  engineer: |
    3段階パイプライン。Proposal で仮説生成、Audit で自己検証、Final で出力確定。
    各フェーズは独立したコンテキストを持ち、フェーズ混在を禁止。
  pmo: |
    「一発で正解を出さない」ガバナンス原則の実装。
    提案→監査→確定の流れで品質を担保。
related:
  - coc
  - exobis
  - tta
version: "2.3.3"
created: 2026-01-26
updated: 2026-01-26
---

# PAF — Proposal → Audit → Final

## 概要

PAF は Ovv の思考プロトコル。3段階の厳格なフェーズで構成され、「一発で正解を出さない」原則を実装する。

## フェーズ

### 1. Proposal Phase

- 仮説・選択肢を生成
- COC オペレータ（Clarify / Options / Commit）を使用
- 不確実性を明示

### 2. Audit Phase

- GUIDE / LEDGER / DS チェック
- A3 判定（Accept / Adjust / Abort）
- 自己監査による品質担保

### 3. Final Phase

- 最終決定を出力
- 曖昧さを排除
- ユーザへの明確な応答

## 原則

- **フェーズ混在禁止**: 各フェーズは独立
- **監査必須**: Audit をスキップしない
- **Never trust the first answer**: 最初の回答を信じない

## 関連

- [[coc]] — Proposal Phase で使用
- [[exobis]] — EXO/BIS 分離
- [[tta]] — 時間軸アーキテクチャ
