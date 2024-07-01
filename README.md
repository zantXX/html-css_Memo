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
スクリプトレット・スクリプト式・EL式
``` jsp
<!-- スクリプトレット -->
<%
  int num = 1;
%>
<!-- スクリプト式 -->
<p><%= num %></p>
<!-- EL式(繰り返しでは使えない) -->
<p>${hoge.name}</p>
<p>${hogeList[0].name}</p>
```
pageディレクティブ
``` jsp
<%@ page contentType="text/html; charset=UTF-8" language="java" pageEncoding="UTF-8"%>
<%@ page import="java.util.*" %>

```

forward・redirect
``` jsp
request.getRequestDispatcher("index2.jsp").forward(request, response);
response.sendRedirect("index3.jsp");
```

scope
``` java
// requestScope(一往復まで情報を保持)
request.setAttribute("key", "value");
Hoge hoge = (Hoge) request.getAttribute("key");
// sessionScope(個人のアプリケーションの情報を保持)
HttpSession session = request.getSession();
session.setAttribute("key", "value");
Hoge hoge = (Hoge) session.getAttribute("key");
session.removeAttribute("key");
session.invalidate();
// applicationScope(全員のアプリケーションの情報を保持)
ServletContext context = this.getServletContext();
application.setAttribute("key", "value");
Hoge hoge = (Hoge) application.getAttribute("key");
application.removeAttribute("key");
```

init・destroy
```java
public void init(ServletConfig config) throws ServletException {
  super.init(config);
    // 初期化処理
}
public void destroy() {
    // 終了処理
}
```
Listener・Filter
```java
@WebListener
public class HogeListener implements ServletContextListener {
  public void contextInitialized(ServletContextEvent sce) {}
  public void contextDestroyed(ServletContextEvent sce) {}
}
@WebFilter("/Hoge/*")
public class HogeFilter implements Filter {
  public void init(FilterConfig config) {}
  public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {}
  public void destroy() {}
}
```

include
``` jsp
<!-- 動的include -->
<% request.getRequestDispatcher().include(request, response); %>
<jsp:include page="header.jsp"/>
<!-- 静的include -->
<%@ include file="header.jsp" %>

```

taglib(外部ライブラリのインポートが必要)
``` jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<!-- 安全に変数を出力 -->
<c:out value="${変数名}" />
<!-- 条件分岐 -->
<c:if test="${変数名} == 値">
  <p>条件が成立</p>
</c:if>
<c:choose >
  <c:when test="${変数名} == 値1">
    <p>条件が成立</p>
  </c:when>
  <c:when test="${変数名} == 値2">
    <p>条件が成立</p>
  </c:when>
  <c:otherwise>
    <p>条件が成立しない</p>
  </c:otherwise>
</c:choose>
<!-- 繰り返し -->
<c:forEach var="変数名" begin="開始値" end="終了値" step="増加値">
  <p>${変数名}</p>
</c:forEach>
<c:forEach var="変数名" items="${配列/リスト}" >
   <p>${変数名}</p>
</c:forEach>
```

JDBC(JDBCドライバのインポートが必要)
``` java
Class ConnectManager{
  private final String JDBC_URL = "接続先URL";
  private final String DB_DRIVER = "ドライバ名";
  private final String DB_USER = "ユーザー名";
  private final String DB_PASS = "パスワード";
  private Connection con;

  public ConnectManager(){
    try{
      Class.forName(DB_DRIVER);
    }catch(ClassNotFoundEception e){
      throw new IllegalArgumentException("JDBCドライバが見つかりません");
    }

    try{
      con = DriverManager.getConnection(JDBC_URL, DB_USER, DB_PASS);
    }catch(SQLException e){
      throw new IllegalArgumentException("DB接続に失敗しました");
    }
  }

  public List<> getList(String sql){
    try{
      PreparedStatement pStmt = con.prepareStatement(sql);
      ResultSet rs = pStmt.executeQuery();

      while(rs.next()){
        //取得したデータを格納する
        String s = rs.getString("カラム名");
        int i = rs.getInt("カラム名");
      }
    }catch(SQLException e){
      e.printStackTrace();
      return null;
    }
    return null;

    public boolean setList(String sql, List<> list){
    try{
      // String sql = "INSERT INTO テーブル名 (カラム名,...) VALUES (?,...)";
      PreparedStatement pStmt = con.prepareStatement(sql);
      pStmt.setString(1,list.get(0));
      int result = pStmt.executeUpdate();

      if( result != 1 ){
        return false;
       }
    }catch(SQLException e){
      e.printStackTrace();
      return false;
    }
    return true;
}