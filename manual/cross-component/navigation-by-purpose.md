# 目的別の画面案内

画面名が分からない場合は、まずこの表から目的に近い入口を選びます。詳細はリンク先の NMS または DI の画面解説を参照してください。

| 目的 | 最初に開く場所 | 次に見る場所 | 主な製品 |
| --- | --- | --- | --- |
| 全体の状態を概観したい | NMS Dashboard | Alerts、Instant Status、Device Manager | NMS |
| 監視対象の一覧や状態を見たい | NMS Device Manager | Edit Device、Device Summary、Object Manager | NMS |
| 新しい機器が収集対象になっているか知りたい | NMS Discovery Manager | Candidates、Discovery Queue、Device Manager | NMS |
| ある機器で何を収集しているか知りたい | NMS Device Manager | Edit Device、Object Manager、Object Summary | NMS |
| しきい値やポリシーを確認したい | NMS Policy Browser / Threshold Browser | Device Groups、Object Groups、Alerts | NMS |
| 現在発生しているアラートを見たい | NMS Alerts | Device / Object Summary、Policy / Threshold | NMS |
| 時系列グラフやダッシュボードを見たい | DI Reports | Report、Widget、Instant Graphs | DI |
| 既存レポートを探したい | DI Report Manager | SevOne / Global / Personal Folders、Report Settings | DI |
| 一時的に性能を掘り下げたい | DI Instant Graphs | 対象 Device / Object / Indicator、関連 Report | DI |
| TopN、比較、集約を見たい | DI Report の TopN / Performance Metrics | 連携した Widget、Report Variables | DI |
| Flow を分析したい | DI Flow Explorer または Flow Widget | NMS Flow Configuration、関連 Report | DI → NMS |
| レポートにデータが出ない理由を切り分けたい | DI Data Sources | DI Report の対象設定 → NMS Device / Discovery / Object | DI → NMS |
| レポートの見える範囲を確認したい | DI Tenant / Team | NMS User Manager / User Role Manager | DI → NMS |
| 収集・レポートの新しい統合を確認したい | DI Integration Manager | NMSで作成された Device / Object、Data Sources | DI → NMS |

## 読み方

- **NMS** から始まるものは、監視対象そのものや収集・アラートの状態を確認する目的です。
- **DI** から始まるものは、収集済みデータの可視化・比較・共有を行う目的です。
- **DI → NMS** は、DIの結果から収集元・アラート条件へ戻るときに使います。

関連する全体像は [NMS から DI へのデータの流れ](nms-to-di.md) を参照してください。
