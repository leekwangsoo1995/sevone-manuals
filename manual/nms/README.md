# SevOne NMS 8.1.0: 画面ガイド

完全新規で導入する **SevOne NMS 8.1.0** 向けの画面説明用要約です。NMSはデータ収集、監視対象管理、しきい値とアラートを担い、継続的な可視化、共有ダッシュボード、レポートは Data Insight (DI) を中心に扱います。

## 読み方

1. 現在地が分からないときは [メニュー地図](navigation.md)。
2. 用語やデータの流れは [基本概念](concepts.md)。
3. 表示中のメニューに近い画面群を `pages/` から選びます。

|目的|参照先|
|---|---|
|全体の状態を確認する|[ダッシュボード](pages/dashboard.md)|
|監視対象を登録・検出する|[デバイスとディスカバリー](pages/devices-and-discovery.md)|
|収集項目を把握する|[オブジェクトと監視](pages/objects-and-monitoring.md)|
|監視対象を整理する|[グループとメタデータ](pages/groups-and-metadata.md)|
|異常を確認・定義する|[アラートとルール](pages/alerts-and-rules.md)|
|通信フローを扱う|[フロー監視](pages/flow-monitoring.md)|
|利用者・権限を扱う|[アクセスと認証](pages/access-and-authentication.md)|
|クラスタや全体設定を扱う|[管理](pages/administration.md)|
|外部機能を把握する|[統合とプラグイン](pages/integrations-and-plugins.md)|

## 新規環境での原則

- 収集対象、アクセス、収集方法を整えてから、ポリシーと通知を設計します。
- NMS の旧レポート／Instant Graphs は既存資産の参照として扱い、新しい可視化資産は DI に作成します。
- 画面の表示と利用可否はロール、ライセンス、導入済みコンポーネントにより異なります。

## 公式出典

- [NMS User Guide 8.1.0（日本語）](https://www.ibm.com/docs/ja/sevone-npm/8.1.0?topic=guides-sevone-nms-user-guide)
- [SevOne NMS 8.1.0 資料一覧](https://www.ibm.com/docs/ja/sevone-npm/8.1.0)
- [Data Insight 8.1.0 リリース・ノート](https://www.ibm.com/docs/ja/sevone-npm/8.1.0?topic=notes-release-sevone-data-insight-810)
