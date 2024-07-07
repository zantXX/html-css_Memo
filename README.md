# html-css_Memo
workpage: https://zantXX.github.io/html-css_memo

レイアウトの詳細を知りたいときは、Developer Tools(検証)を使う。

Developer Tools(検証)のstyleにはcssが、Computedにはboxのサイズ等が記述されるためデバックで用いると良い。

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
| link  | 外部リンクと紐付け  | 外部リンクと紐付け(css, javascript, favicon)。head内に記述する場合が多い  | [link](https://developer.mozilla.org/ja/docs/Web/HTML/Element/link) |
| body | ページの本文 | ここに色々書く | [body](https://developer.mozilla.org/ja/docs/Web/HTML/Element/body) |

### body内
| タグ名 | 用途 | 主な属性<br>(*:cssに記述推奨) | 効果 | 備考 |
| ---- | ---- | ---- | ---- | ---- |
| h1~h6  | 見出し | *font-size | フォントサイズを変える | [h1](https://developer.mozilla.org/ja/docs/Web/HTML/Element/Heading_Elements) |
| br | 改行  |  (global)  | 改行する  |  [br](https://developer.mozilla.org/ja/docs/Web/HTML/Element/br)  |
| hr  | 区切り線  |  (global)  | 区切り線を引く  |  [hr](https://developer.mozilla.org/ja/docs/Web/HTML/Element/hr)  |
| p | 段落 | (global) | (global) | [p](https://developer.mozilla.org/ja/docs/Web/HTML/Element/p)  |
| q | 引用  |  cite  | 引用先を示すURL  |  [q](https://developer.mozilla.org/ja/docs/Web/HTML/Element/q)  |
| blockquote  | 引用ブロック  | cite | 引用元のURL  | [blockquote](https://developer.mozilla.org/ja/docs/Web/HTML/Element/blockquote)   |
| a  | リンク | href | リンクの設定 | [a](https://developer.mozilla.org/ja/docs/Web/HTML/Element/a)  |
| ^  | ^ | download | リンク先をダウンロードするように指示 | ^ |
| button | ボタン  | onclick | ボタンが押されたときの動作をjavascriptで指定(リンクを作成するときは、"loction.href='リンク先のURL'"と設定) | [button](https://developer.mozilla.org/ja/docs/Web/HTML/Element/button)  |
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
| fieldset | フォーム内でグループ化する要素  | name | radioを内包する場合のkey名になる | [fieldset](https://developer.mozilla.org/ja/docs/Web/HTML/Element/fieldset) |
| legend  | fieldsetのラベル  | (global) | (global) | [legend](https://developer.mozilla.org/ja/docs/Web/HTML/Element/legend) |
| div  | ブロック要素  | (global) | (global) | [div](https://developer.mozilla.org/ja/docs/Web/HTML/Element/div) <br>フローコンテンツの汎用ブロックコンテナ |
| span  | インライン要素  | (global) | (global) | [span](https://developer.mozilla.org/ja/docs/Web/HTML/Element/span) <br>記述コンテンツの汎用インラインコンテナ|

### table内
| タグ名 | 用途 | 主な属性<br>(*:cssに記述推奨) | 効果 | 備考 |
| ---- | ---- | ---- | ---- | ---- |
| table  | テーブル作成 | (global) | (global) | [table](https://developer.mozilla.org/ja/docs/Web/HTML/Element/table) |
| caption | 表題 | (global) | (global) | [caption](https://developer.mozilla.org/ja/docs/Web/HTML/Element/caption) |
| colgroup | 列のグループ分け | span | またがる列の数を指定 | [colgroup](https://developer.mozilla.org/ja/docs/Web/HTML/Element/colgroup) |
| col | 列のグループ分けの中身 | span | またがる列の数を指定 | [col](https://developer.mozilla.org/ja/docs/Web/HTML/Element/col) |
| thead | テーブルヘッダ(見出し) | (global) | (global) | [thead](https://developer.mozilla.org/ja/docs/Web/HTML/Element/thead) |
| tbody  | テーブルボディ  |  (global)  |  (global)  | [tbody](https://developer.mozilla.org/ja/docs/Web/HTML/Element/tbody)  |
| tfoot  | テーブルフッタ  |  (global)  |  (global)  | [tfoot](https://developer.mozilla.org/ja/docs/Web/HTML/Element/tfoot)  |
| tr  | テーブル行(row)  |  (global)  |  (global)  | [tr](https://developer.mozilla.org/ja/docs/Web/HTML/Element/tr)  |
| th  | テーブルヘッダ  |  (global)  |  (global)  | [th](https://developer.mozilla.org/ja/docs/Web/HTML/Element/th)  |
| ^  | ^ | colspan | 列の結合 | ^ |
| ^  | ^ | rowspan | 行の結合 | ^ |
| ^  | ^ | abbr | セルの内容説明 | ^ |
| ^  | ^ | scope | 関連するセルを定義 | ^ |
| td  | テーブルデータ |  headers  |  th要素と対応するようになる  | [td](https://developer.mozilla.org/ja/docs/Web/HTML/Element/td)  |
| ^  | ^ | colspan | 列の結合 | ^ |
| ^  | ^ | rowspan | 行の結合 | ^ |


### form・input
タグ名
| タグ名 | 用途 | 主な属性<br>(*:cssに記述推奨) | 効果 | 備考 |
| ---- | ---- | ---- | ---- | ---- |
| form | フォーム | action | 送信する情報を処理するURLを指定 | [form](https://developer.mozilla.org/ja/docs/Web/HTML/Element/form) |
| ^  | ^ | method | 送信する方法を指定(get, post) | ^ |
| ^  | ^ | autocomplete | 補完入力を受け付けるか設定 | ^ |
| input | 入力フォーム  | type  | 入力タイプを指定(下に詳細)  |  [input](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input)   |
|  ^  |  ^  | name  | 送信される情報の名前  |  ^  |
|  ^  |  ^  | value  | 入力フォームに設定する値  |  ^  |
| label | ラベル   | for  | 関連させる入力フォームのIDを指定  |  [label](https://developer.mozilla.org/ja/docs/Web/HTML/Element/label)<br>inputの説明として有効 |
|textarea| 大きいテキスト入力フォーム   | name   |  送信される情報のkeyを指定 |  [textarea](https://developer.mozilla.org/ja/docs/Web/HTML/Element/textarea)<br>input type="text"と同様に使える  |
|  ^  |  ^  | cols  | 表示幅の文字数を指定   |   ^   |
|   ^  |   ^   | rows   | 表示行数の指定   |
|  ^  |  ^  | value  | 入力フォームに設定する値  |  ^  |
| ^  | ^ |maxlength | 最大入力文字数の指定 | ^ |
| ^  | ^ | minlength | 最低入力文字数の指定 | ^ |
| ^  | ^ | placeholder | 短いヒントを提供(labelの使用を推奨) | ^ |
| ^  | ^ | wrap | 改行コードの扱いについて指定 | ^ |
| select  | 選択フォーム   | name   | 送信される情報のkeyを指定  |  [select](https://developer.mozilla.org/ja/docs/Web/HTML/Element/select)  |
| ^  | ^ | required | 空でない項目の選択を必須とする | ^ |
| ^  | ^ | size | 一度に見えるべきリストの行数を指定 | ^ |
| optgroup   | オプションのグループ化   | label    | ラベルを表示  |  ^  |
| option  | 選択肢   | value  | 選択フォームに設定する値  |  [option](https://developer.mozilla.org/ja/docs/Web/HTML/Element/option)  |
| ^  | ^ | label | 選択肢の意味を指定 | ^ |
| ^  | ^ | selected | 初期状態を指定。 | selectに一要素のみ |
| button | ボタン  | formaction | 送信された情報を処理するURLを個別で指定 | [button](https://developer.mozilla.org/ja/docs/Web/HTML/Element/button)  |
|  ^   |  ^  | formmethod  | 送信する方法を個別で指定(get, post) |  ^  |
|  ^   |  ^  | form | 関連付けするform idを指定 |  ^  |

input type一覧（各表示は[ここ](https://zantXX.github.io/html-css_memo)・このREADME.mdをmarkdownを直接開く)
| input type属性 | アイコン |用途 | 主な属性<br>(*:cssに記述推奨) | 効果 | 備考 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| text | <input type="text"> | テキスト入力  | name | 送信される情報のkeyを指定 | [text](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/text) |
| ^  | ^ | ^ | maxlength | 最大入力文字数の指定 | ^ |
| ^  | ^ | ^ | minlength | 最低入力文字数の指定 | ^ |
| ^  | ^ | ^ | pattern | 正規表現による入力制限 | ^ |
| ^  | ^ | ^ | placeholder | 短いヒントを提供(labelの使用を推奨) | ^ |
| ^  | ^ | ^ | readonly | 編集不可能とする | ^ |
| ^  | ^ | ^ | size | 入力欄の幅を何も自分にするかを指定 | ^ |
| ^  | ^ | ^ | required | 必須項目として指定 | ^ |
|  ^   |  ^  |  ^  | inputmode  | 入力パターンの指定  |  [inputmode](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input#inputmode)  |
| password  | <input type="password"> | パスワード  | name   | 送信される情報のkeyを指定   |   [password](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/password)  |
|   ^   |   ^   |   ^  |maxlength   | 最大の文字数を指定   |   ^   |
|   ^   |   ^   |   ^  |minlength   | 最小の文字数を指定   |   ^   |
|  ^   |  ^  |  ^  | pattern  | 入力内容の正規表現を指定  |  ^  |
|  ^   |  ^  |  ^  | placeholder  | 短いヒントを提供(labelでの説明を推奨)  |  ^  |
|  ^   |  ^  |  ^  | required  | 必須項目として指定  |  ^  |
|  ^   |  ^  |  ^  | autocomplete  | パスワードの自動入力  |  ^  |
|  ^   |  ^  |  ^  | inputmode  | 入力パターンの指定  |  [inputmode](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input#inputmode)  |
| number  | <input type="number" value="1" size=3 >  | 数値   | name   | 送信される情報のkeyを指定    |   [number](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/number)   |
|  ^   |  ^  |  ^  | step  | 入力できる数値の間隔を指定  |  小数第二位までの指定は、step="0.01"とする  |
|  ^   |  ^  |  ^  | min  | 最小値を指定  |  ^  |
|  ^   |  ^  |  ^  | max  | 最大値を指定  |  ^  |
|  ^   |  ^  |  ^  | value  | 初期値を指定  |  ^  |
|  ^   |  ^  |  ^  | list  | 選択肢をリストとして指定  |  datalistタグを使用する  |
|  ^   |  ^  |  ^  | pattern  | 入力内容の正規表現を指定  |  ^  |
|  ^   |  ^  |  ^  | placeholder  | 短いヒントを提供(labelでの説明を推奨)  |  ^  |
|  ^   |  ^  |  ^  | size  | 文字数を指定  |  ^  |
|  ^   |  ^  |  ^  | readonly  | 入力できないようにする  |  ^  |
|  ^   |  ^  |  ^  | required  | 必須項目として指定  |  ^  |
| email  | <input type="email" placeholder="hoge@gmail.com"> |メールアドレス  | name   | 送信される情報のkeyを指定   |   [email](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/email)  |
|   ^   |   ^   |   ^  |maxlength   | 最大の文字数を指定   |   ^   |
|   ^   |   ^   |   ^  |minlength   | 最小の文字数を指定   |   ^   |
|   ^   |   ^   |   ^  |list   | カンマや空白での複数入力を許可   |   ^   |
| ^  | ^ | ^ | pattern | 正規表現による入力制限 | ^ |
| ^  | ^ | ^ | placeholder | 短いヒントを提供(非推奨) | ^ |
| ^  | ^ | ^ | readonly | 編集不可能とする | ^ |
| ^  | ^ | ^ | size | 入力欄の幅を何も自分にするかを指定 | ^ |
| ^  | ^ | ^ | required | 必須項目として指定 | ^ |
| tel | <input type="tel"  placeholder="090-9999-9999"> | 電話番号 | name  | 送信される情報のkeyを指定  |  [tel](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/tel)<br>スマホでは、電話入力専用のキーパッドを表示できる  |
|   ^   |   ^   |   ^  |maxlength   | 最大の文字数を指定   |   ^   |
|   ^   |   ^   |   ^  |minlength   | 最小の文字数を指定   |   ^   |
|  ^   |  ^  |  ^  | list  | 選択肢のリストを指定  |  datalistタグを使用  |
| ^  | ^ | ^ | pattern | 正規表現による入力制限 | ^ |
| ^  | ^ | ^ | placeholder | 短いヒントを提供(非推奨) | ^ |
| ^  | ^ | ^ | readonly | 編集不可能とする | ^ |
| ^  | ^ | ^ | size | 入力欄の幅を何も自分にするかを指定 | ^ |
| ^  | ^ | ^ | required | 必須項目として指定 | ^ |
| ^  | ^ | ^ | autocorrect | Safariで自動修正を行える | ^ |
| url | <input type="url" placeholder="https://example.com"> | url | name  | 送信される情報のkeyを指定  |  [tel](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/url)|
|   ^   |   ^   |   ^  |maxlength   | 最大の文字数を指定   |   ^   |
|   ^   |   ^   |   ^  |minlength   | 最小の文字数を指定   |   ^   |
|  ^   |  ^  |  ^  | list  | 選択肢のリストを指定  |  datalistタグを使用  |
| ^  | ^ | ^ | pattern | 正規表現による入力制限 | ^ |
| ^  | ^ | ^ | placeholder | 短いヒントを提供(非推奨) | ^ |
| ^  | ^ | ^ | readonly | 編集不可能とする | ^ |
| ^  | ^ | ^ | size | 入力欄の幅を何も自分にするかを指定 | ^ |
| ^  | ^ | ^ | required | 必須項目として指定 | ^ |
| ^  | ^ | ^ | autocorrect | Safariで自動修正を行える | ^ |
| button | <input type="button" value="button"> | ボタン | name  | 送信される情報のkeyを指定  |  [button](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/button)  |
| ^  | ^ | ^ | value | ボタン内に表示する文字を指定 | ^ |
| ^  | ^ | ^ | disabled  | ボタンを押せなくする  |  ^  |
| checkbox  | <input type="checkbox" name="checkboxA">|チェックボックス  | name  | 送信される情報のkeyを指定  |   [checkbox](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/checkbox) <br>labelタグを併用することで、当たり判定を増やせる   |
|  ^  |  ^  |  ^ |value  | 送信される値を指定  |  ^  |
|  ^  |  ^  |  ^ |checked  | 既定のチェック状態を設定  |  ^  |
| radio  | <input type="radio"> | ラジオボタン  | name   | 送信される情報のkeyを指定  |   [radio](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/radio)<br>同一nameに設定することを忘れない  |
|  ^   |  ^  |  ^  | value  | 値の格納  | ^ |
|  ^   |  ^  |  ^  | checked  | 初期値の入力  |  同一nameで１つのみ  |
| color | <input type="color" value="#FF0000"> | 色 | name   | 送信される情報のkeyを指定   |   [color](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/color)  |
|  ^  |  ^  |  ^ |value  | 既定の色の設定を行う(RGB)  |  ^  |
| month  | <input type="month" value="2024-08"> |月  | name   | 送信される情報のkeyを指定   |   [month](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/month)<br>表示形式はブラウザによって異なる  |
|  ^  |  ^  |  ^ |max  | 日にちの上限を設定(yyyy-mm)  |  ^  |
|  ^  |  ^  |  ^ |min  | 日にちの下限を設定(yyyy-mm)  |  ^  |
| week  | <input type="week" value="2024-W33"> | 週  | name   | 送信される情報のkeyを指定   |   [week](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/week)<br>表示形式はブラウザによって異なる  |
|  ^  |  ^  |  ^ |value  | 既定の日にち設定を行う(yyyy-Www)  |  ^  |
|  ^  |  ^  |  ^ |max  | 日にちの上限を設定(yyyy-Www)  |  ^  |
|  ^  |  ^  |  ^ |min  | 日にちの下限を設定(yyyy-Www)  |  ^  |
| ^  | ^ | ^ | required | 必須項目として指定 | ^ |
| date  | <input type="date" value="2024-08-18"> |日付  | name   | 送信される情報のkeyを指定   |   [date](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/date)<br>表示形式はブラウザによって異なる  |
|  ^  |  ^  |  ^ |value  | 既定の日にち設定を行う(yyyy-mm-dd)  |  ^  |
|  ^  |  ^  |  ^ |max  | 日にちの上限を設定(yyyy-mm-dd)  |  ^  |
|  ^  |  ^  |  ^ |min  | 日にちの下限を設定(yyyy-mm-dd)  |  ^  |
| ^  | ^ | ^ | required | 必須項目として指定 | ^ |
| datetime-local  | <input type="datetime-local" value="2024-08-18T08:30"> |日時  | name   | 送信される情報のkeyを指定   |   [datetime-local](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/datetime-local)<br>表示形式はブラウザによって異なる<br>タイムゾーンは別の方法で付加する必要がある  |
|  ^  |  ^  |  ^ |value  | 既定の日時設定を行う(yyyy-MM-ddThh:mm)  |  ^  |
|  ^  |  ^  |  ^ |max  | 日時の上限を設定(yyyy-MM-ddThh:mm)  |  ^  |
|  ^  |  ^  |  ^ |min  | 日時の下限を設定(yyyy-MM-ddThh:mm)  |  ^  |
| time  | <input type="time" value="06:30"><br><input type="time" value="06:30:30"> | 時刻  | name   | 送信される情報のkeyを指定   |   [time](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/time)<br>表示形式はブラウザによって異なる  |
|  ^  |  ^  |  ^ |value  | 既定の時刻設定を行う(hh:mm or hh:mm:ss)  |  ^  |
|  ^  |  ^  |  ^ |max  | 時刻の上限を設定(hh:mm or hh:mm:ss)  |  ^  |
|  ^  |  ^  |  ^ |min  | 時刻の下限を設定(hh:mm or hh:mm:ss)  |  ^  |
|  ^  |  ^  |  ^ |step  | 時刻のステップを秒で設定  |  ^  |
| file  | <input type="file" placeholder=""> | ファイル  | name   | 送信される情報のkeyを指定   |   [file](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/file)<br>右のファイル名の表示の変更や、ファイルサイズの制限はjavascriptで行う  |
| ^  | ^ | ^ | accept | 許可するファイル形式を定義(.doc,.docx,.imgなど) | ^ |
| ^  | ^ | ^ | capture | acceptに画像や映像データが指定された場合にどのカメラを使用するか指定 | ^ |
|   ^   |   ^   |   ^  |multiple   | 複数入力を許可   |   ^   |
| ^  | ^ | ^ | required | 必須項目として指定 | ^ |
| hidden  |<input type="hidden" name="hidden" value="hidden data">| 隠しフォーム  | name   | 送信される情報のkeyを指定   |   [hidden](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/hidden)  |
| image  | <input type="image" src="login-button.png" width=100> | 画像  | src   | 送信される情報のkeyを指定   |   [image](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/image) <br>画像をボタンとして指定できるのみ |
| ^  | ^ | ^ | alt | 画像に対するラベルを付与  | ^ |
| ^  | ^ | ^ | height | 画像の高さをピクセル単位で指定  | ^ |
| ^  | ^ | ^ | width | 画像の幅をピクセル単位で指定  | ^ |
| range  | <input type="range"> |範囲  | name   | 送信される情報のkeyを指定   |   [range](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/range)  |
|  ^   |  ^  |  ^  | step  | 入力できる数値の間隔を指定  |  小数第二位までの指定は、step="0.01"とする  |
|  ^   |  ^  |  ^  | min  | 最小値を指定  |  ^  |
|  ^   |  ^  |  ^  | max  | 最大値を指定  |  ^  |
|  ^   |  ^  |  ^  | list  | 選択肢の目盛を記述  |  datalistタグを使用。datalist内のoptionにlabelを付与することで、目盛にもラベルが付与される。  |
|  ^   |  ^  |  ^  | *appearance | 方向の指定 |  [appreance](https://developer.mozilla.org/ja/docs/Web/CSS/appearance)<br>slider-verticalで垂直方向に |
|  ^   |  ^  |  ^  | *writing-mode | 進行方向の指定 |  [writing-mode](https://developer.mozilla.org/ja/docs/Web/CSS/writing-mode) |
| reset  | <input type="reset"> |リセットボタン  |value   | ボタン内の文字を指定   |   [reset](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/reset)<br>form内の入力をすべて消す。(間違えて押さないようにする工夫が必要)  |
| submit | <input type="submit"> |送信ボタン |value   | ボタン内の文字を指定   | [submit](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input/submit) |
|  ^   |  ^  |  ^  | formaction | 送信された情報を処理するURLを個別で指定 | ^  |
|  ^   |  ^  |  ^  | formmethod  | 送信する方法を個別で指定(get, post) |  ^  |
|  ^   |  ^  |  ^  | form | 関連付けするform idを指定 |  ^  |

### display
displayは、画面構成をどのように行うかを指定するものです。

画面構成を考えるだけなら、ブロックとインラインの違いがわかれば良さそう。
[ここ](https://www.htmq.com/style/display.shtml)参照

詳しくは以下を参照

https://developer.mozilla.org/ja/docs/Learn/CSS/CSS_layout/Introduction

種類は主に以下です
- inline
  - 文字や画像など、
  - 単語のように文章内に続けて横並びに配置するのに使われる
- block
- flow
- flex
- grid



右揃え
``` css
/* 親要素で指定 */
text-align: right;
/* 子要素で指定 */
display: flex;
justify-content: flex-end;
```

中央揃え
``` css
/* 親要素で指定 */
margin: 0 auto;
/* 子要素で指定 */
display: flex; justify-content: center;
```


左揃え
``` css
/* 親要素で指定 */
text-align: left;
/* 子要素で指定 */
display: flex;
justify-content: flex-start;
```
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

よく使うcssプロパティ
| プロパティ名 | 指定方法 | 備考 | url |
| ---- | ---- | ---- | ---- |
| margin | <length>,<percentage>,auto | ボックス外側の余白。0 autoで上下の余白o,左右の余白を自動で決める  | [margin](https://developer.mozilla.org/ja/docs/Web/CSS/margin)   |
| padding  | <length>,<percentage>,auto  | ボックス内側の余白。0 autoで上下の余白o,左右の余白を自動で決める  | [padding](https://developer.mozilla.org/ja/docs/Web/CSS/padding)  |
| border  | <width> <style> <color>  | 境界線の設定。 | [border](https://developer.mozilla.org/ja/docs/Web/CSS/border) |
| color | <color> | フォントの色指定   | [color](https://developer.mozilla.org/ja/docs/Web/CSS/color)   |
| font-size  | larger, smaller, ..., <length>, <percentage>  | フォントの大きさを指定 | [font-size](https://developer.mozilla.org/ja/docs/Web/CSS/font-size)   |
| font-family  | <family-name>, <generic-name> | フォント指定やフォント優先度を設定  | [font-family](https://developer.mozilla.org/ja/docs/Web/CSS/font-family)   |
|  width | <length>,<percentage>,auto,fit-content   | 要素の幅を設定。100%にすると幅すべてを使う気がする。 | [width](https://developer.mozilla.org/ja/docs/Web/CSS/width)|
| height | <length>,<percentage>,auto,fit-content    | 要素の高さを設定。100%にすると幅すべてを使う気がする。 | [height](https://developer.mozilla.org/ja/docs/Web/CSS/height)|
| display | block, inline, flow, ..., | 表示方法を選択 | [display](https://developer.mozilla.org/ja/docs/Web/CSS/display) |


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