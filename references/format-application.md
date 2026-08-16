# フォーマット別の適用方法

`references/color-palettes.json` のトークンと `references/design-principles.md` の原則を、Claudeが実際に作成するアウトプット形式ごとにどう反映するかのガイド。

## 共通の進め方

1. まずパレットを1つ選ぶ（指定がなければ既定は `Blue`。既に社内/プロジェクトのブランドカラーがある場合はそれに一番近いパレットを選ぶ）。
2. `text` / `background` トークンをベース配色に、`chart` トークンをグラフの系列色に、`semantic` トークンを増減・達成状況の色分けに使う。
3. `/mnt/skills/public/xxx/SKILL.md`（pptx, xlsx, docx, frontend-design）の各スキルと**併用**する。本スキルは配色・レイアウト・グラフ選定の「何を」、各フォーマットスキルは「どう作るか」を担当する。

## PowerPoint（.pptx）

- テーマカラーとして `background.standard` をスライド背景、`background.highlight`（キーカラー）をタイトル・アクセントに使う。
- グラフの系列色は `chart.*` を上から順に割り当てる（多くて5系列まで）。
- 増減矢印・数値は `semantic.positive` / `semantic.negative` を使う。
- pptxスキルの標準テンプレートに、本スキルのグリッド原則（16:9・2〜6分割）とタイトル/凡例のシンプルさのルールを適用する。

## Excel（.xlsx）

- KPIセルの条件付き書式に `semantic.success` / `semantic.error` を使う。
- 表ヘッダーの背景に `background.control`、強調行に `background.highlight` を薄めて使う。
- グラフのデータ系列色を `chart.*` に設定する。

## Word（.docx）

- 見出し・強調ボックスの配色に `background.highlight` とその上のテキストに `text.textWhite`（コントラスト4.5:1を確認）を使う。
- 表のヘッダー行に `background.control` を使う。

## HTML / React アーティファクト（ダッシュボード風UI・簡易アプリ）

CSS変数として展開する例（Blueパレットの場合）：

```css
:root {
  --color-text-black: #000000;
  --color-text-white: #FFFFFF;
  --color-label: #626264;
  --color-link: #0017C1;
  --color-bg-standard: #F8F8FB;
  --color-bg-highlight: #0017C1;
  --color-bg-control: #F1F1F4;
  --color-chart-1: #3460FB; /* Blue600 */
  --color-chart-2: #7096F8; /* Blue400 */
  --color-chart-3: #C5D7FB; /* Blue200 */
  --color-chart-4: #D2A400; /* Yellow600 */
  --color-chart-5: #999999; /* SolidGray400 */
  --color-positive: #3460FB;
  --color-negative: #FE3939;
  --color-success: #197A4B;
  --color-error: #CE0000;
}
```

- recharts / chart.js を使う場合、`chart.*` の値を配列にして `colors` prop に渡す。
- レイアウトは16:9想定のダッシュボードなら `grid-template-columns: repeat(6, 1fr)` のような2〜6分割グリッドを基本にし、KPIカードを左上、詳細グラフを右・下に配置する。
- コントラスト比のチェックは実装後に目視 or ツールで確認する（背景×グラフ色 3:1以上、テキスト×背景 4.5:1以上）。

## 色以外の判別手段（アクセシビリティ）

どの形式でも、系列が2つ以上ある場合は色だけでなく、線種（実線/破線）・マーカー形状・直接ラベルのいずれかを併用する。
