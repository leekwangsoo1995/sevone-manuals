# DI：現在画面で読む代表要素

DIでは、まず「どのNMSデータを」「誰の範囲で」「どの期間・集約で」見ているかを確認します。同じWidgetやレポートでも、Data Source、Tenant、Team、Variables、Timespanによって意味が変わります。

## Login / Quick Start / User Menu

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Quick Start、NMS Details | 新規環境でNMSとDIを接続・初期化する入口 | 認証情報は画面説明に記録・出力しない |
| User menu、Change Team、Change Tenant | 現在の利用者コンテキストを切り替える入口 | 見えるレポート・データ範囲が変わり得る |
| Theme、Logout、Version | 表示・セッション・製品情報に関する要素 | 画面名の同定にも使える |

## Report Manager

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Quick Access、SevOne / Global / Personal Folders | レポートの分類・共有範囲の入口 | Report Settings、Tenant / Team |
| Name、Description、Owner | レポートの識別と所有者 | Report View、Settings |
| Last Updated、Last Opened | 更新・参照の時点 | 期間やデータ更新時刻とは別の値 |
| Favorite、Template、OOTB | 個人の参照設定、テンプレート、標準提供レポートの区別 | Report Editor |
| Run、Edit、Settings、Trash | レポートを表示・変更・管理する操作 | 閲覧時はRun / 表示情報を中心に読む |

## Report View / Report Editor

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Data Source | レポートが参照するNMSクラスタや外部ログ接続 | 同名の対象でもData Sourceが違えば別のデータになり得る |
| Timespan、Refresh、Rotate | 表示期間、自動更新、表示切替 | 「現在値」か履歴かを最初に確認する |
| Variables | 複数Widgetに共通で渡す対象・条件 | Widget個別のResource指定と混同しない |
| Section、Widget title | レポート内の表示単位 | titleだけでデータ対象を断定しない |
| View / Edit、Add widget、Save | 閲覧・編集モードと構成変更に関する操作 | Saveは共有レポートに影響し得る |
| Linking / chaining | 表の行やグラフの対象を関連Widgetへ渡す仕組み | 遷移先のWidgetが表示対象を引き継ぐことがある |

## Metrics / Ranking widgets

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Performance Metrics | 指標を時系列・表・ゲージなどで表示するWidget | 対象Resource、Timespan、Aggregation |
| TopN | 条件に対する上位・下位の対象を並べるWidget | 比較範囲、並び順、期間 |
| Group Metrics | Group単位の集約値を表示するWidget | Device / Object Group |
| Unit、Aggregation、legend、axis | 数値の単位、集計、系列、スケール | Data / Analyze / Charts設定 |
| Heatmap、Table、Trend | 同じ指標を異なる見せ方で表示する形式 | 表示形式とデータ内容を混同しない |

## Alert / Metadata / Log widgets

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Alert Details | 個々のアラートの対象・状態・時刻・条件を読むWidget | NMS Alerts、Device / Object |
| Alert Summary | 重大度や件数の概況を読むWidget | Alert Details、NMS Alerts |
| Metadata | 対象に付与された属性を読むWidget | NMS Groups / Metadata |
| Logs | 接続済みログソースのイベントを読むWidget | Data Sources |
| Acknowledge、Ignore、Assign、Comment | アラート運用に影響する操作 | 閲覧目的では実行しない |

## Flow / Maps / Topology widgets

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Flow | 通信量・送受信・相手・プロトコル等を条件で集計するWidget | 期間、方向、対象、フィルターを確認する |
| Maps | 位置・背景・レイアウト上で対象を読むWidget | 見た目の配置と監視設定を混同しない |
| Topology | デバイス間の物理・論理関係を表示するWidget | NMSで把握された関係・導入済み機能に依存する |
| focal device、hops、resource | 表示の中心対象・探索範囲 | 表示範囲がネットワーク全体とは限らない |

## Instant Graphs / Flow Explorer

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Instant Graphs | 保存済みレポートを作らずに指標を一時分析する画面 | Device / Object / Indicator、Report |
| Flow Explorer | フローデータを対話的に絞り込む画面 | Flow Widget、NMS Flow Configuration |
| Data Source、Flow Source、Filters | どの流入データをどの条件で分析するか | Data Sources、期間設定 |
| Draw graph、Advanced settings | 現在の条件で可視化する操作・詳細条件 | 実行前後のフィルター差分を確認する |

## Data Sources

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Active Datasources | DIが利用できる接続先の一覧 | 現在のTenant / Teamで見える範囲に依存する |
| Connection Status | DIとData Sourceの接続状態 | データ品質やNMS内の個別監視状態とは別の観点 |
| Health Status、Cluster Status、Peers | NMSクラスタ・Peerの健全性を読む入口 | 詳細はNMS Cluster Managerも参照する |
| Datasource Settings | 接続情報・種類に関する設定 | 変更はレポート・Teamの表示に影響し得る |

## Tenants / Teams / Themes

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Tenant | Data Source、NMS Role、metadata filterなどを束ねる利用範囲 | Data Sources、User Role |
| Team | 利用者・共有・Data Sourceの作業単位 | Report permissions |
| Members、Roles | だれがどの範囲を利用できるか | NMS User / Role |
| Theme | 表示テーマの利用範囲 | User menu |

## Integration Manager

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Integration name / type | 外部クラウド・SDN・サービスとの連携の識別 | 利用できる種類は導入・ライセンスに依存する |
| Status、対象範囲 | 統合の状態と取り込み対象 | NMS上のDevice / Objectと関連し得る |
| Add / Edit / credentials | 統合の作成・変更に関わる操作 | 閲覧目的では実行しない |

## 関連資料

- [DI画面ガイド](README.md)
- [DIのメニュー地図](navigation.md)
- [NMSとDIのデータの流れ](../cross-component/nms-to-di.md)
- [画面索引](../screen-index.md)
