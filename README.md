AngularJS-Google-Directions
=========
An angular.js wrapper around the Google Directions API (heavily inspired by [AngularJS-Google-Places](https://github.com/arunisrael/angularjs-google-places))

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

Demo
--
See this [plunker](http://embed.plnkr.co/uiwQtK3E0f0KQuMoDf2Y/preview)

Usage
--
- Include the [Google Maps JS library](http://maps.googleapis.com/maps/api/js?libraries=places&sensor=true_or_false) in your app
- Add dbaq.google.directions as a dependency
- Inject googleDirections as a dependency to your controller or other service
- Invoke the getDirections method and pass in an origin and a destination

Example
--
```
var myApp = angular.module('myApp', ['dbaq.google.directions']);

myApp.controller('mainCtrl', function($scope, googleDirections) {
  var args = {
    origin: '37.7738571,-122.4102823',
    destination: '37.7891231,-122.4173545',
    travelMode: 'bicycling'
  }

  $scope.directions = googleDirections.getDirections(args).then(function(directions) {
    return directions;
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

## Donations

If your app is successful or if you are working for a company, please consider donating some beer money :beer::

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.me/dbaq/10)

Keep in mind that I am maintaining this repository on my free time so thank you for considering a donation. :+1:



Testing
--
```
TODO
```

License
--
MIT
