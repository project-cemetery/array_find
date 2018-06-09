[![Packagist](https://img.shields.io/packagist/v/kamyshev/array_find.svg?style=flat-square)](https://packagist.org/packages/kamyshev/array_find)
[![Build Status](https://img.shields.io/travis/igorkamyshev/array_find/master.svg?style=flat-square)](https://travis-ci.org/igorkamyshev/array_find)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://raw.githubusercontent.com/TheNovel/array_find/master/LICENSE)

# array_find
> A PHP function that find element in an array by a callback.

## Installation

To get the latest version of `array_find`, simply require the project using Composer:

``` shell
$ composer require kamyshev/array_find
```

If you do not want to use Composer, you can just `require` the `src/array_find.php` file.

## Usage

To use `array_find`, simply pass an array and callback:

``` php
$records = [
    [
        'state'  => 'IN',
        'city'   => 'Indianapolis',
        'object' => 'School bus',
    ],
    [
        'state'  => 'IN',
        'city'   => 'Indianapolis',
        'object' => 'Manhole',
    ],
    [
        'state'  => 'IN',
        'city'   => 'Plainfield',
        'object' => 'Basketball',
    ],
    [
        'state'  => 'CA',
        'city'   => 'San Diego',
        'object' => 'Light bulb',
    ],
    [
        'state'  => 'CA',
        'city'   => 'Mountain View',
        'object' => 'Space pen',
    ],
];

$grouped = array_find($records, function ($state) {
    return $state['city'] === 'San Diego';
});
```

Example output:

``` text
Array
(
    [state] => CA
    [city] => San Diego
    [object] => Light bulb
)
```

If the element was not found, `array_find` returns `null`.
