# React + LaravelのDocker環境構築

## 開発環境
* frontend: React / TypeScript
* backend(api): PHP / Laravel

## clone
```
git clone 
```

## 環境構築

### コンテナ起動
```
cp .env.example .env
docker-compose up -d --build
```

### Laravelインストール
```
docker-compose exec api composer install
docker-compose exec api cp .env.example .env
docker-compose exec api php artisan key:generate
```

インストール終了後、`localhost:80`にアクセスするとLaravelのページが表示される

### Next.jsインストール
```sh
docker-compose exec front yarn

# 開発用サーバーの起動
docker-compose exec front yarn start
```

インストール終了後、`localhost:3000`にアクセスするとNext.jsのページが表示される
開発用サーバーの停止は`control + c`

