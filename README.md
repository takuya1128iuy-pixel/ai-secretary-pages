# ai-secretary-pages

Google OAuth の公開ステータスを「テスト中」→「本番」に切り替えるためだけの、
ホームページとプライバシーポリシーの2枚。GitHub Pages で公開する前提。

連絡先は `takuya.wallet.1128@gmail.com`（このアプリ専用に作ったもの）。
**このページは公開されるので、ここに個人が特定できるものを足さないこと。**

## 公開の手順

1. GitHub で新しい **public** リポジトリを作る（例: `ai-secretary-pages`）
   README は追加しない（このフォルダをそのまま push するため）
2. このフォルダを push する
   ```bash
   cd ~/ai-secretary-pages
   git init
   git add index.html privacy.html README.md
   git commit -m "add pages for OAuth verification"
   git branch -M main
   git remote add origin git@github.com:<ユーザー名>/ai-secretary-pages.git
   git push -u origin main
   ```
3. GitHub のリポジトリ → **Settings → Pages**
   Source を「Deploy from a branch」、Branch を `main` / `root` にして Save
4. 数分待つと `https://<ユーザー名>.github.io/ai-secretary-pages/` で見える
5. [Google Cloud Console](https://console.cloud.google.com/) →
   **APIs & Services → OAuth consent screen**
   - Application home page: `https://<ユーザー名>.github.io/ai-secretary-pages/`
   - Application privacy policy link: `https://<ユーザー名>.github.io/ai-secretary-pages/privacy.html`
   - 保存
6. 同じ画面で **PUBLISH APP**（本番に公開）を押す
   - 「確認していないアプリです」の警告は出る。自作アプリなら正常
     （テストユーザーのときと同じ）。
   - **`gmail.readonly` は Google の分類で「制限付き（restricted）」。**
     本番にしたあと、Google から審査（場合によってはセキュリティ評価）を
     求められることがある。求められたら、そこで判断すること。
     どうしても通らないときは、`SCOPES` から `gmail.readonly` を外せば
     残りは「機微（sensitive）」だけになる。外すと `trip_scan_mail`
     （予約メールから旅行を記録する機能）が使えなくなるが、
     Gmail はブラウザ経由でも読めるので、代わりはある。
7. 確認: `.venv/bin/ai-secretary --google-login` をやり直して、
   7日ではなく長期間の許可になっているか見る
   （`docs/google-calendar.md` の「7日で切れる問題」を参照）
