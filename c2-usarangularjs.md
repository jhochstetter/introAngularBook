##2­ Cómo usar Angular JS en nuestra aplicación web

### 2.1 Directivas nativas:
Una directiva es un atributo personalizado que fue previamente desarrollado en Angular, es decir una funcionalidad que implementaremos en nuestra web, existen muchas directivas y nos permiten desarrollar nuestra web SPA, dentro de las más importantes se encuentran la ng-app, ng-controller, ng-include, ng-repeat, ng-show, ng-if, ng-class, ng-form, ng-model, entre muchas otras, de modo que ahora podremos definir el comportamiento de nuestros elementos dentro del layout mediante las diferentes directivas de Angular.

####Definiciones

* `ng-app`: Directiva para indicar el modulo principal de la aplicación en AngularJS.

```html
<html ng-app="app">
```

* `ng-init`: Directiva para inicializar una variable desde el HTML.

```html
<div ng-init= " saludo=’HolaMundo’"   > {{saludo}}
</div>
```

* `ng-controller`: Permite crear un controlador que funcionará dentro de la aplicación.

```html
<body ng-controller="AppController">
```

* `ng-class`: Permite reemplazar el atributo `class` de un elemento de forma programática.

```html
<p ng-class= "active: true" ></p>
```

* `ng-submit`: Funciona bajo el evento submit dentro de un formulario, generalmente invoca una función.

```html
<body ng-app="app" ng-controller="AppController" >
<form  ng-submit="miFuncion()" >
  <input type="text">
  <input type="submit">
</form>
<p> {{texto}} </p>
<script>
  var app = angular.module('app', []);
  app.controller('AppController', function($scope){
    $scope.texto = 'Aún no presionas el submit';
    $scope.miFuncion = function () {
      $scope.texto = 'Presionaste el submit!';
    };
  });
</script>
</body>
```

* `ng-repeat`: Genera una iteración, generalmente se usa para recorrer una lista, similar a `ForEach`.

```html
<ul ng-init "nombres=['John Snow', 'Ash Ketchum', 'Gary Oak']" >
  <li ng-repeat="name in nombres">
    {{name}}
  </li>
</ul>
```

* `ng-show`: Permite mostrar u ocultar un elemento, recibe un booleano.

```html
<div ng-show="true">Hola Mundo</div>
```

* `ng-if`: Similar a ng-show, oculta o muestra elemento pero los falsos no los muestra en el HTML.

```html
<div ng-if="true"> Hola Mundo</div>
```
* `ng-include`: Nos permite agregar un template de HTML, este recibe la ruta del HTML.

```html
<div ng-include="vista.html"></div>
```
