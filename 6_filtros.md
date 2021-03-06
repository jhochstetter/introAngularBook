# 6 Filtros


Para poder excluir, ordenar u operar cierta información en nuestra web, Angular también soporta filtros, algunos existentes y otros que podemos desarrollar, un filtro como su nombre bien lo dice nos permite seleccionar cierta información a mostrar y generalmente es sobre un array, por ende es importante dar un correcto uso de estos cuando debemos mostrar cierta información.

Ejemplo:
Ordenar por un valor en un array:
```HTML
<div ng-app="miApp" ng-controller="AppController">

<p>Iterando los objetos ordenados por pais:</p>
<ul>
  <li ng-repeat=" x in nombres | orderBy:'pais' ">
    {{ x.nombre + ', ' + x.pais }}
  </li>
</ul>

</div>

<script>
angular.module('miApp', []).controller('AppController', function($scope) {
    $scope.nombres = [
        { nombre : 'Jani' , pais : 'Noruega' },
        { nombre : 'Carl' , pais : 'Suecia' },
        { nombre : 'Margareth' , pais : 'Reino Unido' },
        { nombre : 'Hege' , pais : 'Noruega' },
        { nombre : 'Joe' , pais : 'Dinamarca' },
        { nombre : 'Gustav' , pais : 'Suecia' },
        { nombre : 'Birgit' , pais : 'Dinamarca' },
        { nombre : 'Mary' , pais : 'Reino Unido' },
        { nombre : 'Kai' , pais : 'Noruega' }
        ];
});
</script>
```



Filtro Personalizado:
```HTML
<ul ng-app="miApp" ng-controller="appCtrl">
<li ng-repeat="x in names">
    {{x | miFiltro}}
</li>
</ul>

<script>
var app = angular.module('miApp', []);

app.filter('miFiltro', function() {

    return function(x) {
        var i, c, txt = "";
        for (i = 0; i < x.length; i++) {
            c = x[i];
            if (i % 2 == 0) {
                c = c.toUpperCase();
            }
            txt += c;
        }
        return txt;
    };
});
app.controller('appCtrl', function($scope) {
    $scope.nombres = [
        'Jani',
        'Carl',
        'Margareth',
        'Hege',
        'Joe',
        'Gustav',
        'Birgit',
        'Mary',
        'Kai'
        ];
});
</script>

```