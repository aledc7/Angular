![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)


# Angular - Manual de Bolsillo


## Geting Started

#### Pre requisitos:

- [x] Node
- [x] NPM

1. Instalando el __CLI__ de Angular
```php
npm install -g @angular/cli
````

2. Crear nuestro primer proyecto de Angular
```php
ng new nombreApp
````

3. Preguntará algunas opciones acerca de que framework de CSS usar y si usar Angular Route, esto dependera de cada proyecto.   
Luego de esto, acceder a la carpeta que tendrá el nombre de la App, y correrla con el siguiente comando:  
```php
ng serve -o 
````
la opción -o es para que se abra luego de ejecutar el server (open) .



# Como es que se levanta una app en Angular

El Framework de angular, entre otras cosas es muy utilizado para crear SPA (Single Page Application).  Normalmente, cada proyecto de angular tiene dentro de __SRC/__  el archivo __index.html__.   Aqui dentro  tenemos un html comun, y el elemento __<app-root></app-root>__     Aqui un ejemplo del index.html que se genera al crear un proyecto base en blanco:

```php
# Archiv  index.thml


<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Costcontrol</title>
  <base href="/">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
<body>

  # Este tag es el que inyecta Angular dentro del HTML
  <app-root></app-root>
  
</body>
</html>
````


Este elemento __<app-root></app-root>__  se encuentra definido dentro del compoonente __/src/app/app.componet.ts__

```php
# Archivo app.component.ts


import { Component } from '@angular/core';

# Este es el decorador de la clase Component
@Component({

  # Aca se declara el nombre del componente que existe en el HTML.
  selector: 'app-root',
  
  # Aca se indica cual es la plantilla HTML que se va a utilizar en la App.   
  templateUrl: './app.component.html',
  
  # Aca se indica cual es el archiv CSS que se va a utilizar en la App.   
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Cost Control';
}
````

Luego en el archivo __/src/main.js__  se cargarán otras aplicaciones:
```php
# archivo main.js

# Este archivo main levanta el componente del archivo module.ts


import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

import { AppModule } from './app/app.module';
import { environment } from './environments/environment';

if (environment.production) {
  enableProdMode();
}

# Aca se levanta el modulo de AppModule, que es una clase de Javascript, está relacionado con el archivo /src/app/app.module.ts
platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err));
````



```php
# archivo /src/app/app.module.ts

# Esta clase se compone de varios elementos, se comenta sobre cada uno


import { BrowserModule } from '@angular/platform-browser';

# esta importacion es para usar el decorador @NgModule 
import { NgModule } from '@angular/core';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';

# este es un decorador, que contendrá 4 elementos
@NgModule({

  # En el array de declaraciones se declaran los componentes propios que se vayan a utilizar.
  declarations: [
    AppComponent
  ],
  # en el array de Imports se agregan otros modulos ya sean de Angular u otros externos. 
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  
  # El array de proveedores se vera mas adelanet
  providers: [],
  
  # Aca se india que componente va a levantar al inicar la App.
  bootstrap: [AppComponent]
}) 

# Esta es la clase que se usa en 'platformBrowserDynamic().bootstrapModule(AppModule)' en el archivo 'main.js'
export class AppModule { }
````

Este de arriba es el flujo básico para levantar una App en Angular.  


Entonces, los elementos de un componente son:  

- Una clase de Typescrip (.ts)
- Un decorador
  - Un Selector que sera el que se usa en el index.thmlç
  - La plantilla HTML a utilizar
  - El archivo de estilos CSS que se vaya a utilizar

Con esto completamos la intro.













