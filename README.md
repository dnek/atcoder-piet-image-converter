# atcoder-piet-image-converter

## 概要
[AtCoder](https://atcoder.jp/)で画像ファイルを[Plain PPM](https://netpbm.sourceforge.net/doc/ppm.html#plainppm)形式に変換し、Pietのソースコードとして提出できるようにします。
また、Plain PPM形式の提出結果を画像に変換して表示します。

## 詳細

### 画像ファイルを提出用に変換
AtCoderのソースコードエディタに「変換 (Piet)」というボタンを追加します。
このボタンをクリックして画像ファイルを選択、または、このボタンに画像ファイルをドラッグ&ドロップすることで、その画像をPPM形式に変換してソースコードエディタに反映します。
PNGやGIF等のブラウザで表示可能な形式の画像であれば変換できるはずです。

また、Plain PPM形式は読みやすい反面冗長であるため、AtCoderのコード長制限に抵触しがちです。
そのため、変換時に以下を適用してPietのソースコードとしての等価性を保ちながらコード長を節約します。

- 最大コーデルサイズが1になるように画像の解像度を下げる。
- 色成分の最大値を85にする。
- Plain PPMのマジックナンバー (P3) の直後を空白で区切らない。

### 提出結果を画像に変換
AtCoderの提出結果ページで、以下の条件を満たす場合にPietのソースコードを画像に変換して表示します。

- ジャッジ結果が表示されている。
- 提出言語がPietである。
- ソースコードがPlain PPM形式で書かれている。

また、ボタンをクリックして以下を行えます。

- プレビュー画像の拡大率を変更する。
- 画像をPNG形式でダウンロードする。

## インストール
- Greasy Fork https://greasyfork.org/ja/scripts/553186-atcoder-piet-image-converter

## ソース
- https://github.com/dnek/atcoder-piet-image-converter/raw/main/atcoder-piet-image-converter.user.js

## 関連
- AtCoderで改行をLFにして提出し、コード長も表示するUserScript https://github.com/dnek/atcoder-lf-submit
