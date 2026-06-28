# アサヒファースト ホームページ 進捗メモ

---

## 完了したこと

### 調査・設計
- [x] 参考サイト（japan-support-corp.com）のデザイン分析 → `design-analysis.md`
- [x] 自社サイト仕様書の作成（ヒアリング形式で入力） → `my-site-spec.md`
- [x] アーキテクチャ選定：**Astro**（静的サイトジェネレーター）に決定

### セキュリティ設定
- [x] `.npmrc` に `ignore-scripts=true` / `save-exact=true` を設定
- [x] `package.json` の Astroバージョンを `^6.3.0` → `6.3.0` に完全固定
- [x] Astroのテレメトリ（匿名データ収集）を無効化
- [x] Noto Sans JP フォントをCDNではなくローカル配信に変更

### Phase 1: 会社紹介ページ（index）
- [x] Astroプロジェクト作成（`asahi-first-web/`）
- [x] グローバルCSS作成（オレンジ系カラー、レスポンシブ対応）
- [x] 共通レイアウト（`Layout.astro`）
- [x] ヘッダーコンポーネント（スティッキー、ガラスモーフィズム、モバイルドロワー）
- [x] フッターコンポーネント
- [x] トップページ実装（`src/pages/index.astro`）
  - ヒーローセクション
  - About（会社紹介・3カード）
  - 企業向けCTA
  - お問い合わせCTA
- [x] ビルド確認（エラーなし）

### Phase 1: 会社情報ページ（/about）
- [x] 会社情報専用ページ実装（`src/pages/about.astro`）
  - 経営理念（ダミーテキスト・3バリュー）
  - 企業情報テーブル（会社名・代表者・所在地・電話・設立・資本金・業務内容・許可番号・営業エリア）
  - アクセス（Google Maps 埋め込み）
- [x] ヘッダーナビの ABOUT → COMPANY（`/about`）に更新
- [x] ビルド確認（2ページ生成）

---

## 残りのTODO
### Phase 2: 企業向けページ（/corporate）
- [ ] サービス紹介ページ（`src/pages/corporate/index.astro`）
- [ ] サービス内容・料金・フローの説明セクション

### その他（随時）
- [ ] キャッチコピーの確定（現在は仮）
- [ ] 実際の画像素材の差し替え（現在はCSSのブロブ形状でプレースホルダー）
- [ ] お問い合わせフォームの実装
- [ ] 本番ホスティング先の検討（Vercel / Netlify / S3 など）

---

## 開発コマンド

```bash
cd asahi-first-web

# ローカル確認
npm run dev        # → http://localhost:4321

# 本番ビルド
npm run build

# ビルド結果のプレビュー
npm run preview
```

---

## ディレクトリ構成

```
asahi_first/
├── design-analysis.md       # 参考サイトのデザイン分析
├── my-site-spec.md          # 自社サイト仕様書
├── progress.md              # このファイル
└── asahi-first-web/
    ├── .npmrc               # セキュリティ設定
    ├── package.json         # 依存パッケージ（Astro 6.3.0 固定）
    ├── package-lock.json
    ├── public/
    │   ├── fonts/NotoSansJP.ttf
    │   └── styles/global.css
    └── src/
        ├── layouts/Layout.astro
        ├── components/
        │   ├── Header.astro
        │   └── Footer.astro
        └── pages/
            ├── index.astro   # トップページ（完了）
            └── about.astro   # 会社情報ページ（完了）
```
