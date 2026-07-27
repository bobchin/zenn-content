---
title: "PC のボリュームを調整する"
---

ロータリボタンを使って、PC のボリュームを調整してみます。
Companion から直接 PC のボリュームを設定できないため、[Remote Volume](https://github.com/ultimategmbh/remote-volume) を使用します。

## Remote Volume のインストール

[Release](https://github.com/leonreucher/remote-volume/releases) から、
環境に応じたモジュールをダウンロードしてインストールします。

モジュールを起動すると、デフォルトでポート 2501 で、 WebScoket で待ち受けます。

## Connection の追加

Connections ページを開き、右側の `Add New Connection` で `volume` を検索して、`UTS: Remote Volume` を Add します。

以下の設定にします。

- Target IP address: 127.0.0.1
- Port: 2501
- [x] Reconnect

## ロータリーボタンの設定

`Buttons` ページを開き、ロータリーボタンを選択します。

ロータリーアクションを追加します。
`Options` タブで、`Rotary Actions` を有効にします。

## アクションの追加

アクション設定をします。
`Step1` タブを開きます。

- Rotate left actions
  - Remote_Volume: Decrease Volume
    - Decrease by: 5

- Rotate right actions
  - Remote_Volume: Increase Volume
    - Decrease by: 5

- Press actions
  - Remote_Volume: Set Mute
    - Mute: Toggle

## 動作確認

ロータリーボタンの左右に回して、ボリュームが増減することを確認します。
ロータリーボタンをクリックするとミュートがオン・オフすることを確認します。

