# NMS：現在画面で読む代表要素

NMSでは、画面上の値が「収集対象」「収集したデータ」「監視条件」「発生したアラート」のどれに属するかを分けて読むと理解しやすくなります。日本語UIでの実際の表記は、ロールや導入済み機能によって異なることがあります。

## Dashboard

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Alert Summary、重大度別件数 | 現在または指定範囲のアラートの概況 | Alerts |
| Instant Status、色付きのグループ階層 | グループ配下の最も高いアラート状態を要約する表示 | Device Groups、Alerts |
| デバイス・アラートへのリンク | 個別の監視対象またはイベントを掘り下げる入口 | Device Manager、Alerts |
| グラフ・共有レポートへの導線 | NMSの状態表示から、より柔軟な可視化へ進む入口 | DI Reports |

## Device Manager

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Device Name、IP Address、Alternate Name | 監視対象機器の識別情報 | 名前とIPは同じ概念ではない |
| Device Group、Device Type | 所属・分類。アクセス、ポリシー、レポートの対象に使われる | 表示範囲は権限の影響を受ける |
| Objects、Poller、Polling Frequency | 収集対象数、収集を担当するPeer、収集間隔 | Object数があっても各指標の状態は別途確認する |
| Discovery、Queue、Last 24 Hours | 検出・収集の進行や最近の状態を読む手掛かり | 表示名や列は環境で異なる |
| Add / Edit / Deletion Queue | デバイス設定や削除待ちに関わる操作 | 閲覧用途では実行しない |

## Edit Device / New Device

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Name、IP Address、Peer | デバイスの識別と担当収集Peer | Device Manager、Cluster Manager |
| Plugin、SNMP設定、資格情報欄 | どの方式で何を収集するかの前提 | Object Manager、Plugin / Integration |
| Poll Frequency、Discovery | 収集・検出の更新頻度や実行状態 | Discovery Manager |
| Device Summary、Metadata | そのデバイスの状態・属性へ進む入口 | Object Manager、Groups / Metadata |

## Discovery Manager

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Watched Subnets | 検出候補を探索するネットワーク範囲 | Candidate |
| Candidates | 応答を確認したが、まだ監視デバイスとして確定していない候補 | Device Manager、Edit Device |
| Discovery Queue | ObjectやIndicatorの検出待ち・進行中の対象 | Device Manager、Object Manager |
| Peer、Queue、Start Time | 検出を担当するPeer、優先度、実行状況 | Cluster Manager |

## Object Manager / Object Summary

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Object Type、Object | インターフェース、CPUなどの種類と、その個別実体 | DeviceとObjectを混同しない |
| Indicator / Indicator Type | 個別に測定される値と、その種類 | DIのグラフ・表の選択対象になり得る |
| Auto、Enabled、Disabled | 自動ルールか、収集対象かを示す状態 | 手動設定は自動ルールを上書きし得る |
| Visible、Hidden | UI表示上の扱い | Hiddenでも収集・アラートの状態は別に確認する |
| Object Summary | 個別Objectの状態や関連情報を掘り下げる入口 | Alerts、Policy / Threshold |

## Device Groups、Object Groups、Metadata

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Group hierarchy、members、rules、pinned members | 分類対象と、その所属理由 | Policy、DIのResource選択 |
| Metadata key / value | DeviceやObjectに付ける属性 | DIのフィルター、Flowの対応付け |
| Device Group Access | グループ単位の閲覧・操作範囲 | User Role Manager |

## Alerts / Alert Summary

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Severity | 異常の重大度区分 | 重大度は原因や優先順位を単独で確定しない |
| Status、Acknowledged、Assigned、Comment | アラートの運用上の状態・担当・注記 | 確認応答は発生条件を消す操作ではない |
| First、Last | 最初の発生時刻と、最後に更新された時刻 | 選択中のタイムゾーン・期間を併せて読む |
| Device / Object / Threshold | どの対象と条件に紐づくアラートか | Device / Object Summary、Policy / Threshold |
| Archive | 現在アクティブでないアラートの履歴 | 表示条件で件数が変わる |

## Policy Browser / Threshold Browser

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Policy | 複数の対象に適用する監視・通知条件のまとまり | Device Group、Device Type、Alerts |
| Threshold | 値や状態をアラート条件にする定義 | 対象Device / Object、Alert |
| Trigger、Clear、Duration、Aggregation | 発生・復旧の判定と、評価方法 | 関連Alert、対象Indicator |
| Schedule、Notification | 条件を評価・通知する時間帯や宛先 | Administration |

## Cluster Manager

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Cluster、Peer、Appliance | NMSを構成する単位と担当ノード | 単一構成か複数Peerかで見え方が変わる |
| Capacity、License、health関連の値 | 利用量や全体の稼働状況を読む手掛かり | 画面上の状態だけで性能原因を断定しない |
| Cluster Settings、Peer Settings | NMS全体・Peer単位の設定 | 変更は広範囲に影響し得る |

## User / Role / Authentication

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| User | NMSを利用するアカウント | User Role |
| User Role、Page Permission | 画面・機能へのアクセス範囲 | Device Group Access |
| Device Group Access | どの監視対象を見られるか | Device Groups |
| Authentication、Session | 認証方式やログイン状態に関する領域 | DIのTenant / Team |

## Flow Configuration

| 観測できる要素 | 意味 | 次に確認する場所 |
| --- | --- | --- |
| Flow Source、Flow Device | フローを送信・受信する監視対象 | Device Manager |
| Flow Rules、Device / Object Mapping | 受信フローとNMSの対象を対応付ける定義 | DI Flow Explorer、Flow Widget |
| Apps / Protocols、Interface | フローを分類・集計するための属性 | DI Traffic / Topology |

## Plugins / Integrations

| 観測できる要素 | 意味 | 読むときの注意 |
| --- | --- | --- |
| Plugin | SNMP、VMwareなど、NMSがデータを収集する方式 | 利用可能なPluginは導入環境に依存する |
| Integration | 外部サービス・クラウド・SDN等との接続 | DI Integration Managerが主導線になるものがある |
| Pluginの資格情報・接続状態 | 収集の前提となる設定・到達性 | 閲覧用のQ&Aでは変更しない |

## 関連資料

- [NMS画面ガイド](README.md)
- [NMSのメニュー地図](navigation.md)
- [NMSとDIのデータの流れ](../cross-component/nms-to-di.md)
- [画面索引](../screen-index.md)
