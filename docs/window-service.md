<!-- WARNING: Generated documentation. Edit docs and examples in the rule and examples file ('rules/window-service.js', 'examples/window-service.js'). -->

# window-service - use `$window` instead of `window`

Instead of the default window object, you should prefer the AngularJS wrapper service $window.

**Styleguide Reference**

* [y180 by johnpapa - Angular $ Wrapper Services - $document and $window](https://github.com/johnpapa/angular-styleguide#style-y180)

## Examples

Examples with default configuration

    /*eslint angular/window-service: 2*/

    // valid
    $window.alert('Hello world!');

    // invalid
    window.alert('Hello world!'); // error: You should use the $window service instead of the default window object

## Links

* [Rule source](../rules/window-service.js)
* [Example source](../examples/window-service.js)