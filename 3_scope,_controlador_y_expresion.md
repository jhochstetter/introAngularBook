## 3 $scope, Controlador y Expresión

### 3.1 $scope y Expresión:

Scope, o `$scope` es un objeto que guarda una referencia con el modelo en la aplicación. Es un contexto de ejecución para expresiones. Los Scopes pueden organizarse de forma jerárquica imitando la estructura del DOM de la aplicación. Además los Scopes pueden observar expresiones (`$watch`) y propagar eventos (`$apply`).

Los Scopes proveen el contexto en el cual las expresiones son evaluadas. Por ejemplo `{{username}}` no tiene ningún significado, a no ser que sea evaluada dentro de un Scope específico que define la propiedad `username`.

Scope es el "pegamento" entre la Vista y el Controlador. El controlador posee una referencia al Scope, esto aisla al Controlador del DOM haciendolo independiente a las Vistas.

Además el controlador puede añadir comportamientos al Scope. Los métodos definidos a través del Scope pueden ser accedidos desde la vista y asociados a eventos del DOM (onClick, onSubmit, etc.)

El siguiente controlador expone a través de `$scope` la propiedad `username` y el método `sayHello()`:

```javascript
angular.module('scopeExample', [])
.controller('MyController', ['$scope', function($scope) {
  $scope.username = 'World';

  $scope.sayHello = function() {
    $scope.greeting = 'Hello ' + $scope.username + '!';
  };
}]);
```
Fuente:

[https://docs.angularjs.org/guide/scope](https://docs.angularjs.org/guide/scope)


---


Ejemplo:
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF­8">
  <title>Ejemplo Angular</title>
  <link rel="stylesheet" href="">
  <script src="lib/js/angular.min.js"></script>
  <script >
    (function(){
      var app= angular.module("app",[]);
      app.controller("applicationController", ['$scopen',function($scope){
        // ejemplo es una propiedad
        $scope.ejemplo='Esto es un ejemplo de Angular JS';
        // hola() es un método
        $scope.hola = function(){
          $scope.ejemplo = 'hola';
        };
      }]);
    })();
    </script>
  </head>

  <body ng-app="app" ng-controller="applicationController">
    {{ejemplo}}
    <button ng-click="hola()">Hola!<button>
  </body>
</html>
```

[https://jsfiddle.net/oqkeu3zs/](https://jsfiddle.net/oqkeu3zs/)

