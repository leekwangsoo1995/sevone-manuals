# Tenants、Teams、Themes

## 何をする場所か

DIの利用範囲を分ける管理画面群。Tenantはデータと利用者の論理区画、Teamはtenant内の利用者とData Sourceのまとまり、Themeは見た目の設定である。少人数の新規環境でも、閲覧者がどのtenant/teamで見ているかはReportの見え方を左右する。

## 主な機能

- **Tenants**: tenantの作成・変更、Data Source・メタデータを基にした可視範囲、利用可能Themeの管理。
- **Teams**: tenantに属するteamの作成・変更・削除、関連Data Source、メンバー、レポートバージョン保持の設定。
- **Themes**: System Light / System Darkの切替と、権限がある場合のcustom themeの管理。
- ユーザー名メニューの `Change Tenant` / `Change Team` で、現在の閲覧コンテキストを切り替える。

## どこから開くか

- `Administer > Tenants`
- `Administer > Teams`
- `Configure > Themes`
- 表示中のtenant/teamの切替: 左ナビゲーションのユーザー名メニュー。

## 関連・遷移先

```text
Tenant → Data Source / metadataによる可視範囲 → Reports
Tenant → Teams → members + associated Data Sources → Report permissions
User menu → Change Tenant / Change Team / Change Theme
```

1つのtenantに複数teamがある場合、Report SettingsのMulti-team共有が利用できる。複数tenantを構成する場合は、Reportの共有範囲とData Source割当てを併せて確認する。[Reports](session-and-reports.md)と[Data Sources](data-sources.md)が主な接続先である。

## 将来変更する場合の影響

- tenantやteamへの利用者・Data Sourceの割当て変更は、ログアウト・再ログインが必要になることがある。8.1.0では新しいteamに利用者を追加後、再ログインして反映する。
- reportのPublic、Restricted、Multi-team、Multi-tenant等の共有設定は、tenant/team構造と連動する。ownerは常に完全権限を持つ。
- Teamに複数Data Sourceを追加しても、認可ソースの適切なrole IDを持つ利用者だけがメンバー候補となる。異なるData Sourceにまたがるメンバーを単純に定義できるわけではない。
- custom themesは見た目を変える共有資産であり、Super AdminまたはTenant Adminでのみ扱える。

## 関連用語

`tenant`、`team`、`member`、`role ID`、`owner`、`Public`、`Restricted`、`Multi-team`、`Multi-tenant`、`System Light`、`System Dark`

## 公式出典

- [Teams](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=administer-teams)
- [Reports: multi-tenant / multi-team access](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-reports)
- [Login: tenant, team, theme switching](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=guide-login)
