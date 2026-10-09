# アラートとコンテキスト

## 何をする場所か

アラートの詳細・件数・重大度を、対象リソースと期間に結び付けて見るためのwidget群。主に `Alert Details`、`Alert Summary`、必要に応じて `Logs` と `Metadata` をReport Editorで使う。

## 主な機能

- **Alert Details**: 指定リソースの重大度、発生時刻・回数、メッセージなどを詳細に表示する。
- **Alert Summary**: 重大度またはリソースごとに、アラート数または発生回数を集計する。概要から詳細への入口になる。
- **Logs**: Elasticsearch / SplunkをData Sourceにしたログを、アラートと同じReportの文脈で確認する。
- **Metadata**: NMSのメタデータを表示し、所属・場所・分類などの補助情報を添える。

## どこから開くか

`Reports` → 対象Report → `Edit` → `Add widget`。Alert SummaryからAlert Details／Logsへchainingする構成が代表例である。

## 関連・遷移先

```text
Alert Summary（件数・重大度の概観）
  ├─ chaining → Alert Details（個別の発生内容）
  └─ chaining → Logs（周辺ログ）
Alert Details → NMS側の対象device / object、Performance Metrics、Flow
```

対象の性能推移は[メトリック](metrics-and-ranking.md)、通信の内訳は[Flow](traffic-and-topology.md)、ログ接続は[Data Sources](data-sources.md)を参照する。

## 将来変更する場合の影響

- アラートwidgetのresource選択を空にしたままReport Linkingを設定すると、8.1.0の既知問題によりエラーとなる場合がある。対象リソースを明示する。
- 集計を重大度、リソース、件数、発生回数のどれにするかで意味が異なる。閲覧時にタイトルだけで判断せず設定を確認する。
- Logs widgetを使うには、ElasticsearchまたはSplunkのData Sourceと列マッピングが必要になる。

## 関連用語

`severity`、`occurrence`、`Alert Details`、`Alert Summary`、`Logs`、`Metadata`、`chaining`

## 公式出典

- [Create: widgets and chaining](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-create)
- [DI 8.1.0 Release Notes: known issue](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=notes-release-sevone-data-insight-810)
