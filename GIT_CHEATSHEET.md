# Git コマンド早見表（このフォルダで使う用）

最終更新: 2026-07-08

「折々に少しずつ Git を育てる」ための手元メモ。困ったらここを見る。
※ Windows の PowerShell / Git Bash どちらでも同じコマンドで使えます。

---

## 0. 最初の1回だけ（ユーザー設定）
```bash
git config --global user.name "あなたの名前"
git config --global user.email "あなたのメール"
git config --global init.defaultBranch main   # 初期ブランチ名を main に
```

## 1. このフォルダを Git 管理下にする（最初の1回）
```bash
git init          # Git 管理を開始
git status        # 今の状態を見る（困ったらまずこれ）
```

## 2. 毎日の基本サイクル（いちばん使う）
```bash
git status                    # 何が変わったか確認
git add .                     # 変更を全部ステージ（次のコミット対象にする）
git commit -m "変更の内容"     # コミット（履歴に記録）
git push                      # GitHub に送る（連携後）
```
> `git add ファイル名` で個別に選ぶこともできる。

## 3. 変更内容・履歴を見る
```bash
git diff          # まだ add していない変更内容を見る
git diff --staged # add 済みの変更内容を見る
git log --oneline # コミット履歴を1行ずつ簡潔に見る
```

## 4. GitHub と連携する（最初の1回）
```bash
# GitHub 側で空の Private リポジトリを作ってから↓
git remote add origin https://github.com/ユーザー名/リポジトリ名.git
git branch -M main
git push -u origin main       # 初回はこれ。次回以降は git push だけでOK
```

## 5. ブランチ（作業を枝分かれさせる）
```bash
git switch -c 新ブランチ名     # ブランチを作って移動
git switch main               # main に戻る
git branch                    # ブランチ一覧
git merge ブランチ名           # 現在のブランチに取り込む
```

## 6. 間違えた！ときの戻し方（あわてない）
```bash
git restore ファイル名         # 編集を取り消して最後のコミット状態に戻す
git restore --staged ファイル名 # add を取り消す（変更自体は残る）
git commit --amend -m "新メッセージ"  # 直前のコミットメッセージを修正
```
> ⚠️ push 済みの履歴を書き換える操作（reset --hard 等）は慣れるまで避ける。困ったら聞く。

## 7. その他のtips
- 最新のリモート情報を取得する
```bash
git fetch origin
```
- 新しいフォルダにリモートブランチを取り込む方法
```bash
git switch -c todo更新-remote origin/todo更新
```


---

## コミットメッセージのコツ
- 「何をしたか」が一目で分かる短い文にする
  - 良い例: `READMEにサーバー情報を追記`
  - 惜しい例: `更新` / `いろいろ修正`
- 迷ったら「動詞 + 対象」で書く（例: `追加`, `修正`, `削除`）

## 困ったときの合言葉
1. まず `git status` を見る
2. `git log --oneline` で今どこにいるか確認する
3. それでも分からなければそのまま質問する（無理に戻さない）
