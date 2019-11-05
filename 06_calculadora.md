![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)

# Ejercicio Calculadora


1.  Primero creo un nuevo componente y lo llamo calculadora
```js
ng generate component calculadora
````

2. Luego en el archivo __/src/app.component.html__  hago referencia para que se renderice primero que nada el nuevo componente recién creado:


```js
# archivo app.component.html

<div style="text-align: center;">
    
    // referencio al componente recien creado
    
    <app-calculadora></app-calculadora>
    
    
</div>

````
3. Creo los elementos necesarios en el template HTML:

```js
# archivo calculadora.component.html


<h1>{{ tituloApp }}</h1>
<div class="card">
  <div class="row">
    <div class="col">

        <h5>Primer numero a sumar:</h5>

        <input type="number"
        class="form-comtrol"
        [(ngModel)]="input_a">


        <h5>Segundo numero a sumar:</h5>

        <input type="number"
        class="form-comtrol"
        [(ngModel)]="input_b">
        <br>
        <button class="brn btn-outline-primary btn-sm" (click)=sumar()  >sumar</button>
        <button class="brn btn-outline-success btn-sm" (click)=restar()  >restar</button>
        <button class="brn btn-outline-danger btn-sm" (click)=producto()  >producto</button>
        <button class="brn btn-outline-warning btn-sm" (click)=division()  >division</button>
        <br>
        Resultado: {{resultado}}

    </div>
  </div>
</div>


````

4. Luego el contenido de la lógica de la calculadora, en el archivo de Typescript:
```js
# archivo calculadora.component.ts

import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-calculadora',
  templateUrl: './calculadora.component.html',
  styleUrls: ['./calculadora.component.css']
})
export class CalculadoraComponent implements OnInit {


  tituloApp = "Aplicacion de Calculadora";
  input_a :number;
  input_b :number;
  resultado:number;

  sumar(){
    this.resultado = (this.input_a + this.input_b);
  }
  restar(){
    this.resultado = (this.input_a - this.input_b);
  }
  producto(){
    this.resultado = (this.input_a * this.input_b);
  }
  division(){
    this.resultado = (this.input_a / this.input_b);
  }

  constructor() { }

  ngOnInit() {
  }

}
````

El resultado debería ser el siguiente:   

![Calculadora](https://github.com/aledc7/Angular/blob/master/resources/calculadora.png?raw=true)





