---
title: "まず使ってみる"
---

[StackBlitz](https://stackblitz.com/) 上で動かしてみます。
データベースは、[SQLite3](https://sqlite.org/) を使用します。
データベースドライバは、better-sqlite3 を使用します。

:::details データベース接続について
drizzle はいろいろなデータベースを扱えますが、各データベース毎にインストールするものや使い方に違いがあるようです。
[Get started](https://orm.drizzle.team/docs/get-started) ページにはデータベース（さらに新規か既存かも分かれている）ごとのドキュメントがあるので参照します。
使用したいデータベースドライバについても、`Connect` 欄を参照します。今回は、`better-sqlite3` を使用します。
:::

## 環境構築

### StackBlitz 上に Typescript の環境を構築

- `New project` から、`node.new(Node.js)` を選択します。

  ```bash
  # typescriptとtsxのインストール. nodejsの型情報をインストール
  npm install -D typescript tsx @types/node

  # tsconfig.json生成
  npx tsc --init
  ```

  ```json:tsconfig.json
  {
    "compilerOptions": {
          :
      "rootDir": "./src",
      "outDir": "./dist",
          :
      "lib": ["esnext"],
      "types": ["node"],
          :
      // Other Outputs
      // "sourceMap": true,
      // "declaration": true,
      // "declarationMap": true,
    }
  }
  ```

  :::details tsconfig.json

  ```json
  {
    "compilerOptions": {
      // ========================
      "rootDir": "./src",
      "outDir": "./dist",
      // ========================

      // Environment Settings
      "module": "nodenext",
      "target": "esnext",
      // For nodejs:
      // ========================
      "lib": ["esnext"],
      "types": ["node"],
      // ========================

      // ========================
      // Other Outputs
      // "sourceMap": true,
      // "declaration": true,
      // "declarationMap": true,
      // ========================

      // Stricter Typechecking Options
      "noUncheckedIndexedAccess": true,
      "exactOptionalPropertyTypes": true,

      // Style Options
      // "noImplicitReturns": true,
      // "noImplicitOverride": true,
      // "noUnusedLocals": true,
      // "noUnusedParameters": true,
      // "noFallthroughCasesInSwitch": true,
      // "noPropertyAccessFromIndexSignature": true,

      // Recommended Options
      "strict": true,
      "jsx": "react-jsx",
      "verbatimModuleSyntax": true,
      "isolatedModules": true,
      "noUncheckedSideEffectImports": true,
      "moduleDetection": "force",
      "skipLibCheck": true
    }
  }
  ```
  :::

### drizzle の環境構築

- インストール

  ```bash
  # drizzle(ORマッパー)とsqlite3のインストール
  npm install drizzle-orm better-sqlite3
  npm install -D @types/better-sqlite3

  # drizzle-kit(migration管理)のインストール
  npm install -D drizzle-kit
  ```

- ファイル・フォルダ構成

  ```text
  .
  ├── db/
  │   ├── connect.ts      : データベース接続定義ファイル
  │   ├── schema.ts       : スキーマ定義ファイル
  │   └── sqlite.db       : データベース本体
  ├── drizzle/
  │   ├── meta/
  │   └── xxx_yyy_zzz.sql : マイグレーション用のSQLファイル
  ├── src/
  │   └── index.ts
  ├── drizzle.config.ts   : drizzle-kit 用の設定ファイル
  └── .env                : 環境変数ファイル
  ```

- 設定ファイルの作成

  ```js:.env
  DB_FILE="sqlite.db"
  ```

  ```js:drizzle.config.ts
  import { defineConfig } from 'drizzle-kit'
  process.loadEnvFile()

  export default defineConfig({
    dialect: "sqlite",          // 使用する DB(postgresql|mysql|sqlite)
    schema : "./db/schema.ts",  // DBスキーマ定義ファイル
    out    : "./drizzle",       // マイグレーション関係の出力フォルダ

    dbCredentials: {
      url: process.env.DB_FILE as string, // DB接続の認証
    },
  })
  ```

- スキーマの作成

  ```js:db/schema.ts
  // sqlite用にスキーマを作る
  import { text, integer, sqliteTable } from 'drizzle-orm/sqlite-core'

  export const todos = sqliteTable('todos', {
    id: integer('id', { mode: 'number' }).primaryKey({ autoIncrement: true }),
    name: text('name'),
    isCompleted: integer('is_completed', { mode: 'boolean' })
      .notNull()
      .default(false),
  })
  ```

- マイグレーションの作成

  ```bash
  npx drizzle-kit generate
  npx drizzle-kit migrate
  ```

- DB への接続

  ```js:db/connect.ts
  // sqlite用のDBアクセス
  import { drizzle, BetterSQLite3Database } from "drizzle-orm/better-sqlite3"
  import Database from "better-sqlite3"
  process.loadEnvFile()

  const sqlite = new Database(process.env.DB_FILE)
  export const db: BetterSQLite3Database = drizzle(sqlite)
  ```

- 操作
