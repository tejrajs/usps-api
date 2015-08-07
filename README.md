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

USPS Address Verify
---------------------
```php
<?php
use tejrajs\uspsapi\USPSAddressVerify; 

$verify = new USPSAddressVerify('xxxx');

// During test mode this seems not to always work as expected
//$verify->setTestMode(true);

// Create new address object and assign the properties
// apartently the order you assign them is important so make sure
// to set them as the example below
$address = new USPSAddress;
$address->setFirmName('Apartment');
$address->setApt('100');
$address->setAddress('9200 Milliken Ave');
$address->setCity('Rancho Cucomonga');
$address->setState('CA');
$address->setZip5(91730);
$address->setZip4('');

// Add the address object to the address verify class
$verify->addAddress($address);

// Perform the request and return result
print_r($verify->verify());
print_r($verify->getArrayResponse());

var_dump($verify->isError());

// See if it was successful
if($verify->isSuccess()) {
  echo 'Done';
} else {
  echo 'Error: ' . $verify->getErrorMessage();
}
?>```