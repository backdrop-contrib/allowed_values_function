Allowed Values Function
=======================
**(and "Default value function" too!)**

---

This module allows you to populate a list field's options (and default value(s)) with the 
results of calling a custom function.

Once enabled, in the Field UI, add a new list (ex: List (text)).  You will now see a box to enter
a value for "Allowed values function".  Likewise you can enter a function name for "default_value_function".
These should be a function name only (no parenthesis), which returns an associative array of values.


Usage
-----

On the Configure field screen you will see a new box for the Allowed values function. 
Let's say you enter "my_module_test":

`Allowed values function:  my_module_test`

Then, in your module your function should look like so, including the expected arguments:

```
function my_module_test($field, $instance, $entity_type, $entity = NULL, $cacheable = FALSE) {
  return ['a' => 'Apple', 'ban' => 'Banana'];
}
```

To configure a Default value function, on the Configure field screen:

`Default value function: my_module_get_default`

Then, in your module, the function should look like so (**notice the expected arguments are different!**)

```
function my_module_get_default($entity_type, $entity, $field, $instance, $langcode) {
  return array(
                0 => array('value' => "my_value_goes_here")
               );
}
```

**Take note** of what is being returned; it is not a simple value, but rather a nested array.


Installation
------------

- Install this module using the official Backdrop CMS instructions at
  https://backdropcms.org/guide/modules


Current Maintainers
-------------------

- [Richard Peacock](https://github.com/swampopus)
- Seeking additional maintainers.


Credits
-------

- Created by Backdrop CMS by [Richard Peacock](https://github.com/swampopus)
- Development sponsored by [FlightPath Academics](https://flightpathacademics.com)


License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for
complete text.