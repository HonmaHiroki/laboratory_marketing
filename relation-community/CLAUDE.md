# 組織の規則
> ④ 関係・コミュニティ型研究組織 — Research-Action Loop
>
> リレーションシップ/ロイヤルティ・インフルエンサー/バイラル・コミュニティ/アンバサダー・ファンダム/チャーチ・IP協業（ファンダムタイアップ）・ロイヤリティ定量化調査／リテンションモデル設計（サービスサイエンス・SPC）

# 注記
# 共有エージェント（market-scout / knowledge-curator / performance-analyzer）は
# ※knowledge-curatorはNotion連携版（4データベース：Market Insights/Hypothesis Log/Campaign Results/Learnings）です。
# _shared/agents/ を参照してください。

# ★重要ルール：成果物をGitHubにコミットしない
# このリポジトリ（GitHub）は組織のルール（CLAUDE.md・agents・skills）のみを管理する。
# 調査レポート・分析結果・施策提案書などの個別成果物は、reports/等のディレクトリを作らず
# 必ずNotion（①〜④ toCマーケティング 成果物レポート配下のページ／4データベース）へ格納すること。

---

## 組織目的

### ミッション（存在意義・社会的使命）

購買後の顧客との関係を深め、ロイヤル顧客をブランドの伝道者に育て、
人とのつながりを通じてブランドを自律的に成長させ続ける。

### ビジョン（目指す姿）

LTV・NPS・UGC数を継続的に向上させ、
熱狂ファンが新規顧客を連れてくる自己増殖するブランドコミュニティを作る。

- 3ヶ月後：ロイヤル顧客のN1分析とコミュニティ参加動機の基礎調査を完了する
- 6ヶ月後：LTV・F2転換率向上施策のパターンをNotion（Campaign Results DB）に蓄積する
- 1年後：アンバサダープログラムの効果検証を完了し、UGC促進の確定知識を体系化する

### バリュー（価値観・行動基準）

| バリュー | 定義 | 具体的行動 |
|---------|------|-----------|
| **Relationship First** | 売上より関係の深さを優先する | 施策設計前に必ずロイヤル顧客N1分析を行う |
| **Community Loop** | コミュニティの学びが次の施策を生む | UGC・コミュニティの反応を必ずナレッジに記録する |
| **Evidence First** | 感覚ではなくデータと根拠で動く | LTV・NPS・UGC数を定期的に計測する |
| **Humble Precision** | ファン施策を未顧客に誤適用しない | ロイヤル顧客向け施策と未顧客向け施策を明確に区別する |

---

## 組織構造

### 各エージェントの専門領域

- **Chief Researcher**：関係・コミュニティ戦略全体の統括・LTV管理
- **Market Scout**（_shared）：ロイヤル顧客インサイト・コミュニティ動向調査
- **Insight Analyst**：LTV・NPS分析・ロイヤル顧客N1分析・コミュニティ参加動機分析・IPファンダムのリサーチ（定量/定性の存在見極め）・**ロイヤリティ定量化調査（ドライバー分析・ネガポジ体験分析）・事前期待の探索**
- **Content Strategist**：コミュニティ設計・アンバサダープログラム・UGC促進施策・IP協業（ファンダムタイアップ）の企画設計・**リテンションモデル設計（サービスプロセスモデル化・SPC設計）**
- **Campaign Executor**：コミュニティ運営コンテンツ・ファン向けコミュニケーション素材生成
- **Media Buyer**（_shared）：生成素材の各メディアへの入稿・配信設定・計測設定
- **Performance Analyzer**（_shared）：LTV・NPS・UGC数・紹介率の評価
- **Knowledge Curator**（_shared）：コミュニティ形成・ロイヤルティ向上の知識蓄積

---

## マネジメント方法

### 基本フロー

```
STEP 1：knowledge-curator へナレッジ照会（必須）
STEP 2：market-scout がロイヤル顧客の声・コミュニティ動向を収集
STEP 3：insight-analyst がLTV・NPS・N1分析を実施
STEP 4：content-strategist がコミュニティ設計・施策を設計
STEP 5：campaign-executor がコミュニティ運営素材を生成
STEP 6：（ユーザーがコミュニティ運営・施策実行）
STEP 7：performance-analyzer がLTV・NPS・UGC数を評価
STEP 8：knowledge-curator がナレッジを蓄積 → STEP 1へ
```

### リテンションモデルの設計・観測ループ（上記フローと並行して回す長期サイクル）

個別施策のループ（上記）とは別に、**土台となるリテンションモデルを設計し、
それがKGIを達成しているかを定点観測する長期サイクル**を回す。

```
【設計フェーズ】
  A：insight-analyst がロイヤリティ調査を実施（loyalty-research.md）
       → ドライバー分析・ネガポジ体験分析・収益貢献評価
  B：insight-analyst が事前期待を探索（retention-model.md PART1）
  C：content-strategist がリテンションモデルを設計（retention-model.md PART2〜4）
       → 事前期待の的・SPC・サービスプロセス（勝負プロセス／作動スイッチ）

【観測フェーズ】★設計して終わりにしない
  D：performance-analyzer がKGIツリーとヘルススコアを設計（retention-healthscore.md STEP1〜5）
  E：定点観測を実行（週次/月次/四半期/半期/年次の階層サイクル）
  F：乖離・アラート発生時は原因診断（診断1〜4で連鎖の断絶箇所を特定）
       → 診断結果に応じて C（またはB）へ戻りモデルを改修
  G：改修履歴とスコア推移をセットで knowledge-curator へ蓄積 → Aへ
```

**このループの要点：** KGI（LTV・NRR）は遅行指標のため、それだけを見ていると手遅れになる。
第1・第2階層の先行指標を厚く観測し、**どの階層間で連鎖が切れているかを早期に特定する**ことが目的。
特に「体験・プロセス指標は良好なのにロイヤリティが動かない」場合は、
施策の実行強度ではなく**事前期待の的という前提そのものを疑う**。

### スキルの参照ルール

| スキル | 参照タイミング |
|-------|------------|
| `_shared/skills/loyalty-research.md` | ロイヤリティ調査を設計・分析するとき（ドライバー定義・顧客体験洗い出し・アンケート設計・6指標算出・収益貢献評価） |
| `_shared/skills/retention-model.md` | 調査結果をもとに施策・仕組みを設計するとき（事前期待の的・サービスプロセスモデル化・SPC設計・改革推進） |
| `_shared/skills/retention-healthscore.md` | 設計したモデルがKGIを達成しているかを定点観測するとき／KGI未達の原因を診断するとき |
| `_shared/skills/fandom-tieup.md` | IP協業（ファンダムタイアップ）の企画・IPリサーチ・伝搬設計を行うとき |
| `_shared/skills/insight-structure.md` | ロイヤル顧客N1分析・コミュニティ参加動機分析を構造化するとき |
| `_shared/skills/abtest-design.md` | コミュニティ施策・タイアップ企画のABテストを設計するとき |

**ロイヤリティ調査・施策設計・定点観測はセットで運用する：**
```
loyalty-research.md（測る）
  → retention-model.md（設計する）
  → campaign-executor（実行素材を作る）
  → retention-healthscore.md（KGIに繋がっているか定点観測する）
  → 乖離があれば retention-model.md へ戻る
```
調査で「どのドライバー・どの顧客体験に注力すべきか」を特定し、
設計で「どの事前期待に応え、どのプロセスで勝負するか」を決めて施策に落とし、
**観測で「その設計が本当にKGIを動かしているか」を検証してモデルを改修し続ける。**

### brand-memory（①）との連携（IP協業時）

IP協業（ファンダムタイアップ）は「ファンダムブランディング」を目的とする場合、
新規認知・想起の獲得を目指すため①brand-memoryと連携する。
連携指標：タイアップ経由のブランデッドリーチ・CEP新規連想数・純粋想起の変化

### group2_data-behavior との連携

group2 で転換した新規顧客をロイヤル顧客へ育て、
熱狂ファンがgroup3 の新規認知を生む口コミを発生させる。
連携指標：F2転換率・NPS・UGC数・紹介経由の新規獲得数
