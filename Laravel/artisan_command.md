# Artisan Command

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

### Factory 생성
```
php artisan make:factory PostFactory

```

### DB Seeder 생성
```
php artisan make:seeder UserSeeder
php artisan make:factory UserMachineFactory --model=UserMachine // 모델 지정
```

### Seeder 실행
```
php artisan db:seed
php artisan db:seed [--class=UserSeeder]
php artisan migrate:fresh --seed // 초기화 후 seed
```

### RESTful Resource Controller 만들기
```
php artisan make:controller PostController --resource
```

### API Controller 생성
```
php artisan make:controller API/V1/PostController --api
```

### 미들웨어 정의하기
```
php artisan make:middleware MiddlewareName
```

### Request Class 생성
```
php artisan make:Request PostsRequest
```

### Test Class 생성
```
php artisan make:test UserTest [--unit]
```

### Test 실행
```
php artisan test
vendor/bin/phpunit tests/Unit/Test.php
```

### 각종 캐시 삭제
```
php artisan cache:clear
php artisan route:clear
php artisan config:clear
php artisan view:clear
```

### 모든 캐시 삭제
```
php artisan optimize:clear
```


### 컴포저 오토로드 최적화
```
composer dump-autoload
```
> 오토로딩이란 자동으로 클래스나 인터페이스를 로딩해주는 것  
> 새로운 파일이나 폴더가 추가되면 컴포저는 오토로딩 정보를 갱신 필요.  
<<<<<<< HEAD
> [출처](https://www.lesstif.com/laravelprog/auto-loader-24445513.html)
=======
> [출처](https://www.lesstif.com/laravelprog/auto-loader-24445513.html)
>>>>>>> bc2b6f4a27789cda780549b6c9583cd2d5c3473a
