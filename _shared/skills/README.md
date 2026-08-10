# _shared/skills — 共有スキル定義

## スキルとは何か

スキルは「複数のエージェントが共通して使う具体的な処理手順・計算式・フォーマット」を定義したMarkdownファイルです。

### エージェント定義との違い

| | エージェント（agents/） | スキル（skills/） |
|--|-------------------|----------------|
| **役割** | 「誰が」担当するかの定義 | 「どうやって」実行するかの手順 |
| **粒度** | 1つの専門職・役割 | 1つの具体的な作業・計算・フォーマット |
| **呼び出し** | Taskツールでエージェントを起動 | エージェントのプロンプト内で参照・実行 |
| **状態** | 目的・原則・全体フロー | 入力→処理→出力の具体的なステップ |

### スキルの参照方法

エージェントのプロンプト内で以下のように参照する：

```
このタスクを実行する際は _shared/skills/cep-scoring.md の
スコア算出手順に従うこと。
```

---

## スキル一覧

| ファイル | 用途 | 使用するエージェント |
|--------|------|------------------|
| `cep-scoring.md` | CEPポテンシャルスコアの算出 | insight-analyst / content-strategist |
| `insight-structure.md` | インサイト4要素の構造化フォーマット | market-scout / insight-analyst |
| `abtest-design.md` | ABテスト16項目の設計テンプレート | campaign-executor / media-buyer |
| `hypothesis-format.md` | 仮説の記述フォーマット（信頼度付き） | insight-analyst / performance-analyzer |
| `report-format.md` | 最終レポートの共通フォーマット | chief-researcher |
| `utm-naming.md` | UTMパラメータの命名規則 | media-buyer / performance-analyzer |
| `sales-letter.md` | セールスレター設計（ベネフィット〜P.S.の全構造） | campaign-executor（全グループ） |
| `sales-script.md` | セールススクリプト設計（商談の脳科学・4つの物語・障害対処） | campaign-executor（全グループ） |
| `article-writing.md` | 記事作成（SEO・LLMO対応・ニーズ調査〜校閲23項目） | campaign-executor / content-strategist（全グループ） |
| `site-design.md` | WEBサイト構築設計（戦略〜要件〜構造〜骨格〜システム設計） | campaign-executor / content-strategist（全グループ） |
| `abm-account-selection.md` | ABMアカウント選定・ICPスコアリング（6指標・優先度判定） | account-intelligence-analyst / abm-strategist（toB） |
| `stakeholder-analysis.md` | ステークホルダー分析（5分類・パワーマップ・チャンピオン育成） | stakeholder-mapper / abm-strategist（toB） |
| `proposal-writing.md` | 提案書・ROI試算書・RFP回答書設計（ステークホルダー別8ステップ構成） | sales-enablement-executor / abm-strategist（toB） |
| `customer-success.md` | ヘルススコア・NRR・チャーン評価・QBR設計 | customer-success-analyzer（toB） |
| `consulting-sales-process.md` | コンサルティングセールスプロセス（7工程・DiSC別対応の前提・スマートアウトバウンド） | abm-strategist / sales-enablement-executor（toB） |
| `sales-rep-matching.md` | 営業担当者タイプ分類・アサイン最適化・結果分析（DiSC相性マトリクス・勝率分析） | abm-strategist / sales-enablement-executor / customer-success-analyzer（toB） |
| `fandom-tieup.md` | IP協業・ファンダムタイアップ設計（IP選定8ヶ条・ターゲティング4象限・伝搬設計） | insight-analyst / content-strategist（relation-community） |
| `loyalty-research.md` | ロイヤリティ定量化調査（サービスサイエンス・6指標・顧客体験洗い出し・不満足調査設計・収益貢献評価） | insight-analyst / performance-analyzer（relation-community） |
| `retention-model.md` | リテンションモデル設計（事前期待の的・SPC設計・サービスプロセスモデル化・改革推進4UP STEP） | content-strategist / insight-analyst（relation-community） |
| `retention-healthscore.md` | リテンションヘルススコア設計・定点観測（KGIツリー・5カテゴリ100点・連鎖断絶の診断） | performance-analyzer（主担当） / insight-analyst / content-strategist（relation-community） |

---

## スキルの追加ルール

1. 複数のエージェントで同じ処理を繰り返している場合はスキルに抽出する
2. ファイル名はスネークケース（`skill-name.md`）
3. 各スキルファイルの冒頭に「入力・処理・出力」を明記する
4. スキルはできるだけ汎用的に書き、特定のグループ固有の内容は含めない
