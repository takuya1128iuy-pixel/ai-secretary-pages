# てつづきコンパス（公開用）

このフォルダの `index.html` は **生成物**。直接編集しないこと。

元のソースは別リポジトリ `claudecode01` の `tetsuzuki-compass/` にある。
中身（保険会社・リンク・電話番号）を直したいときは、そちらを編集してから
1枚のHTMLに固め直して、このファイルを差し替える:

```bash
cd claudecode01/tetsuzuki-compass
# data.js などを編集
node tools/check-links.mjs      # リンクの疎通確認
node tools/build-single.mjs     # dist/index.html を作る
cp dist/index.html ../../ai-secretary-pages/tetsuzuki-compass/index.html
```

公開URL: https://takuya1128iuy-pixel.github.io/ai-secretary-pages/tetsuzuki-compass/

LINE公式アカウントのリッチメニューからこのURLを開かせている。
リッチメニュー側の設定は `claudecode01/line-richmenu/` にある。

`hoken-navi/` は旧URL。リッチメニューに埋め込み済みのリンクがそこを指しているので、
新URLへ転送するだけのページとして残してある。リッチメニューを作り直したら消してよい。
