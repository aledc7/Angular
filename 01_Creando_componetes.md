![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)


En Angular, los componentes se crean dentro de __src/app/nombre_componente_nuevo__.   
Para mantener el código limpio, se recomienda crear dentro de src una carpeta para cada componente nuevo que se genere.  

##  Generando un componente:

Dentro de la terminal, en Vs Code, se pueden generar los componentes de la siguiente manera
```php
ng generate component personas

# El resultado debería ser el siguiente
CREATE src/app/personas/personas.component.css (0 bytes)
CREATE src/app/personas/personas.component.html (23 bytes)
CREATE src/app/personas/personas.component.spec.ts (642 bytes)
CREATE src/app/personas/personas.component.ts (277 bytes)
UPDATE src/app/app.module.ts (483 bytes)
```
En el ejemplo de arriba, veos que se genera automaticamente la carpeta con el nombre del componente, y adentro los 4 archivos principales necesarios.  
También se hará automaticamente la importación del componente dentro del archivo __app.module.ts__
```php
# archivo app.module.ts

#se agrega automaticamente el import para el componente en cuestión
import { PersonasComponent } from './personas/personas.component';


# Se agrega también en la declaracion de los componentes

@NgModule({
  declarations: [
    AppComponent,
    
    # Aca se agrega el componente automaticamente.
    PersonasComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})

````

