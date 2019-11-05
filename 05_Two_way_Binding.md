![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)

# Two Way Binding  (ngModel)

Mediante esta método es posible enviar informacion desde el componente Typescript hacia la plantilla html, y viceversa, o sea desde la plantolla html hacia el componente.

Veamoslo con un ejemplo simple.


Seguimos trabajando con el componente PersonaComponet.

1. Primeramente, necesitamos importar el modulo __FormsModule__ de Angular en el archivo __/src/app/app.modules.ts__
```js
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

// Hago el import de FormsModule
import { FormsModule } from '@angular/forms';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { PersonasComponent } from './personas/personas.component';

@NgModule({
  declarations: [
    AppComponent,
    PersonasComponent
  ],
  
  // Luego meto 'FormsModule' dentro del array de imports
  
  imports: [
    BrowserModule,
    AppRoutingModule,
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

````

Two Ways Bindings lo que hace es combinar __Propertyes Binding__ con __Event Binding__.   
Esto significa que por una parte se responderá a un evento, y por otro lado se modificará la propiedad en la clase de typescript.

Para combinar estas dos propiedades en Angular, se hace uso de __ngModel__:


```js
<div class="container">
  <div class="row">
    <div class="col">
        <h1>Angular Componentes</h1>
        <h2>Probando segundo</h2>
        <h3>Tercero</h3>

        <label>Nombre Persona</label>
        <br>
        <input type="text"
        class="form-comtrol"
        [(ngModel)]="tituloPersona">

        <br>
        {{tituloPersona}}
        <br>
        <h1>Lustado de Personas</h1>


        Nombre: {{nombrePersona}}
        <br>
        Apellido: {{apellidoPersona}}
        <br>
        Edad: {{edad - 6}}
        <br>
        <button class="btn btn-primary" [disabled]=!agregarPersona (click)="onCrearPersona()">Agregar Persona</button>
        <p>{{ agregarPersonaStatus }}</p>
    </div>
  </div>
</div>

````






