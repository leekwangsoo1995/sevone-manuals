# 画面索引：見えているラベルから資料を引く

この索引は、Playwright MCPで観測した見出し、選択中メニュー、タブ、表の列名、Widget名から、**必要な画面資料だけ**を探すためのものです。製品を順番に学ぶための目次ではありません。

## 使い方

1. 画面見出しまたは選択中メニューを最優先に、この表を検索します。
2. 候補の「参照先」と「代表要素集」を開き、実際に見える要素が一致するか確認します。
3. 一致しなければ、タブ名・表の列名・Data Source / Tenantなどの追加情報で再検索します。
4. ボタン名だけは複数画面に出るため、単独では画面を断定しません。

## NMS

| 観測キーワード・手掛かり | 画面群 | 参照先 | 代表要素集 |
| --- | --- | --- | --- |
| Dashboard、ダッシュボード、Alert Summary、Instant Status | 概況の入口 | [Dashboard](nms/pages/dashboard.md) | [NMS画面要素](nms/screen-cues.md#dashboard) |
| Devices、Device Manager、Add Device、デバイス名、IP、Poller | デバイス一覧 | [Devices / Discovery](nms/pages/devices-and-discovery.md) | [Device Manager](nms/screen-cues.md#device-manager) |
| Edit Device、New Device、Plugin、Poll Frequency、Device Summary | デバイス詳細 | [Devices / Discovery](nms/pages/devices-and-discovery.md) | [Device Detail](nms/screen-cues.md#edit-device--new-device) |
| Discovery Manager、Watched Subnets、Candidates、Discovery Queue | 検出状況 | [Devices / Discovery](nms/pages/devices-and-discovery.md) | [Discovery](nms/screen-cues.md#discovery-manager) |
| Object Manager、Object Type、Indicator、Enabled、Disabled、Hidden | 収集オブジェクト | [Objects / Monitoring](nms/pages/objects-and-monitoring.md) | [Object Manager](nms/screen-cues.md#object-manager--object-summary) |
| Device Groups、Object Groups、Metadata | 分類・絞り込み | [Groups / Metadata](nms/pages/groups-and-metadata.md) | [Groups / Metadata](nms/screen-cues.md#device-groups-object-groups--metadata) |
| Alerts、Severity、Acknowledged、Assigned To、Alert Archive | アラート運用 | [Alerts / Rules](nms/pages/alerts-and-rules.md) | [Alerts](nms/screen-cues.md#alerts--alert-summary) |
| Policy Browser、Threshold Browser、Trigger、Clear、Schedule | 監視条件 | [Alerts / Rules](nms/pages/alerts-and-rules.md) | [Policies / Thresholds](nms/screen-cues.md#policy-browser--threshold-browser) |
| Cluster Manager、Peer、Cluster Settings、Capacity | クラスター管理 | [Administration](nms/pages/administration.md) | [Cluster](nms/screen-cues.md#cluster-manager) |
| User Manager、User Role Manager、Authentication、Session | アクセス・認証 | [Access / Authentication](nms/pages/access-and-authentication.md) | [Access](nms/screen-cues.md#user--role--authentication) |
| Flow Configuration、Flow Rules、Flow Interface、NetFlow、sFlow、IPFIX | Flow収集 | [Flow Monitoring](nms/pages/flow-monitoring.md) | [Flow](nms/screen-cues.md#flow-configuration) |
| Plugin、SNMP、VMware、xStats、Integration | 収集方式・統合 | [Integrations / Plugins](nms/pages/integrations-and-plugins.md) | [Plugin / Integration](nms/screen-cues.md#plugins--integrations) |

## DI

| 観測キーワード・手掛かり | 画面群 | 参照先 | 代表要素集 |
| --- | --- | --- | --- |
| Login、Quick Start、Change Team、Change Tenant、Logout | ログイン・利用コンテキスト | [Session / Reports](di/pages/session-and-reports.md) | [Session](di/screen-cues.md#login--quick-start--user-menu) |
| Reports、Report Manager、SevOne Folders、Global Folders、Personal Folders | レポート一覧 | [Session / Reports](di/pages/session-and-reports.md) | [Report Manager](di/screen-cues.md#report-manager) |
| View、Edit、Add widget、Save、Variables、Timespan、Refresh、Rotate | レポート表示・編集 | [Report Editor](di/pages/report-editor.md) | [Report View / Editor](di/screen-cues.md#report-view--report-editor) |
| Performance Metrics、TopN、Group Metrics、Aggregation、Heatmap | 指標・ランキング | [Metrics / Ranking](di/pages/metrics-and-ranking.md) | [Metrics](di/screen-cues.md#metrics--ranking-widgets) |
| Alert Details、Alert Summary、Metadata、Logs、Acknowledged | アラート文脈 | [Alerts / Context](di/pages/alerts-and-context.md) | [Alert widgets](di/screen-cues.md#alert--metadata--log-widgets) |
| Flow、Maps、Topology、Canvas、focal device | 通信・地図・接続 | [Traffic / Topology](di/pages/traffic-and-topology.md) | [Flow / Maps / Topology](di/screen-cues.md#flow--maps--topology-widgets) |
| Instant Graphs、Flow Explorer、Draw graph、Filters | アドホック分析 | [Explore](di/pages/explore.md) | [Explore](di/screen-cues.md#instant-graphs--flow-explorer) |
| Configure、Data Sources、Cluster Status、Peers、CONNECTED、HEALTHY | データ接続 | [Data Sources](di/pages/data-sources.md) | [Data Sources](di/screen-cues.md#data-sources) |
| Administer、Tenants、Teams、Themes | 利用範囲・外観 | [Tenants / Teams](di/pages/tenants-teams-and-themes.md) | [Tenant / Team](di/screen-cues.md#tenants-teams--themes) |
| Integrations、Integration Manager、Meraki、Mist、AWS | 外部統合 | [Integration Manager](di/pages/integrations.md) | [Integrations](di/screen-cues.md#integration-manager) |

## どの行にも一致しない場合

- まず、画面が **NMS** か **DI** かを [START_HERE](START_HERE.md) で判断します。
- 次に、観測できた画面見出し、選択中メニュー、タブ名、表の列名をそのままローカル検索します。
- 一致が弱い場合は、候補を一つに断定せず、「このラベルとこのメニューが見えれば候補A」のように説明します。
- 新規機能、個別Plugin、ベンダー固有画面は、導入済みライセンス・統合・ロールによって出現しないことがあります。
