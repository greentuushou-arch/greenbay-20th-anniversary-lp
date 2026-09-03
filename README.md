# マヌカハニー専門グリーンベイ｜楽天出店20周年記念祭 特集ページ

`index.html` 1ファイル完結（CSS / JS すべて内包）。画像は `images/` 配下（相対パス）。
どのディレクトリに置いても動きます。楽天GOLD・商品ページ埋め込みのどちらでも使えます。

- Webフォント（Google Fonts）を読み込みます（Zen Kaku Gothic New / Kaisei Opti / Josefin Sans / Zen Maru Gothic）。
- 「グリーンベイキッチン」のレシピカードのサムネイルは、楽天の画像CDN（`tshop.r10s.jp`）を直接参照しています。

---

## よく編集する場所（`index.html`）

### 1. クーポンURL — `<script>` 内の `COUPONS`

現在は下記URLを設定済みです。変わったら書き換えてください。
空文字 `""` にすると、そのボタンが自動で「（準備中）」表示になり押せなくなります。

```js
var COUPONS = {
  fukubukuro : "https://coupon.rakuten.co.jp/getCoupon?getkey=TFBLUy1KTE9OLVRHR1EtN0lUWg--&rt=", // 福袋セット 50%OFF
  flash4h    : "https://www.rakuten.co.jp/manuka/contents/marathon_4h/",       // 9/4 4時間限定
  time24h    : "https://www.rakuten.co.jp/manuka/contents/20260730/",          // 9/5 24時間限定
  regular    : "https://www.rakuten.co.jp/manuka/contents/marathon20260511/",  // 9/6–9/11
  time30h    : "https://www.rakuten.co.jp/manuka/contents/buttobase20260616/"  // 9/9 30時間限定
};
```

### 2. カウントダウン（パタパタ時計）の日時 — `<script>` 内

```js
var SALE_START = new Date('2026-09-04T20:00:00+09:00');
var SALE_END   = new Date('2026-09-11T01:59:00+09:00');
```

開始前は「開始まであと」、期間中は「終了まであと」、終了後は「終了しました」に自動で切り替わります。

### 3. 「スーパーSALEカレンダー」ブロックを、SALE終了後に消す

`<section class="gb-schedule" id="schedule">` … `</section>` を丸ごと削除します
（前後に `▼▼▼ 楽天スーパーSALE 期間中のみ表示 ▼▼▼` のコメントあり）。
あわせて、`href="#schedule"` のボタン2か所（最後のCTA「スーパーSALEカレンダーを見る」／
スマホ追従バー「SALEカレンダー」、いずれも直前に削除用コメントあり）も削除してください。

### 4. 写真の差し替え（`<!-- ▼差し替え -->` が目印。同名で上書きするだけ）

| 場所 | ファイル |
|---|---|
| FV看板（全面） | `images/hero/fv-banner.jpg` |
| FV下の商品写真（光る枠） | `images/hero/product-hero.jpg` |
| 20周年福袋セット バナー | `images/fukubukuro/banner.jpg` |
| ここまでの歩み（1997〜2026） | `images/story/*.jpg` |
| リニューアル（毎日でも飽きずに） | `images/renewal/manuka-jars.jpg` |
| 歩み2026 の写真 | `images/renewal/drizzle.jpg` |
| 店長メッセージ | `images/story/apiary.jpg` |
| 当店人気マヌカハニー | `images/hero/product-hero.jpg`（FV下と同じ画像） |

### 5. 「グリーンベイキッチン」のレシピカード

`<!-- ▼記事が入れ替わったら href / img / タイトルを差し替え -->` の下の
`<a class="gb-kitchen-card">` を編集。`href`＝記事URL、`img src`＝サムネイルURL、
`.k-t`＝タイトル。カードを増やす場合は `<a>…</a>` をコピーして追加します。

### 6. その他リンク

- ヘッダーの店名 → `https://www.rakuten.co.jp/manuka/`（店舗トップ）
- 「当店人気のマヌカハニーを見る」 → 楽天の検索結果URL（`sid=221827` / `nitem=在庫限り 一掃`）
- 「20周年福袋セットを見る」 → `https://item.rakuten.co.jp/manuka/gb10and15/`

---

## 確認

`index.html` をダブルクリックで開けばそのまま表示されます。
（ローカルサーバーで見る場合は `scripts/serve.ps1` を実行 → `http://localhost:8747`）

## 納品物

`index.html` と `images/` フォルダ。`scripts/` は開発用のため不要です。
