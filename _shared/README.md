# _shared — 全グループ共有リソース

## agents/
全グループが共有して使うエージェント定義ファイルです。
各グループの `.claude/agents/` からシンボリックリンクまたはコピーして使用します。

| ファイル | 役割 |
|---------|------|
| `market-scout.md` | 8つのAPIとWEBアンケートからデータ収集（v4） |
| `knowledge-curator.md` | ナレッジベースの照会・保存・管理 |
| `performance-analyzer.md` | 実務結果の評価・仮説照合 |

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
