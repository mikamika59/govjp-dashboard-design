---
name: govjp-dashboard-design
description: デジタル庁「ダッシュボードデザインの実践ガイドブック」に基づく配色トークン・レイアウト原則・グラフ選定ルール・アクセシビリティ基準を適用するスキル。Mikaがダッシュボード、KPIレポート、資料、スライド、Excel集計、社内向けの数値可視化アプリ（HTML/React含む）など、データを見せる成果物をClaudeに作らせる時は、明示的に「デジタル庁のガイドラインで」と言われなくても積極的にこのスキルを使うこと。"dashboard", "ダッシュボード", "データ可視化", "KPIレポート", "グラフ", "資料のデザイン", "見やすく可視化" 等のキーワードで発火する。
---

# デジタル庁ダッシュボードデザインガイドブック 適用スキル

## これは何か

デジタル庁が公開している「ダッシュボードデザインの実践ガイドブックとデザインテンプレート」の考え方（制作プロセス／グラフ選定／レイアウト／7色のカラーパレット／アクセシビリティ基準）を、Claudeが作るあらゆる成果物（資料・スライド・スプレッドシート・HTML/Reactアプリ等）に適用するためのスキル。

出典・原本：
- ガイドブック本体：https://www.digital.go.jp/resources/dashboard-guidebook
- カラーパレット詳細：https://www.digital.go.jp/resources/dashboard-guidebook/color-palette
- カラーコード一覧：https://www.digital.go.jp/resources/dashboard-guidebook/color-palette/color-code
- 配色テーマJSON・Power BIテンプレート原本（GitHub, PDL1.0）：https://github.com/digital-go-jp/policy-dashboard-assets

このスキル内のテキストは上記の要点を要約・パラフレーズしたものであり、原文の逐語転載ではない。正確な文言や図版が必要な場合は上記リンク先（PDF本体22MB）を直接参照すること。色コード自体は事実データなのでそのまま使ってよい。

## 使うタイミング

以下のような依頼が来たら、明示的な指示がなくてもこのスキルを適用する。

- ダッシュボード、KPIサマリー、経営会議資料、週次/月次レポートなど、数値を人に見せる資料・アプリを作る
- 「グラフを整理して」「見やすく可視化して」「配色を考えて」といった相談
- pptx/xlsx/docx/HTML/Reactでチャートや指標カードを含む成果物を作る
- 過去にこのスキルで選んだパレット（例：Blue）を継続して使ってほしいと言われた場合

逆に、単なる数値の計算・分析や、可視化を伴わないテキスト作成にはこのスキルは不要。

## 使い方（進め方）

1. **目的を確認する**：誰が・何を判断するために見るのかが不明なら一言だけ確認する（5W1H、詳細は`references/design-principles.md`）。ただし依頼がすでに具体的なら聞き直さず、妥当な前提を置いて進めてよい。
2. **パレットを選ぶ**：指定がなければ既定は `Blue`。ブランドカラーや文脈（警告系ならRed、環境・成長系ならGreen等）に応じて7色（SolidGray/Blue/LightBlue/Cyan/Green/Orange/Red）から選ぶ。色の正確な値は `references/color-palettes.json` を参照する。
3. **グラフの種類を選ぶ**：データの性質（時系列／比較／構成比／相関／地理）に応じて `references/design-principles.md` の選定表に従う。
4. **レイアウトを組む**：16:9・2〜6分割グリッド、全体→詳細の情報階層、フィルターの位置などのルールを適用する。
5. **フォーマットに落とし込む**：pptx/xlsx/docx/HTML・Reactそれぞれの具体的な適用方法は `references/format-application.md` を参照し、該当する他のスキル（pptx, xlsx, docx, frontend-design）と併用する。
6. **最終チェック**：`references/design-principles.md` 末尾のチェック観点（利用者体験／グラフデザイン／テクニカル／データ設計／アクセシビリティ）で見直す。特にコントラスト比（背景×グラフ3:1以上、テキスト4.5:1以上）と「色だけに頼っていないか」は必ず確認する。

## 参照ファイル

- `references/color-palettes.json` — 7パレット × Text/Background/Chart/Semantic の正確なカラーコード（機械可読）
- `references/design-principles.md` — 制作プロセス、グラフ選定ルール、Do's/Don'ts、レイアウト、アクセシビリティ、最終チェック観点
- `references/format-application.md` — pptx / xlsx / docx / HTML・React それぞれへの具体的な適用方法とCSS変数の例

## ライセンス・出典に関する注意

デザインテンプレート（.pbit）・カラーテーマ（.json）は公共データ利用規約（PDL1.0）が適用される。**改変・加工して使う場合は出典明記は不要**。**無改変で公開する場合のみ**下記の出典を明記する。

> 出典：デジタル庁 ダッシュボードデザインの実践ガイドブックとデザインテンプレート https://www.digital.go.jp/resources/dashboard-guidebook

行政区域ポリゴンデータ（地図）を使う場合は国土交通省「国土数値情報ダウンロードサイト」の利用規約を別途確認すること：https://nlftp.mlit.go.jp/ksj/other/agreement.html
