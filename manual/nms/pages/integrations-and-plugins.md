# 統合とプラグイン

## 何をする場所か

統合とプラグインは、NMSの収集方法を広げ、外部システムとデータやイベントをやり取りする領域です。すべてを最初から有効化する場所ではなく、利用したい監視対象・通知先・分析機能に応じて必要なものを選ぶための入口です。

## 主な機能

- プラグインにより、SNMP、ICMP、WMI、外部データソースなどの収集を実装します。
- SNMPトラップ、Webhook、電子メールなどにより、NMSイベントを外部へ通知できます。
- REST APIを使う統合では、デバイス、アラート、ユーザー等の情報を扱えます。
- Wi-Fi、SD-WAN、Cloudなどの追加ソリューションは、導入済み機能に応じて画面が現れます。

## どこから開くか

**管理** のプラグイン、クラスタ設定、通知関連設定、または対象ソリューションの専用メニューから開きます。統合により入口が異なります。

## 関連・遷移先

- 取得したデータの対象 → [デバイスとディスカバリー](devices-and-discovery.md)
- 収集項目とルール → [オブジェクトと監視](objects-and-monitoring.md)
- 通知条件 → [アラートとルール](alerts-and-rules.md)
- APIの使用範囲と権限 → [アクセスと認証](access-and-authentication.md)

## 将来変更する場合の影響

プラグインや通知統合の変更は、ポーリング負荷、認証情報、外部チケット・監視システム、アラートの重複に影響します。統合ごとに所有者、認証方式、失敗時の通知、停止・復旧方法を確認します。

## 関連用語

プラグイン、SNMP、トラップ、Webhook、REST API、統合、資格情報、ソリューション。

## 公式出典

- [SNMP の使用可能化](https://www.ibm.com/docs/ja/sevone-npm/8.1.0?topic=guide-enable-snmp)
- [SevOne Data Platform エンドポイント・マッピング・ガイド](https://www.ibm.com/docs/ja/sevone-npm/8.1.0?topic=guides-sevone-data-platform-endpoint-mapping-guide)
- [SevOne NMS User Guide 8.1.0（日本語）](https://www.ibm.com/docs/ja/sevone-npm/8.1.0?topic=guides-sevone-nms-user-guide)
