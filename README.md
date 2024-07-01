# html-css_Memo
workpage: https://zantXX.github.io/html-css_memo
レイアウトの詳細を知りたいときは、Developer Tools(検証)を使う。styleには、cssが、Computedには、boxのサイズ等が記述される。

cssは、テンプレとして使えるフレームワークが複数存在
- [bulma](https://bulma.io/)
- [bootstrap](https://getbootstrap.jp/)
- [semantic-ui](https://semantic-ui.com/)

## 1. HTML
### 文書全体
| タグ名 | 用途 | 備考 | url |
| ---- | ---- | ---- | ---- |
| html | 文書全体の設定 | 大体、「lang="ja"」をつける | [html](https://developer.mozilla.org/ja/docs/Web/HTML/Element/html) |
| head | 本文でない環境設定 | 文字コードとかタイトルとかスタイルとかjavascriptとか | [head](https://developer.mozilla.org/ja/docs/Web/HTML/Element/head) |
| body | ページの本文 | ここに色々書く | [body](https://developer.mozilla.org/ja/docs/Web/HTML/Element/body) |

### body内
| タグ名 | 用途 | 主な属性<br>(*:cssに記述推奨) | 効果 | 備考 |
| ---- | ---- | ---- | ---- | ---- |
| h1~h6  | 見出し | *font-size | フォントサイズを変える | [h1](https://developer.mozilla.org/ja/docs/Web/HTML/Element/Heading_Elements) |
| p | 段落 | (global) | (global) | [p](https://developer.mozilla.org/ja/docs/Web/HTML/Element/p)  |
| a  | リンク | href | リンクの設定 | [a](https://developer.mozilla.org/ja/docs/Web/HTML/Element/a)  |
| ^  | ^ | download | リンク先をダウンロードするように指示 | ^ |
| img  | 画像 | src | 画像のファイル場所を指定 | [img](https://developer.mozilla.org/ja/docs/Web/HTML/Element/img) |
| ^  | ^ | alt | 画像の説明を添付 | ^ |
| ^  | ^ | width | 画像の幅を指定<br>(heightと同時指定で、事前に場所の確保できる) | ^ |
| ^  | ^ | height | 画像の高さを指定<br>(widthと同時指定で、事前に場所の確保できる) | ^ |
| ^  | ^ | srcset, sizes | srcsetで画像群を設定し、sizesで適する値を入力することで適する画像を選択できる | ^ |
| ^  | ^ | loading | lazyに指定することで、表示の初速を早めることができる | ^ |
| ^  | ^ | *vertical-align | 垂直方向の位置を調整 | [vertical-align](https://developer.mozilla.org/ja/docs/Web/CSS/vertical-align) |
| ^  | ^ | *margin | 上下左右の余白を設定<br>(0 auto)で上下の余白なし、左右中央揃えになることが多い | [margin](https://developer.mozilla.org/ja/docs/Web/CSS/margin) |
| ul | リスト | type | 行頭の形を変えることができる(・や■など) | [ul](https://developer.mozilla.org/ja/docs/Web/HTML/Element/ul)  |
| ol | 番号付きリスト | type | 行頭の形を変えることができる(1,a,A,i,Iなど)  | [ol](https://developer.mozilla.org/ja/docs/Web/HTML/Element/ol) |
| ^  | ^ | start | 最初の数字を指定できる | ^ |
| ^  | ^ | reversed | 数字を逆順にできる | ^ |
| li | リストの中身 | value | olの順番を無視して指定 | [li](https://developer.mozilla.org/ja/docs/Web/HTML/Element/li) |
| div  | ブロック要素  | (global) | (global) | [div](https://developer.mozilla.org/ja/docs/Web/HTML/Element/div) <br>フローコンテンツの汎用ブロックコンテナ |
| span  | インライン要素  | (global) | (global) | [span](https://developer.mozilla.org/ja/docs/Web/HTML/Element/span) <br>記述コンテンツの汎用インラインコンテナ|

### table内

### form・input

### display
- flow
- flex
- grid

## 2. CSS

| 指定方法 | cssの書き方 | 制限 |
| ---- | ---- | ---- |
| タグ名 | tag  | 同じタグで複数指定できない |
| id | #id  | 同じIDで複数指定できない |
| class | .class  | 同じclassで複数指定できる |

例:
``` css
html{
  background-color: #0000FF;
}

#id{
  color:#00FF00;
}

.class{
  color:#FF0000;
}

```

``` html
<html>
  <head>
    <title>タイトル</title>
    <meta charset="utf-8">
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
    <h1>タイトル</h1>
    <p>本文</p>
    <div class="class">
      <span id="id">
        ここに文字が入る
      </span>
    </div>
  </body>
</html>

```

## 3.jsp
### jspの書き方
スクリプトレット・スクリプト式
``` jsp
<%-- スクリプトレット -->
<%
  int num = 1;
%>
<%-- スクリプト式 -->
<p><%= num %></p>
```
pageディレクティブ
``` jsp
<%@ page contentType="text/html"; charset="UTF-8" language="java" %>
<%@ page import="java.util.*" %>

```
include
``` jsp
<%@ include file="header.jsp" %>

```