# SevOne Data Insight (DI) 8.1.0

SevOne Data Insight 8.1.0（DI）を初めて見る管理者・作業者向けの画面地図です。手順書ではなく、画面の目的、他画面とのつながり、変更時の影響を簡潔に説明します。日本語UIでも製品ラベルが英語のことがあるため、画面名は原則英語を併記します。

## DI が担うこと

- NMS が収集・保管するメトリック、フロー、アラートを、レポートとウィジェットで可視化・分析する。
- データソース、テナント、チーム、レポート権限を管理する。
- 8.1.0では Flow Explorer、Data Sources のクラスタ健全性、Device Groups、Integration Manager が重要な入口である。

## 読み方

1. 画面の位置は [navigation.md](navigation.md)。
2. DI と NMS の役割・用語は [concepts.md](concepts.md)。
3. 現在の画面に近い項目を `pages/` から開く。

## ページ一覧

- [セッションと Reports](pages/session-and-reports.md)
- [Report Editor と共通操作](pages/report-editor.md)
- [メトリックとランキング](pages/metrics-and-ranking.md)
- [アラートとコンテキスト](pages/alerts-and-context.md)
- [Flow、Maps、Topology](pages/traffic-and-topology.md)
- [Flow Explorer](pages/explore.md)
- [Data Sources](pages/data-sources.md)
- [Tenants、Teams、Themes](pages/tenants-teams-and-themes.md)
- [Integration Manager](pages/integrations.md)

## 境界と版の注意

実機の権限、導入済みプラグイン、画面ラベルは環境で異なるため、画面タイトルと左ナビゲーションで同定する。本ガイドは個別設定手順、全widgetの詳細、selectors、実機照合を扱わない。対象は **DI 8.1.0 + NMS 8.1.0** であり、IBM は両者を同一版に保つことを推奨している。NMS上のデバイス・オブジェクト名を変更すると、固定名を使うDIレポート変数が壊れることがある。

## 公式出典

- [DI User Guide 8.1.0](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guides-sevone-data-insight-user-guide)
- [DI 8.1.0 Release Notes](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=notes-release-sevone-data-insight-810)
- [What's new in NPM 8.1](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=whats-new)
