---
title: "セレクタを作成する（その３）"
---

![](/images/companion/selector.png =600x)
*作成するセレクタのサンプル*

## 全出力ボタンの作成

### 見た目の作成

`Style` で以下を設定します。

- Text
  - Button text string: 全出力
  - Text Size: 30

`Feedbacks` で以下を設定します。

- internal: Button: When pushed
  - Location: \$(this:page)/\$(this:row)/\$(this:column)
  - Layered Styles Overrides
    - Background(Color): 橙

### アクションの作成

`Step1` に設定します。

センターモニタへの出力

- Press actions
  - internal: Custom Variable: Set value
    - Custom variable: selected_center_ch
    - [x] Create if not exists
    - Value: $(custom:selected_ch)

  - tcp-udp: Send Command
    - Command: $(expression:center_moniter_command)
    - Command End Character: CRLF

プロジェクタへの出力

- Press actions
  - internal: Custom Variable: Set value
    - Custom variable: selected_projecter_ch
    - [x] Create if not exists
    - Value: $(custom:selected_ch)

  - tcp-udp: Send Command
    - Command: $(expression:projector_command)
    - Command End Character: CRLF

## 全解除ボタンの作成

### 見た目の作成

`Style` で以下を設定します。

- Text
  - Button text string: 全解除
  - Text Size: 30

`Feedbacks` で以下を設定します。

- internal: Button: When pushed
  - Location: \$(this:page)/\$(this:row)/\$(this:column)
  - Layered Styles Overrides
    - Background(Color): 橙

### アクションの作成

`Step1` に設定します。

プレビューへの出力

- Press actions
  - internal: Custom Variable: Set value
    - Custom variable: selected_ch
    - [x] Create if not exists
    - Value: 0

  - tcp-udp: Send Command
    - Command: $(expression:preview_command)
    - Command End Character: CRLF

センターモニタへの出力

- Press actions
  - internal: Custom Variable: Set value
    - Custom variable: selected_center_ch
    - [x] Create if not exists
    - Value: 0

  - tcp-udp: Send Command
    - Command: $(expression:center_moniter_command)
    - Command End Character: CRLF

プロジェクタへの出力

- Press actions
  - internal: Custom Variable: Set value
    - Custom variable: selected_projecter_ch
    - [x] Create if not exists
    - Value: 0

  - tcp-udp: Send Command
    - Command: $(expression:projector_command)
    - Command End Character: CRLF
