# GitHub フローに従って開発を進めることができる

GitHub にプッシュをしたことのあるローカルリポジトリ（自分の PC 上のディレクトリ）に移動してください。

```bash
cd ~/Desktop/github_practice
```

## 1. プルリクエストとは

プルリクエストは何か、何のためにあるかをプログラミング初心者にわかるように説明してください。

- チーム開発においては master ブランチはリリース専用とし、各開発者は個別のトピック・ブランチで作業を行うのが標準的となっている。各名が自分のブランチから変更をプッシュした際に、マージする手前のコード・レビューをほかのメンバーに依頼するための機能がプルリクエストである。プルリクエストの内容に問題がなければ、master ブランチへのマージを行い、作業済みのトピックは削除するという流れになる。

## 2. プルリクエストの作成

以下のことを行い、プルリクエストを作成してください。

1. ローカル（自分の PC ）で pullrequest ブランチを新規作成し、切り替えてください
-   <details><summary>ブランチの作成</summary>

    ```bash
    git branch pullrequest
    git checkout pullrequest
    (もしくは、git checkout -b pullrequest)
    ```
    </details>

2. 任意のファイルに変更を行ってください

-   <details><summary>ファイルの変更</summary>

    ```bash
    echo "プルリクエストを送信します" >> README.md
    ```
    </details>

3. 変更をコミットしてください

-   <details><summary>変更の追加、コミット</summary>

    ```bash
    git add README.md
    git commit -m "プルリクエストの練習"
    ```
    </details>

4. GitHub に pullrequest というブランチ名で変更をプッシュしてください

-   <details><summary>変更をプッシュ</summary>

    ```bash
    git push origin pullrequest
    ```
    </details>

5. GitHub を開き、pullrequest ブランチから main ブランチへのプルリクエストを作成してください

- Pull requests 画面を開き、New pull request ボタンをクリック。base: は master のままで compare: を pullrequest に設定し、Create pull request をクリック。 メッセージを入力し、再度 Create pull request をクリック。 

6. 変更内容を確認し、問題なければ GitHub 上で変更をマージしてください

- Pull requests 画面に前項で作成したプルリクエストが表示されるので、Merge pull request → Confirm merge をクリック。

7. GitHub 上の pullrequest ブランチを削除してください

- 前項の作業後に表示される、Delete branch をクリック。

## ３. ローカルへのリポートリポジトリの変更内容の取り込み

ローカルリポジトリのブランチを main ブランチに切り替えてください。

```bash
git checkout master
```

次に、リモートリポジトリ（GitHub）の main ブランチの内容をローカルリポジトリの main ブランチに取り込んでください。

```bash
git fetch origin master
git merge origin/master
(もしくは、git pull origin master)
```

それができたらローカルリポジトリの pullrequest ブランチを削除してください。

```bash
git branch -d pullrequest
```

※開発を行う際はここから1に戻り、この1~2のステップを繰り返します

## 4. GitHub フロー

[GitHub フロー](https://docs.github.com/ja/get-started/quickstart/github-flow) の公式リファレンスを一読してください。

その上で、今後の開発は GitHub フローに基づいて行ってください。多くの組織における基本的な開発フローは GitHub フローもしくは GitHub フローをベースにしたものになります。今から GitHub フローに慣れていきましょう。
