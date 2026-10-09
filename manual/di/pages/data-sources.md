# Data Sources

## 何をする場所か

DIがデータを読む接続先を一覧・確認・管理する画面。通常はNMSクラスタが主要なData Sourceであり、NMSで収集されたmetricsとflowをReportやFlow Explorerへ供給する。ログ分析用にはElasticsearchまたはSplunkを接続できる。

## 主な機能

- 左ペインでActive Datasourcesを検索・選択する。
- 選択したData Sourceについて、`Cluster Status`、`Peers`、`Datasource Settings`を確認する。
- Connection Status（CONNECTED / DISCONNECTED / UNKNOWN）と、NMS 8.1以上で得られるHealth Status（OUTAGE / DEGRADED / INFO / HEALTHY）を確認する。
- NMS（Metrics/FlowまたはFlow）、Elasticsearch、SplunkのData Sourceを作成・編集する。
- ElasticsearchとSplunkはLogs widget向けであり、NMSのdevice名に対応する列マッピングを設ける。

## どこから開くか

左ナビゲーションの `Configure > Data Sources`。初回Quick Startで接続した既定Data Sourceもここに表示される。

## 関連・遷移先

```text
Quick Start → default Data Source → Reports / Flow Explorer
Data Sources → Cluster Status（クラスタ集約の健全性）
             → Peers（peerごとの状態）
             → Datasource Settings（接続情報）
```

Reportやwidgetで値が出ない場合は、ここで接続と健全性を確認した後、NMS側の収集、resource選択、tenant/team割当てを確認する。ログは[アラートとコンテキスト](alerts-and-context.md)で利用する。

## 将来変更する場合の影響

- Data Sourceの作成・編集・削除は、それを参照するReport、widget、teamの表示に影響する。
- Data Sourceはtenantに関連付ける必要がある。接続済みでもtenantに割り当たらなければ期待する利用者に見えない。
- Connection Statusは接続可否、Health Statusは到達可能なData Source内の問題度合いであり、別の観点である。
- 認証情報、API URL、列マッピングの変更は収集・ログ表示を止め得るため、閲覧用アカウントでは操作しない。

## 関連用語

`NMS (Metrics/Flow)`、`NMS (Flow)`、`Cluster Status`、`Peer`、`CONNECTED`、`Health Status`、`Elasticsearch`、`Splunk`

## 公式出典


- [Data Sources](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=configure-data-sources)
