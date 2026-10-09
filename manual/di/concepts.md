# DI の基本概念

## NMS と DI の役割

- **NMS**: デバイス、オブジェクト、インジケータ、フロー、アラートを監視・収集する基盤。
- **DI**: NMSをData Sourceとして接続し、収集済みデータをレポート、widget、Flow Explorerで読む可視化・分析層。

「DIにデータがない」は、レポート条件だけでなく、Data Source接続、NMS側の収集、tenantへの割当て、利用者権限を分けて見る。

## 主要語

| 用語 | 意味 | 関連画面 |
| --- | --- | --- |
| Data Source | DIが読むNMSクラスタ／アプライアンス、またはログ用接続 | Data Sources、widget |
| Tenant | データと利用者の論理的な区切り | Tenants、Teams、Reports |
| Team | tenant内で利用者とData Sourceを結ぶグループ | Teams、Report permissions |
| Report / Widget | 保存した可視化の単位／その部品 | Reports、Report Editor |
| Variable | 閲覧者が選ぶ対象・期間などの入力 | Report Editor |
| Report Linking / chaining | 選択値を別レポート・widgetへ渡す導線 | Report Editor |
| Flow Explorer | 保存前にフローを対話的に集計・絞込む画面 | Flow Explorer |

## 読み取り時の優先順

1. tenant と datasourceを特定する。
2. timespan と report variables を確認する。
3. widgetのresource範囲（device group、device、object等）と集計方法を読む。
4. その値がアラート、性能、フロー、ログのどれかを区別する。

## 変更に関する共通注意

DI 8.1.0はNMSのリソース名を参照する。NMSでデバイス・オブジェクト名を変えると、名前を固定したVariablesを持つレポートが機能しなくなることがある。リソース変更前に共有レポートとVariablesを確認する。

## 公式出典

- [Release Notes: version compatibility and resource names](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=notes-release-sevone-data-insight-810)
- [Select Widget Resources](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-create)
