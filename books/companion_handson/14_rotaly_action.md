---
title: "ロータリーボタンを使用する"
---

ロータリーボタンで、ボタンを回したときにアクションを実行します。
ロータリーボタンを左右に回すことで、２つのボタンの画像をフェードインフェードアウトしてみます。

画像表示用のボタンを追加します。
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

- image2
  - Element Name        : image2
  - Image               : イメージファイルを選択します
  - Horizontal Alignment: 中央
  - Vertical Alignment  : 中央

## カスタム変数を登録する

カスタム変数を追加します。

Variables ページ下の Custom Variables ページを開きます。
以下を追加します。

- $(custom:percent)
  - Description: 透過度のパーセント数
  - [ ] Persist value
  - Current value: 100
  - Startup value: 100

- $(custom:step)
  - Description: 透過度の更新度数
  - [ ] Persist value
  - Current value: 10
  - Startup value: 10

## ロータリーボタンを設定する

ボタンをクリックし、`Options` タブをクリックします。
`Rotary Actions` を有効にします。

ローテートアクションを追加します。
`Step1` タブをクリックします。
`Rotate left actions` と `Rotate right actions` が追加されています。

以下を入力します。

- Rotate left actions
  - internal: Custom Variable: Set value
  - Custom variable: percent
  - [x] Create if not exists
  - Value: `max(0, $(custom:percent) - $(custom:step))`

- Rotate right actions
  - internal: Custom Variable: Set value
  - Custom variable: percent
  - [x] Create if not exists
  - Value: `min(100, $(custom:percent) + $(custom:step))`

画像の透過度の割り当てをします。
`Feedbacks` タブをクリックします。

以下を入力します。

- internal: Variable: Check boolean expression
  - Invert   : Off
  - Expression: `-1 < $(custom:percent)`
  - Layered Style Overrides
    - Image1(Opacity): `$(custom:percent)`
    - Image2(Opacity): `100 - $(custom:percent)`

## 動作確認

ロータリボタンを左右に回すと、2 つの画像が次第に入れ替わります。
