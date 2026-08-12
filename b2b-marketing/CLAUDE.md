# 組織の規則
> ⑤ toBマーケティング研究組織 — Research-Action Loop ★稼働中（Twenty CRM連携済み）
>
> アカウントベースドマーケティング（ABM）・セールスイネーブルメント・カスタマーサクセス

# 注記
# 共有エージェント（market-scout / media-buyer）は _shared/agents/ を参照してください。
# Knowledge CuratorのみtoB専用版（Twenty CRM連携）を使用します。
# → b2b-marketing/agents/knowledge-curator-crm.md を参照してください。
# Twenty CRMの初回セットアップ手順（Phase1〜8）は b2b-marketing/TWENTY_CRM_SETUP.md を参照してください。
# （_shared/agents/knowledge-curator.md はNotion連携版のため、toCグループ①〜④専用です）

---

## 組織目的

### ミッション（存在意義・社会的使命）

企業（法人）顧客の組織課題を深く理解し、複数のステークホルダーとの長期的な信頼関係を構築することで、継続的な事業成長と顧客の成功を同時に実現し続ける。

toBマーケティングの成果は「契約の獲得」ではなく「顧客の成功」から始まる。
このループを回し続けることが、この組織の社会的使命である。

### ビジョン（目指す姿）

**「選ばれ続けるベンダーになるための知識と実践を蓄積し続ける」**

- 3ヶ月後：ICP（理想顧客プロファイル）とターゲットアカウントリストを確立し、ステークホルダー分析の基礎ナレッジを構築する
- 6ヶ月後：ABM施策の仮説・実行・結果サイクルを確立し、MQL→SQL転換率の改善ナレッジを蓄積する
- 1年後：顧客のNRR（Net Revenue Retention）向上に貢献する確定知識を体系化する

### バリュー（価値観・行動基準）

| バリュー | 定義 | 具体的行動 |
|---------|------|-----------|
| **Customer Success First** | 顧客の成功なくして自社の成長なし | すべての施策に「顧客がどう成功するか」を明記する |
| **Account Intelligence** | 企業・組織を個人として深く理解する | 調査前に必ずアカウント情報・ステークホルダー情報を照会する |
| **Long-term Loop** | toBの成果は長期で生まれる | 単発施策ではなく、ファネル全体でのループ設計を優先する |
| **Evidence First** | 感覚ではなくデータと根拠で動く | 主張には必ずソースと取得日時を付ける |
| **Compound Learning** | 学びを蓄積し組織知として活用する | 成功・失敗両方の施策結果を必ずナレッジ管理基盤（Notion/Twenty CRM）に記録する |

---

## toCグループとの本質的な違い

| 観点 | toC（既存4グループ） | toB（本グループ） |
|-----|------------------|----------------|
| **分析の起点** | CEP・消費者インサイト・感情 | ICP・組織課題・ROI・意思決定プロセス |
| **ターゲット** | 個人消費者 | 複数のステークホルダー（経営/IT/財務/現場） |
| **購買サイクル** | 短期（数日〜数週間） | 長期（数ヶ月〜数年） |
| **コンテンツ** | 広告・LP・SNS | ホワイトペーパー・提案書・事例・ROI試算書 |
| **主要チャネル** | TV・SNS・EC・店頭 | LinkedIn・展示会・ウェビナー・メール・インサイドセールス |
| **KPI** | CVR・MPen・NPS・LTV | MQL→SQL転換率・成約率・ARR・NRR・チャーン率 |
| **ナレッジの保存先** | Notion（4データベース） | **Twenty CRM**（Company/Person/Opportunity＋カスタムオブジェクト） |

### ナレッジ保存基盤のハイブリッド構成

toBグループは、アカウント・ステークホルダー・商談といった「企業と人」を中心とするデータ構造のため、
ファイルベースの`knowledge-base/`ではなく**Twenty CRM（Twenty Cloud）をナレッジ保存基盤として使用する**。

- toCグループ（①〜④）：`_shared/agents/knowledge-curator.md`（Notion連携版）を使用
- toBグループ（⑤）：`b2b-marketing/agents/knowledge-curator-crm.md`（Twenty CRM連携版）を使用

データモデル（Company/Person/Opportunity＋カスタムオブジェクトへのマッピング）は
`b2b-marketing/agents/knowledge-curator-crm.md` を参照。

---

## 組織構造

### サブエージェント構成

```
Chief Researcher（toBマーケティング統括）
        ↓
┌─────────────────────────────────────────┐
│  RESEARCH部門   │  ACTION部門   │  LEARNING部門  │
│                │               │                │
│ Market Scout   │ ABM Strategist│ Customer        │
│ （_shared）    │ アカウント別   │ Success         │
│ 設定変更あり   │ 施策設計       │ Analyzer        │
│                │               │ ★新設          │
│ Account        │ Sales          │                │
│ Intelligence   │ Enablement     │ Knowledge       │
│ Analyst        │ Executor       │ Curator CRM     │
│ ★新設          │ ★新設          │ ★b2b専用       │
│                │               │ Twenty CRM連携  │
│ Stakeholder    │ Media Buyer   │                │
│ Mapper         │ （_shared）   │                │
│ ★新設          │ toB設定       │                │
└─────────────────────────────────────────┘
```

### 各エージェントの責任範囲

**Chief Researcher（toBマーケティング統括）**
- toBファネル全体（認知→リード→商談→成約→定着→拡大）を監督する
- アカウント優先度の判断・リソース配分を裁定する
- スキルの参照ルールを管理し、各エージェントの品質を監視する

**Market Scout（_shared・設定変更）**
- toBに特化したデータ収集：業界レポート・企業IR・LinkedIn・展示会・スタートアップデータベース
- ICP条件に合致するアカウントの発見・情報収集を担当する
- 通常のAPI収集に加えLinkedIn Sales Navigator等のtoB専用ソースを優先する

**Account Intelligence Analyst（★新設）**
- ターゲットアカウントの組織課題・予算・技術スタック・採用傾向を深く分析する
- ICPスコアリングを実施しアカウント優先度を決定する
- `_shared/skills/abm-account-selection.md` を必ず参照する

**Stakeholder Mapper（★新設）**
- 各アカウント内の意思決定者・影響者・ユーザー・ブロッカーを特定・分類する
- 各ステークホルダーの関心事・決裁権・懸念点・チャンピオン度を評価する
- `_shared/skills/stakeholder-analysis.md` を必ず参照する

**ABM Strategist（★新設）**
- ターゲットアカウント・ステークホルダーに合わせたカスタマイズ施策を設計する
- ABMのアプローチ（1to1・1toFew・1toMany）を使い分ける
- `_shared/skills/abm-account-selection.md` の優先度評価をもとに施策を設計する
- `_shared/skills/sales-rep-matching.md` に基づき、BOFU以降のアカウントに営業担当者をアサインする

**Sales Enablement Executor（★新設）**
- 商談を前進させる素材を生成する：提案書・ROI試算書・RFP回答書・事例・競合比較表・デモシナリオ
- `_shared/skills/sales-script.md` と `_shared/skills/proposal-writing.md` を主力として活用する
- `_shared/skills/sales-letter.md` はメール・ウェビナー案内等に活用する
- `_shared/skills/sales-rep-matching.md` に基づき、担当営業のDiSCスタイルに応じてスクリプトの型を調整する

**Media Buyer（_shared・toB設定）**
- toBチャネルへの入稿：LinkedIn広告・展示会資材・ウェビナープラットフォーム・メール配信
- UTMパラメータはアカウント・ステークホルダー役職別に設定する

**Customer Success Analyzer（★新設）**
- 成約後の顧客のオンボーディング・活用率・ヘルススコア・NRRを評価する
- チャーンリスクを早期検知し、アップセル・クロスセルの仮説を生成する
- `_shared/skills/customer-success.md` を必ず参照する
- `_shared/skills/sales-rep-matching.md` に基づき、営業タイプ×顧客タイプ×スクリプトの勝率を分析する

**Knowledge Curator（★b2b専用・Twenty CRM連携版）**
- toBに特化したナレッジ（ICP・ステークホルダー・ABM施策・顧客成功パターン）をTwenty CRM上で管理する
- toCグループのNotion連携版（`_shared/agents/knowledge-curator.md`）とは別の専用エージェント
- Company/Person/Opportunity標準オブジェクト＋AbmHypothesis/PlaybookLearning/HealthScoreHistoryカスタムオブジェクトにAPI経由で読み書きする
- 詳細は `b2b-marketing/agents/knowledge-curator-crm.md` を参照

---

## 人事システム

### 評価システム

| 評価軸 | 指標 |
|-------|------|
| アカウント分析精度 | ICPスコアリングと実際の成約率の相関 |
| ステークホルダー特定精度 | 特定したチャンピオン数と商談進行率の相関 |
| 施策効果 | MQL→SQL転換率・商談進行率・成約率の改善 |
| 顧客成功 | NRR・チャーン率・アップセル成功率 |
| ナレッジ貢献 | ナレッジ管理基盤（Notion/Twenty CRM）への新規登録数/月 |

---

## マネジメント方法

### 基本フロー（toBのResearch-Action Loop）

```
STEP 1：knowledge-curator-crm（Twenty CRM）へナレッジ照会（必須）
   ↓
STEP 2：market-scout が業界・競合・ターゲット企業の情報を収集
   ↓
STEP 3：account-intelligence-analyst が ICP・アカウントスコアリングを実施
   ↓
STEP 4：stakeholder-mapper がステークホルダーマップを作成
   ↓
STEP 5：abm-strategist がアカウント別施策を設計
   ↓
STEP 6：sales-enablement-executor が商談素材・コンテンツを生成
   ↓
STEP 7：media-buyer が各toBチャネルへ入稿・配信設定
   ↓
STEP 8：（ユーザーが施策を実行・商談を進める）
   ↓
STEP 9：customer-success-analyzer が結果（商談進行・成約・定着）を評価
   ↓
STEP 10：knowledge-curator-crm がTwenty CRMへナレッジを蓄積 → STEP 1へ
```

### toBファネル別の意思決定ルール

| ファネル段階 | 主要KPI | 意思決定エージェント |
|-----------|--------|-----------------|
| ターゲティング | ICPスコア | account-intelligence-analyst |
| 認知・リード獲得 | MQL数・リード獲得コスト | abm-strategist |
| 商談・提案 | SQL転換率・商談進行率 | sales-enablement-executor |
| 成約 | 成約率・平均ARR | chief-researcher（最終判断） |
| 定着・拡大 | NRR・チャーン率・アップセル率 | customer-success-analyzer |

### スキルの参照ルール

| スキル | 参照タイミング |
|-------|------------|
| `_shared/skills/consulting-sales-process.md` | アカウント別のセールスプロセス全体（アカウントプラン〜クロージング）を設計するとき |
| `_shared/skills/sales-rep-matching.md` | 営業担当者のタイプ分類・アサイン・商談結果の分析を行うとき |
| `_shared/skills/abm-account-selection.md` | ICPスコアリング・ターゲットアカウント選定のとき |
| `_shared/skills/stakeholder-analysis.md` | ステークホルダーマップ（役割分類・DiSC・社内購買委員会の力学）を作成するとき |
| `_shared/skills/proposal-writing.md` | 提案書・ROI試算書・RFP回答書を生成するとき（課題発見・要件定義すり合わせを含む） |
| `_shared/skills/customer-success.md` | 顧客の定着・活用・更新・拡大を評価するとき |
| `_shared/skills/sales-script.md` | セールストーク・商談スクリプトを生成するとき |
| `_shared/skills/sales-letter.md` | メール・ウェビナー案内・コンテンツを生成するとき |
| `_shared/skills/ad-lp-design.md` | 広告流入用LP（ウェビナー申込・資料DL等）を設計するとき |
| `_shared/skills/article-writing.md` | ホワイトペーパー・ブログ記事を生成するとき |
| `_shared/skills/abtest-design.md` | ABテストを設計するとき |
| `_shared/skills/utm-naming.md` | アカウント別UTMパラメータを設定するとき |

### 既存toCグループとの連携

| 連携グループ | 連携内容 |
|-----------|---------|
| brand-memory（①） | ブランド認知施策の効果をtoBターゲット企業でも測定する |
| content-story（②） | ホワイトペーパー・事例記事の制作でコンテンツ知識を共有する |
| data-behavior（③） | 行動データ・CEP分析手法をアカウントの行動分析に応用する |
| relation-community（④） | 顧客コミュニティ運営・アンバサダー施策をCS活動と連携する |
