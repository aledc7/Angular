![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)

# Property Binding

Es una forma de comunicacion entre la plantilla __html__ y los elementos de la clase __typescript__.


Usando como ejemolo el componente Personas, crearemos un boton dentro del html que tendría el fin de agregar nuevas personas.
A este boton se le agregará una propiedad "disabled" para inhabilitarlo.  
Luego esta propiedad que deshabilita el boton, la bindearemos a una propiedad llamada "agregarPersona", la cual cambiará de true a false despues de transcurridos 5 segundos.

Cuando la propuedad AgregarPersona cambie de true a false,  también lo hará la propiedad "disabled" del boton, ya que está bindeada.

Veamoslo en el código:


1. Primero vemos el archivo .html


```html
# archivo personas.component.html

<div class="container">
  <div class="row">
    <div class="col">
    
        # Agrego un boton, y le pongo la propiedad disabled dentro de u array
        # y la igualo a la propiedad 'agregarPera', de esta manera queda bindeada.

        <button class="btn btn-primary" [disabled]=!agregarPersona>Agregar Persona</button>
        
    </div>
  </div>
</div>
````

2. Luego este será el conenido del archivo de typescript, que tendrá una propiedad __agregarPersona__. 
Esta propiedar es la que está bindeada a la propiedad 'disabled' del boton... de tal manera que cuando esta propiedad del compinente typescript cambie, también lo hará la propiedad del boton.

```js
# archivo personas.component.ts

import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-personas',
  templateUrl: './personas.component.html',
  styleUrls: ['./personas.component.css']
})
export class PersonasComponent implements OnInit {



# Esta es la propiedad booleana que está bindeada con el boton
  agregarPersona=false;

  nombrePersona: string = "Ale";
  apellidoPersona: string = "DC";
  edad: number = 40;


# Esta función, luego de 3 segundos, cámbia la propiedad  agregarPersona y la asigna a true. 

  constructor() {
    setTimeout(
      () => {
      this.agregarPersona = true;
    }, 3000);
   }

  ngOnInit() {
  }

}

````

De esta manera, estamos bindeando una propiedad en un boton del tempate html, con una prpiedad dentro del archivo typescript del componente.   






