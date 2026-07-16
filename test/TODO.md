# 構築 TODO チェックリスト

最終更新: 2026-07-08

情報整理は [README.md](./README.md)、Git コマンドは [GIT_CHEATSHEET.md](./GIT_CHEATSHEET.md) を参照。
上から順に進める構成です。**まずはフェーズ1〜3（Git/GitHub 習得）に集中**し、テストサーバー・自動デプロイは後半に回しています。

---

## フェーズ1: Git を使い始める準備 ★今ここ
- [✓] Git のユーザー情報を設定する（初回のみ・必須）
- [✓] `git config --global user.name "名前"`
- [✓] `git config --global user.email "メールアドレス"`
- [✓] このフォルダを Git 管理下にする（`git init`）
- [✓] `.gitignore` を作成（`.env`・認証情報・OS 生成ファイル等を除外）
- [✓] 最初のコミットを作る（`git add .` → `git commit -m "最初のコミット"`）
- [✓] `git log` / `git status` で状態を確認できるようになる

## フェーズ2: GitHub と連携する
- [✓] GitHub アカウントを用意する（無ければ新規作成）
- [✓] GitHub で **Private リポジトリ**を新規作成（例: `testserver`）
- [✓] ローカルフォルダと GitHub をつなぐ（`git remote add origin ...`）
- [✓] 初回 push（`git push -u origin main`）で GitHub 上に反映されるか確認
- [✓] GitHub の画面でファイルが見えることを確認

## フェーズ3: 日々の運用で Git を「育てる」
- [ ] ファイルを編集 → `add` → `commit` → `push` の流れを繰り返す
- [ ] 分かりやすいコミットメッセージを書く練習をする
- [ ] `git diff` で変更内容を確認する習慣をつける
- [ ] ブランチを作って作業してみる（`git switch -c 練習ブランチ`）
- [ ] 間違えたときの戻し方を1つ覚える（`git restore` など）

## フェーズ4: テストサーバー（Xdomain）準備 ※Git に慣れてから
- [ ] Xdomain 無料サーバーのプランを決める（静的 / PHP・MySQL）
- [ ] Webアプリの技術スタックを確認する
- [ ] サーバーを申し込み、管理画面にログイン
- [ ] FTP 接続情報を取得する（ホスト / ユーザー / パスワード）
- [ ] 公開URL（サブドメイン等）を確認する
- [ ] 手動でファイルを1つ FTP アップロードし、ブラウザ表示を確認
- [ ] テスト環境の非公開設定（Basic 認証 / robots.txt）

## フェーズ5: 自動デプロイ ※将来・今はやらない
- [ ] しばらく手動 FTP アップロードで運用する
- [ ] 慣れてきたら FTP 自動デプロイ（GitHub Actions）を検討
- [ ] FTP 接続情報を GitHub Secrets に登録
- [ ] `.github/workflows/deploy.yml` を作成してテスト

---

## メモ・気づき
（作業中に気づいたこと・詰まった点をここに記録）

-

'この文章が正しく追加されているか確認する'