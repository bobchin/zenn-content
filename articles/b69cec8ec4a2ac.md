---
title: "Python勉強"
emoji: "🐍"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["python"]
published: true
---

## Python の勉強

## 環境

### ブラウザで実行する

- [paiza.io](https://paiza.io/ja) を使う
  - サインアップし、ログインしておく
  - 記述したコードは、上部の "[一覧](https://paiza.io/projects)" で見れる
  - 新しくコードを作成するには、"[新規コード](https://paiza.io/ja/projects/new)" を選択し、**Python3** を選択する
  - タイトル(hello_world.py)を入れて、以下のコードを記述する

    ```python:hello_world.py
    print("Hello Python World!")
    ```

  - 標準入力でデータを渡す場合は、下部の **入力** にデータを入れる

    - 取得するには以下を実行

      ```python:main.py
      # input => foo bar baz

      args = input().split()
      console.log(args)   # ['foo', 'bar', 'baz'] 配列として取得できる

      # input が2行の場合
      # foo bar
      # baz
      args = input().split()
      console.log(args)   # ['foo', 'bar']
      args = input().split()
      console.log(args)   # ['baz']
      ```


### Windows で実行する

- Python のインストール
  - [Python](https://www.python.org/downloads/windows/) Stable Release のダウンロード
  - 設定
    - "Use admin privileges when installing py.exe" にチェックを入れる
    - "Add python.exe to PATH" にチェックを入れる
    - **"Install Now"** でインストール

- インストール確認

  ```cmd: コマンドプロンプトで実行
  python --version
  Python 3.13.9         # バージョンが表示されれればOK
  ```

- VSCode の設定
  - 拡張機能で、[Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner) をインストール
  - ソースコード作成

    ```python:hello_world.py
    print("Hello Python World!")
    ```

  - 右クリックして "Run Code" 選択する、もしくは、"CTRL+ALT+N" で実行できる
