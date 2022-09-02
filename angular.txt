## Angular

npm install -g @angular/cli: Se instala primero en angular cli

ng new "Nombre del proyecto": Crear nuevo proyecto

ng serve --open: abrir la aplicación  en el navegador

ng generate component "nombre del componenete": Generar un componente

ng generate component componentes/landingPage/header: Indicando una ruta para el componente

mg add @fortawesome/angular-fontawesome: Agregando el modulo de fontawesome

Agregar FontAwesomeModule al imports ien src/app/app.module.ts:

    import { BrowserModule } from '@angular/platform-browser';
    import { NgModule } from '@angular/core';

    import { AppComponent } from './app.component';
    import { FontAwesomeModule } from '@fortawesome/angular-fontawesome';

    @NgModule({
    imports: [
        BrowserModule,
        FontAwesomeModule
    ],
    declarations: [AppComponent],
    bootstrap: [AppComponent]
    })
    export class AppModule { }

Tambien se agrega el ícono a la propiedad en el componente src/app/app.component.ts:

    import { Component } from '@angular/core';
    import { faCoffee } from '@fortawesome/free-solid-svg-icons';

    @Component({
    selector: 'app-root',
    templateUrl: './app.component.html'
    })
    export class AppComponent {
    faCoffee = faCoffee;
    }

Luego se hace el cambio en la clase:

    import { FaConfig } from '@fortawesome/angular-fontawesome';

    export class AppComponent {
        constructor(faConfig: FaConfig) {
            faConfig.defaultPrefix = 'far';
        }
    }

En el html se incrusta con:

    <fa-icon [icon]="faCoffee"></fa-icon>

En el archivo app.component.ts, para agregar una función o variabales se deben escribir en la clase principal