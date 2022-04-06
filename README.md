<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Install laravel 8:
composer create-project --prefer-dist laravel/laravel rest-api "8.*"

Virtual host
<VirtualHost *:80>
         ServerName laravel.local
         ServerAlias 127.0.0.1
         DocumentRoot /var/www/html/restapi/public
         <Directory "/var/www/html/restapi/public/">
                AllowOverride All
             RewriteEngine on
             RewriteCond %{REQUEST_FILENAME} !-f
             RewriteCond %{REQUEST_FILENAME} !-d
             RewriteRule . index.php
         </Directory>
</VirtualHost>


Install JWT via composer:
composer require tymon/jwt-auth:dev-develop --prefer-source
php artisan vendor:publish
enter serial no for service provider

create JWT secret key:
php artisan jwt:secret

In config/auth.php
set default guard as api
'defaults' => [
        'guard' => 'api',
        'passwords' => 'users',
    ],
    
    
add driver as jwt
'guards' => [
        'web' => [
            'driver' => 'session',
            'provider' => 'users',
        ],
        'api' => [
            'driver' => 'jwt',
            'provider' => 'users',
        ],
    ],
    
in models/users  implement JWTSubject and add methods
getJWTIdentifer() 
getJWTCustomClaims()    

create rescource controller:
-mcr

Tinker:
php artisan tinker

Using tinker we can modify data without using any routes
 App\Models\User::factory()->count(10)->create()
