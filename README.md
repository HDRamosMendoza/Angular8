# Angular8

** Angular
- Fue creado por google.
- Es un framework que serve para crear aplicaciones del lado del cliente.
- Angular no es lo mismo a AngularJS.
- Utiliza html, css/sass y typescript.

** Qué es typescript?
- Es un superconjunto de javascript, que esencialmente añade tipado estático y objetos basados en clases.
- Compila a javascript.
- Es un lenguaje de programaciónm orientado a clases.

** Instalaión de Node.js
- Es un entorno en tiempo de ejcucion multiplaforma, de código abierto.
- Una vez instalado NODE.JS, vamos a utilizar NPM(node package manager) para poder instalar otras librerías.

** Instalación de Angular CLI(Comand Line Interface).
- Es usado para crear un nuevo projecto de angular, el cual nos ayudará para crear packages(documentos ) para el despliegue de la aplicación(deployment).

npm install -g @angular/cli
ng --version
ng -v

** Crear una aplicacion de Angular.
ng new hola-mundo
cd hola-mundo

-> Dentro del proyecto en CMD digitamos: code .
-> Para correr el aplicativo: ng serve
    Al mostrar el aplicativo tambien te muestra cual es el puerto de salida.

** Crear un componente desde 0. Opcion A.
    Dentro de App.

    1. Creamos "cursos.component.ts"
        import { Component } from '@angular/core';
        @Component({
            selector: 'cursos',
            template: `
                <h1>Mis cursos</h1>
                <p>TypeScript</p>
            `,
            styles: ['h1 { color: red;}']
        })
        export class CursosComponent {
            mensaje = 'Curso de Angular';
        }
        
    2. Registrar el "Component"
        En app.module.ts
        import { CursosComponent } from './cursos.component';
        @NgModule({
            declarations: [
                AppComponent,
                CursosComponent
            ]
        })

    3. Para utilizar 
        En app.component.html
        {{mensaje}}
        <cursos></cursos>

** Crear un componente desde 0. Opcion B.
    Angular CLI. No crea los archivos necesarios y nos agrega el componente al archvivo app.module.ts

    1. Dentro del proyecto
        ng g c cursos
        Hay diferencia entre Template y TemplateURL.

** String Interpolation.
    Quiere decir que Angular se encargara de interpretar el valor de una variable o ejecutar alguna función para ver el resultado en la pantalla.

    app.component.ts
    export class AppComponent {
        nombre = 'Luis'

        getNombre() {
            return this.nombre;
        }
    }

    En app.component.html
    {{ 'Mi nombre es ' + getNombre() }}

** Property Binding
    Se enlazara un determinado valor con una propiedad que se encuentra dentro del DOM.

    @Component({
        selector: 'app-root',
        template: `
            <img [src] = "imagenURL"/></br>
            <button [disabled] = "botonStatus">Mi boton</button>
        `,
        styles: ['']
    })

    export class AppComponent {
        imagenURL = "http://lorempixel.com/400/200";
        botonState = false;
    }

** Class binding.
    Vamos a poder añadir un valor a una clase a un determinado elemento en base a una condición.

    @Component({
        selector: 'app-root',
        template: `
            <button [class.activo] = "isActive">Mi boton</button>
        `,
        styles: [`
            .activo {
                background: green;
            }
        `]
    })

    export class AppComponent {
        isActive = true;
    }

** Style binding

Nota: Decorador, componente.

Fuente: https://www.youtube.com/watch?v=7yGHRoLkI30&list=PLK7sa90aSLe7RW_7qotGlmBxMtm-jajCG