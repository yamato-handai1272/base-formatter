# Base Formatter

このリポジトリは、**HTML・CSS・JavaScript** コードの整形と、CSS のスタイルチェックを自動化するための設定をまとめたものです。
Prettier と Stylelint を利用し、コード品質と一貫性を保ちます。

## 機能

- **Prettier** による HTML・CSS・JavaScript コードのフォーマット
- **Stylelint** による CSS/SCSS のスタイルチェックと自動修正
- VS Code 用の推奨拡張機能と保存時自動フォーマット設定
- `.editorconfig` によるエディタ横断のインデント・改行統一

## 整形・スタイルルール概要

- **Prettier**

    - HTML・CSS・JavaScript の整形を自動化します。
    - 主なルール:
        - セミコロン必須
        - インデントはスペース4つ
        - ダブルクォート
        - 1行最大120文字
        - 行末カンマ（ES5対応）
        - 改行コードは LF

- **Stylelint**
    - CSS/SCSS のスタイルチェックと自動修正を行います。
    - 主なルール:
        - 標準的なスタイルルール＋プロパティのアルファベット順ソート
        - `node_modules`・`dist` 配下は対象外

詳細なルールは各設定ファイル（`.prettierrc`, `.stylelintrc`）を参照してください

## セットアップ

1. **依存パッケージのインストール**

    ```sh
    npm install
    ```

2. **推奨 VS Code 拡張機能のインストール**
    - [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
    - [Stylelint](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)
    - [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=editorconfig.editorconfig)

## 使い方

- **コードフォーマット（Prettier）**

    ```sh
    npm run format
    ```

- **スタイルチェック＆自動修正（Stylelint）**

    ```sh
    npm run stylelint
    ```

- **VS Code での自動フォーマット**
  保存時に自動で Prettier と Stylelint が実行されます（`.vscode/settings.json` 参照）。

## 設定ファイル

- [`.prettierrc`](.prettierrc): Prettier の設定
- [`.stylelintrc`](.stylelintrc): Stylelint の設定
- [`.editorconfig`](.editorconfig): インデントや改行コードの統一
- [`.vscode/settings.json`](.vscode/settings.json): VS Code 用の自動フォーマット設定
- [`.vscode/extensions.json`](.vscode/extensions.json): 推奨拡張機能

## 注意事項

- Node.js v22.14、npm v11 での動作を想定しています（`package.json` の `engines` 参照）。
- `.prettierignore` で `*.min.js` ファイルはフォーマット対象外です。
