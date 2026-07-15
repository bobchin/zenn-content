---
title: "Companion をリモートから操作する"
---

[4.画面構成/Protocols](04_gui%252Emd#Protocols) で説明されているように、
Companion 自体をリモートから操作することができます。

## プロトコルを有効にする

`Settings` ページの `Protocols` を開きます。

`HTTP API` を有効にします。

これで、Companion は HTTP でコマンドを受け付けるようになります。

API の詳細は、右ページの `HTTP` タブで確認できます。

## HTTP でリモート制御する

- ボタンをクリックする

  ex) 1 ページの 2 行目 3 列目のボタンをクリック

  ```cmd
  curl -X POST http://localhost:8000/api/location/1/0/1/press
  ```

  :::message
  数値の指定について
  ページは、ページ数をそのまま指定します。ex) 1 ページ => 1
  行数と列数は、`0` から始まることに注意します。 ex) 2 行目 => 1, 3 列目 => 2
  :::

  :::message
  HTTP の実行は、VSCode の [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) プラグインをオススメします。
  :::

- グローバル変数 `select_input` に `2` をセットする

  ex) 1 ページの 2 行目 3 列目のボタンをクリック

  ```cmd
  curl -X POST http://localhost:8000/api/custom-variable/select_input/value?value=2
  ```

