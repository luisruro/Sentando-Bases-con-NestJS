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

  `app.module.ts` define el módulo principal de la aplicación, agrupando y organizando los componentes como controladores y servicios. `app.controller.ts`, en cambio, define el controlador principal, que maneja las solicitudes HTTP y las rutas específicas. El módulo es la estructura, y el controlador gestiona las interacciones.

 - ¿Por qué crees que es importante modularizar la aplicación separando funcionalidades en diferentes módulos?

  Modularizar una aplicación en NestJS es importante porque mejora la organización, facilita el mantenimiento y la escalabilidad. Cada módulo se encarga de una funcionalidad específica, lo que permite desarrollar, probar y actualizar partes de la aplicación de manera independiente, reduciendo el acoplamiento entre componentes y haciendo el código más manejable y reutilizable.

 - ¿Cómo crees que afecta la modularidad al mantenimiento y escalabilidad de la aplicación?

  La modularidad facilita el mantenimiento al permitir actualizar y depurar partes específicas de la aplicación sin afectar otras. Para la escalabilidad, permite añadir nuevas funcionalidades o mejorar las existentes de manera incremental, ya que cada módulo puede desarrollarse y desplegarse de forma independiente, lo que simplifica la expansión de la aplicación.

 - Despues de crear los archivos de los módulos, ¿qué archivos se generan y cómo se relacionan con los módulos creados?

  Al crear un nuevo módulo en NestJS, generalmente se generan tres archivos principales:

  `<nombre>.module.ts`: Define el módulo, importando otros módulos y declarando los controladores y proveedores relacionados.

  `<nombre>.controller.ts`: Define el controlador asociado al módulo, manejando las rutas y solicitudes HTTP.

  `<nombre>.service.ts`: Define el servicio que contiene la lógica de negocio para el módulo.

  Estos archivos se relacionan con el módulo de la siguiente manera:

  El archivo `module.ts` organiza y estructura el módulo, registrando el controlador (`controller.ts`) y el servicio (`service.ts`) para que sean usados dentro de ese módulo.
  El controlador usa el servicio para procesar la lógica necesaria antes de responder a las solicitudes HTTP.

  Este conjunto mantiene la separación de responsabilidades y promueve un diseño limpio y escalable.

 - ¿Qué sucede si defines incorrectamente un decorador en un controlador? ¿Cómo afecta esto a la funcionalidad del endpoint?

  Si defines incorrectamente un decorador en un controlador, el endpoint podría comportarse de manera inesperada o simplemente no funcionar. Esto puede causar que:

  1. El endpoint no sea registrado: Si usas el decorador incorrecto o lo omites, la ruta no se asociará correctamente con el controlador, haciendo que las solicitudes a esa ruta devuelvan un error 404 (No encontrado).

  2. Errores en el manejo de solicitudes: Si el decorador de un método no coincide con el tipo de solicitud HTTP (por ejemplo, usar @Post en lugar de @Get), las solicitudes no serán procesadas adecuadamente.

  3. Fallos en la inyección de dependencias: Decoradores incorrectos en parámetros pueden impedir que los servicios o datos sean inyectados correctamente, causando errores en tiempo de ejecución.

 - ¿Por qué es importante manejar rutas dinámicas (por ejemplo,  `@Get(':id')`) en aplicaciones que interactúan con bases de datos?

 Manejar rutas dinámicas como @Get(':id') es crucial en aplicaciones que interactúan con bases de datos porque permite acceder a recursos específicos, como un registro en particular, mediante parámetros en la URL. Esto es fundamental para operaciones CRUD (Crear, Leer, Actualizar, Eliminar), donde necesitas identificar y manipular datos concretos basados en un identificador único (id). Facilita la extracción de datos precisos, mejora la eficiencia en las consultas y proporciona endpoints claros y funcionales para interactuar con la base de datos.
 
 - ¿Qué ventajas tiene manejar la lógica de negocio en servicios en lugar de controladores?

 Manejar la lógica de negocio en servicios en lugar de controladores ofrece varias ventajas:

  1. Separación de responsabilidades: Mantiene los controladores enfocados en manejar las solicitudes HTTP y delega la lógica de negocio a los servicios, lo que resulta en un código más limpio y modular.

  2. Reutilización del código: Los servicios pueden ser inyectados en múltiples controladores o módulos, permitiendo reutilizar la lógica de negocio en diferentes partes de la aplicación.

  3. Facilita el testeo: Los servicios, al estar desacoplados de la capa de presentación, pueden ser testeados de manera aislada, lo que simplifica las pruebas unitarias y mejora la calidad del código.

  4. Escalabilidad: La lógica de negocio centralizada en servicios facilita la expansión y modificación de la funcionalidad, ya que los cambios se realizan en un solo lugar sin afectar directamente los controladores.

  5. Mantenimiento: Al tener la lógica de negocio separada, es más sencillo mantener y actualizar la aplicación, ya que el código está bien organizado y dividido en unidades coherentes.

 - ¿Cómo se relaciona la inyección de dependencias con la modularidad y la capacidad de prueba de la aplicación?

 La inyección de dependencias está estrechamente relacionada con la modularidad y la capacidad de prueba de la aplicación de las siguientes maneras:

  1. Modularidad: La inyección de dependencias permite que los módulos sean autónomos y desacoplados, ya que cada módulo puede declarar sus propias dependencias sin preocuparse por cómo se instancian. Esto promueve la reutilización y facilita la modificación o sustitución de componentes sin afectar el resto de la aplicación.

  2. Capacidad de prueba: La inyección de dependencias facilita el uso de mocks y stubs en pruebas unitarias, ya que las dependencias de una clase (como servicios, repositorios, etc.) se pueden inyectar desde el exterior. Esto permite testear componentes de forma aislada, asegurando que el comportamiento se puede verificar sin necesidad de instanciar todo el entorno de la aplicación.

 - ¿Por qué es crucial validar los datos de entrada en una aplicación que maneja transacciones financieras?

 Es crucial validar los datos de entrada en una aplicación que maneja transacciones financieras por las siguientes razones:

  1. Seguridad: La validación previene ataques como la inyección de código malicioso o manipulaciones indebidas, protegiendo la integridad de las transacciones y la información sensible.

  2. Precisión: Asegura que los datos sean correctos y en el formato esperado, lo que es vital para cálculos financieros precisos y para evitar errores en la gestión de fondos.

  3. Prevención de fraudes: La validación estricta ayuda a detectar y bloquear intentos de transacciones fraudulentas, protegiendo tanto a la empresa como a los usuarios.

  4. Cumplimiento normativo: Garantiza que las transacciones cumplan con las regulaciones financieras y estándares legales, evitando sanciones y problemas legales.

  5. Confianza del usuario: Asegura que las transacciones se manejen de manera correcta y segura, lo que refuerza la confianza del usuario en la aplicación.

 - ¿Qué podría suceder si un decorador está mal colocado o si no se aplican los pipes correctamente?

 Si un decorador está mal colocado o si los pipes no se aplican correctamente, pueden ocurrir varios problemas:

  1. Fallos en la ruta: Un decorador mal colocado puede hacer que la ruta no se registre correctamente, lo que resultará en errores como 404 (No encontrado) cuando se intenta acceder al endpoint.

  2. Errores en la validación: Si no se aplican los pipes correctamente, los datos de entrada pueden no ser validados o transformados como se espera, lo que puede llevar a errores de tipo, datos incorrectos, o incluso vulnerabilidades de seguridad.

  3. Lógica rota: Un decorador incorrecto puede provocar que la lógica esperada no se ejecute o se ejecute en un momento incorrecto, afectando el flujo de la aplicación.

  4. Inyección de dependencias fallida: Si un decorador está mal colocado en un parámetro, la inyección de dependencias podría fallar, causando errores en la inicialización de servicios o componentes.

  5. Excepciones no manejadas: Pipes mal aplicados pueden causar que excepciones importantes no sean capturadas y manejadas, lo que podría llevar a fallos inesperados y a una mala experiencia del usuario.

 - ¿Cómo impacta el manejo adecuado de excepciones en la experiencia del usuario y en la seguridad de la aplicación?

 Manejar excepciones correctamente mejora la experiencia del usuario al mantener la aplicación estable y amigable, y refuerza la seguridad al proteger la aplicación de exposiciones y ataques potenciales.

 - ¿Por qué es importante tener un manejo centralizado de excepciones en una aplicación NestJS?

 Tener un manejo centralizado de excepciones en una aplicación NestJS es importante por varias razones:

  1. Consistencia: Permite manejar todos los errores de manera uniforme en toda la aplicación, garantizando respuestas consistentes y predecibles para los errores.

  2. Manejo Global: Facilita la captura y gestión de excepciones en un solo lugar, evitando la duplicación de lógica de manejo de errores en cada controlador o servicio.

  3. Seguridad: Ayuda a centralizar la lógica de manejo de errores para proteger contra la exposición de información sensible o detalles internos del sistema que podrían ser explotados por atacantes.

  4. Mantenimiento: Simplifica el mantenimiento al permitir actualizar la lógica de manejo de errores en un único lugar en lugar de modificar múltiples partes del código.

  5. Registro y Monitoreo: Facilita el registro y monitoreo de errores, proporcionando una vista centralizada de los problemas que ocurren en la aplicación, lo que ayuda a identificar y resolver problemas de manera más eficiente.

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
