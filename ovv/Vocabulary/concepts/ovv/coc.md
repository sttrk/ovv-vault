---
id: coc
name: COC
name_ja: COC
category: concepts/ovv
aliases:
  - Clarify-Options-Commit
  - Proposal Operators
perspectives:
  engineer: |
    Proposal Phase 専用の3オペレータ。Clarify で前提確認、Options で選択肢提示、
    Commit でユーザ決定を取得。状態遷移を伴わない。
  pmo: |
    曖昧さを解消するための構造化質問手法。
    推測で埋めず、必要最小限の確認を行う。
related:
  - paf
  - router
version: "2.3.3"
created: 2026-01-26
updated: 2026-01-26
---

# COC — Clarify / Options / Commit

## 概要

COC は PAF の Proposal Phase で使用される3つのオペレータ。曖昧さを解消し、ユーザの意図を明確化する。

## オペレータ

### Clarify

- **用途**: 前提不足、解釈の競合
- **例**: 「スコープに X は含まれますか？」
- **制約**: 必要最小限に制限

### Options

- **用途**: 質的に異なる2つ以上の選択肢
- **例**: 「A案（コスト優先）と B案（速度優先）があります」
- **制約**: 無意味な選択肢を提示しない

### Commit

- **用途**: ユーザによる決定取得
- **例**: 「この方針で進めてよいですか？」
- **制約**: ユーザ起点

## Router との連携

Router は2軸の AND 条件でルーティング：

1. **Uncertainty**: 前提未決定、次ステップが一意でない
2. **Forward Intent**: 判断・設計・選択を求めている

両方 true の場合、Execution Lane に分配し COC 必要性を判定。

## 関連

- [[paf]] — COC は Proposal Phase 専用
- [[router]] — COC 発動判定
