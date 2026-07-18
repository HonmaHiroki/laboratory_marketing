# _shared — 全グループ共有リソース

## agents/
全グループが共有して使うエージェント定義ファイルです。
各グループの `.claude/agents/` からシンボリックリンクまたはコピーして使用します。

| ファイル | 役割 | 部門 |
|---------|------|------|
| `market-scout.md` | 8つのAPIとWEBアンケートからデータ収集（v4） | RESEARCH |
| `knowledge-curator.md` | ナレッジの照会・保存・管理（**Notion連携版**・toC①〜④専用） | LEARNING |
| `performance-analyzer.md` | 実務結果の評価・仮説照合（toC①〜④専用） | LEARNING |
| `media-buyer.md` | 13チャネルへの入稿・配信設定・計測設定 | ACTION |

toB（⑤ b2b-marketing）はナレッジ管理に別エージェント`b2b-marketing/agents/knowledge-curator-crm.md`（Twenty CRM連携版）を使用するため、
上記の`knowledge-curator.md`はtoCグループ専用です。

## skills/
複数のエージェントが共通して使う処理手順・計算式・フォーマットを定義したスキルファイルです。
エージェントのプロンプト内から参照して使用します。
詳細は `_shared/skills/README.md` を参照してください（全体共通スキルとtoB専用スキルを掲載）。

## ナレッジ保存基盤（GitHubファイルからの移行済み）

かつて存在した `knowledge-base/`（Markdownファイル）ディレクトリは廃止されました。
現在は以下のハイブリッド構成でナレッジを保存しています。

| 対象グループ | 保存基盤 | 担当エージェント |
|-----------|---------|--------------|
| toC①〜④ | Notion（4データベース：Market Insights／Hypothesis Log／Campaign Results／Learnings） | `_shared/agents/knowledge-curator.md` |
| toB⑤ | Twenty CRM（Company/Person/Opportunity＋カスタムオブジェクト） | `b2b-marketing/agents/knowledge-curator-crm.md` |

過去のファイルベースのナレッジが必要な場合はGit履歴を参照してください。

## templates/
新しいグループを作成する際のテンプレートファイルです。
`CLAUDE.md.template` と `agents/*.md.template` をコピーして使用します。
