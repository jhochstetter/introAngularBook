## 4 Controladores

Si bien ya hemos hablado un poco de los controladores que podemos crear en angular, ahora nos focalizamos en nuestra estructura.

Cuando nuestro sistema empieza a crecer, nos vemos en la obligación de separar tareas que en un principio nuestro controlador único hacía. Ahora estas serán delegadas a controladores más pequeños que también viven dentro de nuestra aplicación, por ende, estos también deben ser señalados como una dependencia en nuestro `app.js`. Estos controladores operarán sobre los distintos módulos de nuestro sistema.

Ejemplo:
```html
<script>
  // En los [ ] llamamos las dependecias como el 'otro-controlador'
  var app= angular.module('aplicacion',['otro-controlador']);
  app.controller('AplicacionController', function($scope){
    $scope.ejemplo='Esto es un ejemplo de Angular JS';
  });
</script>
```
```html
<script>
  // Nombre de la dependencia creada es 'otro-controlador'
  var app= angular.module('otro-controlador',[]);
  app.controller('OtroControlador', function($scope){
    $scope.saludo='Hola Mundo';
  });
</script>
```