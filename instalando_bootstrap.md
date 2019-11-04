![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)


## Instalando Bootstrap a nuestro Proyecto Angular

Para usar Bootstrap en nuestro proyecto, se recomienda instalar estas tres librerías:   

1.  Dentro del proyecto instalar; primero Bootstrap, y luego dos dependencias necesarias:  

```php
# Primero instalo bootstrap
npm install bootstrap --save

# Luego de finalizado, instalo la dependencia de Jquery
npm install jquery --save

# Luego de terminado, se instala la dependencia popper
npm install popper.js --save
````

2.  Luego se deberá modificar el archivo __angular.json__

```php
# archivo angular.json

 # Agrego bootstrap a los estilos CSS, en el array Styles
"styles": [
# Este es el archivo de estilos personalizado.   
 "src/styles.css",
 # Agrego esta otra linea para agregar el archivo de estilos de bootstrap
 "node_modules/bootstrap/dist/css/bootstrap.min.css"
],

# En el array de Scripts, agrego estas tres lineas
"scripts": [
  "node_modules/jquery/dist/jquery.slim.min.js",
  "node_modules/popper.js/dist/umd/popper.min.js",
  "node_modules/bootstrap/dist/js/bootstrap.min.js"
]
````
3. Luego se debe recargar el server de Angular para que tome los nuevos cámbios, y ya se tendrá disponible Bootstrap en nuestra App. 





    
