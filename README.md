[![Build Status](https://travis-ci.org/bigcommerce-labs/php-bitfield.png?branch=master)](https://travis-ci.org/bigcommerce-labs/php-bitfield)

# php-bitfield

Map an array of options to a binary bitfield as a string or integer, and back again.

# Usage

If you have three values in your bitmask (for ex: a, b, c) then the following code snippets show how to extract values form the bitmask.

```php
$bf = new Bitfield(array('a', 'b', 'c'));

// for just a
$bf->setValue(1);
$options = $bf->getOptionsOn();

// for just b
$bf->setValue(2);
$options = $bf->getOptionsOn();

// for just c
$bf->setValue(4);
$options = $bf->getOptionsOn();
```

If you have a bitmask, a set of values and want to find which are on and which are off you could use the following approach.

```php
$values = array('a', 'b', 'c');
$bf = new Bitfield($values);
$bf->setValue(1);

foreach($values as $val) {
  if ($bf->isOn($val)) {
    // do something
  } else {
    // do something else
  }
}
```
