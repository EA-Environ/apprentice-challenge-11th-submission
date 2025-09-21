# ブランチを利用して開発を進めることができる

Git で管理されているディレクトリに移動してください。

```bash
cd ~/Desktop/github_practice
```

## 1. ブランチの新規作成

feature という名前のブランチを新規作成してください。

-   <details><summary>ブランチの作成</summary>

    ```bash
    git branch feature
    ```
    </details>

## 2. ブランチの切り替え

ローカルリポジトリのブランチを feature ブランチに切り替えてください。

-   <details><summary>ブランチの切り替え</summary>

    ```bash
    git checkout feature
    ```
    </details>

## 3. マージ

feature ブランチでファイルの変更を行い、コミットしてください。そしてローカルリポジトリのブランチを main ブランチに切り替えてください。

-   <details><summary>ファイルの変更</summary>

    ```bash
    echo "ブランチを切り替え、マージします" >> README.md
    git add README.md
    git commit -v
    ```
    </details>

次に、feature ブランチの変更を main ブランチに取り込んでください。なお、他のブランチの変更を取り込むことをマージと言います。

-   <details><summary>マージ（他ブランチの取り込み）</summary>

    ```bash
    #作業ブランチを master に切り替えてから、feature ブランチを取り込む
    git checkout master
    git merge feature
    ```
    </details>

## 4. ブランチの名前の変更

feature ブランチの名前を rename という名前に変更してください。

-   <details><summary>ブランチ名の変更</summary>

    ```bash
    #作業ブランチを feature に戻して、名称変更
    git checkout feature
    git branch -m rename
    ```
    </details>

## 5. ブランチの削除

rename ブランチを削除してください。

-   <details><summary>ブランチの削除</summary>

    ```bash
    #作業ブランチを master に切り替えてから、feature ブランチを削除
    git checkout master
    git branch -d rename
    ```
    </details>