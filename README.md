# Cursorプロジェクトルール on Rails

Rails向けのCursorプロジェクトルールのテンプレートです！

## 前提

- Rails 7.2。APIモードでの使用を想定しています。
- Ruby 3.3.4
- デコレーター： draper
- JSONシリアライザ： blueprinter
- 認可ロジック： pundit
- 非同期処理：sidekiq
- enumの翻訳：enum_help
- 複数のモデルに関連したイベントの実装方法：イベント型モデルを採用
- テスト：rspec-rails
- テストデータの生成：factory_bot_rails
- APIスキーマ検証：committee-rails
- パフォーマンス監視：newrelic_rpm
- エラー監視：sentry-ruby

## 設定方法

1. [muraaano/cursor-project-rules-on-rails](https://github.com/muraaano/cursor-project-rules-on-rails)リポジトリをクローンする
2. `.cursor/rules` 以下を導入したいリポジトリにコピーする

## カスタマイズのポイント

プロジェクトごとにリポジトリのディレクトリ構成が異なる場合は、Cursorルールの配置場所やblobsのパスも合わせて調整しましょう。

- **リポジトリのルートに直接Railsアプリがある場合**  
  テンプレートのまま `.cursor/rules/` 配下にルールファイルを置き、blobsも `app/models/**/*.rb` などそのままのパスで問題ないです。

- **`./backend/` などサブディレクトリにRailsアプリがある場合**  
  ルールファイルも `.cursor/rules/backend/` のようにサブディレクトリを作って配置すると、他の言語やフロントエンドのルールと分けて管理しやすくなります。  
  例えば、`backend/app/models/**/*.rb` のようにblobsのパスも合わせて変更してください。

**例: ディレクトリ構成ごとのルール配置とblobs指定**

ルート直下にRailsアプリがある場合：
```
.
├── app/
├── .cursor/
│   └── rules/
│       ├── models.md（blobs: app/models/**/*.rb など）
│       └── controllers.md（blobs: app/controllers/**/*.rb など）
```

`backend/` 配下にRailsアプリがある場合：
```
.
├── backend/
│   ├── app/
│   └── ...
├── .cursor/
│   └── rules/
│       └── backend/
│           ├── models.md（blobs: backend/app/models/**/*.rb など）
│           └── controllers.md（blobs: backend/app/controllers/**/*.rb など）
```

### その他

- 個別のルールファイルは、必要に応じて追加・編集してください。
