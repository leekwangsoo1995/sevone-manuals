# メトリックとランキング

## 何をする場所か

性能値を時系列で読み、上位・下位の対象を見つけ、グループ単位で比較するためのwidget群を置く場所。主に `Performance Metrics`、`TopN`、`Group Metrics` をReport Editorから追加して使用する。

## 主な機能

- **Performance Metrics**: Device Group、Object Group、Object等のインジケータを時系列で表示・分析する。Line、Bar、Pie、Gauge、Histogram、Trend、Table、Heatmap、Calendar Heatmapなどの表示を選べる。
- **TopN**: 指定条件で上位／下位のリソースを並べ、負荷が大きい対象の入口にする。
- **Group Metrics**: デバイス群またはオブジェクト群の平均・最小・最大・合計といった集約値を読む。
- Analyze設定では集約、単位、基準線、期間比較などを扱う。Charts設定は表示方法を扱う。

## どこから開くか

`Reports` → 対象Report → `Edit` → `Add widget`。閲覧時は対象widgetのタイトル、期間、Variables、Data Sourceから意図を読み取る。

## 関連・遷移先

```text
Performance Metrics / TopN / Group Metrics
  ├─ resource選択 → NMSのDevice Group / Device / Object
  ├─ Analyze → 集約・単位・時系列の読み方
  ├─ Charts → 表示形式
  └─ Linking / chaining → Alert Details、Flow、Logs、Metadata等
```

性能の異常を見つけた後は[アラート](alerts-and-context.md)、通信量や相手先の確認は[Flow](traffic-and-topology.md)へ進む。

## 将来変更する場合の影響

- 自動集約を無効にし細かい集約を長期間に適用すると、描画性能の悪化や結果が出ない原因になり得る。原則は自動集約を維持する。
- TopNの条件・対象範囲を変えると、ランキングの意味が変わる。比較対象のdevice groupと期間を併せて表示する。
- ひとつのReport sectionに多数のwidgetを置くと性能に影響し得る。IBMの作成ガイドは20超のwidget追加で性能問題が起こり得るとする。

## 関連用語

`indicator`、`aggregation`、`timespan`、`baseline`、`top N`、`device group`、`object group`、`heatmap`

## 公式出典

- [Create: available widgets and resource selection](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-create)
