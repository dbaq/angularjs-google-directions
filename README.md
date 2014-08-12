AngularJS-Google-Directions
=========

An angular.js wrapper around the Google Directions API (heavily inspired from [AngularJS-Google-Places](https://github.com/arunisrael/angularjs-google-places))

Bower
--
This module is available as bower package, install it with this command:

```bash
bower install angularjs-google-directions
```
or

```bash
bower install git://github.com/dbaq/angularjs-google-directions.git
```


Usage
--
- Include the [Google Maps JS library](http://maps.googleapis.com/maps/api/js?libraries=places&sensor=true_or_false) in your app
- Add dbaq.google.directions as a dependency
- Inject googleDirections as a dependency to your controller or other service
- Invoke the getDirections method and pass in a latitude/longitude

Example
--
```
var myApp = angular.module('myApp',['ngGPlaces']);

// optional if you want to modify defaults
myApp.config(function(ngGPlacesAPIProvider){
  ngGPlacesAPIProvider.setDefaults({
    radius:500
  });
});

myApp.controller('mainCtrl',function($scope,ngGPlacesAPI){
  $scope.details = ngGPlacesAPI.placeDetails({reference:"really_long_reference_id"}).then(
    function (data) {
      return data;
    });

  $scope.data = ngGPlacesAPI.nearbySearch({latitude:-33.8665433, longitude:151.1956316}).then(
    function(data){
      return data;
    });
});
```

Further Customizations
--
You can override any default option below by passing that property to the getDirections method
```
var defaults = {
    unitSystem: null,
    durationInTraffic: false,
    waypoints: [],
    optimizeWaypoints: false,
    provideRouteAlternatives: false,
    avoidHighways: false,
    avoidTolls: false,
    travelMode: 'driving', // bicycling, transit, walking
    unitSystem: 'metric', // imperial
};
```

Testing
--
```
TODO
```

License
--
MIT