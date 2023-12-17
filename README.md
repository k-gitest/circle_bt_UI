## 目的

スイッチで開閉する円状オブジェクトのコンポーネントを開発する

横スライドするカルーセルに対して円スライドする観覧車を作る

## app概要

es6で構築されたスライドコンポーネントプロジェクトのプロトタイプです。

## 要件

* es6で開発する
* クロスブラウザで動作させる
* 円状に画像を配置し円状にスライドさせる
* 画像にはキャプションをつける
* スイッチで開閉させる
* スイッチは4つ設置し個別に開閉させる
* 開くと回転開始する
* 閉じると回転停止する
* 全体を開閉するメインスイッチをつける

## 開発環境

* JavaScript(ES6)

## ロジック

* 開閉はJS、円配置と回転はCSSで行う
* 回転オブジェクトとエレメントは全て配列に入れる
* 円配置のスタイルは適用しておき座標を0に戻しておく
* スイッチ開閉処理の中に回転処理の再生と停止を書く

## 課題

* 円配置の画像は何個でも入れられるが多いと重なってしまう
* キャプションの文字列が長いと重なってしまう
* 回転のバブリングが生じて円回転しながら画像も回転してしまう

## ポイント

* 円状wrapperオブジェクトに対してimgとキャプションのwrapperは逆回転させる
* 回転をcssで行う事でcpu／gpu依存にする
* 画像は5個が限度、文字列は10文字以内にするとバランスが良い

## 結論

3、4年ほど前のコードだがwebでもスマホでも問題なく動作する。

cpu／gpu依存なので4つ同時に回転させた場合、PCスペックが低いとファンが回る程度にリソースを使用する。メモリも多少消費する。処理落ちはしない。

wrapper部分のコードは改善の余地がある。

使う場面は中々ないが、個別であれば円配置スペースもあるのでメニューなどに使えるかもしれない。その場合は回転させない方が良いだろう。
