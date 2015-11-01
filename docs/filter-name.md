<!-- WARNING: Generated documentation. Edit docs and examples in the rule and examples file ('rules/filter-name.js', 'examples/filter-name.js'). -->

# filter-name - require and specify a prefix for all filter names

All your filters should have a name starting with the parameter you can define in your config object.
The second parameter can be a Regexp wrapped in quotes.
("filter-name":  [2, "ng"])

## Examples

Examples with the configuration `"prefix"`

    /*eslint angular/filter-name: [2,"prefix"]*/

    // valid
    angular.module('myModule').filter('prefixFilter', function () {
        // ...
    });

Examples with the configuration `"/^xyz/"`

    /*eslint angular/filter-name: [2,"/^xyz/"]*/

    // valid
    angular.module('myModule').filter('xyzFilter', function () {
        // ...
    });

    // invalid
    angular.module('myModule').filter('otherFilter', function () {
        // ...
    }); // error: The otherFilter filter should follow this pattern: /^xyz/

Examples with the configuration `"xyz"`

    /*eslint angular/filter-name: [2,"xyz"]*/

    // invalid
    angular.module('myModule').filter('someFilter', function () {
        // ...
    }); // error: The someFilter filter should be prefixed by xyz

## Links

* [Rule source](../rules/filter-name.js)
* [Example source](../examples/filter-name.js)