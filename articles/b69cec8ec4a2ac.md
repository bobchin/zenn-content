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

## 最短距離でゼロからしっかり学ぶ Python入門

### 第２章 変数とシンプルなデータ型

#### まとめ

:::details まとめ
- データ型
  - 文字列
    - 文字
    - 文字列
  - 数値
    - 整数
    - 浮動小数点

- 変数
  - 英数字とアンダースコアを使う
  - 数字で始めない（数値と区別がつかないため）

- メソッド
  - "".title()
  - "".upper()
  - "".lower()
  - "".strip()
  - "".rstrip()
  - "".lstrip()

- f-string
  - 文字列の中で変数を使う

- エスケープシーケンス
  - **画面に表示されない文字(改行・タブなど)** を表す
  - ダブルクォートやシングルクォートのエスケープ

- 四則演算
  - 割り算に注意

- コメント

- 定数
:::

#### やってみよう

:::details 2-1. 簡単なメッセージ
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-01_simplemessage.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 2-2. 簡単な２つのメッセージ
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-02_twomessage.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 2-3. 個人的なメッセージ
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-03_personal_message.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 2-4. 名前の大文字小文字
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-04_upper_lower_name.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 2-5. 名言の引用
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-05_famouse_quote.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 2-6. 名言の引用２
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-06_famous_quote2.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 2-7. 名前から空白を取り除く
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-07_strip.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 2-8. ナンバー８
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-08_number8.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 2-9. 好きな数字
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-09_favorite_number.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 2-10. コメントを追加する
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter2%2F2-10_add_comment.py&hideExplorer=1&hideNavigation=1&view=editor)
:::


### 第３章 リスト入門

:::details 3-1. 名前
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-01_name.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-2. あいさつ
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-02_greeting.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-3. ほしいものリスト
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-03_wishlist.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-4. ゲスト一覧
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-04_guestlist.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-5. ゲスト一覧を変更する
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-05_changelist.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-6. より多くのゲスト
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-06_moreguests.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-7. ゲストを減らす
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-07_remove_guest.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-8. 世界を訪れよう
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-08_visit_the_world.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-9. 夕食のゲスト
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-09_supper_guest.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-10. すべての機能
@[stackblitz](https://stackblitz.com/edit/secret-python-dbr2hzrf?embed=1&file=Chapter3%2F3-10_all_functions.py&hideExplorer=1&hideNavigation=1&view=editor)
:::

:::details 3-11. 意図的なエラー
なし
:::



