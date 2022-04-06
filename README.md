**Install laravel 8:**
composer create-project --prefer-dist laravel/laravel rest-api "8.*"

**Install JWT via composer:**
composer require tymon/jwt-auth:dev-develop --prefer-source
<br>
php artisan vendor:publish
<br>
enter serial no for service provider
<br>
**create JWT secret key:**
php artisan jwt:secret
<br>

**create rescource controller:**
-mcr

**Tinker:**
php artisan tinker

**Using tinker we can modify data without using any routes**
App\Models\User::factory()->count(10)->create()
