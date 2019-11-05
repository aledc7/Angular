![Angular](https://github.com/aledc7/Angular/blob/master/resources/angular.png?raw=true)


[![aledc.tk](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.tk)
[![ingenea.com.ar](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/ingenea.svg)](http://ingenea.com.ar)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)


# Directivas

- [x] NgIf
- [x] NgElse
- [x] NgFor

Aunque existen muchas mas, estas son las principales directivas en Angular, comencemos  usando __NgIf__


1. Tenemos un parrafo que queremos mostrar ante una condición específica

```js
# plantilla.html


        <p *ngIf="estado; else else_resultado" >Resultado: {{resultado}}</p>


        <ng-template #else_resultado>
          <H3>ingrese dos valores</H3>
        </ng-template>

````

Observemos arriba, dentro de la etiqueta __P__ se coloca __*ngIF__ igualado a la propiedad __estadoresultado__.   
Luego punto y coma y un __else__ con otra propiedad, __else_resultado__.

Primeramente la propiedad __estado__ deberá estar declarada en el componente typescript, y podrá ser unicamente de tipo booleano. 
 En caso de que sea True, el parrafo se mostrará, en caso de que sea false, se mostrará el template que tenga como id, la propiedad __else_resultado__  .
 

```js
# archivo.component.ts


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
  
  // Propiedad para usar el ngIf, inicializada en false
  
  estadoresultado: boolean = false;


 // luego en cada función que quiera mostrar ese parrafo, asigno true a la propiedad estadoresultado.
 
 
  sumar(){
    this.estadoresultado = true;
    this.resultado = (this.input_a + this.input_b);
  }
  restar(){
    this.estadoresultado = true;
    this.resultado = (this.input_a - this.input_b);
  }
  producto(){
    this.estadoresultado = true;
    this.resultado = (this.input_a * this.input_b);
  }
  division(){
    this.estadoresultado = true;
    this.resultado = (this.input_a / this.input_b);
  }

  constructor() { }

  ngOnInit() {
  }

}
````





