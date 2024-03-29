---
tags:
  - 環境構築
  - homebrew
  - pyenv
  - Python
  - インストール
  - ターミナル
  - Python基礎
---
# Pythonインストール MacOS編

!!! warning ":snake: Anacondaのインストールについて"
    先生がanacondaをインストールを指定している場合は、先生の指示に従ってインストールをお願いします。
    去年(2021年)では指定されましたが、anacondaである必要ないと私は思ったので、めんどくさいエラーを避けたいなら普通のPythonのインストールをお勧めします。
    ただ今年と同じ授業するのかわからないので先生に聴いて判断をしてください。

!!! warning ":fontawesome-brands-apple: M1 MacBookについて"
    私はM1搭載のMacBookを持っていなく、実機でのテストを行っていません。
    なので、以下の通りに環境構築ができるとは限りません。

!!! Info このページについて
    このページは以下のサイトを参考にして、作成しています。

    [**M1 Mac環境にPython3をインストールする方法**](https://hitori-sekai.com/python/mac-python-install/)(最終アクセス日: 2022/4/9)

    [**pyenvでPythonバージョンを管理する**](https://cyublog.com/articles/python-ja/pyenv/)(最終アクセス日: 2022/4/9)


## インストール手順

:fontawesome-brands-apple: MacOSでのインストール手順を簡単に説明するなら以下のようになります

1. :beer: :apple: Homebrewのインストール
2. :material-snake: pyenvのインストール
3. :fontawesome-brands-python: Pythonのインストール

### 公式ページ一覧
- [HomeBrew - Homepage](https://brew.sh/index_ja)

- [Pyenv - Homepage](https://opencollective.com/pyenv)

- [Python - Homepage](https://www.python.org/)

## Homebrewのインストール

### 既にインストールされていないか確認

まず、brew(Homebrew)がすでにインストールされていないか確認をします。
まずはターミナルを開き、以下のコマンドをコピーして、ターミナルにペーストして実行してください。

!!! note "ターミナルの開き方と使い方"
    ターミナルの開き方と使い方をここで説明するのは少し大変なので、是非このTechcampさんのブログのが分かりやすいので、是非読んで見てください

    [Macの「ターミナル」とは？](https://tech-camp.in/note/technology/18730/)

    何度もショートカットキーを押して開くのは面倒だと思うので、メニューバーに登録するのをおすすめします

```bash title="ターミナル"
brew -v
```

もし、インストールされていなければ、以下のように表示されると思います。
```bash title="ターミナル"
zsh: command not found: brew
```

インストールされていれば、以下のようになると思います。
```brew title="ターミナル"
Homebrew X.X.X
```
^X.X.Xにはバージョンが入るので、数字があれば問題ないです^

インストールされている方は次の[Pyenvのインストール](#pyenv)に行っても大丈夫です。

### Let's インストール
以下のコマンドをコピーして、ターミナルにペーストして実行してください。
```bash title="ターミナル"
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

実行している途中で、権限を求められるので、パソコンのパスワードを打って、++enter++を押してください。

!!! warning
    打ってるパスワードは見えないので注意してください。間違えた場合は ++delete++ を数秒間押して消してください。
    全部消えてるか確認できないので、感でやるしかないです。

こんな感じの表示が出てくると思います
```bash title="ターミナル"
==> Checking for `sudo` access (which may request your password).
Password:
```

しばらくすると、以下のメッセージが表示されるので、++Enter++を押してださい。
```bash title="ターミナル"
Press RETURN to continue or any other key to abort
```

以下のように表示出来たらインストール完了です！
```bash title="ターミナル"
==> Installation successful!

==> Homebrew has enabled anonymous aggregate formulae and cask analytics.
Read the analytics documentation (and how to opt-out) here:
  https://docs.brew.sh/Analytics
No analytics data has been sent yet (or will be during this `install` run).

==> Homebrew is run entirely by unpaid volunteers. Please consider donating:
  https://github.com/Homebrew/brew#donations

==> Next steps:
- Run these two commands in your terminal to add Homebrew to your PATH:
    echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/username/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
- Run `brew help` to get started
- Further documentation: 
    https://docs.brew.sh
```

一応インストールができたか確認しましょう
インストールできたか確認するためには、以下のコマンドを実行してください。
実行する前に、ターミナル再起動（閉じてまた開く）をして下さい。
```bash title="ターミナル"
brew -v
```

もし、インストールされていなければ、以下のように表示されると思います。
```bash title="ターミナル"
zsh: command not found: brew
```

インストールされていれば、以下のようになると思います。
```brew title="ターミナル"
Homebrew X.X.X
```
^X.X.Xにはバージョンが入るので、数字があれば問題ないです^


## Pyenvのインストール

### 既にインストールされていないか確認

まず、pyenvがすでにインストールされていないか確認をします。
まずはターミナルを開き、以下のコマンドをコピーして、ターミナルにペーストして実行してください。


```bash title="ターミナル"
pyenv -v
```

もし、インストールされていなければ、以下のように表示されると思います。
```bash title="ターミナル"
zsh: command not found: pyenv
```

インストールされていれば、以下のようになると思います。
```brew title="ターミナル"
pyenv X.X.X
```
^X.X.Xにはバージョンが入るので、数字があれば問題ないです^

### Let's インストール

では、brewをインストールできたなら、pyenvのインストールを行っていきましょう。
まずは下記のコマンドを実行してください
```bash title="ターミナル"
brew install pyenv
```

このような物が出てくるはずです。
```bash title="ターミナル"
==> Installing dependencies for pyenv: m4, autoconf, openssl@1.1, pkg-config and readline
==> Installing pyenv dependency: m4
==> Pouring m4--1.4.19.arm64_big_sur.bottle.tar.gz
🍺  /opt/homebrew/Cellar/m4/1.4.19: 13 files, 726.3KB
==> Installing pyenv dependency: autoconf
==> Pouring autoconf--2.71.arm64_big_sur.bottle.tar.gz
🍺  /opt/homebrew/Cellar/autoconf/2.71: 71 files, 3.2MB
==> Installing pyenv dependency: openssl@1.1
==> Pouring openssl@1.1--1.1.1k.arm64_big_sur.bottle.tar.gz
==> Regenerating CA certificate bundle from keychain, this may take a while...
🍺  /opt/homebrew/Cellar/openssl@1.1/1.1.1k: 8,071 files, 18MB
==> Installing pyenv dependency: pkg-config
==> Pouring pkg-config--0.29.2_3.arm64_big_sur.bottle.tar.gz
🍺  /opt/homebrew/Cellar/pkg-config/0.29.2_3: 11 files, 677.1KB
==> Installing pyenv dependency: readline
==> Pouring readline--8.1.arm64_big_sur.bottle.tar.gz
🍺  /opt/homebrew/Cellar/readline/8.1: 48 files, 1.7MB
==> Installing pyenv
==> Pouring pyenv--2.0.4.arm64_big_sur.bottle.tar.gz
🍺  /opt/homebrew/Cellar/pyenv/2.0.4: 772 files, 2.7MB
```

### pyenvのpath設定
次にpath設定をしていきます。
自分のシェルに応じて、それぞれのコマンドを一個ずつ実行してください。

!!! note "自分のシェルの確認方法"
    下記のコマンドで確認できるので、自分のシェルに合わせて下記のコマンドを一個ずつ実行してください。
    ```bash title="ターミナル"
    echo "$SHELL"
    ```
#### zshの場合
```bash title="ターミナル"
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
```
```bash title="ターミナル"
echo 'export PATH="$PYENV_ROOT/shims:$PATH"' >> ~/.zshrc
```
```bash title="ターミナル"
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```
```bash title="ターミナル"
source ~/.zshrc
```

#### bashの場合
```bash title="ターミナル"
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
```
```bash title="ターミナル"
echo 'export PATH="$PYENV_ROOT/shims:$PATH"' >> ~/.bash_profile
```
```bash title="ターミナル"
echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
```
```bash title="ターミナル"
source ~/.bash_profile
```

## Pyenvを使ってPythonのインストール

いよいよやってきました。Pythonのインストール:fontawesome-brands-python:

まずpyenvでインストールできるPythonのバージョンを確認します。
```bash title="ターミナル"
pyenv install --list
```
そしたら以下のようになるはずです。
```bash title="ターミナル"
Available versions:
  ...
  2.7.0
  3.7.0
  3.8.0
  3.9.0
  3.9.1
  3.9.2
  3.9.3
  3.9.4
  3.10.0a7
  3.10-dev
  anaconda-1.4.0
  ...
```
で表示された一覧から、最新の物は数字のみで、3つ目の数字が文字が無く、devが書いていない物で一番バージョンが高いものを選ぶか
上の場合だと `3.9.4` です。
心配なら安定の`3.8.X`のどれかにしてください。無ければそれより下の`3.7.X`にしてください。

### Let's インストール
さっきのコマンドでバージョンを選んだと思ったので、実際にインストールしていきます。
選んだものを `X.X.X` に入れて実行してください
```bash title="ターミナル"
pyenv install X.X.X
```
こうなるはずです
```bash title="ターミナル"
python-build: use openssl@1.1 from homebrew
python-build: use readline from homebrew
Downloading Python-3.7.11.tar.xz...
-> https://www.python.org/ftp/python/3.7.11/Python-3.7.11.tar.xz
Installing Python-3.7.11...
python-build: use readline from homebrew
python-build: use zlib from xcode sdk
Installed Python-3.7.11 to /Users/toshiki/.pyenv/versions/3.7.11
```

### インストールでできたか確認

インストールできた確認しましょう。
`X.X.X`は先ほど選んだバージョンです
```bash title="ターミナル"
pyenv versions
```

インストールできていたら、下記のようになります。
```bash title="ターミナル"
 * system (set by /Users/user/.pyenv/version)
   X.X.X
```

インストールはできたのですが、システムに指定されているPythonのバー所を変更する必要があります。
下記のコマンドで変わっていないのが確認できます
```bash title="ターミナル"
python -V
```

そしたらこのような表示が返ってきます。
```bash title="ターミナル"
Python 2.X.X
```

!!! note "補足"
    Macbookでは最初からPythonが入っています。
    ですが、ひと昔のPython2系が入っており、Python2系では、記述手法などがだいぶ変わったPython3系はつかえないので、インストールする必要があります

### システム指定のPythonを変更する
下記の2つのコマンドでさきほど選択したバージョンを`X.X.X`の場所に入れ替えて、実行し、インストールしてください。

```bash title="ターミナル"
pyenv global X.X.X
```
```bash title="ターミナル"
pyenv local X.X.X
```

### 最後にPythonのバージョンを確認する
バージョンが変わったか確認します。
```bash title="ターミナル"
python -V
```

こう表示されていれば成功です
```bash title="ターミナル"
Python X.X.X
```

どうだったでしょうか？これでPythonの環境構築は終わりました。

是非、次の[VSCodeを使ってみよう！]()をやってみましょう！

## 参考サイト一覧
[M1 Mac環境にPython3をインストールする方法](https://hitori-sekai.com/python/mac-python-install/)(最終アクセス日: 2022/4/9)

[pyenvでPythonバージョンを管理する](https://cyublog.com/articles/python-ja/pyenv/)(最終アクセス日: 2022/4/9)