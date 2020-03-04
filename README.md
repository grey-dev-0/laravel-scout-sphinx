# Sphinx for Laravel Scout

Sphinx Search Engine for Laravel Scout.
Forked from https://github.com/egwk/laravel-scout-sphinx
**Note:** The original package version constrains prevented the installation of this package on Laravel versions that are greater than 5.5, I've changed the constrain to support up to Laravel 5.8 but, I haven't tested it yet.

## Prerequisites

You should have Sphinx service installed, see: http://sphinxsearch.com/

## Install

### Installing via composer

To install the engine add the next lines to your `composer.json` file:

```json
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/grey-dev-0/laravel-scout-sphinx"
    }
]
```

Then in terminal using `composer require` command:

```
$ composer require egwk/laravel-scout-sphinx
```

### Configuration

Update `config/scout.php`, and add an entry for `sphinx`:

```php
//
'sphinx' => [
        'host' => env('SCOUT_HOST', 'localhost'),
        'port' => env('SCOUT_PORT', '9306'),
],
//
```

Set `SCOUT_*` variables in your `.env` file:

```
SCOUT_DRIVER=sphinxsearch
SCOUT_PREFIX=myprefix_
SCOUT_HOST=localhost
SCOUT_PORT=9306
```

### Adding to your project

Update `config/app.php` by adding an entry for the service provider:

```php
'providers' => [
    // ...
   Egwk\LaravelScoutSphinx\Provider\SphinxEngineProvider::class,
];
```


See [Laravel Scout Docs](https://laravel.com/docs/5.5/scout) for further info.

## Authors
* The original Engine written by [@hocnt84](https://github.com/hocnt84/laravel-scout-sphinx)
* Modified by [@buchin](https://github.com/buchin/laravel-scout-sphinx), [@egwk](https://github.com/egwk/laravel-scout-sphinx)
* Merged by [@perdodi](https://github.com/perdodi) / [White Könyvtár](https://white-konyvtar.hu)
