---
title: "値の変化に応じて画像を変更する"
---

グローバル変数の値によってボタンの画像が変わるようにしてみます。

まず、画像表示用のボタンを追加します。
左側で空いているボタンを選択します。
`Regular button` を押して、レギュラーボタンを追加します。

## 画像を登録する

`Style` タブをクリックします。
Style の追加をするため、`+` ボタンから `image` を追加します。

以下を入力します。

- image1
  - Element Name        : image1
  - Image               : イメージファイルを選択します
  - Horizontal Alignment: 中央
  - Vertical Alignment  : 中央

:::message
画像を選択する際に、イメージライブラリを使用することができます。
繰り返し使用する可能性がある画像ファイルは、ライブラリに登録しておくと便利です。
`Select Image` ウィンドウから、`Upload to Library` で登録できます。
:::

同様に画像ファイルを3ファイル追加します。

- image2
  - Element Name        : image2
  - Image               : イメージファイルを選択します
  - Horizontal Alignment: 中央
  - Vertical Alignment  : 中央

- image3
  - Element Name        : image3
  - Image               : イメージファイルを選択します
  - Horizontal Alignment: 中央
  - Vertical Alignment  : 中央

- image4
  - Element Name        : image4
  - Image               : イメージファイルを選択します
  - Horizontal Alignment: 中央
  - Vertical Alignment  : 中央


## 値に応じて画像を表示する

見た目の動的な変更は `Feedback` を使います。
`Feedbacks` タブをクリックします。

`Add feedback` から　`internal: Variable: Check value` を選択します。

以下を入力します。

- internal: Variable: Check value
  - Invert   : Off
  - Variable : **custom:select_input**
  - Operation: =
  - Value    : **1**
  - Layered Style Overrides
    - [x] **image1**
    - [ ] image2
    - [ ] image3
    - [ ] image4

:::message
Layered Style Overrides
画像の変更だけしたいため、色の変更部分は削除します。
`+` ボタンで、`Element` から登録した画像(image1 ～ 4)を追加します。
:::

同様に以下３つの設定を追加します。

- internal: Variable: Check value
  - Invert   : Off
  - Variable : **custom:select_input**
  - Operation: =
  - Value    : **2**
  - Layered Style Overrides
    - [ ] image1
    - [x] image2
    - [ ] image3
    - [ ] image4

- internal: Variable: Check value
  - Invert   : Off
  - Variable : **custom:select_input**
  - Operation: =
  - Value    : **3**
  - Layered Style Overrides
    - [ ] image1
    - [ ] image2
    - [x] image3
    - [ ] image4

- internal: Variable: Check value
  - Invert   : Off
  - Variable : **custom:select_input**
  - Operation: =
  - Value    : **4**
  - Layered Style Overrides
    - [ ] image1
    - [ ] image2
    - [ ] image3
    - [x] image4

## 動作確認

グローバル変数 `select_input` の値に応じて画像が変化します。
In1 ～ In4 のボタンを押して、画像が変わることを確認します。
