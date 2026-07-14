---
title: "インストール"
---

## インストール

Companionを実行する環境に応じて[ダウンロード](https://user.bitfocus.io/download)から `Companion` をダウンロード
対応環境としては以下になります。

- Windows(x64)
- Windows(arm64)
- Mac(Intel)
- Mac(Apple Silicon)
- Linux(x64)
- Linux(arm64)
- RaspberryPi ※`Companion Pi` だとOSイメージごと構築できる

## 設定

### Surface

USB サーフィスの検出設定

![](/images/companion/0001.png)

- [x] Watch for newly connected USB devices
- [x] Auto-enable newly discovered surfaces

:::message
- 新規に接続されたUSBデバイスを監視するか
- 新規に検出したサーフィスを自動的に有効にするか
:::

### Button Grid Size

ボタングリッドの大きさ設定（ボタン数）

![](/images/companion/0002.png)

- Rows   : 4
- Columns: 8

:::message
- 行数（たて）
- 列数（よこ）
:::

### Buttons

ボタンの表示設定

![](/images/companion/0003.png)

- Default decoration
  - Top bar
  - Border
  - None
- [ ] Show status icons on each button(状態表示アイコンを表示するかどうか)

:::message
- デフォルトの装飾(選択状態表示)
  - トップバー（上部に表示）
  - ボーダー（押したときに枠を表示）
  - 表示しない
- [ ] 状態表示アイコンを表示するかどうか
:::

### Services

Companion自体を外部制御するかどうかの設定（最初はすべて無効で）

![](/images/companion/0004.png)

**※詳細は [4.画面構成/Protocols](04_gui%252Emd#Protocols) を参照**

- [ ] TCP Raw Socket
- [ ] UDP Raw Socket
- [ ] Open Sound Control (OSC)
- [ ] RossTalk
- [ ] Ember+
- [ ] Artnet

### Usage Statistics

Companion の使用状況を見せるかどうか

![](/images/companion/0005.png)

- [ ] Send anonymous usage statistics

:::message
- [ ] 匿名の使用率の統計情報を送付する
:::

### Admin GUI Password

admin のパスワードを有効にするかどうかとパスワードの変更

![](/images/companion/0006.png)

- [ ] Enable Admin Password　**※開発中はパスワードが面倒なのでチェック外しておく**

:::message
- [ ] 管理者パスワードを有効にする
:::


### Timezone

タイムゾーンの設定

![](/images/companion/0007.png)

- Asia/Tokyo

