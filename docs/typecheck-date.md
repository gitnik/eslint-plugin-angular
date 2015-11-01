<!-- WARNING: Generated documentation. Edit docs and examples in the rule and examples file ('rules/typecheck-date.js', 'examples/typecheck-date.js'). -->

# typecheck-date - use `angular.isDate` instead of `typeof` comparisons

You should use the angular.isDate method instead of the default JavaScript implementation (typeof new Date() === "[object Date]").

## Examples

Examples with default configuration

    /*eslint angular/typecheck-date: 2*/

    // valid
    angular.isDate(someDate);

    // invalid
    Object.prototype.toString.call(someDate) === '[object Date]'; // error: You should use the angular.isDate method

## Links

* [Rule source](../rules/typecheck-date.js)
* [Example source](../examples/typecheck-date.js)