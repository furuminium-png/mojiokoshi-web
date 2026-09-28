# mojiokoshi 公式サイト

mojiokoshi の Developer Website、プライバシーポリシー、サポートページを配信する静的サイトです。

## 公開先

- URL: https://mojiokoshi-web.mojiokoshi.workers.dev
- GitHub: https://github.com/furuminium-png/mojiokoshi-web
- 本番ブランチ: `main`
- ホスティング: Cloudflare Workers Static Assets（Workers Git integration）

## Cloudflare の設定

- 接続リポジトリ: `furuminium-png/mojiokoshi-web`
- Build command: 空欄
- Deploy command: `npx wrangler deploy`
- Root directory: リポジトリのルート

`wrangler.jsonc` の `assets.directory` は `./public` です。Worker 用 JavaScript は使っていません。`public/_redirects` により `/` で `index.html` を配信します。`.html` のURLはそのまま利用できます。

## 配信ファイル

- `/` — トップページ（`public/index.html`）
- `/privacy.html` — プライバシーポリシー
- `/support.html` — サポート
- `/app-ads.txt` — 広告設定用。現在は空ファイル

## 更新方法

`public/` のファイルを編集して `main` に push すると、Cloudflare の Git integration が自動デプロイします。ビルド処理は不要です。

## 2026-09-28 の作業メモ

- 公式サイトの初期ページを作成し、問い合わせ先を `usagisensei2026@gmail.com` に設定。
- Workers Static Assets 用の `wrangler.jsonc` と Wrangler の依存関係を追加。
- Wrangler のローカルプレビューで `/`、各HTML、CSS、`/app-ads.txt` が 200 を返し、ファイル内容と一致することを確認。
- 公開URLは発行済み。こちらの実行環境から公開URLへの確認は 403 応答で完了できなかったため、本番の表示確認は未了。

App Store のリンク先は、確定後に `public/index.html` の `href="#"` を差し替えてください。
