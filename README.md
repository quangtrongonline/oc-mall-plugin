# oc-mall
> E-commerce solution for October CMS 

[![Build Status](https://travis-ci.org/OFFLINE-GmbH/oc-mall-plugin.svg?branch=develop)](https://travis-ci.org/OFFLINE-GmbH/oc-mall-plugin)


## Access pricing information

The price for a `Product` or `Variant` model is stored as an array of currency values.

The following accessors and 
methods are also available for alternative price columns such as `old_price`. Simply modify the property/method names
 accordingly.

### Prices as float values

You can access the pricing information by accessing the `price` property directly:

```php
print_r($product->price);

[
    "CHF" => 20.50,
    "EUR" => 21.50
]
``` 

### Prices as formatted values 

You can get all prices as a formatted string by accessing the `price_formatted` property:

```php
print_r($product->price_formatted);

[
    "CHF" => 'CHF 20.50',
    "EUR" => '21.50 €'
]
``` 

### Price in a specific currency 

You can get the price in a specific currency by calling the `priceInCurrency`, `priceInCurrencyFormatted` or 
`priceInCurrencyInteger` methods.

```php
echo $product->priceInCurrency();

> 20.50

echo $product->priceInCurrency('EUR');

> 21.50

echo $product->priceInCurrencyInteger();

> 2050

echo $product->priceInCurrencyFormatted();

> 'CHF 20.50'

echo $product->priceInCurrencyFormatted('EUR');

> '21.50 €'
``` 