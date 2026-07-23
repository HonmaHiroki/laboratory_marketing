# laboratory_marketing

マーケティング研究組織のリポジトリです。
4つのtoC研究グループ＋1つのtoBグループがResearch-Action Loopを回し、マーケティング精度を継続的に高めます。

## 4つのtoC研究グループ

| グループ | フォルダ | 内包する手法 | 主フェーズ |
|---------|---------|-----------|---------|
| ① ブランド・認知構築型 | `brand-memory/` | カテゴリーマーケティング・CEP刺激・ニューロ/エモーショナル・アンビエント | 認知→興味 |
| ② コンテンツ・ストーリー型 | `content-story/` | インバウンド・コンテンツ・ナラティブ・プロセスエコノミー | 認知→興味→検討→熱狂 |
| ③ データ・行動最適化型 | `data-behavior/` | コンテクスト・ビヘイビアル・プレディクティブ・パーソナライゼーション・ナッジ | 検討→購買→継続 |
| ④ 関係・コミュニティ型 | `relation-community/` | リレーションシップ/ロイヤルティ・インフルエンサー/バイラル・コミュニティ/アンバサダー・ファンダム/チャーチ・IP協業・ロイヤリティ調査/リテンションモデル設計/ヘルススコア定点観測 | 認知→継続→愛着→熱狂 |

## 1つのtoBグループ

| グループ | フォルダ | 内包する手法 | 主フェーズ |
|---------|---------|-----------|---------|
| ⑤ toBマーケティング | `b2b-marketing/` | ABM（アカウントベースドマーケティング）・セールスイネーブルメント・カスタマーサクセス | ターゲティング→認知→商談→成約→定着→拡大 |

toC（個人消費者向け）とtoB（法人向け）は分析の起点・購買サイクル・KPIが根本的に異なるため、
`b2b-marketing/CLAUDE.md` に専用の組織規則を定義しています（詳細は同ファイルを参照）。

## グループ間の連携フロー

```
① ブランド・認知構築型  →（CEP刺激で記憶に刷り込む）
        ↓
② コンテンツ・ストーリー型  →（コンテンツと物語で検討意欲を育てる）
        ↓
③ データ・行動最適化型  →（CEP発動の瞬間に購買を促す）★稼働中
        ↓
④ 関係・コミュニティ型  →（ロイヤル顧客をファン・伝道者に育てる）
        ↓ 熱狂顧客が新規認知を生む（①へループ）
```

### ⑤ toBマーケティングとの連携

toBグループはtoCの循環ループとは別に、法人アカウント単位でファネルを回します。
一方で知見・アセットは以下のようにtoCグループと相互に連携します。

| 連携グループ | 連携内容 |
|-----------|---------|
| ① ブランド・認知構築型 | ブランド認知施策の効果をtoBターゲット企業でも測定する |
| ② コンテンツ・ストーリー型 | ホワイトペーパー・事例記事の制作でコンテンツ知識を共有する |
| ③ データ・行動最適化型 | 行動データ・CEP分析手法をアカウントの行動分析に応用する |
| ④ 関係・コミュニティ型 | 顧客コミュニティ運営・アンバサダー施策をCS活動と連携する |

## 共有リソース

`_shared/` に全グループ共通のエージェント・スキル・ナレッジを集約しています。

**共有エージェント（agents/）**
- `market-scout.md` — 8つのAPIとWEBアンケートからデータ収集（RESEARCH）。toB利用時は企業IR・LinkedIn・展示会等の企業単位ソースを追加使用
- `knowledge-curator.md` — toCグループ①〜④共通の知識管理（LEARNING）。**Notion連携版**：4つのNotionデータベース（Market Insights／Hypothesis Log／Campaign Results／Learnings）にMCP経由で読み書きする（GitHubファイルではない）
- `performance-analyzer.md` — toCグループ共通の結果評価（LEARNING）。toBでは代わりに`b2b-marketing/agents/customer-success-analyzer.md`が評価を担う
- `media-buyer.md` — 13チャネルへの入稿・配信設定・計測設定（ACTION）。LinkedIn AdsなどtoB向けチャネルにも対応

**toB専用エージェント**
- `b2b-marketing/agents/knowledge-curator-crm.md` — b2b-marketingグループ専用の知識管理。**Twenty CRM連携版**：Company/Person/Opportunity標準オブジェクト＋カスタムオブジェクトにAPI経由で読み書きする

**共有スキル（skills/）**

| 分類 | ファイル | 内容 |
|-----|--------|------|
| toC/全体共通 | `cep-scoring.md` | CEPポテンシャルスコアの算出手順 |
| toC/全体共通 | `insight-structure.md` | インサイト4要素の構造化フォーマット |
| toC/全体共通 | `hypothesis-format.md` | 仮説の記述フォーマット（信頼度付き） |
| toC/全体共通 | `report-format.md` | 最終レポートの共通フォーマット |
| 全体共通 | `abtest-design.md` | ABテスト16項目の設計テンプレート |
| 全体共通 | `utm-naming.md` | 13チャネル対応のUTMパラメータ命名規則 |
| 全体共通 | `sales-letter.md` | セールスレター設計（ベネフィット〜P.S.の全構造） |
| 全体共通 | `sales-script.md` | セールススクリプト設計（商談の脳科学・4つの物語） |
| 全体共通 | `article-writing.md` | 記事作成（SEO・LLMO対応・校閲23項目） |
| 全体共通 | `site-design.md` | WEBサイト構築設計（戦略〜システム設計） |
| toB専用 | `abm-account-selection.md` | ABMアカウント選定・ICPスコアリング（6指標） |
| toB専用 | `stakeholder-analysis.md` | ステークホルダー分析（5分類・パワーマップ） |
| toB専用 | `proposal-writing.md` | 提案書・ROI試算書・RFP回答書設計 |
| toB専用 | `customer-success.md` | ヘルススコア・NRR・チャーン評価・QBR設計 |
| toC専用（④） | `fandom-tieup.md` | IP協業・ファンダムタイアップ設計（IP選定8ヶ条・ターゲティング4象限・伝搬設計） |
| toC専用（④） | `loyalty-research.md` | ロイヤリティ定量化調査（サービスサイエンス・6指標・顧客体験洗い出し・収益貢献評価） |
| toC専用（④） | `retention-model.md` | リテンションモデル設計（事前期待の的・SPC設計・サービスプロセスモデル化・改革推進） |
| toC専用（④） | `retention-healthscore.md` | リテンションヘルススコア設計・定点観測（KGIツリー・連鎖断絶の原因診断） |

**ナレッジ保存基盤（ハイブリッド構成）**
- toCグループ①〜④：Notion（`knowledge-curator.md`がMCP経由で読み書き。4データベース：Market Insights／Hypothesis Log／Campaign Results／Learnings）
- toBグループ⑤：Twenty CRM（`knowledge-curator-crm.md`がAPI経由で読み書き。Company/Person/Opportunity＋カスタムオブジェクト）
- リポジトリ内の`knowledge-base/`ディレクトリは廃止済み（過去データの参照が必要な場合はGit履歴を参照）

## 新グループの追加手順

1. `_shared/templates/` からファイルをコピーする
2. 対応するグループフォルダを作成する
3. `CLAUDE.md` の手法名・ミッション・KGIを書き換える
4. `agents/` の4ファイルをグループ特化の内容に更新する
5. Notion側に対応するデータベースのビュー・グループタグを追加する（新規ディレクトリ作成は不要）

**toB型グループを追加する場合：**
上記はtoC型グループ（4エージェント構成）向けの手順です。`b2b-marketing/`のようにtoB型グループを追加する場合は、対象の意思決定者が複数存在する分、エージェント構成も専門分化します（`b2b-marketing/`では6つの専用エージェント＋3つの共有エージェントの構成）。`b2b-marketing/CLAUDE.md`と`b2b-marketing/agents/`を参考テンプレートとして複製・改変してください。
