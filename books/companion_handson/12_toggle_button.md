---
title: "トグルボタンを作成する"
---

ONとOFFを交互に繰り返すボタンを作成します。

## トグルボタンの追加

左側で空いているボタンを選択します。
`Regular button` を押して、レギュラーボタンを追加します。
右上の `+` ボタンを押して、`Step 2` を追加します。

以下を設定していきます。

- Expression Variables
  - Name: button_text
  - Description: トグルボタンの表示
  - Expression: $(custom:select_input) == 1? 'OFF': 'ON'

- Style
  - Text
    - Button text string: $(expression:button_text)

- Step 1
  - Press actions
    - internal: Custom Variable: Set value
      - Custom variable: select_input
      - [ ] Create if not exists
      - Value: 1

- Step 2
  - Press actions
    - internal: Custom Variable: Set value
      - Custom variable: select_input
      - [ ] Create if not exists
      - Value: 2

- Feedbacks
  - internal: Button: Check step
    - Invert: Off
    - Location: $(this:page)/$(this:row)/$(this:column)
    - Step: 1
    - Layered Styles Overrides
      - Text: 黒
      - Background: 緑

  - internal: Button: Check step
    - Invert: Off
    - Location: $(this:page)/$(this:row)/$(this:column)
    - Step: 2
    - Layered Styles Overrides
      - Text: 黒
      - Background: 黄

## 動作確認

ボタンを押す毎にボタンの表示名と背景色が変わることを確認します。



