# Pythonを使った競プロ

インターネットで、プログラミングを勉強していると、競技プログラミングというものに出会うと思います。
おそらく、大体の人は、AtCoder, Paizaスキルチェックなどが印象深いでしょう。
私が思うに、競技プログラミングはその言語に慣れるための練習にいいと思います。

プログラミング的思考やアルゴリズムの知識などが必要なものもあると思いますが、
簡単な問題やグラフ理論などの高校数学を使わない競プロの問題は言語に慣れるための良い練習に使えると思います。

この章では、AtCoderの問題やPaizaの練習問題の解説、Pythonの記述TipsやPythonの実行速度をすこし上げる方法などを解説します。

## Pythonは競プロに向いてるの？

結論から言うと**「あまり向いていません」**

Pythonが向いていないと言われる最大の理由は、実行速度が遅いことが一番の問題です。
競プロでは、実行時間やメモリーの制限などがあり、計算量が多い問題などでは致命的になってしまいます。
処理にとても時間をかけてしまって、失格になったりもします。
場合によってはメモリーを使いすぎて失格になるでしょう。

!!! tip "計算量とは？"
    プログラムを実行して、どのくらいの計算をするか大雑把に表すものです。
    気が向いたら専用の記事を作るかもしれません。

ただ、Pythonにはメリットがあります、それは記述のしやすさです。
他の言語と比べ、とても簡単に、高速に、記述が可能です。

`C++`, `C`, `C#`と比べてみると歴然とした差であることがわかります。
また記述が多くなってはいますが、圧倒的に`C++`, `C`, `C#`の方が速いです。

Pythonでは一部のライブラリーを使うことで、実行速度が速くすることができます。
こういったライブラリーの大体は、`C`などで書いたプログラムをコンパイルしてPythonのモジュールとして実行しています。

??? tips "Numpyがなぜ速いのかもう少し深掘りしたいあなたへ"
    Numpyが速い理由はBLAS APIを実装しているのと、静的型付き言語が大きいと言われています。
    興味がある方は是非調べてみてください。

    私は頑張って調べてみましたが、内容がわけわかめでした。

    間違った内容をここで発信するのはどうかと思ったので、これ以上解説はできないできません。

なのでそういったライブラリーを使えば、普段より高速に実行できると思いますが、そこのコンテンストのルールによっても変わるのでNumpyが使えない場合もあります。
AtCoderやPaizaでは使えるので、お友達の人はたくさんいることでしょう。（ちな俺もともだち）

こういったライブラリーが使えても、どういった場面で使うのか、どうしたら速くなって、どうしてしまったら遅くなるのか、などの知識も必要です。

また、問題によっては全てがnumpyで解けるわけではありません。
それもまたPythonが競プロに向いているとはいえない理由の一つだと思います。

## Tipsで扱う内容について

アルゴリズム解説のほかに、便利な記述方法や関数、メゾットを紹介するコーナーを作っています。
興味がある方は是非使ってみください。