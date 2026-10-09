# SevOne NMS / Data Insight 8.1.0 ローカル・ガイド

IBM SevOne NMS と SevOne Data Insight（DI）の画面を、初めて使うチームとコーディングエージェントが**現在画面を見ながら説明する**ための、オフライン参照用の要約マニュアルです。対象は完全新規導入の NMS / DI 8.1.0 と日本語 UI です。

このリポジトリは IBM Docs の複製ではありません。画面の目的、主な表示要素、隣接する画面、NMS と DI の責務分担を短くまとめています。

## まず使う資料

通常は、画面を最初から説明せず、Playwright MCPで取得した見出し・メニュー・表・フィルター・状態ラベルを入口にします。

- [画面索引](manual/screen-index.md) — 観測したラベルから該当する画面資料を引く
- [現在画面を説明する方法](manual/how-to-explain-current-screen.md) — 要素単位のQ&Aの読み方
- [NMSの代表的な画面要素](manual/nms/screen-cues.md)
- [DIの代表的な画面要素](manual/di/screen-cues.md)
- [エージェント向け利用ルール](AGENTS.md)

画面を同定できないとき、または全体像を説明するときだけ、次を使います。

- [利用開始ガイド（フォールバック）](manual/START_HERE.md)
- [全体像](manual/overview.md)
- [用語集](manual/glossary.md)
- [目的別の画面案内](manual/cross-component/navigation-by-purpose.md)

画面別のガイドは以下に分かれます。

- [NMS](manual/nms/README.md): データ収集、監視、通知、管理
- [DI](manual/di/README.md): 可視化、分析、レポート
- [横断ガイド](manual/cross-component/README.md): NMS と DI の関係
- [公式ソース一覧](sources/links.md): バージョン固定の IBM Docs へのリンク

## 読み方と対象外

1. 現在画面の要素を観測し、画面索引から該当する資料だけを探します。
2. 画面要素集と画面ガイドから、実際に見えている項目の意味を説明します。
3. 詳細な手順や正式な仕様が必要なら、ページ末尾の公式出典を参照します。

本書は画面説明・閲覧を主目的にしています。変更操作の詳細手順、実環境の画面照合、CSS セレクター、個別の障害切り分けは扱いません。画面で変更できる内容がある場合も、影響の見当を付けるための説明に留めます。

## 版と前提

- 対象製品: IBM SevOne NMS 8.1.0 / SevOne Data Insight 8.1.0
- 想定UI: 日本語。IBM が英語のみで説明している固有名詞は英語を併記します。
- 想定導入: 完全新規環境
- 想定利用者: 管理者・作業者。表示されるメニューはロールと権限によって異なります。

DI 8.1.0 は NMS 8.1.0 以前に接続できます。機能の完全性と運用上の分かりやすさのため、このリポジトリでは同一版の組合せを前提に説明します。詳細は [DI 8.1.0 リリースノート](https://www.ibm.com/docs/en/sevone-npm/8.1.0?topic=notes-release-sevone-data-insight-810) を参照してください。

## 更新の考え方

製品版を上げる場合は、まず sources/links.md の URL を新しい版へ更新し、Release Notes を確認したうえで、影響がある画面群だけを更新します。公式資料の本文・画像の転載は行わず、簡潔な要約と原典リンクを維持してください。
