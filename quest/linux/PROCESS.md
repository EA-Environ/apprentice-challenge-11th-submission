# プロセス・ジョブを管理できる

## 1. プロセス

全ユーザーのプロセスを表示してください。

- $ ps ax (実効ユーザー名などの詳細情報も確認する場合は、ps aux)

<details><summary>実行例 ... ps ax</summary>

```bash
PID TTY      STAT   TIME COMMAND
1 ?        Ss     0:00 /sbin/init
2 ?        Sl     0:00 /init
...（以下略）
```
</details>

<details><summary>実行例 ... ps aux</summary>

```bash
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.1 165780 10844 ?        Ss   03:23   0:00 /sbin/init
root           2  0.0  0.0   3060  1792 ?        Sl   03:23   0:00 /init
...（以下略）
```
</details>

## 2. バックグラウンド

sleep コマンドを利用して処理を100秒停止する処理を、バックグラウンドで実行してください。

- $ sleep 100 &

## 3. プロセス・ジョブの終了

2でバックグラウンドで実行されている sleep コマンドを終了させてください。

- $ kill %1

  (2 で実行したジョブ ID が [1] の場合)