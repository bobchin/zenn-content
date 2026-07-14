---
title: "変数(Variables)を作成してみる"
---

## 変数とは

```text
変数
├── ローカル変数
└── グルーバル変数
    ├── カスタム変数
    ├── 式変数
    ├── Intenal変数
    └── コネクション変数
```

変数には主に、`ローカル変数` と `グローバル変数` の２つがありますが、
ここでは `グローバル変数` を扱います。

`ローカル変数` は、ボタンに紐付く変数で、ボタン自身固有の値となります。
一方、`グローバル変数` は、各ボタンからアクセスすることができる共通の値となります。

`グローバル変数` には、いくつか種類があります。

- カスタム変数
  文字列や数字などの `固定した値` を保持できる変数

- 式変数
  カスタム変数を展開した値を使ったり、値を使って計算したりできる変数

- Intenal変数
  Companionにあらかじめ用意されているビルトイン変数

- コネクション変数
  Connection 毎に用意されている変数


## カスタム変数を追加する

カスタム変数を追加します。

Variables ページ下の Custom Variables ページを開きます。


`Create custom variable` に `select_input` を入力して変数を追加すると、
`Ungrouped Custom variables` に `$(custom:select_input)` が追加されます。

カスタム変数は、指定した変数名に `custom:` という接頭辞が付きます。

以下の設定をします。

- [ ] Persist value
- Current value: 0
- Startup value: 0

:::message
設定について

[ ] 値を永続化する
現在の値　: 0
起動時の値: 0

通常、変数は Companion の停止時に値がリセットされるため、
起動時に `Startup value` にセットされた値がセットされます。

永続化にチェックを入れると、Companion の停止時の値が保持され、起動時に元の値に戻ります。このとき、`Startup value` は、値をセットできなくなります。

`Current value` は、現在セットされている値です。
:::

## 式変数を追加する

カスタム変数を追加します。

Variables ページ下の Expression Variables ページを開きます。

上部の `Add Expression Variable` をクリックすると、下に `Unnamed` という変数が作成されます。
式変数は、指定した変数名に `expression:` という接頭辞が付きます。

右側で以下の項目を入力します。
- Name         : double_value
- Description  : 値を2倍する
- Notes        : なし
- Expression   : $(custom:select_input) * 2

:::message
Current Value
Expression の展開結果が表示されます
:::

:::message
変数の値を **数値** として扱う場合
展開した値 `$(custom:select_input)` をそのまま使用します。
:::

さらにもう１つ式変数を追加し、以下の項目を入力します。
- Name         : display_name
- Description  : 選択した入力に応じて表示が変わるボタン名
- Notes        : なし
- Expression   : \`INPUT ${ $(custom:select_input) }\`

:::message
変数の値を **文字列** として扱う場合
Javascript のテンプレートリテラルを使用して、文字列展開表示します。
文字列表示するには、全体をバッククォート(\`\`) で括ります。
さらに、`${}` で囲まれた範囲は変数展開されます。
上記は`${ $(custom:select_input) }` は `$(custom:select_input)` の値に置き換わります。
:::


