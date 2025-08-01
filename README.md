# cursor-project-rules-on-rails
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
