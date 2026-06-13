# Knowledge Base

マーケティング研究組織のナレッジベースです。
Knowledge Curatorが管理し、Research-Action Loopを通じて継続的に蓄積・更新されます。

## 最終Audit日
YYYY-MM-DD（初期構築）

## 構造

```
knowledge-base/
├── market-insights/       市場・競合・消費者の調査情報
│   ├── jobs/              ジョブ定義・無消費実態・間に合わせの対処策
│   ├── cep-map/           CEPマップ・購買文脈の整理
│   ├── competitors/       競合ブランドのCEP・アベイラビリティ状況
│   ├── habits/            習慣・ライフイベント・季節性データ
│   └── trends/            市場トレンド・消費者動向
├── hypothesis-log/        仮説の管理
│   ├── active/            検証中の仮説
│   ├── verified/          支持された仮説（3回未満）
│   ├── confirmed/         確定知識昇格候補（3回以上支持）
│   └── rejected/          棄却仮説と失敗の構造分析
├── campaign-results/      施策の実行結果
│   ├── by-cep/            CEP別の施策結果
│   ├── by-audience/       顧客タイプ別（ロイヤル/競合/未顧客）
│   └── by-channel/        チャネル別の結果
└── learnings/             確定知識（3回以上支持された原則）
    ├── job-insights/      確定したジョブ・インサイトの知識
    ├── cep-principles/    CEPマネジメントの勝ちパターン
    ├── habit-principles/  習慣形成・維持の確定知識
    ├── communication/     コミュニケーション戦略の確定知識
    └── brand-growth/      ブランド成長に関する確定原則
```

## 利用ルール

1. **調査開始前に必ず照会する**：すべてのエージェントはタスク開始前にKnowledge Curatorへ照会すること
2. **タスク完了後に必ず保存する**：アウトプットはKnowledge Curatorへ渡し、適切なフォルダに保存する
3. **棄却仮説も必ず保存する**：失敗から学ぶことが組織の成長につながる
4. **未顧客向けの知識を特に重視する**：ブランド成長の源泉は未顧客にある

## 仮説昇格ルール

```
新規仮説 → active/
    ↓ 1〜2回支持
verified/
    ↓ 3回以上支持
confirmed/ → chief-researcherの承認 → learnings/（確定知識）
```

※「ロイヤル顧客向けで支持」と「未顧客向けで支持」は別カウント
