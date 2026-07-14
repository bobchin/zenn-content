---
title: "コネクションを追加する"
---

## ATEM Mini Proを制御する

Connection に `atem` を追加します。

Connections ページを開き、右側の `Add New Connection` で `atem` を検索してAddします。
※ATEM Mini Pro をネットワーク上に接続しておいてください。
左側に追加された atem から設定を開き、`Target IP` を確認します。

## IDK スイッチャーを制御する

Connection に `tcp-udp` を追加します。

Connections ページを開き、右側の `Add New Connection` で `tcp-udp` を検索してAddします。
以下の設定をします。

- Target Host name or IP: 192.168.1.199
- Target Port           : 1100
- Connect with TCP / UDP: TCP
- Save TCP Response     : OFF
