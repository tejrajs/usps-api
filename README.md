USPS-api
========
This wrapper allows you to perform some basic calls to the USPS api. Some of the features currently supported are:

- Rate Calculator (Both domestic and international)
- Zip code lookup by address
- City/State lookup by zip code
- Verify address
- Create Priority Shipping Labels
- Create Open & Distribute Shipping Labels
- Create International Shipping Labels (Express, Priority, First Class)
- Service Delivery Calculator
- Confirm Tracking

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist tejrajs/usps-api "*"
```

or add

```
"tejrajs/usps-api": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

```php
<?= \tejrajs\uspsapi\; ?>```