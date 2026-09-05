# 保険のお手続きナビ（公開用）

このフォルダの `index.html` は **生成物**。直接編集しないこと。

元のソースは別リポジトリ `claudecode01` の `hoken-navi/` にある。
中身（保険会社・リンク・電話番号）を直したいときは、そちらを編集してから
1枚のHTMLに固め直して、このファイルを差し替える:

```bash
cd claudecode01/hoken-navi
# data.js などを編集
node tools/check-links.mjs      # リンクの疎通確認
node tools/build-single.mjs     # dist/index.html を作る
cp dist/index.html ../../ai-secretary-pages/hoken-navi/index.html
```

公開URL: https://takuya1128iuy-pixel.github.io/ai-secretary-pages/hoken-navi/

LINE公式アカウントのリッチメニューからこのURLを開かせている。
リッチメニュー側の設定は `claudecode01/line-richmenu/` にある。
