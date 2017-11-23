
書籍 "Effective Testing with RSpec 3" のサンプル
https://www.amazon.co.jp/gp/product/B076VTMTV8/

```
$ gem install bundler
$ bundle init

Gemfile を編集

$ bundle install

$ bundle exec rspec --init

spec/spec_helper.rb を編集
```

db の migration
```
$ bundle exec sequel -m ./db/migrations sqlite://db/development.db --echo
```

sinatra の起動
```
$ bundle exec rakeup
```

curl での呼び出し
```
$ curl localhost:9292/expenses/2017-06-10 -w "\n"
[]

$ curl -X POST localhost:9292/expenses --data '{"payee":"Zoo", "amount":10, "date":"2017-06-10"}' -w "\n"
{"expense_id":1}

$ curl localhost:9292/expenses/2017-06-10 -w "\n"
[{"id":1,"payee":"Zoo","amount":10.0,"date":"2017-06-10"}]
```

db の再作成
```
$ rm db/development.rb
$ bundle exec sequel -m ./db/migrations sqlite://db/development.db
```
