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

---

## スキルの追加ルール

1. 複数のエージェントで同じ処理を繰り返している場合はスキルに抽出する
2. ファイル名はスネークケース（`skill-name.md`）
3. 各スキルファイルの冒頭に「入力・処理・出力」を明記する
4. スキルはできるだけ汎用的に書き、特定のグループ固有の内容は含めない
