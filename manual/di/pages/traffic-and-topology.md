# Flow、Maps、Topology

## 何をする場所か

通信量や通信相手を読む `Flow`、地理・論理的な文脈を与える `Maps`、デバイス間の物理・論理関係を描く `Topology` を、保存済みReport内で使う画面群。

## 主な機能

- **Flow widget**: NetFlow、sFlow、J-Flow、IPFIX等のフローデータを、期間・送受信・プロトコル・対象リソースで集計・絞込みする。
- **Maps**: リソースを地図またはキャンバス上で読み、アラートやメトリックを重ねる。位置情報・レイアウトがある場合に有用。
- **Topology**: NMSが把握したデバイスの物理接続・論理関係を、中心デバイスまたはデバイス集合の文脈で表示する。必要に応じてmetadataの緯度経度を使う。

## どこから開くか

`Reports` → 対象Report → `Edit` → `Add widget`。即時にフローだけを分析するなら、保存Reportではなく[Flow Explorer](explore.md)を使う。

## 関連・遷移先

```text
Flow widget → Performance Metrics（マップ済みinterfaceの性能）
Maps → Alert Details / Alert Summary / Metadata / Performance Metrics / TopN
Topology → Alert Details / Alert Summary / Metadata
```

Flowから性能へchainする場合、対象フローとNMSが管理するinterfaceの対応が必要。TopologyはNMSに収集・発見された関係を可視化するため、元データはNMS側にある。

## 将来変更する場合の影響

- Flowの対象を広く、粒度を細かく、長期間にすると実行が遅くなり、15分でタイムアウトする場合がある。範囲・期間・granularityを意識する。
- Mapsはレイアウト・背景・位置情報の変更が共有ビューへ影響する。地図要素はCSV/JSON出力できない。
- Topologyの見え方はNMSの検出データとmetadataに依存する。表示上の接続だけから設定済みの監視範囲まで断定しない。

## 関連用語

`NetFlow`、`sFlow`、`IPFIX`、`granularity`、`focal device`、`hops`、`metadata`、`Map mode`、`Canvas mode`

## 公式出典

- [Create: Flow / Maps / Topology and chaining](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-create)
- [Flow Explorer](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-flow-explorer)
