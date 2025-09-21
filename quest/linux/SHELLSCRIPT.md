# シェルスクリプトを書くことができる

## 1. Hello

シェルスクリプトのファイルを作成し、「Hello!」と出力してください。

なお、シェルスクリプトを実行する際にはファイルに実行権限が付与されている必要があることに気を付けてください。

- Hello.sh のシェルスクリプト・ファイルを下記の手順で作成、実行しました。（保存用ディレクトリも作成）
    1. $ touch ~/Hello.sh ... ファイル作成
    2. $ chmod 755 ~/Hello.sh ... 実行権限の付与
    3. 実行スクリプトをエディット（エディタは、VSCode を使用しています）
        <details><summary>Hello.sh</summary> 

        ```bash
        #!/bin/bash
        #echoでメッセージを表示
        echo "Hello!"
        ```
        </details>
    4. $ bash Hello.sh ... 挙動を確認
    5. $ mkdir ~/bin ... スクリプト保存用ディレクトリを作成（~/bin ディレクトリは、作成すると自動的に環境変数 $PATH に設定されました）
    6. $ mv ~/Hello.sh ~/bin ... スクリプト保存先にファイルを移動（シェルスクリプトの起動も楽になりました）

## 2. 標準入力から値を受け取る

シェルスクリプトのファイルに「What's your name?」と出力し、ユーザーに名前の入力を求めます。その後ユーザーが入力した名前に対して、「Welcome, $name!」（$name は入力された名前）と出力する処理を追加してください。

-   <details><summary>Name.sh</summary>

    ```bash
    #!/bin/bash
    #プロンプトをechoを使って表示
    echo "What's your name?" 
    #キーボード入力を「name」に代入
    read name 
    #結果を表示
    echo "Welcome, $name "
    ```
    </details>

## 3. 条件分岐

四則演算を行う電卓を作成してください。実行すると以下の挙動になります。

```bash
Enter two numbers:
10 # ユーザーが入力
11 # ユーザーが入力
Choose an arithmetic operation (+, -, *, /):
+ # ユーザーが入力
The result:21
```

なお、割り算の時の割る数が 0 であるケースや、演算子の記号 +, -, *, / が合致しないケースを考慮するかは任意とします。

-   <details><summary>Calculate.sh</summary>

    ```bash
    #!/bin/bash

    #関数定義（割り算について ... 除数が0の際はエラー。剰余は算出していません。）
    add_subtract_multiply () {
        echo "The result:"$(echo "$1 $2 $3" | bc)
    }

    divide () {
        if [ "$3" -eq 0 ]; then
            echo "Error: 0 cannot be a divisor."
        else
            echo "The result:"$(echo "$1 $2 $3" | bc)
        fi
    }

    #プロンプトを表示し、キーボード入力をコマンド引数に設定
    #計算が成り立つように、数値以外が入力された場合は再度入力を促す
    while true; do
        echo "Enter two numbers:"
        read num1
        read num2
        is_numeric='^-?[0-9]+([.][0-9]+)?$'
        if ! [[ "$num1" =~ $is_numeric ]] || ! [[ "$num2" =~ $is_numeric ]]; then
            echo "Error: Please enter valid numbers."
        else
            break
        fi
    done
    echo "Choose an arithmetic operation (+, -, *, /):"
    read op

    # 演算実行
    case "$op" in
    "+"|"-"|"*") add_subtract_multiply "$num1" "$op" "$num2" ;;
    "/") divide "$num1" "$op" "$num2" ;;
    *) echo "Error: "$op" is an invalid operator." ;;
    esac
    ```
    </details>

## 4. 繰り返し処理

for 文 または while 文を利用して、1~100までのうち、偶数の数字を表示する処理を書いてください。以下の結果が出力されます。

```bash
2 4 8 ... 100
```

-   <details><summary>EvenNumber.sh</summary>

    ```bash
    #!/bin/bash

    #1~100までの整数で、偶数のみを表示する。
    #一行で表示されるように、各偶数を配列に格納しスペース区切りで出力しています。

    EvenNum=()
    count=0

    for i in {1..100}; do
        if (( $i % 2 == 1 )) ; then
            continue
        fi
        EvenNum[$count]=$i
        ((count++))
    done

    echo ${EvenNum[@]}
    ```
    </details>