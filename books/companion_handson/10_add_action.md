---
title: "ボタンを押したときのアクションを追加する"
---

## アクションの追加

ボタンを押したときの動作を変えるために、アクションを追加します。

Buttons ページを開き、左側に追加したプリセットボタン `In1` をクリックします。

右側で、`Step 1` タブを選択し、
`+Add action` から `internal: Custom Variable: Set value` を選択します。

以下の項目を入力します。

- Custom variable     : select_input
- [ ] Create if not exists
- Value               : $(local:input) (右のアイコンをクリックして式変数モードにする)

:::message
Value の入力モード
- Value モード     : 数値や文字列などをリテラルか単一の変数を指定する
- Expression モード: Expression Variable と同様に式計算して指定する
:::

同様の内容を、`In 1` ～ `In 4` すべてにアクションを追加します。

## 表示確認用のボタンを追加

左側で空いているボタンを選択します。
`Regular button` を押して、レギュラーボタンを追加します。

`Style` タブの `Text` で、以下の項目を入力します。

- Button text string: $(custom:select_input)


同様に２つボタンを追加して、それぞれ以下の内容を入力します。

- Button text string: $(expression:double_value)

- Button text string: $(expression:display_name)

## 動作確認

`In 1` ～ `In 4` ボタンを押して、それぞれのボタン表示が変わることを確認します。

- `In 1` ボタンを押したとき
  - select_inputボタン: 1
  - double_valueボタン: 2
  - display_nameボタン: INPUT 1

- `In 2` ボタンを押したとき
  - select_inputボタン: 2
  - double_valueボタン: 4
  - display_nameボタン: INPUT 2

- `In 3` ボタンを押したとき
  - select_inputボタン: 3
  - double_valueボタン: 6
  - display_nameボタン: INPUT 3

- `In 4` ボタンを押したとき
  - select_inputボタン: 4
  - double_valueボタン: 8
  - display_nameボタン: INPUT 4
