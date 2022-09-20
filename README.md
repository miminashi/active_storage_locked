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
- `rails db:migrate`
- http://localhost:3000/ をひらく
- 4個以上エントリを作成する（必ず画像を添付する）
- `rails c`
- `User.destroy_all`

