# DI のメニュー地図

## 画面同定の早見表

| 見えているもの | 主な入口 | 次に繋がる画面 |
| --- | --- | --- |
| レポートの一覧・検索・作成 | `Reports` | 個別Report、Report Settings、Report Editor |
| グラフや表のキャンバス | Reportsで対象を開く | widget設定、Variables、Report Linking |
| フローをその場で絞るグラフ | `Flow Explorer` | Configure source、Filters、Advanced settings |
| NMS接続先とクラスタ状態 | `Configure > Data Sources` | Cluster Status、Peers、Datasource Settings |
| 利用範囲・所属・見た目 | `Administer > Tenants / Teams`、`Configure > Themes` | tenant/team切替、レポート権限 |
| AWS・Meraki・Mist等の接続 | `Integrations` | Integration Manager、統合ごとの状態・設定 |

## 大まかなデータの流れ

```text
NMS 8.1.0（metrics / flow / alerts を収集）
  └─ Data Source（DIとの接続・健全性）
       └─ Tenant / Team（誰がどの接続先を見られるか）
            ├─ Reports（保存された可視化）→ Widgets / Variables / Linking
            └─ Flow Explorer（対話的なフロー分析）
```

## 初回導線（新規環境）

新規導入時、DIへアクセスすると **SevOne NPM Quick Start** が表示される。NMSクラスタのURLとNMS管理者認証情報で接続・プロビジョニングを完了すると **Report Manager** に遷移し、標準（OOTB）レポートが自動取り込みされる。

## 閲覧者の移動順

1. `Reports` で標準または共有レポートを開く。
2. 期間、Variables、Datasourceを確認し、対象を特定する。
3. フローの深掘りは `Flow Explorer`、データ到達性は `Configure > Data Sources`。
4. 見える内容が期待と異なる場合、現在の tenant と team を確認する。

## 将来変更する場合の影響

データソース、tenant、team、レポート権限、統合の変更は他利用者の可視範囲やレポート実行に波及する。閲覧目的のエージェントは変更ボタンを操作せず、対象画面と現在のtenantを説明する。

## 公式出典

- [Login / Quick Start](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-login)
- [Reports](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-reports)
- [Flow Explorer](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-flow-explorer)
- [Data Sources](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=configure-data-sources)
