## DS のデフォルトブラウザで ES6 を処理する手順

babel-standaline を使って ES6 以降の JavaScript コードをトランスパイルします。  
説明の詳細はオリジナルのサイト（[このページ](https://babeljs.io/docs/en/babel-standalone)）を参照。

以下、手順概要

1. DS のロボット設定画面のオプション設定画面を開く
1. `ページロード中` タブ内の `ページの変更` で、`テキストフォーマット > パターンの置き換え` を選択し、babel でトランスパイルするタグを設定する。
   1. 変換対象となる javaScript コードのタグタイプを `text/babel` に変更
1. `ページロード中` タブ内の `ページの変更` で、`テキストフォーマット > テキストの置き換え` を選択し、babel の読み込みタグを設定する。
   1. `babel-standalone` のスクリプトファイルをページに組み込む

<br/>

### 変換対象となる javaScript コードのタグタイプを `text/babel` に変更

- パターン

```
<script(.*?)>
```

- エクスプレッションを置き換え

```javascript
contains($1, "text/javascript") ?
    replaceText($0,$1,replaceText($1,"text/javascript","text/babel")) :
    ( length($1) > 1 ?
        replaceText($0,$1,$1 + >> type="text/babel"<<) :
        replaceText($0,">",>> type="text/babel"><<)
    )
```

<br/>

### `babel-standalone` のスクリプトファイルをページに組み込む

- このテキストを検索

```html
</title>
```

- このテキストに置き換え

```html
</title>
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```
