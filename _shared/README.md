# _shared — 全グループ共有リソース

## agents/
全グループが共有して使うエージェント定義ファイルです。
各グループの `.claude/agents/` からシンボリックリンクまたはコピーして使用します。

| ファイル | 役割 | 部門 |
|---------|------|------|
| `market-scout.md` | 8つのAPIとWEBアンケートからデータ収集（v4） | RESEARCH |
| `knowledge-curator.md` | ナレッジベースの照会・保存・管理 | LEARNING |
| `performance-analyzer.md` | 実務結果の評価・仮説照合 | LEARNING |
| `media-buyer.md` | 13チャネルへの入稿・配信設定・計測設定 | ACTION |

## skills/
複数のエージェントが共通して使う処理手順・計算式・フォーマットを定義したスキルファイルです。
エージェントのプロンプト内から参照して使用します。

| ファイル | 内容 | 使用するエージェント |
|--------|------|------------------|
| `cep-scoring.md` | CEPポテンシャルスコアの算出手順 | insight-analyst / content-strategist |
| `insight-structure.md` | インサイト4要素の構造化フォーマット | market-scout / insight-analyst |
| `abtest-design.md` | ABテスト16項目の設計テンプレート | campaign-executor / media-buyer |
| `utm-naming.md` | UTMパラメータの命名規則 | media-buyer / performance-analyzer |

## knowledge-base/
全グループが参照できる共通ナレッジです。

### market-insights/
market-scoutが収集した市場・競合・消費者情報を格納します。
各グループのmarket-insightsと連携して重複調査を防ぎます。

### learnings/
全グループ横断で確定した知識を格納します。

| ファイル | 内容 |
|---------|------|
| `brand-growth.md` | ブランド成長の確定原則（ダブルジェパディ等） |
| `cep-principles.md` | CEPマネジメントの確定知識 |
| `communication.md` | コミュニケーション戦略の確定知識 |
| `habit-principles.md` | 習慣形成・維持の確定知識 |
| `job-insights.md` | ジョブ理論・インサイトの確定知識 |

## templates/
新しいグループを作成する際のテンプレートファイルです。
`CLAUDE.md.template` と `agents/*.md.template` をコピーして使用します。
