## リンク情報

### W3C HTMLの仕様書
[仕様書](http://www.w3.org/TR/html51)

### HTML/CSSのブラウザ対応状況
[caniuse.com](https://caniuse.com/) 

### ブラウザの利用状況
[StatCounter Global Sats](http://gs.statcounter.com/) 

## CSSの継承
+ フォント関係のプロパティは継承する
+ 背景色や背景画像などのプロパティは継承しない
+ ボックスモデル関係のプロパティは継承しない
+ その他の多くのプロパティは継承しない

## フォントサイズ
よくあるフォントサイズの指定方法
+ タグごとにフォントサイズを指定する方法
+ 全てのフォントサイズを相対的に決める方法
相対的にフォントサイズを決める場合は、
<html>要素に対して「基準のフォントサイズ」を単位pxで設定する。(bodyではなくて、htmlに基準を設定する。)

## フォント設定
フォント設定のよくあるパターン

+ 表示するフォントにゴシック体を使用する場合は、次のようなCSSを書くのがお決まりのパターン
```css
body {
    font-family: "Hiragino Kaku Gothic ProN", "ヒラギノ角ゴ ProN", Meiryo, "MS　Pゴシック", sans-serif;
}
```

+ 表示するフォントをゴシック体にする省略パターン
```css
body {
    font-family: sans-serif;
}
```

## Webフォントを利用する
Webフォントを利用する例

```html
<head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="style.css">
    <title>Webフォントを使用する</title>
    <link rel="stylesheet" href="http://fonts.googleapis.com/earlyaccess/notosansjapanese.css">
</head>
<style>
    body {
        font-family: 'Noto Sans Japanese';
    }
</style>
```

## brタグの使い方
brタグは単に改行をしたい位置で使わない。同じ意味のコンテンツ内で改行をしたい場合に使う。

## id名の付け方
id名に意味がある必要はない。id名は機械的に決める方がいい。
+ id名の付け方1:見出しのテキストをそのままid名にする
```html
<h2 id="おかしいと思ったら">おかしいと思ったら</h2>
```

+ id名の付け方2:HTMLを書いている瞬間の時間をid名にする
```html
<h2 id="headline2127">見出し</h2>
```

## 属性セレクタ

<a>タグでtarget="_blank"が指定されている場合のみ、リンクの後ろに画像を表示する
```css
a[target="_blank"]::after {
    content: url(".");
}
```

属性セラクタを利用すると、例えば
+ 拡張子がpdfにリンクされているものは、pdfアイコンを表示する      
+ checkが付いているチェックボックスの背景色を変更する      
などが簡単に実現できる。

## 子孫セレクタ
子孫セレクタは、<img>タグが<a>タグの子要素であっても、孫要素であっても選択される。よって、HTMLの構造に合わせて、間のタグを全て指定する必要はない。

## opacityプロパティ
透明度を指定する。0〜1の少数を指定する。

## インラインボックスとブロックボックス

### インラインボックス
コンテンツが収まる最小限のボックス
<img><input><strong><b><i><a>...

### ブロックボックス
コンテンツの量に関係なく親要素と同じ幅のボックス

#### そのタグがコンテンツに何らかの意味づけをするもの
<h1><ul><li><p>...      
そのテキストを修飾するタグしか入れれない

#### 他のタグを囲んで、情報の整理をしたりグループ化したりするもの
<div><ul><li><article><section>...      
どんなタグも子要素にできる


