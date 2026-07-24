---
title: "Panasonic の PTZ カメラを制御する"
---

Panasonic の PTZ カメラ `AW-UE20W` を対象とします。

## Connection を追加する

Connection に `http` を追加します。

Connections ページを開き、右側の `Add New Connection` で `http` を検索してAddします。
以下の設定をします。

- Base URL: http://192.168.0.10/cgi-bin


## ボタンを追加する

プリセットを呼び出すボタンを作成してみます。

`Buttons` ページを開き、以下のボタンを追加します。
HTTP の GET メソッドでコマンドを指定します。

- Preset1
  ---
  - Local Variables
    - internal: User Value
      - Variable name: preset
      - Current Value: `1`
      - [x] Persist value

  - Style
    - Text
      - Button text string: Preset$(local:preset)

  - Step1
    - http: GET
      - URL: `/aw_ptz?cmd=%23R0${$(local:preset) - 1}&res=1`
      - header input(JSON): なし
      - JSON Response Data Variable: None
      - [x] JSON Stringify Result
      - Response Status Code Variable: None

  :::message
  設定について
  header input(JSON)           : リクエストを送信する際に指定するヘッダ(ex. JSON でデータを送信する場合 `{"content-type": "application/json"}`)
  JSON Response Data Variable  : JSON 形式のレスポンスデータを格納する変数を指定
  JSON Stringify Result        : レスポンスデータを、文字列とする(チェックあり)か、JSON オブジェクトとする(チェックオフ)か
  Response Status Code Variable: HTTP ステータスコードを格納する変数を指定
  :::

  :::message
  URLの設定
  Expression モードで指定しています。
  プリセット番号 `1` を呼び出すときに指定する数値は `0` になるので、
  ローカル変数から計算して出力しています。
  文字列を指定する場合は、javascript のテンプレート文字列で指定するので、
  バッククォートで全体を囲みます(\`\`)
  `${xxx}` で囲まれた内容は、xxx の部分が計算されて展開されます。
  :::

## 動作確認

ボタンを押して、プリセット位置に移動することを確認します。
