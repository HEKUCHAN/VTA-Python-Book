## 文字列でインデックスを指定する
Pythonの文字列は文字の配列なので、Pythonではインデックス指定して値を取り出すことができます。
ただ普通の配列と違って、値の変更はできません。

文字列のインデックス指定は配列と同じように使えます。
マイナスにする事で、後ろから値を取得することができます。

```py
 +---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1
# https://docs.python.org/ja/3/tutorial/introduction.html#strings より引用
```

実際に指定してみましょう。

```py title="main.py"
language = "Python"
print(language[0], language[2]) # -> P t
print(language[-2], language[-3]) # -> o h
```

## 文字列のスライス

Pythonの文字列は配列と一緒で、スライス（分割）機能を持っています。
インデックス指定のように文字列の後に`[]`を書きますが、インデックス指定違うのは、開始地点と終了地点を指定する所です。
`[開始値:終了値]`のように指定します。

```py title="main.py"
abc = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

# 3個以内の文字
print(abc[:3]) # -> ABC

# 3個目以上の文字
print(abc[3:]) # -> DEFGHIJKLMNOPQRSTUVWXYZ

# 7個目から10個目まで
print(abc[7:10]) # -> HIJ

# 負の指定
print(abc[-6:]) # -> UVWXYZ
```

### スライスのステップ機能

ステップを指定したら指定した値以上の約数の場合は取得できます。それを利用して、インデックス番号が奇数と偶数をそれぞれ取得できます。
ステップ機能はスライス機能のあとにもう一つ指定するだけです。`[開始値:終了値:ステップ値]`
```py title="main.py"
abc = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

# 偶数
print(abc[::2]) # -> ACEGIKMOQSUWY

# 奇数
print(abc[1::2]) # -> BDFHJLNPRTVXZ

# 11ステップのものだけ取得
print(abc[::11]) # -> ALW
```

### スライス機能を使って文字を反転

ステップを`-1`に指定するば文字列を反転できます。これは配列でも使えるので、必要な場面が来たら是非使ってみてください。

```py title="main.py"
abc = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

print(abc[::-1]) # -> ZYXWVUTSRQPONMLKJIHGFEDCBA
```

## joinメゾット

joinメゾットを使うことで、インデックスとインデックスの間に指定の文字を入れてくれます、あと文字列が入った配列じゃないとエラー出ます。

```py title="main.py"
fruits = ["apple", "banana", "mango"]
print(", ".join(fruits)) # -> apple, banana, mango
```


## 文字列を綺麗に並べえる（ソート）

sortメゾットを使えばできます。ただ帰り値で返ってくるのは配列なので、joinを使って結合しなければなりません。
またfor文でも問題ないでしょう

```py title="main.py"
abc = "YNUKGLQTMWJVDXFIZHRPCEOBSA"


# sorted関数
abc = sorted(abc)
print(abc) # -> ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']

print("".join(abc)) # -> ABCDEFGHIJKLMNOPQRSTUVWXYZ

answer = ""
for spell in abc:
    answer += spell

print(answer) # -> ABCDEFGHIJKLMNOPQRSTUVWXYZ
```

ある程度のことは、だいたいこれほど扱えれば問題ないと思います。
他にもいろんなメゾットや関数があるので興味がある人は是非調べて見てください。


## 文字列の長さを取得

文字列の長さを取得するには`len`関数を使えば、配列と同じような感じに使えます。

```py title="main.py"
name = "藤本 太郎喜左衛門"
print(len(name)) # -> 9
```