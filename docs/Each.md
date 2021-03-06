# Each

- `Each(Validatable $ruleForValue)`
- `Each(null, Validatable $ruleForKey)`
- `Each(Validatable $ruleForValue, Validatable $ruleForKey)`

Iterates over an array or Iterator and validates the value or key
of each entry:

```php
$releaseDates = [
    'validation' => '2010-01-01',
    'template'   => '2011-01-01',
    'relational' => '2011-02-05',
];

v::arrayVal()->each(v::date())->validate($releaseDates); // true
v::arrayVal()->each(v::date(), v::stringType()->lowercase())->validate($releaseDates); // true
```

Using `arrayVal()` before `each()` is a best practice.

***
See also:

  * [Key](Key.md)
  * [ArrayVal](ArrayVal.md)
