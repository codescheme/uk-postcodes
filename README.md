# UK Postcodes

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Software License][ico-license]](LICENSE.md)
[![Build Status][ico-travis]][link-travis]
[![Total Downloads][ico-downloads]][link-downloads]

A php API client for the methods at ```postcodes.io``` - useful for UK postcode validation and reverse geocoding: that is, determining postcode from lat, long coordinates.
**No fiddling around with api keys or authentication necessary...**

With thanks to https://postcodes.io


## Install

Via Composer

``` bash
$ composer require codescheme/uk-postcodes
```

## Basic Usage

Return data for a given postcode

```php
use Codescheme\Ukpostcodes\Postcode;

$client = new Postcode();

$results = $client->postcodeLookup('SE21 8JL');

if ($results->status === 200) {
    print_r($results);
}
```

## Methods

```
->validate('SE31 9AX'); //returns boolean
->postcodeLookup('SE21 8JL');
->nearest('SE21 8JL');
->reverseGeocode(-0.397913, 51.44015); // lng,lat
->autocomplete('RG1 3');
->outcodeLookup('SE21');

$postcodes = ['OX49 5NU', 'M32 0JG', 'NE30 1DP'];
->postcodeLookupBulk($postcodes);
	
$coordinates = [
    ['longitude' =>  0.629834723775309, 'latitude' => 51.7923246977375],
    ['longitude' => -2.49690382054704, 	'latitude' => 53.5351312861402]
    ];
->reverseGeocodeBulk($coordinates);
```

## Testing

``` bash
$ composer test
```

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

[ico-version]: https://img.shields.io/packagist/v/codescheme/uk-postcodes.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-travis]: https://img.shields.io/travis/codescheme/uk-postcodes/master.svg?style=flat-square
[ico-scrutinizer]: https://img.shields.io/scrutinizer/coverage/g/codescheme/uk-postcodes.svg?style=flat-square
[ico-code-quality]: https://img.shields.io/scrutinizer/g/codescheme/uk-postcodes.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/codescheme/uk-postcodes.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/codescheme/uk-postcodes
[link-travis]: https://travis-ci.org/codescheme/uk-postcodes
[link-scrutinizer]: https://scrutinizer-ci.com/g/codescheme/uk-postcodes/code-structure
[link-code-quality]: https://scrutinizer-ci.com/g/codescheme/uk-postcodes
[link-downloads]: https://packagist.org/packages/codescheme/uk-postcodes
[link-author]: https://github.com/codescheme
[link-contributors]: ../../contributors
