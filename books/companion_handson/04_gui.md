---
title: "画面構成"
---

## 画面構成

> - [Connections](#connections)
> - [Buttons](#buttons)
> - [Surfaces](#surfaces)
> - [Triggers](#triggers)
> - [Variables](#variables)
> - [Modules](#modules)
> - [Settings](#settings)
> - [Import/Export](#importexport)
> - [Log](#log)

## Connections

Comapnion でデイバスやソフトウェアを制御したい場合に、それらに接続するための方法を選択する。追加されているモジュールは、[Modules](#modules) で確認できる。

:::message
ex)
  ATEM Mini Pro  => "atem" を選択
  IDK MSD        => "tcp-udp" を選択
  HTTP リクエスト => "http" を選択
  ボタンの点滅表示 => "Button Blinker" を選択
:::

## Buttons

操作画面（= ボタンの配置と動作）の設定。GUI はここで設定することになる。
ボタンの大枠の設定は、[Settings-Buttons](#buttons-1) で設定するので注意。

## Surfaces

物理的なコントローラ（操作機器）との接続と割り当てをする。また、コントローラの調整もできる。

:::message
ex)
⁠Elgato Stream Deck
:::

バーチャルエミュレータで、物理的なコントローラがなくても操作できる。

## Triggers

Companionを自動化することができます。
フィードバックや変数の更新といった特定のイベントに対して、`アクション` を実行することができる。

## Variables

変数を定義できる。システム内で値を保持したい場合に利用できる。
カスタム変数と式変数の2種類

- **カスタム変数**

  文字列や数字などの `固定した値` を保持できる変数

- **式変数**

  カスタム変数を展開した値を使ったり、値を使って計算したりできる変数

- **Internal 変数**

  Companionにあらかじめ用意されているビルトイン変数

- **Connection 変数**

  Connection 毎に用意されている変数

## Modules

Connections と Surfaces を一元管理する

## Settings

システムの設定全般

- **General**

  システムのインストールやデータに関する設定

- **Buttons**

  ボタン設定の大枠（ボタン配置や見せ方など）の部分の設定

- **Image Library**

  ボタンで再利用するための画像を保存する

- Surfaces

  ※[Surfaces](#surfaces) と同じ

- **Protocols**

  Comapnion 自体に対して接続できるプロトコルを設定
  以下の接続が可能で、API制御できる

  - TCP/UDP
    一般的なネットワークソケット接続  
    TCP/UDP でコマンドを送る。デリミタは、\n(0x0A) or \r\n(0x0D0A)  

    ex) ページ1 行2 カラム3 のボタンを押下  
        `LOCATION 1/2/3 PRESS\r\n`  

  - HTTP
    一般的なWeb技術のHTTP接続  
    REST に従う。変更系は、POST メソッド。取得系は、GET メソッド。  

    ex) ページ1 行2 カラム3 のボタンを押下  
        `POST http://localhost:8000/api/location/1/2/3/press HTTP/1.1`  

  - OSC(Open Sound Control)
    電子楽器やPCで使用されているリアルタイムメッセージ通信
  - Artnet/DMX
    照明用のネットプロトコル
  - Rosstalk
    スイッチャー(RossVideo?)を制御するためのテキストベースのプロトコル
  - Ember+
    放送・オーディオ・映像システム向けのオープンな制御プロトコル

- **Backups**

  スケジュールを指定したバックアップの取得が可能

- **Advanced**

  - Adminのパスワード変更
  - HTTPSを有効にするか
  - 実験的な機能を有効にするか


- **Import/Export**

  設定のインポートとエクスポート。リセットもできる。

- **Log**

  ログを見ることができる

