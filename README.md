# TABIWORK / 観光HR デモサイト

静的HTML（ビルド不要）。求職者向けブランドは **TABIWORK**（タグライン「旅の、その先まで。」）、施設向けは「観光HR（仮称）」。

| パス | 対象 | 内容 |
|---|---|---|
| `/` | 求職者（18〜29歳） | TABIWORK LP — FV → 共感 → TABIWORKとは → 旅だけで終わらせない（リゾバ比較） → ネオキャリアだから旅の後も相談できる → 今の安心/その先の安心 → 日本中が職場 → 求人 → ストーリー → 3ステップ → FAQ → 低圧CTA |
| `/business/` | 企業・施設 | サービスLP（悩み → 6つの支援手段 → 選ばれる理由 → 30分ヒアリングCTA） |

## Cloudflare Pages へのデプロイ

1. Cloudflare ダッシュボード → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
2. このリポジトリを選択
3. ビルド設定
   - Framework preset: **None**
   - Build command: （空欄）
   - Build output directory: `/`
4. **Save and Deploy** → 以降は `main` への push で自動デプロイ

## 構成

```
index.html            求職者向けトップ
business/index.html   企業向けサービスLP
assets/common.css     共通スタイル（色・ヘッダー・フッター・フォーム・FAQ）
```

- 求人カードは `index.html` 末尾の `JOBS` 配列（架空データ）から生成
- 画像は Unsplash の URL 参照。差し替える場合は `assets/img/` に置いて `src` を変更
- フォームは送信先未接続（デモ）。送信すると完了メッセージだけ表示

## 差し替えポイント

- サービス名「観光HR（仮称）」→ 正式名称
- `business/index.html` 内の電話番号 `03-XXXX-XXXX`、派遣許可番号
- 人手不足の規模別グラフの数値（※現状はイメージ値）
