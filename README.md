Allowed Values Function
=================

This module allows you to populate a list field's options with the results of calling a custom function.

Once enabled, in the Field UI, add a new list (ex: List (text)).  You will now see a box to enter
a value for "Allowed values function".  This should be a function name only (no parenthesis), which
returns an associative array of values.

For example, on the Configure field screen:

`Allowed values function:  my_module_test`

Then, in your module your function should look like so, including the expected arguments:

```
function my_module_test($field, $instance, $entity_type, $entity = NULL, $cacheable = FALSE) {
  return ['a' => 'Apple', 'ban' => 'Banana'];
}
```

Installation
------------

- Install this module using the official Backdrop CMS instructions at
  https://backdropcms.org/guide/modules


Current Maintainers
-------------------

- [Richard Peacock](https://github.com/swampopus) (original creator for Backdrop CMS)
- Seeking additional maintainers.


License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for
complete text.