# 利用開始ガイド：現在画面を説明するためのフォールバック

これは順番に読むチュートリアルではありません。通常は、Playwright MCPで取得した**現在画面の見出し・メニュー・表・状態ラベル**を [画面索引](screen-index.md) で引き、必要な画面資料だけを参照します。

このページを使うのは、画面がNMSかDIか分からない場合、画面名を同定できない場合、または利用者が製品全体の関係を質問した場合です。

## 通常の使い方：現在画面から答える

1. **現在画面を観測する。** ページ見出し、選択中の左メニュー、パンくず、タブ、表の列名、カード・グラフの題名、現在のフィルター、期間、Data Source / Tenant / Team、状態表示を確認します。
2. **質問された要素を特定する。** たとえば「Severity列」「No data表示」「このWidget」「Apply Filterボタン」のように、実際のラベルで扱います。
3. **画面索引で該当資料を引く。** 見出しや選択中メニューを最優先に、1〜2件の候補へ絞ります。
4. **見えている範囲だけを説明する。** その要素が何を示すか、現在の選択条件の意味、関連して確認できる画面を答えます。
5. **不明なら追加観測を一つ依頼する。** 例: 画面見出し、現在のData Source、期間、表の列名、対象Device。

画面の同定には、**画面見出し > 選択中メニュー > タブ名 > 表の列名 > ボタン名 > URL断片**の順で使います。

## NMS と DI を見分ける

| 観点 | SevOne NMS | SevOne Data Insight (DI) |
| --- | --- | --- |
| 主な役割 | デバイスからの収集、監視対象の定義、監視状態・アラートの管理 | NMS のデータをレポート、ダッシュボード、分析画面として可視化 |
| 画面で出会いやすい語 | Device、Object、Discovery、Policy、Threshold、Alert、Plugin | Report、Widget、Data Source、Tenant、Team、Flow Explorer、Instant Graph |
| 代表要素集 | [NMS](nms/screen-cues.md) | [DI](di/screen-cues.md) |

製品名がUI上に出ていないときも、表示語から候補を出します。確証がなければ「推定」と明記し、画面名・URL・見出しを追加で確認します。

## 要素の意味を説明するときの確認順

1. **画面の役割** — 何を一覧・表示・管理する場所か。
2. **現在の対象範囲** — 選択中のデバイス、オブジェクト、グループ、期間、テナント、チーム、データソースは何か。
3. **要素の種類** — 状態、計測値、設定値、フィルター、または操作か。
4. **今回の表示から読めること** — 実際に観測できる事実だけ。
5. **隣接する確認先** — より詳しく読むための画面・タブ。

共通の回答形式は [現在画面を説明する方法](how-to-explain-current-screen.md) を参照してください。

## 画面を同定できないときの入口

| 見たいこと | まず参照する資料 |
| --- | --- |
| 監視している機器や収集対象 | [NMS: Devices / Discovery](nms/pages/devices-and-discovery.md) |
| 指標・状態・しきい値 | [NMS: Objects / Monitoring](nms/pages/objects-and-monitoring.md) |
| アラートや通知 | [NMS: Alerts / Rules](nms/pages/alerts-and-rules.md) |
| 通信量・フロー | [NMS: Flow Monitoring](nms/pages/flow-monitoring.md)、[DI: Traffic / Topology](di/pages/traffic-and-topology.md) |
| グラフ、表、レポート | [DI: Session / Reports](di/pages/session-and-reports.md)、[Report Editor](di/pages/report-editor.md) |
| NMSからDIへの到達 | [NMS と DI の接続](cross-component/nms-to-di.md) |
| 権限・表示範囲 | [NMS: Access / Authentication](nms/pages/access-and-authentication.md)、[DI: Tenants / Teams](di/pages/tenants-teams-and-themes.md) |

## 全体像を説明するときだけ使う資料

NMSでデータを収集・整理し、DIでそのデータを報告・分析する関係は [全体像](overview.md) と [NMS と DI の関係](cross-component/nms-to-di.md) にまとめます。

## 出典

- [SevOne NMS User Guide 8.1.0（日本語）](https://www.ibm.com/docs/ja/sevone-npm/8.1.0?topic=guides-sevone-nms-user-guide)
- [SevOne Data Insight User Guide 8.1.0（英語）](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guides-sevone-data-insight-user-guide)
- [Data Insight 8.1.0: Login / 初回セットアップ](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-login)
