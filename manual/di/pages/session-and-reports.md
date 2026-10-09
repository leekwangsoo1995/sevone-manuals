# セッションと Reports

## 何をする場所か

ログイン、tenant選択、保存済みレポートの一覧・閲覧を行う入口。新規導入時はQuick StartでNMSを接続した後、Report Managerが最初の通常画面になる。

## 主な機能

- NMS資格情報によるログイン。マルチtenant時はtenant名も入力する。
- Report Managerで標準（OOTB）・共有・自分のレポートを探し、開き、作成する。
- 開いたレポートでは表示／編集の切替、widgetのstash、設定、アクセス権、スケジュール、バージョンを扱う。
- OOTBレポートは初回プロビジョニング時に読み込まれ、削除や管理者だけへの非表示にはできない。

## どこから開くか

- ログイン: DIのURL。
- 初回: ログイン後の **SevOne NPM Quick Start**。
- 通常: 左ナビゲーションの `Reports`。
- tenant切替: ユーザー名メニューの `Change Tenant`（マルチtenant時）。

## 関連・遷移先

```text
Login → Quick Start（新規のみ）→ Report Manager
Report Manager → 個別 Report → Edit / View → Widget settings
Report settings → Permissions / Schedule / Versions
```

分析対象の変更は [Report Editor](report-editor.md)、接続確認は [Data Sources](data-sources.md)、閲覧範囲は [Tenants / Teams](tenants-teams-and-themes.md) へ進む。

## 将来変更する場合の影響

- レポートの作成・編集・削除は共有者のビューに影響する。特にPermissionsとownerは慎重に扱う。
- OOTBレポートは削除できない。用途別の変更は複製して扱う。
- tenant切替により、見えるレポート・チーム・Data Sourceは変わる。

## 関連用語

`tenant`、`team`、`OOTB report`、`Report Manager`、`permissions`、`schedule`、`version`、`stash`

## 公式出典

- [Login and Quick Start](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-login)
- [Reports](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-reports)
