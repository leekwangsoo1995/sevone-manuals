# NMS から Data Insight へのデータの流れ

対象: IBM SevOne NMS 8.1.0 と SevOne Data Insight 8.1.0 の新規環境。

## 役割分担

NMS は、ネットワークから監視データを収集し、監視対象・しきい値・アラートを管理する場所です。DI は、NMS をデータソースとして選択し、そのデータをレポート、ダッシュボード、グラフ、表、マップとして閲覧・分析する場所です。

| 知りたいこと・行いたいこと | 主に開く製品 | 補助的に開く製品 |
| --- | --- | --- |
| デバイスが登録・検出・ポーリングされているか | NMS | DI |
| オブジェクトや指標を収集する条件を管理したい | NMS | - |
| しきい値、ポリシー、アラートの発生源を確認したい | NMS | DI |
| 現在値、傾向、TopN、ダッシュボードを見たい | DI | NMS |
| フローを集計・比較・掘り下げたい | DI | NMS |
| NMS と DI の接続やデータソースの状態を見たい | DI | NMS |
| レポートを保存、共有、配信したい | DI | - |

## 概念上のデータ経路

```text
ネットワーク機器 / Flow 送信元
  ↓
NMS: Device
  ↓  (Plugin、Discovery、Polling)
NMS: Object / Indicator / Metric
  ├─→ NMS: Policy / Threshold → Alert
  └─→ DI: Data Source
             ↓
          Resource 選択（Device、Group、Object など）
             ↓
          Widget（グラフ、表、Alert、Flow、Map など）
             ↓
          Report / Dashboard / Export / Schedule
```

この図は画面の遷移そのものではなく、データと責務の流れです。たとえば DI のグラフが空の場合、DI のレポート設定だけでなく、NMS のデバイス登録、Discovery、Object、Polling まで戻って確認する必要があります。

## 代表的な画面のつながり

```text
NMS Dashboard
  → Device Manager → Edit Device → Object Manager / Device Summary
  → Alerts → Device / Object Summary → Policy / Threshold
  → Flow Configuration

DI Reports
  → Report 表示 → Widget / Report Editor
  → Instant Graphs / Flow Explorer
  → Data Sources
  → Tenant / Team / Integration Manager
```

### デバイスからレポートまで

1. NMS の **Device Manager** で、監視対象デバイスを確認します。
2. **Discovery** と **Object Manager** で、収集対象のオブジェクト・指標が見つかり、収集対象になっていることを確認します。
3. DI の **Data Sources** で、対象 NMS への接続を確認します。
4. DI の **Reports**、**Instant Graphs**、または **Flow Explorer** で対象データを選び、可視化します。

### アラートから原因を見るまで

1. NMS の **Alerts** で、アラートの重大度、対象デバイスまたはオブジェクト、発生条件を確認します。
2. **Device Summary** または **Object Summary** から状態・指標を確認します。
3. 発生条件は **Policy Browser** または **Threshold Browser** と関連します。
4. 時系列や同種機器との比較が必要なら、DI の Alert 系、Performance Metrics、TopN などのレポートへ進みます。

## データが見えないときの考え方

詳細な障害対応手順ではなく、確認する場所の順序だけを示します。

```text
DI の Data Sources は接続済みか
  → DI の対象 datasource / tenant / team は正しいか
    → Report または Widget の対象・時間範囲は正しいか
      → NMS に Device があるか
        → Discovery 済みの Object / Indicator があるか
          → Polling または Flow 収集が動いているか
```

## 権限と設定変更の境界

DI で見えるデータ範囲は、DI の Tenant・Team と、NMS のユーザー／ロール・デバイスアクセスの影響を受けます。表示されないことを「データがない」と即断せず、アクセス範囲も確認します。

目先の用途は閲覧と画面説明です。将来設定操作を行うときは、次のように担当を分けて考えます。

- **NMS での変更**: デバイス、収集、Object、グループ、ポリシー、しきい値、アラート、Flow の監視条件に影響します。
- **DI での変更**: レポート、Widget、共有、配信、Tenant、Team、Data Source、統合の表示・利用範囲に影響します。

## 新規環境での注意

NMS の従来型レポート機能には、新規導入では非推奨または利用できないものがあります。レポート、ダッシュボード、Instant Graphs、マップは、原則として DI 側の対応機能を入口にします。NMS では監視データを成立させるための設定・状態確認に集中します。

## 公式出典

- [SevOne NMS User Guide 8.1.0](https://www.ibm.com/docs/ja/sevone-npm/8.1.0?topic=guides-sevone-nms-user-guide)
- [SevOne Data Insight User Guide 8.1.0](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guides-sevone-data-insight-user-guide)
- [Data Sources](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=configure-data-sources)
- [Statement of Direction: NMS 8.1](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=new-statement-direction-npm-81)
