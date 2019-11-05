![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)


# Event Binding

Event Binding es la manera de asociar eventos a un componente.

En este ejemplo asociaremos el evento click de un boton agregar persona, y simplemente se reemplazará un párrafo. 

1. Primero en el archivo html asocio al evento __(click)__ la funcion __onCrearPersona()__  .
Observese que la palabra click que indica cual será el evento, debe ir entre corchetes.
Luego usando un parrafo con interpolacion, pongo una propiedad __agregarPersonaStatus__ .

Esta propiedad estará definida en el archovo typescript, y tendrá un método que cambiará el contenido de su texto. 




```js
// Archivo personas.component.html

<div class="container">
  <div class="row">
    <div class="col">
      
        // Agrego la propiedad (click) y la asocio al metodo 'onCrearPersona()'

        <button class="btn btn-primary" [disabled]=!agregarPersona (click)="onCrearPersona()">Agregar Persona</button>
      
         // Renderizo la propiedad agregarPersonas
      
        <p>{{ agregarPersonaStatus }}</p>
    </div>
  </div>
</div>

````
2.  Luego en el achivo typescript definimos la propiedad llamada __agregarPersonaStatus__ y la iniciaremos con un mensaje de texto inicial "No se ha agregado ninguna persona"

Seguidamente creamos un método que cambiará el texto asignado a esta propiedad, para finalmente asignar este método al boton del html.


```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-personas',
  templateUrl: './personas.component.html',
  styleUrls: ['./personas.component.css']
})
export class PersonasComponent implements OnInit {


  // Declaro una clase y le asigno un texto inicial

  agregarPersonaStatus = "No se ha agregado ninguna persona";


  // a la misma clase le cambio el texto inicial
  
   onCrearPersona(){
     this.agregarPersonaStatus = "Persona Agregada";
   }

   ngOnInit(){}


}


````

De esta manera, cada vez que se le de click al boton en el html, se ejecutará el método __onCrearPersona__  que simplemente cambiará el texto de la propiedad __agregarPersonaStatus__ 

Así entonces, hemos bindeado un evento (click) a una propiedad de nuestro componente.



