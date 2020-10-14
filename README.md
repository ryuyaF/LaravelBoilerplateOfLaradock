# LaravelBoilerplateOfLaradock

## 説明
LaradockをベースにしたLaravelのボイラープレート

## 使い方
### リポジトリをクローン
`git clone --recurse-submodules https://github.com/ryuyaF/LaravelBoilerplateOfLaradock.git`

Laradockをサブモジュールとしてリポジトリに組み込んでいるため、`--recuse-submodules`オプションを付ける

### Laradockのenvファイルをコピーする
`cp env-example laradock/.env`

※WSL2を使用している場合、mysqlが上手く起動しないためバージョンは以下を指定する

https://github.com/docker/for-win/issues/4824

```env:laradock/.env
MYSQL_VERSION=5.7.16
```

### Laradockのコンテナ群を立ち上げる
`cd laradock`

`docker-compose up -d mysql nginx`

### Laravelのインストール

`docker-compose exec workspace bash`

`cp .env.example .env`

`composer install`

`php artisan migrate`

`php artisan key:generage`

### 動作確認
[http://localhost](http://localhost)にアクセスしてLaravelのWelcomeページが表示されていればOK
