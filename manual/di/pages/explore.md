# Flow Explorer

## 何をする場所か

保存済みReportを先に作らずに、フローデータを対話的に探索・集計・絞込みする画面。Report Viewerを含む利用者がアドホック分析と一次切り分けに使える。8.1.0の主要な新機能である。

## 主な機能

- Data Sourceを選び、Device group、Object group、Flow Source、Cloud Flowから分析対象を選択する。
- `Configure source`でリソースを定め、`Filters`で条件を追加し、`Advanced settings`でソート、DNS表示、粒度、bits/bytes、合計／平均レートを調整する。
- 表または折れ線等の表示、期間変更、更新間隔、stashを利用する。
- View modeとConfigure source modeを切り替え、必要ならReportへwidgetとして持ち帰る前段の探索に使う。

## どこから開くか

左ナビゲーションの `Flow Explorer`。Report内からのFlow widgetとは別画面であり、必要に応じて同じData Source・対象範囲で比較する。

## 関連・遷移先

```text
Flow Explorer → Configure source → Filters / Advanced settings → Draw graph
                                      └─ stash → Report内での再利用候補
Data Source / Flow Source / Cloud Flow → NMS側のflow収集と関連
```

データソースの接続・クラスタ状態は[Data Sources](data-sources.md)、保存済みの定常可視化は[Reports](session-and-reports.md)、性能値との対応確認は[メトリック](metrics-and-ranking.md)へ進む。

## 将来変更する場合の影響

- フィルタはすべてAND条件として適用される。結果が少ない／ない場合は有効なフィルタの組合せを確認する。
- `Reset`は配置されたwidgetをすべて削除し、元に戻せない。閲覧中は実行しない。
- 検索範囲・結果上限・期間・粒度は結果と性能を左右する。初期表示の過去2時間を基準に、必要な範囲だけ広げる。

## 関連用語

`Flow Source`、`Cloud Flow`、`filter`、`DNS resolution`、`granularity`、`stash`、`View mode`、`Configure source`

## 公式出典

- [Flow Explorer](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-flow-explorer)
- [What's new in NPM 8.1](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=whats-new)
