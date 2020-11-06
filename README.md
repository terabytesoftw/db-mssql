<p align="center">
    <a href="https://github.com/yiisoft" target="_blank">
        <img src="https://avatars0.githubusercontent.com/u/6154722" height="100px">
    </a>
    <h1 align="center">MSSQL Server Extension for Yii 3</h1>
    <br>
</p>

This extension provides the MSSQL Server support for the [Yii framework 3 ](http://www.yiiframework.com).

[![Latest Stable Version](https://poser.pugx.org/yiisoft/db-mssql/v/stable.png)](https://packagist.org/packages/yiisoft/db-mssql)
[![Total Downloads](https://poser.pugx.org/yiisoft/db-mssql/downloads.png)](https://packagist.org/packages/yiisoft/db-mssql)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/yiisoft/db-mssql/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/yiisoft/db-mssql/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/yiisoft/db-mssql/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/yiisoft/db-mssql/?branch=master)


## Support version

|  PHP | Mssql Version            |  CI-Actions
|:----:|:------------------------:|:---:|
|**7.4 - 8.0**| **2017 - 2019**|[![Build status](https://github.com/yiisoft/db-mssql/workflows/build/badge.svg)](https://github.com/yiisoft/db-mssql/actions?query=workflow%3Abuild) [![Mutation testing badge](https://img.shields.io/endpoint?style=flat&url=https%3A%2F%2Fbadge-api.stryker-mutator.io%2Fgithub.com%2Fyiisoft%2Fdb-mssql%2Fmaster)](https://dashboard.stryker-mutator.io/reports/github.com/yiisoft/db-mssql/master) [![static analysis](https://github.com/yiisoft/db-mssql/workflows/static%20analysis/badge.svg)](https://github.com/yiisoft/db-mssql/actions?query=workflow%3A%22static+analysis%22) [![type-coverage](https://shepherd.dev/github/yiisoft/db-mssql/coverage.svg)](https://shepherd.dev/github/yiisoft/db-mssql)


## Installation

The package could be installed via composer:

```php
composer require yiisoft/db-mssql
```

## Configuration

Using yiisoft/composer-config-plugin automatically get the settings of `CacheInterface::class`, `LoggerInterface::class`, and `Profiler::class`.

Di-Container:

```php
use Yiisoft\Db\Mssql\Connection as MssqlConnection;
use Yiisoft\Factory\Definitions\Reference;

return [
    MssqlConnection::class => [
        '__class' => MssqlConnection::class,
        '__construct()' => [
            'dsn' => $params['yiisoft/db-mssql']['dsn']
        ],
        'setUsername()' => [$params['yiisoft/db-mssql']['username']],
        'setPassword()' => [$params['yiisoft/db-mssql']['password']]
    ]
];
```

Params.php

```php
use Yiisoft\Db\Mssql\Dsn;

return [
    'yiisoft/db-mssql' => [
        'dsn' => (new Dsn('sqlsrv', '127.0.0.1', 'yiitest', '1433'))->asString(),
        'username' => 'SA',
        'password' => 'YourStrong!Passw0rd'
    ]
];
```

## Unit testing

The package is tested with [PHPUnit](https://phpunit.de/). To run tests:

```php
./vendor/bin/phpunit
```

Note: You must have MSSQL installed to run the tests, it supports all MSSQL versions.

## Mutation testing

The package tests are checked with [Infection](https://infection.github.io/) mutation framework. To run it:

```php
./vendor/bin/infection
```

## Static analysis

The code is statically analyzed with [Psalm](https://psalm.dev/docs/). To run static analysis:

```php
./vendor/bin/psalm
```
