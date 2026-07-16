---
title: "セレクタを作成する（その１）"
---

セレクタを作成してみます。

![](/images/companion/selector.png =600x)
*作成するセレクタのサンプル*

## 事前準備

入力用の画像を 7 枚準備します。
`Image Library` に、input1.jpg ～ input7.jpg として登録します。

IDK のスイッチャーを制御するため、`Connections` に `tcp-udp` を追加します。

定数値として、以下のグローバル変数を 3 つ追加します。

- $(custom:preview_ch)
  - [x] Persist value
    - Description: output preview channel
    - Current value: 1

- $(custom:center_monitor_ch)
  - [x] Persist value
    - Description: output center monitor channel
    - Current value: 2

- $(custom:projector_ch)
  - [x] Persist value
    - Description: output projector channel
    - Current value: 3


## 入力ボタンの作成

以下を 7 つ作成します。

## 見た目の設定

`Style` で、`Image` に画像ファイル(input1.jpg ～ input7.jpg)を割り当てます。

## ローカル変数を追加

ボタンに`入力チャンネル`を割り当てます

- internal: User Value
  - Variable name: input_channel
  - Current Value: `1`
  - [x] Persist value

## クリックアクションを追加

以下２つのアクションを設定します。
- グローバル変数に選択中のチャンネルを設定
- プレビュー表示のコマンド送信

### グローバル変数に選択中のチャンネルを設定

グローバル変数 `selected_ch` を作成

- $(custom:selected_ch)
  - [ ] Persist value
    - Description: selected input channel
    - Current value: 0
    - Startup value: 0

`Step1` に アクションを追加

- Press actions
  - internal: Custom Variable: Set value
    - Custom variable: selected_ch
    - [x] Create if not exists
    - Value: $(custom:selected_ch) == $(local:input_channel)? 0: $(local:input_channel)

  :::message
  Value について
  Expression モードで Javascript の三項演算子を利用しています。
  グローバル変数 `selected_ch` とローカル変数 `input_channel` が
  同じなら `0`
  違うなら ローカル変数 `input_channel`
  を設定しています。
  つまり選択中に同じボタンをクリックしたら解除にするということになります。
  :::

### プレビュー表示のコマンド送信

IDK スイッチャーにコマンドを送信します。

グローバルの式変数 `preview_command` を作成

- $(expression:preview_command)
  - Name: preview_command
  - Description: preview_command
  - Expression: `@SSW,${$(custom:selected_ch)},${$(custom:preview_ch)}`

  :::message
  Expression について
  `@SSW,X,1` というコマンドを生成しています。`X` には、上記でセットした選択チャンネルがセットされます。
  :::

`Step1` に アクションを追加

- Press actions
  - tcp-udp: Send Command
    - Command: $(expression:preview_command)
    - Command End Character: CRLF

## ボタン選択中の効果を追加

ボタン選択中に背景色を表示します。

`Feedbacks` で以下を追加します。

- internal: Variable: Compare two variables
  - Compare Variable: custom:selected_ch
  - Operation       : =
  - Against Variable: local:input_channel
  - Layered Styles Overrides
    - Image(Opacity)   : 30
    - Background(Color): 橙