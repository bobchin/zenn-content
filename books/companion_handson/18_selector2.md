---
title: "セレクタを作成する（その２）"
---

![](/images/companion/selector.png =600x)
*作成するセレクタのサンプル*

センターモニタ表示用のボタンを作成します。

## 出力ボタンの作成

### ボタンの見た目を設定
`Style` で以下を設定します。

- Text
  - Button text string: Center　⇨
  - Text Size         : 20

### グローバル変数を追加

グローバル変数 `selected_center_ch` を作成

- $(custom:selected_center_ch)
  - [ ] Persist value
    - Description: selected center monitor channel
    - Current value: 0
    - Startup value: 0

グローバルの式変数 `calc_center_display` を作成

- $(expression:calc_center_display)
  - Name: calc_center_display
  - Description: calc_center_display
  - Expression:
    ```js
    $(custom:selected_center_ch) != 0
      && $(custom:selected_center_ch) == $(custom:selected_ch)
      ? 0
      : $(custom:selected_ch)
    ```

  :::message
  Expression について
  `selected_center_ch` の値に応じて処理が変わります。
  - 未送出時(selected_center_ch == 0)は選択中のチャンネルを割り当てます。
  - 送出中の場合
    - 送出中と同じものを選択している場合、0 (解除)を割り当てます。
    - 送出中と違うものを選択している場合、選択中のチャンネルを割り当てます。
  :::

### アクションを追加
`Step1` で以下を設定します。

グローバル変数 `selected_center_ch` にチャンネルをセットします。

- Press actions
  - internal: Custom Variable: Set value
    - Custom variable: selected_center_ch
    - [x] Create if not exists
    - $(expression:calc_center_display)


## 出力画像表示ボタンの作成

### ボタンの見た目を設定
`Style` で以下を設定します。

`+` ボタンで `Image` を 7 つ追加します。
`Background` で `Color` を黒にします。

### 選択状態によって画像を変える

グローバル変数 `selected_center_ch` の値によって画像表示を変えます。

`FeedBacks` に以下を追加します。

- Display1
  -  internal: Variable: Check value
     - Variable : custom:selected_center_ch
     - Operation: =
     - Value    : 1
     - Layered Styles Overrides
       - [x] Image1(Enabled)
       - [ ] Image2(Enabled)
       - [ ] Image3(Enabled)
       - [ ] Image4(Enabled)
       - [ ] Image5(Enabled)
       - [ ] Image6(Enabled)
       - [ ] Image7(Enabled)

- Display2
  -  internal: Variable: Check value
     - Variable : custom:selected_center_ch
     - Operation: =
     - Value    : 2
     - Layered Styles Overrides
       - [ ] Image1(Enabled)
       - [x] Image2(Enabled)
       - [ ] Image3(Enabled)
       - [ ] Image4(Enabled)
       - [ ] Image5(Enabled)
       - [ ] Image6(Enabled)
       - [ ] Image7(Enabled)

- Display3
  -  internal: Variable: Check value
     - Variable : custom:selected_center_ch
     - Operation: =
     - Value    : 3
     - Layered Styles Overrides
       - [ ] Image1(Enabled)
       - [ ] Image2(Enabled)
       - [x] Image3(Enabled)
       - [ ] Image4(Enabled)
       - [ ] Image5(Enabled)
       - [ ] Image6(Enabled)
       - [ ] Image7(Enabled)

:
:

- Display OFF
  -  internal: Variable: Check value
     - Variable : custom:selected_center_ch
     - Operation: =
     - Value    : 0
     - Layered Styles Overrides
       - [ ] Image1(Enabled)
       - [ ] Image2(Enabled)
       - [ ] Image3(Enabled)
       - [ ] Image4(Enabled)
       - [ ] Image5(Enabled)
       - [ ] Image6(Enabled)
       - [ ] Image7(Enabled)

## プロジェクタ表示用のボタン

プロジェクタ表示用のボタンは、センターモニタ表示用を参考にして作成してみてください。
