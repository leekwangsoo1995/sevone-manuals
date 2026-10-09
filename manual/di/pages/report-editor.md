# Report Editor と共通操作

## 何をする場所か

レポートにwidgetを配置し、対象リソース、期間、Variables、表示形式、他レポート／widgetへの遷移を組み立てる画面。閲覧時には「このグラフが何を、どの条件で示すか」を理解する画面でもある。

## 主な機能

- widgetの追加、複製、全画面化、再読み込み、削除、CSV/JSON出力（対応widgetのみ）。
- widgetごとのData Sourceとresource type（Device Group、Device、Object Group、Object Type等）の選択。
- Variablesにより、閲覧者が対象デバイス群・デバイス・オブジェクト等を選べるレポートを作る。
- Report Linkingとwidget chainingにより、選択した値から詳細レポート／別widgetを開く。
- Report Settingsから名称、権限、スケジュール、バージョン管理へ進む。

## どこから開くか

`Reports`でレポートを開き、Editへ切り替える。新規レポートはReport Managerの作成ボタンから開く。

## 関連・遷移先

```text
Reports → Report Editor
  ├─ Add widget → Widget Settings → Data / resource selection
  ├─ Variables → 共有可能な対象選択
  ├─ Linking / chaining → 詳細 widget・別 Report
  └─ Report Settings → Permissions / Schedule / Versions
```

widgetの目的別説明は[メトリックとランキング](metrics-and-ranking.md)、[アラート](alerts-and-context.md)、[Flow・Maps・Topology](traffic-and-topology.md)を参照する。

## 将来変更する場合の影響

- Data Sourceやresource typeの変更は値の対象を変える。`Run`できない場合は、この二つの未選択を疑う。
- 固定値のVariablesを持つレポートはNMSのリソース改名で壊れ得る。
- chainingとreport linkingは渡す変数型が合う前提で機能する。追加後は受け側のVariablesも確認する。
- Maps、Text、URL widgetはCSV/JSON出力の対象外である。

## 関連用語

`widget`、`datasource`、`resource type path`、`variable`、`report linking`、`chaining`、`stash`、`Run`

## 公式出典

- [Create: widget resources, variables, chaining, export](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-create)
- [Reports](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-reports)
