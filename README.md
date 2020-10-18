# LaravelBoilerplateOfLaradock

## 説明
LaradockをベースにしたLaravelのボイラープレート

## 使い方
### 任意のプロジェクト名でリポジトリをクローン
`git clone --recurse-submodules https://github.com/ryuyaF/LaravelBoilerplateOfLaradock.git {ProjectName}`

Laradockをサブモジュールとしてリポジトリに組み込んでいるため、`--recuse-submodules`オプションを付ける

### Laradockの環境構築
``` bash
cd {ProjectName}
cp env-example laradock/.env
```

※既に他のLaradockプロジェクトを構築している場合、`COMPOSE_PROJECT_NAME`の値を変更する

``` bash
cd laradock
docker-compose up -d mysql nginx
```

### Laravelのインストール
``` bash
docker-compose exec workspace bash
cp .env.example .env
composer install
php artisan migrate
php artisan key:generage
```

### 動作確認
[http://localhost](http://localhost)にアクセスしてLaravelのWelcomeページが表示されていればOK
