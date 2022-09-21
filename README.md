# active_storage_locked

以下の組み合わせでデータベースがロックする問題の再現コード

- Rails7
- SQLite3
- Active Job with async adapter

ロックしたときに発生するエラー
```
SQLite3::BusyException: database is locked (ActiveRecord::StatementInvalid)
```

再現手順

- このレポジトリをclone
- `rails db:reset`
  - db/seeds.rb から10個エントリが作成される
- `rails c`
- `User.destroy_all`

