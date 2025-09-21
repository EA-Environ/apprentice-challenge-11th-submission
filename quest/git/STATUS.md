# 変更状況を確認できる

Git で管理されているディレクトリに移動してください。任意のファイルに何らかの変更を追加してください。

```bash
cd ~/Desktop/git_practice

#前回作成した README.md に下記コマンドで文章を記入

echo "Git コマンドを練習しています。" >> README.md
```

## 1. 変更状況の確認

現在何のファイルが変更されているかを確認してください。

<details><summary>実行例 ... git status</summary>

```bash
git status

#ワークツリーに変更があったというメッセージが表示されました。
# Changes not staged for commit:
# modified:   README.md (赤い文字で表示)

#ステージとリポジトリの間に差分がある場合
# Changes to be committed:
# modified:   README.md (緑の文字で表示)
```
</details>

## 2. 変更内容の確認

何が変更されたか、変更内容を確認してください。

<details><summary>実行例 ... git diff</summary>

```bash
git diff

#ワークツリーとインデックス（ステージエリア）の差分が表示されました。
# +Git コマンドを練習しています。

git add README.md

git diff --staged

#ステージとリポジトリの差分が表示されました。
# +Git コマンドを練習しています。
```
</details>

## 3. 変更履歴

変更の履歴（ログ）を確認してください。

<details><summary>実行例 ... git log</summary>

```bash
git log

# COMMIT.md で実行したコミットの情報が、下記のとおり出力されました。
# コミットファイルのハッシュ値 (commit)、作成者 (Author)、日付 (Date)、コミットメッセージ - 「新規ファイルを作成」

git commit -v

#コミットメッセージは、「文言を入力」としました。

git log

#今回実行した2回目のコミット情報と、1回目のコミット情報が出力されました。

# git log では、 --oneline  -p <ファイル名> -n <コミット数> といったオプションが使用される。
```
</details>
