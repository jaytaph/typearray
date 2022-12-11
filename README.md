# Typed Array

Simple wrapper around property-accessor to fetch elements in a typed way. This package is created because I was fiddling around with a lot of json-arrays 
that were not typed and phpstan had a big issue with that.

So, instead of having `mixed[] $myarray`, we can use `TypeArray`, and fetch elements with:

```
$arr = new TypeArray(['foo' => 'string', 'bar' => 4 ]);

$arr->getString('[foo]');  // always returns a string
$arr->getString('[notexists]', 'defaultval');   // Returns default val when not found

$arr->getInt('[bar]');  // returns int(4)
$arr->getInt('[foo]');  // Returns InvalidTypeException as this element is a string, not an int

```

See symfony propertyaccess component for the path syntax used.
