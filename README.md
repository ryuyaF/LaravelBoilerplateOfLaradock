# LaravelBoilerplateOfLaradock

## 説明
LaradockをベースにしたLaravelのボイラープレート

## 使い方

### このテンプレートリポジトリをベースに、新しいGitHubリポジトリを作成する

1. 画面上部の`Use This Template`のリンクをクリック
2. リポジトリ名、概要等の必要な情報を入力し、新しいリポジトリを作成

### 任意のプロジェクト名で作成したリポジトリをクローン
`git clone --recurse-submodules　your_create_new_repository.git {ProjectName}`

Laradockをサブモジュールとしてリポジトリに組み込んでいるため、`--recurse-submodules`オプションを付ける

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
