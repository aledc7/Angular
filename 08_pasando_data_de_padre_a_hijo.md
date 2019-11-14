![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)


# Pasando Información de un Componente Padre Hacia un Componente Hijo



Partimos de la base de tener un componente con demasiada lógica, entonces se decide separar parte de esa lógica a un nuevo componente.


En este caso el ejemplo concreto es el siguiente:

 En el componente __app.component.ts__ se tiene declarado un array que contiene un listado de personas.
 Luego en el archivo __app.component.html__ se itera ese array con unf __*ngFor__
 Se pretende acceder a este listado de personas desde un componente nuevo, que llamaremos __persona__ de esta manera se llevará la estructura __HTML__ necesaria a este nuevo componente y se modulizará un poco el código.
 
 
 ## Archivo  app.component.html
 
 Esta es la estructura con el __ngFor__ que se llevará a un nuevo componente.
 
 ```php
# archivo app.component.html

  <div class="row">
    <div class="col-xs-12">
      <div *ngFor="let persona of personas; let i = index">
        {{i +1}}: {{persona.nombre}} {{persona.apellido}}
      </div>
    </div>
  </div>
````

## Archivo app.component.ts

Este es el archivo Padre que contiene in array llamado __'personas'__ al que se quiere acceder desde un componente hijo.

```php
# Archivo app.component.ts


import { Component } from '@angular/core';
import { Persona } from './persona.models';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Pruebas de Angular';

# Este es el array al que se accederá desde un componente hijo
  personas: Persona[] = [
    new Persona("Ale", "Dc"),
    new Persona("Pablo", "Salut"),
    new Persona("Abel", "Ranni"),
    new Persona("Nahuel", "Sarlangue")
    ]
  nombreInput:string;
  apellidoInput:string;

  onAgregarPersona(){
    let persona1 = new Persona(this.nombreInput, this.apellidoInput);
    this.personas.push(persona1);
  }


}
```


Partiendo de esa base, estos serían los pasos para importar DATA de un componente Padre a un componente Hijo: 
 
 
 
 1. Crear el nuevo componente por terminal, este comando creará  los 4 archivos tipicos con los que se trabajará.
 
 
 ```php
 ng generate component persona
 
 # El resultado debería ser el siguiente:
CREATE src/app/persona/persona.component.css (0 bytes)
CREATE src/app/persona/persona.component.html (22 bytes)
CREATE src/app/persona/persona.component.spec.ts (635 bytes)
CREATE src/app/persona/persona.component.ts (273 bytes)
UPDATE src/app/app.module.ts (911 bytes) 
````

2. Luego pasar la estructura donde se encuentra el __*ngFor__ desde el archivo __app.component.html__ hacia el nuevo componente recien creado __persona.component.html__  

 
 ```php
# archivo persona.component.html

  <div class="row">
    <div class="col-xs-12">
      <div *ngFor="let persona of personas; let i = index">
        {{i +1}}: {{persona.nombre}} {{persona.apellido}}
      </div>
    </div>
  </div>
```` 


Aquí se podrá observar en el editor que ya no se tiene acceso a __personas__ que es el array que se quiere iterar en el *ngFor. Este array __personas__  se encuentra definido en el archivo __app.component.ts__ tal como se mostró mas arriba.


3. Luego, se debe incluir el componente hijo dentro del padre, incluyendo la etiqueta del nuevo componente __<app-persona /></app-persona/>__  en el componente Padre.
 
Luego, en esta etiqueta que incluye al hijo, es necesario  agregarle el componente __*ngFor__ se debe ej









