---
title: "Python勉強"
emoji: "🐍"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["python"]
published: true
---

## 参考

:::message
公式

- [Python Documentation](https://docs.python.org/ja/3/)

  - [言語リファレンス](https://docs.python.org/ja/3/reference/index.html)

  - [チュートリアル](https://docs.python.org/ja/3/tutorial/index.html)

  - [標準ライブラリ](https://docs.python.org/ja/3/library/index.html)
:::

https://docs.python.org/ja/3/

https://docs.python.org/ja/3/reference/index.html

https://docs.python.org/ja/3/tutorial/index.html

https://docs.python.org/ja/3/library/index.html

---

:::message
MicroPython

- [MicroPython Documentation](https://docs.micropython.org/en/latest/)

- [MicroPython 日本語ドキュメント](https://micropython-docs-ja.readthedocs.io/ja/latest/)
:::

https://docs.micropython.org/en/latest/

https://micropython-docs-ja.readthedocs.io/ja/latest/

---

## チートシート

:::message
一覧
- [Basic](https://github.com/ehmatthes/pcc_3e/blob/main/cheat_sheets/color_sheets/individual_sheets_color/beginners_python_cheat_sheet_pcc.pdf)
- [If/While](https://github.com/ehmatthes/pcc_3e/blob/main/cheat_sheets/color_sheets/individual_sheets_color/beginners_python_cheat_sheet_pcc_if_while.pdf)
- [List](https://github.com/ehmatthes/pcc_3e/blob/main/cheat_sheets/color_sheets/individual_sheets_color/beginners_python_cheat_sheet_pcc_lists.pdf)
- [Dictionary](https://github.com/ehmatthes/pcc_3e/blob/main/cheat_sheets/color_sheets/individual_sheets_color/beginners_python_cheat_sheet_pcc_dictionaries.pdf)
- [Function](https://github.com/ehmatthes/pcc_3e/blob/main/cheat_sheets/color_sheets/individual_sheets_color/beginners_python_cheat_sheet_pcc_functions.pdf)
- [Class](https://github.com/ehmatthes/pcc_3e/blob/main/cheat_sheets/color_sheets/individual_sheets_color/beginners_python_cheat_sheet_pcc_classes.pdf)
:::

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
