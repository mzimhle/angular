#AngualarJS

### Directives

- ng-app : Open the angularjs app or name the application also.
- ng-model : Defined in controls ( input, select, textarea) they basically id/name
- nd-bind : Outputs the ng-model data
- ng-init : In the same tag as ng-app, initialize selected variables (ng-bind) of the app. 
  - ng-init="var1=val1;var2='val2'"
  - ng-init="person={firstName:'John',lastName:'Doe'}"
  - ng-init="points=[1,15,19,2,40]"
- data-ng-init : alternative to ng-init - To make HTML valid
- data-ng-bind : alternative to ng-bind - To make HTML valid
- ng-controller : defines the controller to be used for this application.

P.S.: The naming of the directive on the tags and app.directive can be different but still be the same. The above refer to each other:
```sh
// On initialization inside script
movieApp.directive("movieDirective", function(){
....
// On the html code
<movie-directive></movie-directive>
```
You can create your own directive with angularjs:
```sh
// Use the directive in a div
<div ng-app="myApp" myDirectiveExample> ... </div>
<script>
var app = angular.module('myApp', []);
// Create the custom directive
app.directive("myDirectiveExample", function() {
  return {
    template : "Custom template over here!"
  }
});
</script> 
```

The returned array in the custom directive could be:
- template : Data to be returned.
- templateUrl : The url of the template, e.g. my-customer.html
- restrict : Specified how a directive will be used, either as an element or attribute.
  - A - matche attribute name
  - E - match element name
  - C - match class name
  - M - match comment
  - AEC - match either attribute, element, or class name.
- scope - 
  - default value is false
  - 
### Data expression

This is to display the data, use {{ expression }} to express data. e.g.:
```sh
> {{ 5 + 5 }}
> {{ name }}
> {{firstName + " " + lastName}}
> {{ points[2] }}
```

### Controllers

The module defines the application inside the js script block.
The controller, controls the angularjs application. 

- If app name in ng-app is defined and/or ng-controller is there. You cannot use expressions or an error will come up.

Initialize a controller: 
```sh
<div ng-app="myApp" ng-controller="myCtrl">
...
// Define the application
var app = angular.module('myApp', []);
// Declare its controller.
app.controller('myCtrl', function($scope) {
  // These are the ng-model tags in the html.
  $scope.firstName = 'John';
  $scope.lastName = 'Doe';
})
```

###
