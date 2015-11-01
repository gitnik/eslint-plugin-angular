<!-- WARNING: Generated documentation. Edit docs and examples in the rule and examples file ('rules/di.js', 'examples/di.js'). -->

# di - require a consistent DI syntax

All your DI should use the same syntax : the Array, function, or $inject syntaxes ("di":  [2, "array, function, or $inject"])

## Examples

Examples with default configuration

    /*eslint angular/di: 2*/

    // valid
    angular.module('myModule').factory('myService', function ($http, $log, anotherService) {
       // ...
    });

    // invalid
    angular.module('myModule').factory('myService', ['$http', '$log', 'anotherService', function ($http, $log, anotherService) {
        // ...
    }]); // error: You should use the function syntax for DI

Examples with the configuration `"array"`

    /*eslint angular/di: [2,"array"]*/

    // valid
    angular.module('myModule').factory('myService', ['$http', '$log', 'anotherService', function ($http, $log, anotherService) {
        // ...
    }]);

Examples with the configuration `"$inject"`

    /*eslint angular/di: [2,"$inject"]*/

    // valid
    angular.module('myModule').factory('myService', myServiceFn);
    myServiceFn.$inject=['$http', '$log', 'anotherService'];
    function myServiceFn($http, $log, anotherService) {
        // ...
    }

## Links

* [Rule source](../rules/di.js)
* [Example source](../examples/di.js)