# WpBridge

[![Latest Version on Packagist](https://img.shields.io/packagist/v/gwa/wp-bridge.svg?style=flat-square)](https://packagist.org/packages/gwa/wp-bridge)
[![Total Downloads](https://img.shields.io/packagist/dt/gwa/wp-bridge.svg?style=flat-square)](https://packagist.org/packages/gwa/wp-bridge)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)

## Master

[![Build Status](https://img.shields.io/travis/gwa/WpBridge/master.svg?style=flat-square)](https://travis-ci.org/gwa/WpBridge)
[![Coverage Status](https://img.shields.io/scrutinizer/coverage/g/gwa/WpBridge.svg?style=flat-square)](https://scrutinizer-ci.com/g/gwa/WpBridge/code-structure)
[![Quality Score](https://img.shields.io/scrutinizer/g/gwa/WpBridge.svg?style=flat-square)](https://scrutinizer-ci.com/g/gwa/WpBridge)

## Install

Via Composer

``` bash
$ composer require gwa/wp-bridge
```

## Usage

First init ```WpBridge``` class.

```php
$bridge = new \Gwa\Wordpress\WpBridge\WpBridge();
```

Now it allows us to use a class to call methods in the global namespace.
Methods should be called in camelcase.

``` php
// To call
wp_get_attachment_image_src(...);

// use
$bridge->wpGetAttachmentImageSrc(...);
```

Or you like to use a trait, than set ```WpBridgeTrait``` in a class.

```php
use Gwa\Wordpress\WpBridge\Traits\WpBridgeTrait;

class TestClass
{
    use WpBridgeTrait;

    public function testFunc()
    {
        $img = $this->getWpBridge()->wpGetAttachmentImageSrc(...);

        ...
    }
}

$test = new TestClass();
$test->setWpBridge($bridge);
```

## Change log

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Testing

``` bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Credits

- [Great White Ark](https://github.com/gwa)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
