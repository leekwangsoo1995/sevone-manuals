# Integration Manager

## 何をする場所か

AWS、Cisco Meraki、Juniper Mistなどの外部プラットフォームをSevOneへ取り込み、その統合の作成・状態確認・保守を一箇所で行う画面。DI 8.1.0では Integration Manager が統合の主導線であり、新規環境ではNMSのDevice Managerを代替する領域がある。

## 主な機能

- 対応するintegrationを選択し、新規integrationを追加する。
- 認証情報、API接続、SNMP資格情報、ネットワーク到達性、組織へのアクセス等の前提を確認し、統合をオンボードする。
- 統合が作成したNMSのデバイス、メタデータ、メトリックを、DIのReportsやData Source経由で可視化する。
- 対応製品・前提条件・設定項目はintegrationごとに異なるため、個別のQuick Startを参照する。

## どこから開くか

左ナビゲーションの Integrations。たとえばMerakiでは Integrations → Add new integration → Cisco Meraki の順に進む。

## 関連・遷移先

```text
Integrations → Integration Manager → 外部API / cloud / SDN
                                  └─ NMS上にdevice・metadata・metricsを作成
                                        └─ Data Sources → Reports / Flow Explorer
```

統合後の観測結果は[Data Sources](data-sources.md)、[メトリック](metrics-and-ranking.md)、[Flow](traffic-and-topology.md)で読む。収集対象の詳細確認が必要ならNMS側のDevicesへ進むが、統合由来の設定変更はIntegration Managerを正とする。

## 将来変更する場合の影響

- AWS pluginの設定は、NMS 8.1ではNMS Device ManagerではなくDIのIntegration Managerへ移行する方針である。
- 統合が作成・管理するdeviceをNMS Device Managerで直接編集すると、NMS画面とIntegration Managerの内容に不整合が生じ得る。変更はIntegration Managerで実施する。
- APIキー、接続先、SNMP資格情報、組織アクセスの変更は収集停止や再検出につながり得る。閲覧目的では変更せず、統合名・状態・対象範囲を説明する。
- Integration Managerに見える種類は導入済み機能・契約・バージョンに依存する。実機にない項目を前提にしない。

## 関連用語

integration、Integration Manager、API key、organization、collector、metadata、Meraki、AWS、Juniper Mist

## 公式出典

- [What's new in NPM 8.1](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=whats-new)
- [Cisco Meraki integration](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=integrations-meraki)
- [NPM 8.1 Statement of Direction: AWS configuration](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=new-statement-direction-npm-81)
- [Troubleshooting: editing integration devices](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=troubleshooting-topics)
