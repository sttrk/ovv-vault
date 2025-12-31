---
type: cdc_summary
cdc_id: CDC-2024-001
trigger: blocked
date: 2024-12-31
resolved: true
---

# force_once フラグ保持バグ

## Observation

!force コマンド実行後、推論は成功するが force_once フラグが消費されない問題が発生。

## Impact

- フラグが永続的に true のまま
- Pre-PAF バイパスが無限に継続

## Action Taken

- update_pre_paf_state で既存の force_once を保持するよう修正
- consume_force_once が正しく呼ばれるように修正

## Lessons Learned

- 状態更新関数は既存フィールドを保持する必要がある
- イベントログで状態遷移を追跡することが重要
