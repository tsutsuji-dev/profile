# ポートフォリオサイト 要件定義（HTML＋CSSのみ／GitHub Pages）

## 1. 概要
- **目的**：副業獲得のための自己紹介・スキル提示・実績紹介  
- **公開先**：GitHub Pages（`username.github.io` または任意のリポジトリ）  
- **技術制約**：HTML5＋CSS3のみ（JSなし）  
- **デザイン方針**：エンジニアっぽい無機質×端正（モノクロ基調／コード感のあるタイポ）  
- **対応端末**：モバイル・タブレット・PC（レスポンシブ）  
- **言語**：日本語（必要に応じ英語版は将来対応）

## 2. ターゲット・ユースケース
- **想定閲覧者**：副業依頼主、採用担当、技術者  
- **ゴール**：  
  - スキルと担当可能領域を10秒で把握  
  - 連絡手段がワンクリックで分かる  
  - 実績（準備中でも）更新予定と熱量が伝わる

## 3. コンテンツ要件
### 3.1 ヘッダー／ヒーロー
- サイトロゴ（テキストでOK）  
- キャッチコピー（例：「Webエンジニア｜フルスタックエンジニア）  
- **プロフィール画像**：ダミー画像を配置（`/assets/img/avatar-placeholder.png`）  
- CTA：**Contact / Email** ボタン（`mailto:`）

### 3.2 自己紹介（About）
- 名前：tsutsuji
- 1〜2行の要約（得意領域・価値提供）  
- 在住エリア・稼働時間帯（例：平日夜/週末）
- 稼働状況（例：**副業受付中** / 週〜30時間程）※これ以上も可能だが要相談というメッセージをつけたい

### 3.3 スキル（Skills）
- メイン：**Next.js**, **Laravel**  
- 追加で予め記入する想定の例：TypeScript / React / Node.js / PHP / MySQL / PostgreSQL / Docker / AWS / GitHub Actions / Vite / Tailwind CSS / REST API / Java /  Google APP Script / jQuery
- 表示形式：  
  - **タグ風バッジ**（CSSのみ）  
  - レベル表現は★やバーも可（CSSのみで実装）
- 使用技術はFront, Back, infraのようにグループごとに分類したいです

### 3.4 プロジェクト（Projects）
- 見出し＋グリッド。**現状は「Coming soon」**のカードを3枚程度並べる  
- プロジェクトカード要素（将来用）：  
  - タイトル、簡単説明、役割、技術、期間、リンク（GitHub/デモ）  
  - 現状はプレースホルダで非活性リンク

## 4. 画面・構造要件
- ページ数：**単一ページ（index.html）**  
- セクション構造：`header` / `main`（hero, about, skills, projects, contact）/ `footer`  
- ナビゲーション：同一ページ内アンカー（`#about` 等）

## 5. デザイン要件
- **配色**：モノクロ＋アクセント1色（例：#00D8FF または #38BDF8）  
- **タイポ**：  
  - 見出し：等幅系（例：`ui-monospace, SFMono-Regular, Menlo, Consolas`）  
  - 本文：システムUI  
- **エンジニア感**：  
  - コード風ボックス、行番号風装飾、バッジ、薄いグリッド  
- **ダークモード**：`prefers-color-scheme` に応答（CSSで切替）  
- **アイコン**：SVG（インライン）  

## 6. 非機能要件
- **パフォーマンス**：画像はWeb最適化（ダミーは<100KB）  
- **アクセシビリティ**：コントラスト比、`alt`、スキップリンク  
- **SEO**：  
  - `title/meta/ogp` 設定  
  - 構造化データ（`Person` の最低限 JSON-LD、※JSなしでも `<script type="application/ld+json">` は可）  
- **セキュリティ/プライバシー**：外部トラッキングは原則なし（必要ならプライバシーポリシー）  

## 7. 運用要件
- **更新頻度**：月1回以上（プロジェクト更新を想定）  
- **更新容易性**：  
  - プロジェクトカードはHTMLの繰り返しで増減  
  - スキルタグも同様に増減  
- **バージョン管理**：Git（mainブランチにpush→Pages公開）

## 8. 受け渡し物
- `index.html`（単一ページ）  
- `assets/css/style.css`  
- `assets/img/avatar-placeholder.png`（ダミー）  

## 9. サイトマップ（単一ページ内）
- `/`  
  - `#hero` → `#about` → `#skills` → `#projects` → `#contact`

## 10. 想定ディレクトリ
```
/
├─ index.html
└─ assets/
   ├─ css/
   │  └─ style.css
   └─ img/
      └─ avatar-placeholder.png
```

## 11. 最低実装チェックリスト
- [ ] GitHub Pages 有効化  
- [ ] `index.html` のセクション実装  
- [ ] スキル：Next.js / Laravel 明記＋追加タグ  
- [ ] Projects：**Coming soon** カード表示  
- [ ] OGP（`og:title`, `og:description`, `og:image`）  
- [ ] スマホ幅での表示確認（375px）  
- [ ] Lighthouse で簡易計測（任意）
