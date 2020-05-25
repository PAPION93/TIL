# Artisan Command

## 명령어

### Model 생성

```
$ php artisan make:model Post
$ php artisan make:model Author
```

> 모델명은 단수, 테이블명은 복수

### DB Migration 생성

```
$ php artisan make:migration create_posts_table
$ php artisan make:migration create_authors_table
$ php artisan make:migration add_name_to_authors_table
```

> 생성 후 database/migrations 디렉토리 하위에 생성된 파일 작업

### 마이그레이션과 롤백 그리고 초기화

```
$ php artisan migrate
$ php artisan migrate:rollback    // 직전 롤백
$ php artisan migrate:reset       // 데이터베이스 초기화
$ php artisan migrate:refresh     // reset -> 처음부터 다시 실행
```

### DB Seeder 작성
```
php artisan make:seeder UserSeeder
```

### Seeder 실행
```
composer dump-autoload
php artisan db:seed
php artisan db:seed --class=UserSeeder
php artisan migrate:fresh --seed // 초기화 후 seed
```

### RESTful Resource Controller 만들기

```
php artisan make:controller PostsController --resource
```