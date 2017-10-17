## oauth2によるログイン

https://qiita.com/arakaji/items/39818b207f9c1c3c4058

### rails側作業
```
bundle exec rails g devise:install
bundle exec rails g devise user
bundle exec rake db:migrate
```

```
bundle exec rails g doorkeeper:install
bundle exec rails g doorkeeper:migration
```

この状態だとmigrationファイルのバージョンが古いので手動で修正
ActiveRecord::Migration -> ActiveRecord::Migration[5.1]
[参考](https://github.com/doorkeeper-gem/doorkeeper/pull/985)

```
bundle exec rake db:migrate
```
