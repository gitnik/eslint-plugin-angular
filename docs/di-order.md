<!-- WARNING: Generated documentation. Edit docs and examples in the rule and examples file ('rules/di-order.js', 'examples/di-order.js'). -->

# di-order - require DI parameters to be sorted alphabetically

Injected dependencies should be sorted alphabetically.
If the second parameter is set to false, values which start and end with an underscore those underscores are stripped.
This means for example that `_$httpBackend_` goes before `_$http_`.

## Examples

Examples with default configuration

    /*eslint angular/di-order: 2*/

    // valid
    angular.module('myModule').factory('myService', function($http, $location, $q, myService, someService) {
        // ...
    });

    // valid
    beforeEach(inject(function (_$compile_, $httpBackend, _$log_, _$rootScope_) {
        // ...
    }));

    // valid
    angular.module('myModule').factory('myService', function(CONFIG, URLs, authService, zero) {
        // ...
    });

    // invalid
    angular.module('myModule').factory('myService', function($q, $http) {
        // ...
    }); // error: Injected values should be sorted alphabetically

    // invalid
    angular.module('myModule').controller('SomeController', function(myService, $http) {
        // ...
    }); // error: Injected values should be sorted alphabetically

    // invalid
    angular.module('myModule').filter('myFilter', function(someService, myService) {
        // ...
    }); // error: Injected values should be sorted alphabetically

Examples with the configuration `true`

    /*eslint angular/di-order: [2,true]*/

    // valid
    beforeEach(inject(function (_$compile_, $httpBackend, _$log_, _$rootScope_) {
        // ...
    }));

    // invalid
    beforeEach(inject(function ($httpBackend, _$compile_, _$log_, _$rootScope_) {
        // ...
    })); // error: Injected values should be sorted alphabetically

Examples with the configuration `false`

    /*eslint angular/di-order: [2,false]*/

    // valid
    beforeEach(inject(function ($httpBackend, _$compile_, _$log_, _$rootScope_) {
        // ...
    }));

    // invalid
    beforeEach(inject(function (_$compile_, $httpBackend, _$log_, _$rootScope_) {
        // ...
    })); // error: Injected values should be sorted alphabetically

## Links

* [Rule source](../rules/di-order.js)
* [Example source](../examples/di-order.js)