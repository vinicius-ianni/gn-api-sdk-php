# SDK GERENCIANET FOR PHP

Sdk for Gerencianet Pagamentos' API.
For more informations about parameters and values, please refer to [Gerencianet](http://gerencianet.com.br) documentation.

**:warning: This module is under development and is based on the new API that Gerencianet is about to release. It won't work in production by now.**


[![Build Status](https://travis-ci.org/gerencianet/gn-api-sdk-php.svg)](https://travis-ci.org/gerencianet/gn-api-sdk-php)


## Installation
Require this package with [composer](https://getcomposer.org/):
```
$ composer require gerencianet/gerencianet-sdk-php
```
Or include it in your composer.json file:
```
...
"require": {
  "gerencianet/gerencianet-sdk-php": "1.*"
},
...
```

## Getting started
Require the module and namespaces:
```php
require __DIR__ . '/../sdk/vendor/autoload.php';

use Gerencianet\Gerencianet;
```
Although the web services responses are in json format, the sdk will convert any server response to array. The code must be within a try-catch and exceptions can be handled as follow:
```php
try {
  /* code */
} catch(GerencianetException $e) {
  /* Gerencianet's api errors will come here */
} catch(Exception $ex) {
  /* Other errors will come here */
}
```

### For development environment
Instantiate the module passing using your client_id, client_secret and sandbox equals true:
```php
$options = [
  'client_id': 'client_id',
  'client_secret': 'client_secret',
  'sandbox': true
];

$api = new Gerencianet($options);
```

### For production environment
To change the environment to production, just set the third sandbox to false:
```php
$options = [
  'client_id': 'client_id',
  'client_secret': 'client_secret',
  'sandbox': false
];

$api = new Gerencianet($options);
```

## Running tests

To run tests install [PHPUnit](https://phpunit.de/getting-started.html) and run the following command:
```php
$ phpunit -c test/config.xml
```

## Additional Documentation

#### Charges
- [Creating charges](/docs/CHARGE.md)
- [Paying a charge](/docs/CHARGE_PAYMENT.md)
- [Detailing charges](/docs/CHARGE_DETAIL.md)
- [Updating informations](/docs/CHARGE_UPDATE.md)

#### Carnets

- [Creating carnets](/docs/CARNET.md)
- [Detailing carnets](/docs/CARNET_DETAIL.md)
- [Updating informations](/docs/CARNET_UPDATE.md)

#### Subscriptions

- [Creating subscriptions](/docs/SUBSCRIPTION.md)
- [Setting the payment method](/docs/SUBSCRIPTION_PAYMENT.md)
- [Detailing subscriptions](/docs/SUBSCRIPTION_DETAIL.md)
- [Updating informations](/docs/SUBSCRIPTION_UPDATE.md)
- [Listing plans](/docs/PLAN_LIST.md)

#### Marketplace

- [Creating a marketplace](/docs/MARKETPLACE.md)

#### Notifications

- [Getting notifications](/docs/NOTIFICATION.md)

#### Payments

- [Getting the payment data](/docs/PAYMENT_DATA.md)


## License ##
[MIT](LICENSE)
