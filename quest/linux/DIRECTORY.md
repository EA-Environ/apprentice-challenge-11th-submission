# ディレクトリを操作できる

Linux にログインしてターミナル上で行ってください。

## 1. 現在のディレクトリ

自分が現在いるディレクトリを表示してください。

- $ pwd

## 2. ルートディレクトリ

現在のディレクトリから、"/" ディレクトリに移動してください。

- $ cd /

## 3. ホームディレクトリ

現在のディレクトリから、ホームディレクトリに移動してください。

- $ cd /home

## 4. 一つ上のディレクトリ

現在のディレクトリから、一つ上の親ディレクトリに移動してください。

- $ cd ..

## 5. ディレクトリの内容

現在のディレクトリの内容を表示してください。

- $ ls （ルートディレクトリで実行しています）

<details><summary>実行例 ... $ ls </summary>

```bash
bin   dev  home  lib    lib64   lost+found  mnt  proc  run   snap  sys  usr
boot  etc  init  lib32  libx32  media       opt  root  sbin  srv   tmp  var
```
</details>

## 6. 隠しファイル

現在のディレクトリの隠しファイルを含む全てのファイルとディレクトリを表示してください。

- ls に 1. の -a オプションをつける。タイプ識別子も表示させる場合は、2. の -aF オプションにする。
1. $ ls -a
2. $ ls -aF

<details><summary>実行例 ... $ ls -a</summary>

```bash
.   .bash_history  .bashrc  .config     .lesshst  .motd_shown  .sudo_as_admin_successful
..  .bash_logout   .cache   .landscape  .local    .profile
```
</details>

<details><summary>実行例 ... $ ls -aF</summary>

```bash
./   .bash_history  .bashrc  .config/     .lesshst  .motd_shown  .sudo_as_admin_successful
../  .bash_logout   .cache/  .landscape/  .local/   .profile
```
</details>

## 7. 詳細なリスト形式

"/etc" ディレクトリの内容を、詳細なリスト形式で表示してください。

なおわからない場合は、"man ls" コマンドで ls コマンドの詳細を確認することができます。"List files in the long format" といった説明のあるオプションを付けてください。

- $ ls -l /etc

<details><summary>実行例 ... $ ls -l /etc</summary>

```bash
合計 788
drwxr-xr-x 2 root root       4096  1月  7  2025 PackageKit
drwxr-xr-x 8 root root       4096  9月  5 09:44 X11
-rw-r--r-- 1 root root       3028  1月  7  2025 adduser.conf
drwxr-xr-x 2 root root       4096  9月  5 09:45 alternatives
drwxr-xr-x 3 root root       4096  1月  7  2025 apparmor
drwxr-xr-x 8 root root       4096  9月  5 09:42 apparmor.d
drwxr-xr-x 3 root root       4096  9月  5 09:42 apport
drwxr-xr-x 8 root root       4096  1月  7  2025 apt
-rw-r--r-- 1 root root       2319  1月  7  2022 bash.bashrc
-rw-r--r-- 1 root root         45 11月 12  2021 bash_completion
drwxr-xr-x 2 root root       4096  9月  5 09:42 bash_completion.d
...（以下略）
```
</details>

## 8. ディレクトリの作成

ホームディレクトリに移動し、"projects" という名前のディレクトリを作成してください。

- 下記の順に実行する。 
1. $ cd ~
2. $ mkdir ./projects

## 9. ディレクトリの削除

作成した "projects" ディレクトリを削除してください。

- $ rmdir ./projects