# govjp-dashboard-design（Claude Skill）

デジタル庁「ダッシュボードデザインの実践ガイドブックとデザインテンプレート」の考え方を、Claudeで資料・スライド・スプレッドシート・アプリを作るときに適用するためのスキルです。

- 出典：https://www.digital.go.jp/resources/dashboard-guidebook
- カラーコード：https://www.digital.go.jp/resources/dashboard-guidebook/color-palette/color-code
- 配色データ原本（GitHub, PDL1.0）：https://github.com/digital-go-jp/policy-dashboard-assets

このリポジトリはMika Uenoが個人で保守する、会社に紐づかないスキルです。MacBook Proを機種変更しても、Synesthesia Lab以外の会社のClaude環境で作業する場合でも、このリポジトリから中身をコピー／インポートすれば同じ配色・原則を再現できます。

## 中身

```
govjp-dashboard-design/
├── SKILL.md                        本体：いつ使うか・進め方・参照先
├── README.md                       このファイル
└── references/
    ├── color-palettes.json         7色パレット × Text/Background/Chart/Semanticの正確なカラーコード
    ├── design-principles.md        制作プロセス・グラフ選定・Do's/Don'ts・レイアウト・アクセシビリティ
    └── format-application.md       pptx/xlsx/docx/HTML・Reactへの具体的な適用方法
```

## 使い方（環境別）

### 1. claude.ai（自分のアカウント、Web/モバイル/デスクトップ）
設定 → スキル（Capabilities/Skills）からアップロード。アカウントに紐づくので、同じアカウントであればMacBook Proを機種変更しても、iPhoneや新しいMacからも自動的に使える。**このケースだけならGitHubがなくても持ち運べるが、他社のClaude環境には引き継がれない。**

### 2. 他社のClaude環境（会社支給のClaude Team/Enterprise等、別アカウント）
このリポジトリをそのままアップロードできない場合は、以下のいずれかで持ち込む。
- `SKILL.md` と `references/` の中身をコピーして、Claude ProjectsのProject Knowledgeやカスタム指示に貼り付ける
- Claude Codeなら `.claude/skills/govjp-dashboard-design/` にこのリポジトリをそのままclone/配置する
- 会話の中でこのGitHubリポジトリのURL（またはraw.githubusercontent.comのURL）を渡し、「このスキルを読み込んで適用して」と伝える

### 3. Claude Code
```bash
git clone https://github.com/<your-github-username>/govjp-dashboard-design.git .claude/skills/govjp-dashboard-design
```

## 更新について

デジタル庁側でカラーコードやガイドブックが更新された場合（更新履歴は本家サイト参照）、`references/color-palettes.json` の値を見直し、コミットしておくと全環境に反映しやすい。

## ライセンス・出典に関する注意

デジタル庁が公開する配色データ・テンプレートは公共データ利用規約（PDL1.0）に基づく。**改変・加工して使う場合は出典明記は不要**。**無改変で公開する場合のみ**下記を明記する。

> 出典：デジタル庁 ダッシュボードデザインの実践ガイドブックとデザインテンプレート https://www.digital.go.jp/resources/dashboard-guidebook

本リポジトリの `SKILL.md` / `references/*.md` 内の説明文はMikaおよびClaudeによる要約・パラフレーズであり、ガイドブック原文の逐語転載ではない。
