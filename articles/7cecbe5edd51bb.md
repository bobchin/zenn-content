---
title: "リアルタイムOS自作"
emoji: "😸"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Arduino"]
published: false
---

## 環境

### uv(python)

https://zenn.dev/egg_glass/books/python_uv_book

- 以下がバラバラだった
  - venv, virtualenv         : 仮想環境を作成・管理
  - pip                      : パッケージインストール
  - pyenv                    : バージョンの切換
  - pip-tools, Poetry, Pipenv: プロジェクトの依存関係を固定

- 機能
  - パッケージのインストール・アンインストール・一覧表示
  - 仮想環境の作成・管理
  - 仮想環境の再生
  - Pythonバージョンの切換

- インストール

  ```bash
  # Linux/Mac
  # curl -LsSf https://astral.sh/uv/install.sh | sh

  # Windows
  powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

  ###########################

  # インストールリスト
  uv --version

  # インストールリスト
  uv python list

  # インストール
  uv python 3.14

  # スクリプト実行
  uv run xxx.py
  ```

- 主なコマンド体系
  - uv python     : Python 本体のインストールおよびバージョン管理
  - pyproject.toml: プロジェクト管理
  - uv run        : Python スクリプト実行
  - uv tool       : プロジェクトとは独立して CLI ツールを管理
  - uv pip        : pip 互換機能
  - ユーティリティ: uv 自体の状態や内部データを管理

  ```bash
  # バージョン管理
  uv python install xxx
  uv python uninstall xxx
  uv python list
  uv python find
  uv python pin

  # プロジェクト管理
  uv init    # pyproject.tomlの作成
  uv add     # 依存関係追加
  uv remove  # 依存関係削除
  uv sync    # pyproject.tomlを元にしてプロジェクトを同期
  uv lock    # uv.lock 作成
  uv run     # プロジェクトの仮想環境内でコマンドやスクリプトを実行
  uv tree    # プロジェクトの依存関係ツリーを表示
  uv build   # プロジェクトをsdistやwheel形式でビルド
  uv publish # ビルドしたパッケージをPyPIなどのインデックスに公開

  # スクリプトの実行
  uv run
  uv add --script    # スクリプト内に、"# requirements:" に依存関係の追加
  uv remove --script # スクリプト内の、"# requirements:" から依存関係の削除
  ```

### Git/GitHub

```cmd
git clone https://github.com/iory/learning-os-from-arduino.git
cd learning-os-from-arduino/docs/os-on-arduino/code
```
