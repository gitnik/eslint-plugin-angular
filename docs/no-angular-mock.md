<!-- WARNING: Generated documentation. Edit docs and examples in the rule and examples file ('rules/no-angular-mock.js', 'examples/no-angular-mock.js'). -->

# no-angular-mock - require to use `angular.mock` methods directly

All methods defined in the angular.mock object are also available in the object window.
So you can remove angular.mock from your code

## Examples

Examples with default configuration

    /*eslint angular/no-angular-mock: 2*/

    // valid
    dump($scope);

    // valid
    inject(function (someService) {
        // ...
    });

    // valid
    module('myModule');

    // invalid
    angular.mock.dump($scope); // error: You should use the "dump" method available in the window object.

    // invalid
    angular.mock.inject(function (someService) {
        // ...
    }); // error: You should use the "inject" method available in the window object.

    // invalid
    angular.mock.module('myModule'); // error: You should use the "module" method available in the window object.

## Links

* [Rule source](../rules/no-angular-mock.js)
* [Example source](../examples/no-angular-mock.js)