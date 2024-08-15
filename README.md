<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master" target="_blank"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#9" alt="Coverage" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

## Description

[Nest](https://github.com/nestjs/nest) framework TypeScript starter repository.

## Installation

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Test

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://kamilmysliwiec.com)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](LICENSE).



# Questions

## 1. Configuración del Proyecto
### ¿Qué propósito cumple el archivo main.ts en un proyecto NestJS y por qué es crucial en la configuración inicial?
Este se encarga de configurar y darle inicio al servidor de la app, configurando las capas externas y orquestando la inicializacion de la app si hacer parte de la logica de necio; es crucial ya que conecta todos los componentes de la aplicacion para posteriormente procesar solicitudes orquestando.

### ¿Qué diferencia existe entre app.module.ts y app.controller.ts? ¿Cómo se relacionan estos archivos con la modularidad y la estructura de la aplicación?
app.module agrupa y organiza la configuracion y los modulos de la app, no se involucra en la logica de negocio, mientras que el controller es una interfaz entre el exterior y la logica interna de la app, recibe las solicitudes HTTP, delegar y dar una resupuesta al usuario.

## 2. Creación de Módulos Básicos
### ¿Por qué crees que es importante modularizar la aplicación separando funcionalidades en diferentes módulos?
Debido a que será mas legible, mas escalable y mantenible.

### ¿Cómo crees que afecta la modularidad al mantenimiento y escalabilidad de la aplicación?
Al ser mas legible y separar responsabilidades, la aplicación permite agregar nuevas funcionalidades sin afectar las ya existentes, ademas por la mis razón será mas facil el mantenimiento dado que es posible identficar cuellos de botella o errores que se esten generando.

### Despues de crear los archivos de los módulos, ¿qué archivos se generan y cómo se relacionan con los módulos creados?
Posterior a crear los archivos .module.ts (el cual permite orquestar los componentes de cada entidad), se crean los controladores, los cuales deben ir dentro del modulo para poder recibir la peticion, delegar y entregar la informacion.

## 3. Implementación de Controladores
### ¿Qué sucede si defines incorrectamente un decorador en un controlador? ¿Cómo afecta esto a la funcionalidad del endpoint?
Inicialmente el editor de codigo mostrará un error donde el controlador generó el error, posteriormente si le damos start no dejará desplegar el localhost, debido a que nombramos mal el decorador, si el tipado del controlador esta correcto pero la definicion posterior esta mal realizar, el endpoint no correrá. 

### ¿Por qué es importante manejar rutas dinámicas (por ejemplo, @Get(':id')) en aplicaciones que interactúan con bases de datos?
Para asi obtener la data solicitada y evitar confusion entre endpoints

## Desarrollo de Servicios
### ¿Qué ventajas tiene manejar la lógica de negocio en servicios en lugar de controladores?
La principal ventaja es mantener aislada la logica del negocio, dando facilidad de mantenimiento, tester y/o modificaciones.
Otra ventaja de suma importancia es que permite la reutilizacion en diferentes partes o etapas de la aplicacion.

### ¿Cómo se relaciona la inyección de dependencias con la modularidad y la capacidad de prueba de la aplicación?
Al inyectar las dependencias desde el exterior promueve la flexibilidad y facilidad de testeo, ademas permite reemplazar facilmente una implementación sin modificar el codigo. Por otro lado, la capacidad de prueba mejora debido a que los componentes inyectados puede ser simulados de mejor manera en pruebas y facilita las pruebas unitarias y de integracion.

## Aplicación de Decoradores y Pipes
### ¿Por qué es crucial validar los datos de entrada en una aplicación que maneja transacciones financieras?
Debido a que valida antes de ser procesado por el controlador de manera centralizada y uniforme.

### ¿Qué podría suceder si un decorador está mal colocado o si no se aplican los pipes correctamente?
Pueden generar un error en la aplicacion, sin permitir el despliegue de esta o simplemente ingresaran datos erroneos que pueden crashear la aplicación

## Configuración de Exception Filters
### ¿Cómo impacta el manejo adecuado de excepciones en la experiencia del usuario y en la seguridad de la aplicación?
Indican al usuario cual es ese error y definen cómo debe responder la aplicación al cliente (comprender que salio mal); ademas en seguridad controla la informacion sensible que se envia a un cliente cuando ocurre un error, protegiendo datos sensibles del sistema.

### ¿Por qué es importante tener un manejo centralizado de excepciones en una aplicación NestJS?
Capturar los errores en un solo lugar, lo que facilita la gestión y el mantenimiento del código.