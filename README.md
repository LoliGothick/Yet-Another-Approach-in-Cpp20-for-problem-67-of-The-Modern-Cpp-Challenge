# Modern C++チャレンジ問題67のたったひとつの冴えた解き方
Modern C++チャレンジ読書会 vol.27

## 実装コメント

使えるC++20の機能は利用、実装されていない部分はC++17の機能で我慢。
回答ではデコレータを使っていたが、ストラテジーパターンを採用した。
バリデーションの結果、エラー理由がわからなければバリデーションとして三流。
ということで、自分で作ったresult型のライブラリを投入して真面目にコーディングした。

## ビルド環境について

コンパイラはg++11（gcc-head）を利用している。
result型のライブラリがBoostライブラリを利用しているのでBoostのインストールも必要。
result型のライブラリが[{fmt}](https://github.com/fmtlib/fmt)も使っている。
これはBoost.FormatがC++20で削除された機能を使っているためである。

このコードをコンパイルして動かしたい場合はリポジトリ内のDockerfileをビルドするとよい。
さすれば、悠久の時がすぎたあとにビルド環境が整うであろう。
まあ、そんなことをしなくても
```shell
docker pull enumack/mitama-env:gcc-head-2020-11-11
```
をすればよいのですけど。
あなたと
巨大なDocker Imageいますぐダウンロー

ド
