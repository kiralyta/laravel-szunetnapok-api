# Forked!

[Original Repo](https://github.com/huszerldani/laravel-szunetnapok-api)

The following config value must be added to config/app.php file: ```szunetnapok_api_key```.

Like this:

```php
return [

    /*
    |--------------------------------------------------------------------------
    | Application Name
    |--------------------------------------------------------------------------
    |
    | This value is the name of your application. This value is used when the
    | framework needs to place the application's name in a notification or
    | any other location as required by the application or its packages.
    |
    */

    'name' => env('APP_NAME', 'Laravel'),

    ...

    'szunetnapok_api_key' => env('SZUNETNAPOK_API_KEY'),
];
```

# Laravel Munkaszüneti napok API

Egyszerű munkaszüneti napok lekérdezése bármelyik évre, kiegészítve a plusz munkanapokkal.

## A package a [szunetnapok.hu](https://szunetnapok.hu/) API-ját használja
https://szunetnapok.hu/

### [Az eredeti API dokumentációja](https://szunetnapok.hu/acc#api_desc)

## Feltételek

A használathoz szükséges API kulcsot igényelni:
#### [Szünetnapok.hu regisztráció](https://szunetnapok.hu/reg)

## Telepítés

```bash
composer require kiralyta/laravel-szunetnapok-api
```
<br/>
Az API kulcsot a .env file-ban kell megadni:

```
SZUNETNAPOK_API_KEY=
```

## Használat

```php
use Pinasen\SzunetNapok\SzunetNapok;

$year = 2021;

// Év megadása nem kötelező.
// Alapértelmezetten az aktuális évet kéri le
$szunetnapok = SzunetNapok::getYear($year);
```
