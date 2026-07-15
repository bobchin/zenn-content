---
title: "IDK のスイッチャーを制御する"
---

## Connection を追加する

Connection に `tcp-udp` を追加します。

Connections ページを開き、右側の `Add New Connection` で `tcp-udp` を検索してAddします。
以下の設定をします。

- Target Host name or IP: 192.168.1.199
- Target Port           : 1100
- Connect with TCP / UDP: TCP
- Save TCP Response     : OFF

## ボタンを追加する

OUT1 の入力を変更するボタンを作成してみます。

`Buttons` ページを開き、以下のボタンを追加します。

- IN1
  ---
  - Local Variables
    - internal: User Value
      - Variable name: input
      - Current Value: `1`
      - [x] Persist value

  - Style
    - Text
      - Button text string: IN$(local:input)

  - Step1
    - tcp-udp: Send Command
      - Command              : @SSW,$(local:input),1
      - Command End Character: CRLF - \r\n(Common Windows)

  :::message
  以降は似た設定のため、ボタンの `Copy` を使うことをオススメします。
  主に太字の部分のみ変更するだけになります。
  :::

- IN2
  ---
  - Step1
    - tcp-udp: Send Command
      - Command              : @SSW,$(local:input),1
      - Command End Character: CRLF - \r\n(Common Windows)
  - Style
    - Text
      - Button text string: IN$(local:input)
  - Local Variables
    - internal: User Value
      - Variable name: input
      - Current Value: `2`
      - [x] Persist value

- IN3
  ---
  - Step1
    - tcp-udp: Send Command
      - Command              : @SSW,$(local:input),1
      - Command End Character: CRLF - \r\n(Common Windows)
  - Style
    - Text
      - Button text string: IN$(local:input)
  - Local Variables
    - internal: User Value
      - Variable name: input
      - Current Value: `3`
      - [x] Persist value

- OFF
  ---
  - Step1
    - tcp-udp: Send Command
      - Command              : @SSW,$(local:input),1
      - Command End Character: CRLF - \r\n(Common Windows)
  - Style
    - Text
      - Button text string: `OFF`
  - Local Variables
    - internal: User Value
      - Variable name: input
      - Current Value: `0`
      - [x] Persist value

## 動作確認

各ボタンを押して、スイッチャーの OUT1 の入力が変わることを確認します。

## やってみよう

上記では、OUT1 のチャンネルを指定するのに、`1` を直接指定していました。
もしチャンネルを変えたい場合に複数個所を変更する必要がありますので、
変数で指定することをオススメします。

- グローバル変数 `out_ch` を作成する
- ボタンのアクションの設定で、`out_ch` を指定するように変更する

:::details 参考設定
- Custom Variables
  - $(custom:out_ch)
    - [x] Persist value
    - Current value: 1

- 各ボタン
  - Step1
    - tcp-udp: Send Command
      - Command              : @SSW,\$(local:input),\$(custom:out_ch)
:::
