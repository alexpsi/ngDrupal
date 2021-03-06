ngDrupal
========

(Version 0.1.2 Very very alpha version)

Angular service that allows Restangular to connect to a Drupal site utilizing Services 3.5+. Provides authentication and file upload methods.

# Installation 

Download source from bower  

````bash
bower install angular-drupal -S 
````

Add Restangular and ngDrupal to app and configure REST endpoint. 

````
  angular.module('myApp', [
    'restangular',
    'ngDrupal'
    ...
  ])
  .config(function (ngDrupalProvider) {
    ngDrupalProvider.config({
      hostname: 'http://hostname/',
      endpoint: 'api'
    });
  })
````

And finally inject ngDrupal to your controller 

````
  controller('MainCtrl', function ($scope, ngDrupal) {});
```

  
At server side, you can provision a new drupal installation by using the [feature branch] (https://github.com/alexpsi/ng-drupal/tree/feature)
  
# Usage

All ngDrupal methods return promises. 

## Login

````
  ngDrupal.login({username: username, password: password}).then(function(data) {console.log(data);});
````

## Logout

````
  ngDrupal.logout();
````

## System connect
Returns current user information 
````
   ngDrupal.systemConnect().then(function(data) {console.log(data);});
````

## NodeFactory
Returns a Restangular object pointing to api/node 
````
   var node = ngDrupal.nodeFactory();
````






