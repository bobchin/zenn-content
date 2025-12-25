---
title: "Nix"
emoji: "🌟"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Nix"]
published: false
---

## Nix

https://nixos.org/

純粋関数型パッケージマネージャ

以下のような特徴をもつ
1. 純粋関数的ビルドシステム
2. Nixストアによるパッケージと依存関係の厳密な管理
3. Nix言語とFlakesによる宣言的ビルド
4. Profilesによる非破壊的パッケージ構成管理

- **再現性**
- **宣言的**
- **信頼性**

### 用語

- devShell
  - 開発用のシェル環境
  - 環境外の既存ツールを使うことができる

- direnv
  - Nix を起動するには、`nix develop` する必要があるが面倒。
  - ディレクトリごとに自動で環境変数やシェル環境を切り替えることができる

ｰ home-manager
  - Nix を使ってユーザのホーム環境を管理する

- Nixpkgs
  - Nix で使えるパッケージのコレクション

-　importNpmLock

## Links

https://zenn.dev/asa1984/books/nix-introduction

https://zenn.dev/asa1984/books/nix-hands-on

https://zero-to-nix.com/

https://nixos-and-flakes.thiscute.world/