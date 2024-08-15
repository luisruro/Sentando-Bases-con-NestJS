# Sentando-Bases-con-NestJS

## Así inicio el proyecto:
**Todo lo inicio primero desde la consola de bash**

 1. npm i @nestjs/cli
 2. npx @nestjs/cli new nombre-del-proyecto
 3. cd nombre-del-proyecto
 4. code .
 5. En la carpeta src, elimino los archivos y dejo solo app.modules.ts y
    main.ts
 6. npm i --save @nestjs/typeorm typeorm mysql2
 7. Como esta local utilizo **npx** e instalo **nest g mo loans** y **nest g mo users** para crear los moduloes
 8.  Luego para crear los controladores **npx nest g co loans**
 9.  Luego creo los servicios **npx nest g s loans**

**preguntas:**

 - ¿Qué propósito cumple el archivo `main.ts` en un proyecto NestJS y por qué es crucial en la configuración inicial?

El archivo `main.ts` es el punto de entrada de una aplicación NestJS. Su propósito es inicializar la aplicación, configurar el servidor HTTP, y aplicar configuraciones globales como middleware, pipes, filters o interceptores. Es crucial porque arranca el ciclo de vida de la aplicación y define cómo se comportará globalmente.

 - ¿Qué diferencia    existe entre `app.module.ts` y `app.controller.ts`?
 - ¿Por qué crees que es importante modularizar la aplicación separando funcionalidades en diferentes módulos?
 - ¿Cómo crees que afecta la modularidad al mantenimiento y escalabilidad de la aplicación?
 - Despues de crear los archivos de los módulos, ¿qué archivos se generan y cómo se relacionan con los módulos creados?
 - ¿Qué sucede si defines incorrectamente un decorador en un controlador? ¿Cómo afecta esto a la funcionalidad del endpoint?
 - ¿Por qué es importante manejar rutas dinámicas (por ejemplo,  `@Get(':id')`) en aplicaciones que interactúan con bases de datos?
 - ¿Qué ventajas tiene manejar la lógica de negocio en servicios en lugar de controladores?
 - ¿Cómo se relaciona la inyección de dependencias con la modularidad y la capacidad de prueba de la aplicación?
 - ¿Por qué es crucial validar los datos de entrada en una aplicación que maneja transacciones financieras?
 - ¿Qué podría suceder si un decorador está mal colocado o si no se aplican los pipes correctamente?
 - ¿Cómo impacta el manejo adecuado de excepciones en la experiencia del usuario y en la seguridad de la aplicación?
 - ¿Por qué es importante tener un manejo centralizado de excepciones en una aplicación NestJS?

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
