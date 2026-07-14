---
title: "値の変化に応じてボタンの表示を変更する"
---

変数の値によって、ボタンの表示を変更してみます。

## 変更確認用ボタンの追加

左側で空いているボタンを選択します。
`Regular button` を押して、レギュラーボタンを追加します。

`Style` タブの `Text` で、以下の項目を入力します。

- Button text string: color

`Feedbacks` タブを選択し、
`+Add feedback` から `internal: Variable: Check value` を追加します。

以下の項目を設定します。

- internal: Variable: Check value
  - Invert   : Off
  - Variable : **custom:select_input**
  - Operation: =
  - Value    : **1**
  - Layered Style Overrides
    - Background: **赤**

同様に以下３つの `internal: Variable: Check value` を追加します。

- internal: Variable: Check value
  - Invert   : Off
  - Variable : **custom:select_input**
  - Operation: =
  - Value    : **2**
  - Layered Style Overrides
    - Background: **青**

- internal: Variable: Check value
  - Invert   : Off
  - Variable : **custom:select_input**
  - Operation: =
  - Value    : **3**
  - Layered Style Overrides
    - Background: **黄**

- internal: Variable: Check value
  - Invert   : Off
  - Variable : **custom:select_input**
  - Operation: =
  - Value    : **4**
  - Layered Style Overrides
    - Background: **緑**

:::message
設定が似ているものを追加する場合、
設定済みの欄の右上にある `Duplicate feedback` ボタンを使用すると便利です。
異なる箇所 (Value と Background) を変更するだけで済みます。
:::

## 動作確認

`In 1` ～ `In 4` ボタンを押して、変更確認用ボタンの背景色が変わることを確認します。

- `In 1` ボタンを押したとき: 赤

- `In 2` ボタンを押したとき: 青

- `In 3` ボタンを押したとき: 黃

- `In 4` ボタンを押したとき: 緑


