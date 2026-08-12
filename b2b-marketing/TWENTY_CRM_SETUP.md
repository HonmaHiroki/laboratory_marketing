# Twenty CRM 手動セットアップ手順書（b2b-marketing用）

`b2b-marketing/agents/knowledge-curator-crm.md` で設計したデータモデルを、実際のTwenty CRMワークスペースに反映するための作業手順。
**Twenty CRMの管理画面（Settings → Data model）から手動で作成する前提**の手順書です。

APIキー発行は完了済みのため、ここではスキーマ（オブジェクト・フィールド）の作成から進める。

---

## 作業前の重要事項：順序を守ること

一部のフィールドは他のオブジェクトへの**リレーション**を持つため、**参照先のオブジェクトを先に作らないとリレーションフィールドが作成できない**。
以下の順序（Phase 1〜8）を必ず守って進めること。

```
Phase 1：Company にカスタムフィールド追加（依存なし）
Phase 2：Person にカスタムフィールド追加（依存なし）
Phase 3：SalesRep オブジェクトを新規作成（依存なし）
Phase 4：Opportunity にカスタムフィールド追加（Phase 3のSalesRepへのリレーションを含む）
Phase 5：AbmHypothesis オブジェクトを新規作成（Companyへのリレーション）
Phase 6：PlaybookLearning オブジェクトを新規作成（AbmHypothesisへのリレーション）
Phase 7：HealthScoreHistory オブジェクトを新規作成（Companyへのリレーション）
Phase 8：DealOutcome オブジェクトを新規作成（Opportunityへのリレーション）
```

---

## 重要：標準オブジェクト（Company/Person/Opportunity/Note）は削除・作り直し不要

Twenty CRMの**標準オブジェクトは削除できない仕様**（できるのは非アクティブ化＝Deactivateのみ）。
これはバグではなく仕様であり、そもそも本手順書では**削除・作り直しを一切想定していない**。

- Company・Person・Opportunity・Noteは**既存のものをそのまま使い、カスタムフィールドを追加するだけ**でよい
- 「一度消してから設計通りに作り直したい」と考える必要はない。既存レコード・標準フィールドは維持されたまま、Phase1・2・4で追加するカスタムフィールドが**上乗せ**される
- 誤って標準オブジェクトの削除を試みて「削除できない」と表示された場合は仕様通りの挙動なので、そのままPhase 1（フィールド追加）に進んでよい
- 一方、**カスタムフィールドを型違いなどで作り直したい場合も「完全削除」は現状不可**（Deactivateのみ対応）。作り直す場合は該当フィールドをDeactivateし、正しい型で別名の新フィールドを追加する

---

## Phase 1：Companyへのカスタムフィールド追加

Settings → Data model → Company → 「+ Add field」から以下を1つずつ作成する。

| フィールド名 | タイプ | 選択肢（Selectの場合） |
|---|---|---|
| `icpScoreTotal` | Number | ー |
| `icpScoreFit` | Number | ー |
| `icpScorePain` | Number | ー |
| `icpScoreBudget` | Number | ー |
| `icpScoreAccess` | Number | ー |
| `icpScoreCompetition` | Number | ー |
| `priority` | Select | ★★★／★★／★／対象外 |
| `abmApproach` | Select | 1to1／1toFew／1toMany |
| `companyStage` | Select | スタートアップ／成長期／成熟期／上場企業 |
| `techStack` | Text | ー |
| `healthScore` | Number | ー（0〜100の数値として運用） |
| `healthStatus` | Select | Healthy／Neutral／AtRisk |
| `nrr` | Number | ー（%の数値として運用） |
| `churnRiskLevel` | Select | 高／中／低 |
| `arr` | Number | ー |

**チェック：** Company詳細画面を開き、上記15フィールドがすべて表示されることを確認する。

---

## Phase 2：Personへのカスタムフィールド追加

Settings → Data model → Person → 「+ Add field」

| フィールド名 | タイプ | 選択肢 |
|---|---|---|
| `stakeholderRole` | Select | EDM／TV／Influencer／EU／Champion／Blocker |
| `influenceLevel` | Select | ★★★／★★／★ |
| `championLevel` | Select | 高／中／低 |
| `relationshipStage` | Select | 未接触／認知／興味／検討／推進 |
| `concerns` | Text | ー |
| `messagingAngle` | Text | ー |
| `discStyle` | Select | D／i／S／C |

**チェック：** Person詳細画面で7フィールドが表示されることを確認する。

---

## Phase 3：SalesRepオブジェクトの新規作成

Settings → Data model → 「+ Add object」

- Object名：`SalesRep`（表示名：営業担当者プロファイル）
- 作成後、以下のフィールドを追加：

| フィールド名 | タイプ | 選択肢 |
|---|---|---|
| `name` | Text | ー（標準のName相当。既定で存在する場合は流用） |
| `discStyle` | Select | D／i／S／C |
| `hunterFarmerType` | Select | ハンター／ファーマー |
| `industryExperience` | Text | ー |
| `preferredDealType` | Select | 即決型／提案型 |
| `preferredFunnelStage` | Select | TOFU／MOFU／BOFU／アフター |

**チェック：** SalesRepオブジェクトが左サイドバーに表示され、レコードを1件テスト作成できることを確認する。

---

## Phase 4：Opportunityへのカスタムフィールド追加

Settings → Data model → Opportunity → 「+ Add field」

| フィールド名 | タイプ | 選択肢 |
|---|---|---|
| `funnelStage` | Select | ターゲティング／認知／商談／提案／成約／定着／拡大 |
| `abmApproach` | Select | 1to1／1toFew／1toMany |
| `hypothesis` | Text | ー |
| `targetKpi` | Text | ー |
| `assignedRep` | **Relation**（→SalesRep） | ー |
| `repCustomerFitScore` | Select | ◎／△ |
| `scriptStyleUsed` | Select | D型／i型／S型／C型 |
| `dealResult` | Select | 成約／失注／保留 |

`assignedRep`を作成する際、リレーション先オブジェクトとして**Phase 3で作成したSalesRep**を選択する（Many-to-One：1つのOpportunityに1人のSalesRep、を推奨設定とする）。

**チェック：** Opportunity詳細画面で`assignedRep`にSalesRepレコードをテストで紐付けられることを確認する。

---

## Phase 5：AbmHypothesisオブジェクトの新規作成

Settings → Data model → 「+ Add object」

- Object名：`AbmHypothesis`（表示名：ABM仮説）

| フィールド名 | タイプ | 選択肢 |
|---|---|---|
| `hypothesisText` | Text | ー |
| `category` | Select | ICP／ステークホルダー／施策／CS |
| `status` | Select | active／verified／confirmed／rejected |
| `supportCount` | Number | ー |
| `relatedCompany` | **Relation**（→Company） | ー |
| `evidenceNote` | Text | ー |

**チェック：** `relatedCompany`で既存のCompanyレコードを紐付けられることを確認する。

---

## Phase 6：PlaybookLearningオブジェクトの新規作成

Settings → Data model → 「+ Add object」

- Object名：`PlaybookLearning`（表示名：確定知識）

| フィールド名 | タイプ | 選択肢 |
|---|---|---|
| `title` | Text | ー |
| `principle` | Text | ー |
| `applicableSegment` | Select（または Multi-select） | 業種／規模／役職 等、運用しながら選択肢を追加 |
| `sourceHypothesis` | **Relation**（→AbmHypothesis） | ー |
| `confirmedDate` | Date | ー |

`sourceHypothesis`は**双方向リレーション**として作成する（Twenty CRMのリレーションフィールドは自動的に相手側にも逆参照フィールドが作られる。AbmHypothesis側に「確定した知識」のような名前で表示されることを確認する）。

**チェック：** AbmHypothesisの詳細画面を開き、紐付けたPlaybookLearningが逆参照として表示されることを確認する。

---

## Phase 7：HealthScoreHistoryオブジェクトの新規作成

Settings → Data model → 「+ Add object」

- Object名：`HealthScoreHistory`（表示名：ヘルススコア推移）

| フィールド名 | タイプ | 選択肢 |
|---|---|---|
| `company` | **Relation**（→Company） | ー |
| `recordedDate` | Date | ー |
| `healthScore` | Number | ー |
| `nrr` | Number | ー |
| `note` | Text | ー |

**チェック：** 同一Companyに対して複数のHealthScoreHistoryレコードを作成できる（One-to-Many）ことを確認する。

---

## Phase 8：DealOutcomeオブジェクトの新規作成

Settings → Data model → 「+ Add object」

- Object名：`DealOutcome`（表示名：商談結果ログ）

| フィールド名 | タイプ | 選択肢 |
|---|---|---|
| `opportunity` | **Relation**（→Opportunity） | ー |
| `repDiscStyle` | Select | D／i／S／C |
| `customerDiscStyle` | Select | D／i／S／C |
| `preAssessedFit` | Select | ◎／△ |
| `scriptStyleUsed` | Select | D型／i型／S型／C型 |
| `dealType` | Select | 即決型／提案型 |
| `result` | Select | 成約／失注／保留 |
| `lossReason` | Text | ー |
| `cycleDays` | Number | ー |

**チェック：** Opportunityの詳細画面からDealOutcomeを1件紐付けて作成できることを確認する。

---

## 全Phase完了後の最終確認

```markdown
## セットアップ完了チェックリスト

- [ ] Company：15カスタムフィールドすべて作成済み
- [ ] Person：7カスタムフィールドすべて作成済み
- [ ] SalesRep：オブジェクト作成済み・6フィールド作成済み
- [ ] Opportunity：8カスタムフィールド作成済み（assignedRepのリレーション動作確認済み）
- [ ] AbmHypothesis：オブジェクト作成済み・Companyへのリレーション動作確認済み
- [ ] PlaybookLearning：オブジェクト作成済み・AbmHypothesisへのリレーション動作確認済み
- [ ] HealthScoreHistory：オブジェクト作成済み・Companyへのリレーション動作確認済み
- [ ] DealOutcome：オブジェクト作成済み・Opportunityへのリレーション動作確認済み
- [ ] 各オブジェクトでテストレコードを1件ずつ作成し、正常に保存できることを確認した
```

---

## API疎通テスト（任意・推奨）

UIでの作成が終わったら、`knowledge-curator-crm.md`に記載のAPIが実際に動くか確認する。

```bash
# APIベースURLとAPIキーを環境変数に設定
# ※ワークスペースURL（laboratory-marketing.twenty.com）はブラウザ用。
#   API呼び出しはTwenty Cloud共通のapi.twenty.comを使う（テナントはAPIキーで判定される）
export TWENTY_API_BASE_URL="https://api.twenty.com"
export TWENTY_API_KEY="（発行済みのAPIキー）"

# Companyレコードの一覧取得テスト
curl -s -X GET "$TWENTY_API_BASE_URL/rest/companies?limit=1" \
  -H "Authorization: Bearer $TWENTY_API_KEY"

# 新規作成したカスタムオブジェクト（例：SalesRep）の一覧取得テスト
# ※エンドポイント名はオブジェクト名の複数形・キャメルケースが基本（例：salesReps）
curl -s -X GET "$TWENTY_API_BASE_URL/rest/salesReps?limit=1" \
  -H "Authorization: Bearer $TWENTY_API_KEY"
```

正常なJSONレスポンス（`data`キーを含む）が返れば疎通成功。`401`エラーの場合はAPIキーを、`404`の場合はオブジェクト名（エンドポイント名）を再確認する。

---

## 完了後にお願いしたいこと

全Phaseが完了したら、以下の情報を教えてください。`knowledge-curator-crm.md`に「接続済みTwenty CRMワークスペース」セクションを追加し、
プレースホルダー（`{company_id}`等）を実際の運用に即した記載に更新します（Notionのときと同様の対応）。

1. 実際のワークスペースURL（`TWENTY_API_BASE_URL`）
2. 各カスタムオブジェクトの実際のAPIエンドポイント名（例：`salesReps`、`abmHypotheses`等。Twenty CRMが自動生成する名前がこちらの想定と異なる場合があるため）
3. Phase 1〜8ですべて完了したか、途中で仕様上作れなかったフィールド・オブジェクトがあれば教えてください（Twenty CRMのプラン・バージョンによって機能差がある可能性があるため）
