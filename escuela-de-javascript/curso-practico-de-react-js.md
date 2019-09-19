---
description: Notas y recolección de información para complementar este curso.
---

# Curso Práctico de React JS

## React

![React.svg](https://upload.wikimedia.org/wikipedia/commons/thumb/4/47/React.svg/245px-React.svg.png)

**React** \(también llamada **React.js** o ReactJS\) es una biblioteca [Javascript](https://es.wikipedia.org/wiki/JavaScript) de [código abierto](https://es.wikipedia.org/wiki/C%C3%B3digo_abierto) diseñada para crear [interfaces de usuario](https://es.wikipedia.org/wiki/Interfaz_de_usuario) con el objetivo de facilitar el desarrollo de [aplicaciones en una sola página](https://es.wikipedia.org/wiki/Single-page_application). Es mantenido por [Facebook](https://es.wikipedia.org/wiki/Facebook) y la comunidad de [software libre](https://es.wikipedia.org/wiki/Software_libre), han participado en el proyecto más de mil [desarrolladores](https://es.wikipedia.org/wiki/Desarrollador_de_software) diferentes. [1](https://es.wikipedia.org/wiki/React#cite_note-infoworld-1)​

React intenta ayudar a los desarrolladores a construir [aplicaciones](https://es.wikipedia.org/wiki/Aplicaci%C3%B3n_inform%C3%A1tica) que usan datos que cambian todo el [tiempo](https://es.wikipedia.org/wiki/Tiempo). Su objetivo es ser sencillo, declarativo y fácil de combinar. React sólo maneja la [interfaz de usuario](https://es.wikipedia.org/wiki/Interfaz_de_usuario) en una aplicación; React es la **Vista** en un contexto en el que se use el patrón [MVC](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93controlador) \(Modelo-Vista-Controlador\) o [MVVM](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93modelo_de_vista) \(Modelo-vista-modelo de vista\). También puede ser utilizado con las extensiones de React-based que se encargan de las partes no-UI \(que no forman parte de la interfaz de usuario\) de una [aplicación web](https://es.wikipedia.org/wiki/Aplicaci%C3%B3n_web).

Según el servicio de análisis Javascript \(en inglés "javascript analytics service"\), Libscore, React actualmente está siendo utilizado en las páginas principales de Imgur, Bleacher Informe, [Feedly](https://es.wikipedia.org/wiki/Feedly), [Airbnb](https://es.wikipedia.org/wiki/Airbnb), SeatGeek, HelloSign, y otras.[2](https://es.wikipedia.org/wiki/React#cite_note-2)​

### Historia

React fue creada por Jordan Walke, un ingeniero de software en Facebook, inspirado por los problemas que tenía la compañía con el mantenimiento del código de los anuncios dentro de su plataforma. Enfocado en la experiencia del usuario y la eficiencia para sus programadores, influenciado por XHP \(un marco de componentes de [HTML](https://es.wikipedia.org/wiki/HTML) para [PHP](https://es.wikipedia.org/wiki/PHP)\), nace el prototipo ReactJS.

## DOM virtual y detalles de implementación

### ¿Qué es el DOM virtual?

El DOM virtual \(VDOM\) es un concepto de programación donde una representación ideal o “virtual” de la IU se mantiene en memoria y en sincronía con el DOM “real”, mediante una biblioteca como ReactDOM. Este proceso se conoce como [reconciliación](https://es.reactjs.org/docs/reconciliation.html).

Este enfoque hace posible la API declarativa de React: le dices a React en qué estado quieres que esté la IU, y se hará cargo de llevar el DOM a ese estado. Esto abstrae la manipulación de atributos, manejo de eventos y actualización manual del DOM que de otra manera tendrías que usar para construir tu aplicación.

Ya que “DOM virtual” es más un patrón que una tecnología específica, las personas a veces le dan significados diferentes. En el mundo de React, el término “DOM virtual” es normalmente asociado con [elementos de React](https://es.reactjs.org/docs/rendering-elements.html) ya que son objetos representando la interfaz de usuario. Sin embargo, React también usa objetos internos llamados “fibers” para mantener información adicional acerca del árbol de componentes. Éstos pueden ser también considerados como parte de la implementación de “DOM virtual” de React.

### ¿Es el Shadow DOM lo mismo que el DOM virtual?

No, son diferentes. El Shadow DOM es una tecnología de los navegadores diseñada principalmente para limitar el alcance de variables y CSS en componentes web. El DOM virtual es un concepto que implementan bibliotecas en JavaScript por encima de las APIs de los navegadores.

## Create React App

[Create React App](https://github.com/facebookincubator/create-react-app) es un ambiente cómodo para **aprender React**, y es la mejor manera de comenzar a construir **una nueva** [**aplicación de página única**](https://es.reactjs.org/docs/glossary.html#single-page-application) usando React.

**Create React App** configura tu ambiente de desarrollo de forma que puedas usar las últimas características de Javascript, brindando una buena experiencia de desarrollo, y optimizando tu aplicación para producción. Necesitarás tener Node &gt;= 8.10 y npm &gt;= 5.6 instalados en tu máquina. Para crear un proyecto ejecuta:

```text
npx create-react-app my-app
cd my-app
npm start
```

> Nota
>
> En la primera línea `npx` no es un error de escritura: Es una [herramienta de ejecución de paquetes que viene con npm 5.2+](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b).

Create React App no se encarga de la lógica de `backend` o de bases de datos; tan solo crea un flujo de construcción para `frontend`, de manera que lo puedes usar con cualquier `backend`. Para ello internamente usa [Babel](https://babeljs.io/) y [webpack](https://webpack.js.org/), pero no necesitas saber nada de estas herramientas para usar Create React App.

Cuando estés listo para desplegar a producción, ejecuta `npm run build` lo cual crea una compilación optimizada de tu aplicación en el directorio `build`. Puedes aprender más acerca de **Create React App** [en su archivo README](https://github.com/facebookincubator/create-react-app#create-react-app--) y en la [Guía del Usuario](https://facebook.github.io/create-react-app/).

