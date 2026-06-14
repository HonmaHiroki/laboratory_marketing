# スキル：UTMパラメータ命名規則

**使用するエージェント：** media-buyer / performance-analyzer  
**入力：** チャネル名・施策名・CEP名・パターン  
**出力：** UTMパラメータ文字列

---

## 命名規則

すべてのUTMパラメータは**スネークケース（小文字・アンダースコア区切り）**で統一する。

### パラメータ定義

```
utm_source   = 流入元メディア（どこから来たか）
utm_medium   = 広告種別（どんな手段か）
utm_campaign = 施策名（何のキャンペーンか）
utm_content  = クリエイティブ識別子（ABパターン等）
utm_term     = CEP名（どの購買文脈向けか）
```

### utm_source 命名例

| メディア | utm_source |
|---------|-----------|
| YouTube | youtube |
| Meta（FB/IG） | meta |
| TikTok | tiktok |
| X（Twitter） | x |
| Google検索広告 | google_search |
| ディスプレイ広告 | google_display |
| メールマガジン | email |
| プッシュ通知 | push |
| Podcast | podcast |
| ラジオ | radio |
| 店頭QR | instore_qr |
| チラシQR | flyer_qr |
| パッケージQR | package_qr |

### utm_medium 命名例

| 種別 | utm_medium |
|-----|-----------|
| 動画広告 | video |
| バナー広告 | display |
| 検索広告 | cpc |
| SNS投稿（オーガニック） | social |
| SNS広告 | paid_social |
| メール | email |
| プッシュ通知 | push |
| QRコード | qr |
| 音声広告 | audio |

### utm_campaign 命名規則

```
[グループ略称]_[施策テーマ]_[年月]

例：
db_cep_morning_routine_202501    （data-behavior / CEP「朝のルーティン」/ 2025年1月）
bm_brand_awareness_summer_202506 （brand-memory / 夏の認知施策 / 2025年6月）
```

### utm_content 命名規則

```
pattern_[a or b]_[フォーマット略称]

例：
pattern_a_video30s     （パターンA・30秒動画）
pattern_b_banner_feed  （パターンB・フィードバナー）
```

### utm_term 命名規則

```
cep_[CEP名をスネークケースで]

例：
cep_morning_coffee     （CEP「朝のコーヒータイム」）
cep_post_workout       （CEP「運動後のリカバリー」）
cep_rainy_day_home     （CEP「雨の日の在宅時間」）
```

---

## UTM付きURL生成フォーマット

```
https://[ドメイン]/[パス]?utm_source=[X]&utm_medium=[X]&utm_campaign=[X]&utm_content=[X]&utm_term=[X]
```

例：
```
https://example.com/product/?utm_source=youtube&utm_medium=video&utm_campaign=db_cep_morning_routine_202501&utm_content=pattern_a_video30s&utm_term=cep_morning_coffee
```

---

## 禁止事項

- スペースを使わない（`+`や`%20`に変換されてデータが汚染される）
- 大文字を混在させない（`YouTube`と`youtube`が別データとして計測される）
- 特殊文字（`&` `=` `?`）をパラメータ値に含めない
- 同一施策で命名規則が異なるパターンを混在させない
