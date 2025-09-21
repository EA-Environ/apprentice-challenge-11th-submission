# ファイルを操作できる

## 1. ファイルの中身を出力

/etc/hosts ファイルの中身を出力してください。/etc/hosts ファイルが存在しない場合は、何らかのテキストファイルの中身を出力してください。

- $ cat /etc/hosts

<details><summary>実行例 ... $ cat /etc/hosts</summary>

```bash
127.0.0.1       localhost
127.0.1.1       DESKTOP-T0UOT7S.localdomain     DESKTOP-T0UOT7S

::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```
</details>

## 2. ファイルの中身をスクロール表示

/etc/hosts ファイルの中身をスクロール式で表示してください。/etc/hosts ファイルが存在しない場合は、何らかのテキストファイルの中身を表示してください。

- $ less /etc/hosts

実行結果 ... ディスプレイが切り替わり、**$ cat /etc/hosts** と同様の結果が表示されました。

## 3. ファイルの作成

ホームディレクトリの直下に、README.md という名前の空ファイル（中身が空のファイル）をコマンドを利用して作成してください。

- $ touch ~/README.md

## 4. ファイル名の変更

先程作成した README.md ファイルの名前を TMP.md という名前に変更してください。

- $ mv ~/README.md ~/TMP.md

## 5. ファイルのコピー

先程作成した TMP.md ファイルをコピーして COPY.md ファイルを作成してください。

- $ cp ~/TMP.md ~/COPY.md

## 6. ファイルの削除

先程作成した TMP.md ファイルを削除してください。

- $ rm ~/TMP.md

## 7. シンボリックリンク

作成した README.md に対して、シンボリックリンクを貼ってください。シンボリックリンクのファイル名は README_SYMBOLIC.md としてください。作成後、README.md に対して任意の文章を追記してください。その後、symbolic_file の中身を出力し、追記した内容が README_SYMBOLIC.md にも反映されていることを確認してください。

- 下記の手順で実行しました。（cd ~ でホームディレクトリに移動した状態です）
1. $ touch README.md
2. $ ln -s README.md README_SYMBOLIC.md
3. $ echo "hello" > README.md
4. $ cat README_SYMBOLIC.md

実行結果 ... $ cat README_SYMBOLIC.md

```bash
 hello
 ```

## 8. ファイルの検索

ホームディレクトリ以下のファイルに対して、README という文字列が含まれるファイルを全て検索し、出力してください。なお、find コマンドを使用して実現することができます。

- $ find ~ -name '\*README\*' -print

## 9. 検索

~/sample.txt ファイルを作成し、以下の内容を記載してください。

```bash
apple
banana
grape
lemon
```

その上で、sample.txt ファイルから、"a" で始まる単語を検索してください。なお、grep コマンドを使用して実現することができます。

- 下記の手順で実行しました。（cd ~ でホームディレクトリに移動した状態です）
1. $ touch sample.txt
2. $ echo -e "apple\nbanana\ngrape\nlemon" >> sample.txt
3. $ grep -e "^a" sample.txt

実行結果 ... $ grep -e "^a" sample.txt

```bash
 apple
 ```