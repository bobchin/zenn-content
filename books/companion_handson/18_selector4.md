---
title: "セレクタを作成する（その４）"
---

![](/images/companion/selector.png =600x)
*作成するセレクタのサンプル*

## プロジェクタ電源ボタンの作成

トグルボタンを作成します。
`Step1` を電源OFF状態のときの表示、`Step2` を電源ON状態のときの表示とします。

### 見た目の作成

`Feedbacks` に以下の設定をします。

- internal: Button: When pushed
  - Location: \$(this:page)/\$(this:row)/\$(this:column)
  - Layered Styles Overrides
    - Background(Color): 橙

- internal: Button: Check step
  - Location: \$(this:page)/\$(this:row)/\$(this:column)
  - Step: 1
  - Layered Styles Overrides
    - Text(Button text string): Power\n⇩\nON
    - Background(Color): 灰

- internal: Button: Check step
  - Location: \$(this:page)/\$(this:row)/\$(this:column)
  - Step: 2
  - Layered Styles Overrides
    - Text(Button text string): Power\n⇩\nOFF
    - Background(Color): 赤

### アクションの作成

`Step1` のアクションを追加

- Press actions
  - tcp-udp: Send Command
    - Command: @EXC,1
    - Command End Character: CRLF

`Step2` のアクションを追加

- Press actions
  - tcp-udp: Send Command
    - Command: @EXC,2
    - Command End Character: CRLF

