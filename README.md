# デンタ君 - GitHub Pages 公開手順

## 1. アップロードするファイル
このフォルダの4つを、GitHubリポジトリの一番上の階層にそのまま置いてください。

- index.html
- manifest.json
- sw.js
- icon-192.png
- icon-512.png

## 2. GitHub Pagesを有効化
1. GitHubで新しいリポジトリを作成（例: denta-kun）
2. 上記ファイルをアップロード（Add file → Upload files）
3. リポジトリの Settings → Pages
4. Source を「Deploy from a branch」、Branch を「main / (root)」に設定して Save
5. 数分待つと `https://ユーザー名.github.io/denta-kun/` のようなURLが発行されます

## 3. オフラインで使えるようにする（重要）
1. 発行されたURLに、電波が入る場所で**一度アクセス**してください
   （このときにservice workerがファイルをスマホ内にキャッシュします）
2. スマホのブラウザ（iPhoneはSafari、AndroidはChrome）の共有メニューから
   「ホーム画面に追加」を実行
3. 以降はホーム画面のアイコンから開けば、圏外・機内モードでも動作します

## 4. 更新したときの注意
中身を直してGitHubに再アップロードしたら、`sw.js` の一番上にある
`CACHE_NAME = "dentakun-v1"` の数字を `v2` などに変えてください。
これをしないと、スマホ側が古いキャッシュを使い続けてしまい、
変更が反映されないことがあります。
