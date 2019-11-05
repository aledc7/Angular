![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)

# Interpolaciones

La interpolación en Angular, al igual que en Vuejs, se indica a traves de dos pares de llaves __{{ }}__  y dentro de estas llaves, la propiedad que se vaya a emplear en la interpolacion.

Las interpolaciones sirven basicamente para municarse entre la clase de __typescript__ de nuestro componente, y la página __html__ de la vista.  De esta manera, se podrá acceder desde las págunas HTML a información contenida en alguna clase de typescript.

Como ejemplo Se usará un componete creado llamado __personas__  este fue creado mediante linea de comando. 



Primeramente se muestra el contenido del archivo html, en el que se usan tres interpolaciónes , para mostrar, el nombre, apellido y edad, que estan harcodeadas en la clase de typescript.

```php
# archivo personas.component.html


Nombre: {{ nombrePersona }}

Apellido: {{ apellidoPersona }}

Edad: {{ edad }}
````

Luego el contenido del la clase typescript tendrá lo siguiente:

```php
# archivo persona.component.ts


import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-personas',
  templateUrl: './personas.component.html',
  styleUrls: ['./personas.component.css']
})

#Estos son los elementos que seran accedidos a traves de las interpolaciones dentro del archivo html.
  
export class PersonasComponent implements OnInit {

  nombrePersona: string = "Ale";
  apellidoPersona: string = "DC";
  edad: number = 40;
  
}
````

Dentro de las interpolaciones es posible utilizar todo tipo de expresiones matemáticas y seran aceptadas :
```php
# archivo personas.component.html


Edad: {{edad - 6}}
````

También es posible acceder a métodos dentro de la clase de typescript.  Esto es muy útil cuando se tienen propiedades de tipo Private.  De esta forma la única manera de acceder a esta propiedad sería a través de su método:

```php
# archivo persona.component.ts 

getEdad():number{
 return this.edad;
 }
````

Luego en el archivo html, se llama al método dentro de la interpolación

```php
# archivo personas.component.html


Nombre: {{ nombrePersona }}

Apellido: {{ apellidoPersona }}

Edad: {{ getEdad() }}
````










