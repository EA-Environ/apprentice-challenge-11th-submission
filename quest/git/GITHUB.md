# GitHub を使って開発を進めることができる

## 1. リモートリポジトリ

GitHub 上に新規リポジトリを作成してください。

- GitHub の Profile ページにアクセスし、Repositories をクリック。
- New をクリックし新規リポジトリを作成。リポジトリ名は、github_practice にしました。

## 2. プッシュ

ローカルの PC 上に GitHub 上で作成したリポジトリの同じ名前のディレクトリを作成し、そのディレクトリ内に README.md　ファイルを作成してください。

-   <details><summary>ディレクトリ作成</summary>

    ```bash
    cd ~/Desktop
    mkdir ./github_practice

    cd ./github_practice
    touch README.md
    ```
    </details>

次に、ローカルリポジトリを新規作成し、変更をステージに追加、コミットしてください。

-   <details><summary>ローカルリポジトリを作成し、コミット</summary>

    ```bash
    git init
    git add README.md
    git commit
    ```
    </details>

リモートリポジトリを登録してください。そして GitHub に変更をプッシュしてください。

-   <details><summary>リモートリポジトリを作成し、プッシュ</summary>

    ```bash
    git remote add origin <前項で作成したリモートリポジトリ URL>
    git push -u origin master
    ```
    </details>

## 3. 追加の変更をプッシュ

README.md に変更を追加してください。そしてその変更を GitHub にプッシュしてください。

-   <details><summary>README.md を変更し、プッシュ</summary>

    ```bash
    echo "変更を GitHub にプッシュします" >> README.md
    git add README.md
    git commit
    git push
    ```
    </details>

## 4. クローン

GitHub 上にある他者が作成したリポジトリを自分の PC 上にクローンしてください。クローン対象は何でも良いです。

-   <details><summary>実行例 ... git clone</summary>

    ```bash
    cd ~/Desktop
    git clone https://github.com/APPRENTICE-jp/apprentice-challenge.git
    ```
    </details>