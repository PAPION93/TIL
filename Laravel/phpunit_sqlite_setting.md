# phpunit sqlite 환경 세팅하기

1. phpunit.xml
```
<server name="DB_CONNECTION" value="sqlite"/>
<server name="DB_DATABASE" value=":memory:"/>
```

2. config/database.php
```
'database' => database_path('database.sqlite'),
```

3. sqlite 파일 생성
```
touch database/database.sqlite
```

4. Database Migrate
```
php artisan migrate --database=sqlite
```

5. Database Seed
```
php artisan db:seeder --database=sqlite
```

6. Test
```
php artisan test
```