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

# Hola mundo

El más pequeño de los ejemplos de React se ve así:

```js
ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```

Este muestra un encabezado con el texto “Hello, world!” en la página.

# [Stateful and Stateless Components in React](https://programmingwithmosh.com/javascript/stateful-stateless-components-react/)

## Componentes con estado y sin estado

Hoy, revisaremos qué componentes con estado y sin estado se encuentran en React, cómo puede notar la diferencia y el complejo proceso de decidir si los componentes tienen estado o no.

## Revisión del estado

Primero, repasemos qué estado es.

En un componente, el estado son datos que importamos, generalmente para mostrar al usuario, que están sujetos a cambios. Podría cambiar porque la base de datos de la que estamos obteniendo puede actualizarse, el usuario la modificó, ¡hay muchas razones por las que los datos cambian!

```javascript
import React, {Component} from 'react'

class Pigeons extends Component {
  constructor() {
    super()
    this.state = {
      pigeons: []
    }
  }
  render() {
    return (
      <div>
        <p>Look at all the pigeons spotted today!</p>
        <ul>
          {this.state.pigeons.map(pigeonURL => {
            return <li><img src={pigeonURL} /></li>
          })}
        </ul>
      </div>
    )
  }
}
```

Por lo general, también tendríamos un componenteDidMount () que tomaría nuestros datos de una base de datos, pero el ejemplo anterior debería darle una idea básica: tenemos estado y podemos representar cosas desde el estado.

## Componentes con estado y sin estado

Los componentes con estado y sin estado tienen muchos nombres diferentes.

También son conocidos como:

- Componentes de contenedor vs presentación

- Componentes inteligentes vs tontos

La diferencia literal es que uno tiene estado y el otro no. Eso significa que los componentes con estado realizan un seguimiento de los datos cambiantes, mientras que los componentes sin estado imprimen lo que se les da a través de accesorios, o siempre representan lo mismo.

Componente con estado / contenedor / inteligente:

```javascript
class Main extends Component {
 constructor() {
   super()
   this.state = {
     books: []
   }
 }
 render() {
   <BooksList books={this.state.books} />
 }
}
```

Sin estado / Presentacional / Componente tonto:

```javascript
const BooksList = ({books}) => {
 return (
   <ul>
     {books.map(book => {
       return <li>book</li>
     })}
   </ul>
 )
}
```

Observe que el componente sin estado se escribe como una función. Tan bueno como es el estado, siempre debe tratar de hacer que sus componentes sean lo más simples y sin estado posible, de modo que los diferentes componentes se puedan reutilizar como piezas de Lego, incluso si no tiene planes inmediatos para reutilizar un componente. ¡Los con estado deberían sentirse afortunados de ser así!

## Componentes Visuales

Conocidos en inglés como Presentational Components. Este tipo de componentes solo deben centrase y enfocar sus esfuerzos en como debe renderizarse la UI. Este tipo de componentes puede componerse de otros elementos visuales y suele incluir estilos y clases. Todos los datos implicados en su renderización se deben recibir a través de props, por lo que deben ser independientes de llamadas a servicios externos. Este tipo de componentes suelen ser de tipo Stateless ya que no necesitan estado, y deben de gestionar las acciones pasándoselas a componentes padre a través de sus props.

**_Ejemplo:_**

```js
class Item extends React.Component {  
    render () {  
        return (  
            <li><a href='#'>{ this.props.valor }</a></li>  
        );  
    }  
}
```

# Presentando JSX

Considera la declaración de esta variable:

```
const element = <h1>Hello, world!</h1>;
```

Esta curiosa sintaxis de etiquetas no es ni un string ni HTML.

Se llama JSX, y es una extensión de la sintaxis de JavaScript. Recomendamos usarlo con React para describir cómo debería ser la interfaz de usuario. JSX puede recordarte a un lenguaje de plantillas, pero viene con todo el poder de JavaScript.

JSX produce “elementos” de React. Exploraremos como renderizarlos en el DOM en la  [siguiente sección](https://es.reactjs.org/docs/rendering-elements.html). A continuación puedes encontrar lo básico de JSX que será necesario para empezar.

## ¿Por qué JSX?

React acepta el hecho de que la lógica de renderizado está intrínsecamente unida a la lógica de la interfaz de usuario: cómo se manejan los eventos, cómo cambia el estado con el tiempo y cómo se preparan los datos para su visualización.

En lugar de separar artificialmente  _tecnologías_  poniendo el maquetado y la lógica en archivos separados, React  [separa  _intereses_](https://es.wikipedia.org/wiki/Separaci%C3%B3n_de_intereses)  con unidades ligeramente acopladas llamadas “componentes” que contienen ambas. Volveremos a los componentes en  [otra sección](https://es.reactjs.org/docs/components-and-props.html), pero si aún no te sientes cómodo maquetando en JS,  [esta charla](https://www.youtube.com/watch?v=x7cQ3mrcKaY)  podría convencerte de lo contrario.

React  [no requiere](https://es.reactjs.org/docs/react-without-jsx.html)  usar JSX, pero la mayoría de la gente lo encuentra útil como ayuda visual cuando trabajan con interfaz de usuario dentro del código Javascript. Esto también permite que React muestre mensajes de error o advertencia más útiles.

Con eso fuera del camino, ¡empecemos!

## Insertando expresiones en JSX

En el ejemplo a continuación, declaramos una variable llamada  `name`  y luego la usamos dentro del JSX envolviéndola dentro de llaves:

```js
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

Puedes poner cualquier  [expresión de JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Expressions_and_Operators)  dentro de llaves en JSX. Por ejemplo,  `2 + 2`,  `user.firstName`, o  `formatName(user)`  son todas expresiones válidas de Javascript.

En el ejemplo a continuación, insertamos el resultado de llamar la función de JavaScript,  `formatName(user)`, dentro de un elemento  `<h1>`.

```js
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

[**Pruébalo en CodePen**](https://es.reactjs.org/redirect-to-codepen/introducing-jsx)

Dividimos JSX en varias líneas para facilitar la lectura. Aunque no es necesario, cuando hagas esto también te recomendamos envolverlo entre paréntesis para evitar errores por la  [inserción automática del punto y coma](https://stackoverflow.com/q/2846283).

## JSX también es una expresión

Después de compilarse, las expresiones JSX se convierten en llamadas a funciones JavaScript regulares y se evalúan en objetos JavaScript.

Esto significa que puedes usar JSX dentro de declaraciones  `if`  y bucles  `for`, asignarlo a variables, aceptarlo como argumento, y retornarlo desde dentro de funciones:

```js
function getGreeting(user) {
  if (user) {
    return <h1>Hello, {formatName(user)}!</h1>;
  }
  return <h1>Hello, Stranger.</h1>;
}
```

## Especificando atributos con JSX

Puedes utilizar comillas para especificar strings literales como atributos:

```js
const element = <div tabIndex="0"></div>;
```

También puedes usar llaves para insertar una expresión JavaScript en un atributo:

```js
const element = <img src={user.avatarUrl}></img>;
```

No pongas comillas rodeando llaves cuando insertes una expresión JavaScript en un atributo. Debes utilizar comillas (para los valores de los strings) o llaves (para las expresiones), pero no ambas en el mismo atributo.

> **Advertencia:**
> 
> Dado que JSX es más cercano a JavaScript que a HTML, React DOM usa la convención de nomenclatura  `camelCase`  en vez de nombres de atributos HTML.
> 
> Por ejemplo,  `class`  se vuelve  [`className`](https://developer.mozilla.org/es/docs/Web/API/Element/className)  en JSX, y  `tabindex`  se vuelve  [`tabIndex`](https://developer.mozilla.org/es/docs/Web/API/HTMLElement/tabIndex).

## Especificando hijos con JSX

Si una etiqueta está vacía, puedes cerrarla inmediatamente con  `/>`, como en XML:

```jsx
const element = <img src={user.avatarUrl} />;
```

Las etiquetas de Javascript pueden contener hijos:

```jsx
const element = (
  <div>
    <h1>Hello!</h1>
    <h2>Good to see you here.</h2>
  </div>
);
```

## JSX previene ataques de inyección

Es seguro insertar datos ingresados por el usuario en JSX:

```jsx
const title = response.potentiallyMaliciousInput;
// Esto es seguro:
const element = <h1>{title}</h1>;
```

Por defecto, React DOM  [escapa](https://stackoverflow.com/questions/7381974/which-characters-need-to-be-escaped-on-html)  cualquier valor insertado en JSX antes de renderizarlo. De este modo, se asegura de que nunca se pueda insertar nada que no esté explícitamente escrito en tú aplicación. Todo es convertido en un string antes de ser renderizado. Esto ayuda a prevenir vulnerabilidades  [XSS (cross-site-scripting)](https://es.wikipedia.org/wiki/Cross-site_scripting).

## JSX representa objetos

Babel compila JSX a llamadas de  `React.createElement()`.

Estos dos ejemplos son idénticos:

```jsx
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```

```js
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

`React.createElement()`  realiza algunas comprobaciones para ayudarte a escribir código libre de errores, pero, en esencia crea un objeto como este:

```jsx
// Nota: Esta estructura está simplificada
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
```

Estos objetos son llamados “Elementos de React”. Puedes pensar en ellos como descripciones de lo que quieres ver en pantalla. React lee estos objetos y los usa para construir el DOM y mantenerlo actualizado.

Vamos a explorar el renderizado de los elementos de React al DOM en la siguiente sección.

> **Tip:**
> 
> Recomendamos usar la  [Definición del lenguaje en “Babel”](https://babeljs.io/docs/editors)  en tu editor de elección para que tanto el código en ES6 como el código en JSX sea resaltado apropiadamente. Este sitio web utiliza el esquema de color  [Oceanic Next](https://labs.voronianski.com/oceanic-next-color-scheme/), el cual es compatible con esto.

# Estilo y CSS

## ¿Cómo agrego clases CSS a los componentes?

Pasa una string como la prop  `className`:

```jsx
render() {
  return <span className="menu navigation-menu">Menu</span>
}
```

Es común que las clases CSS dependan de las props o del estado del componente:

```jsx
render() {
  let className = 'menu';
  if (this.props.isActive) {
    className += ' menu-active';
  }
  return <span className={className}>Menu</span>
}
```

> Tip
> 
> Si a menudo escribes código como este, el paquete  [classnames](https://www.npmjs.com/package/classnames#usage-with-reactjs)  puede hacerlo más simple.

## ¿Puedo usar estilos en línea?

Sí, ve la documentación sobre estilo  [aquí](https://es.reactjs.org/docs/dom-elements.html#style).

## ¿Los estilos en línea son malos?

Las clases CSS son generalmente mejores para el rendimiento que los estilos en línea.

## ¿Qué es CSS-in-JS?

“CSS-in-JS” se refiere a un patrón donde el CSS se compone usando JavaScript en lugar de definirlo en archivos externos. Lee una comparación de las bibliotecas CSS-in-JS  [aquí](https://github.com/MicheleBertoli/css-in-js).

_Ten en cuenta que esta funcionalidad no es parte de React, sino que es proporcionada por bibliotecas de terceros._  React no tiene una opinión sobre cómo se definen los estilos; en caso de dudas, un buen punto de partida es definir tus estilos en un archivo  `*.css`  separado como de costumbre y referirse a ellos usando  [`className`](https://es.reactjs.org/docs/dom-elements.html#classname).

## ¿Puedo hacer animaciones en React?

React puede usarse para potenciar animaciones. Revisa  [React Transition Group](https://reactcommunity.org/react-transition-group/)  y  [React Motion](https://github.com/chenglou/react-motion)  o  [React Spring](https://github.com/react-spring/react-spring), por ejemplo.

# Componentes y propiedades

Los componentes permiten separar la interfaz de usuario en piezas independientes, reutilizables y pensar en cada pieza de forma aislada.Esta página proporciona una introducción a la idea de los componentes. Puedes encontrar una  [API detallada sobre componentes aquí](https://es.reactjs.org/docs/react-component.html).

Conceptualmente, los componentes son como las funciones de JavaScript. Aceptan entradas arbitrarias (llamadas “props”) y devuelven a React elementos que describen lo que debe aparecer en la pantalla.

## Componentes funcionales y de clase

La forma más sencilla de definir un componente es escribir una función de JavaScript:

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

Esta función es un componente de React válido porque acepta un solo argumento de objeto “props” (que proviene de propiedades) con datos y devuelve un elemento de React. Llamamos a dichos componentes “funcionales” porque literalmente son funciones JavaScript.

También puedes utilizar una  [clase de ES6](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Classes)  para definir un componente:

```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

Los dos componentes anteriores son equivalentes desde el punto de vista de React.

Las clases tienen algunas características adicionales que veremos en las  [próximas secciones](https://es.reactjs.org/docs/state-and-lifecycle.html). Hasta entonces, usaremos componentes funcionales por su brevedad.

## Renderizando un componente

Anteriormente, sólo encontramos elementos de React que representan las etiquetas del DOM:

```jsx
const element = <div />;
```

Sin embargo, los elementos también pueden representar componentes definidos por el usuario:

```jsx
const element = <Welcome name="Sara" />;
```

Cuando React ve un elemento representando un componente definido por el usuario, pasa atributos JSX a este componente como un solo objeto. Llamamos a este objeto “props”.

Por ejemplo, este código muestra “Hello, Sara” en la página:

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```

[**Pruébalo en CodePen**](https://es.reactjs.org/redirect-to-codepen/components-and-props/rendering-a-component)

Recapitulemos lo que sucede en este ejemplo:

1.  Llamamos a  `ReactDOM.render()`  con el elemento  `<Welcome name="Sara" />`.
2.  React llama al componente  `Welcome`  con  `{name: 'Sara'}`  como “props”.
3.  Nuestro componente  `Welcome`  devuelve un elemento  `<h1>Hello, Sara</h1>`  como resultado.
4.  React DOM actualiza eficientemente el DOM para que coincida con  `<h1>Hello, Sara</h1>`.

> **Nota:**  Comienza siempre los nombres de componentes con una letra mayúscula.
> 
> React trata los componentes que empiezan con letras minúsculas como etiquetas del DOM. Por ejemplo,  `<div />`  representa una etiqueta div HTML pero  `<Welcome />`  representa un componente y requiere que  `Welcome`  esté definido.
> 
> Para saber más sobre el razonamiento detrás de esta convención, puedes consultar  [JSX en profundidad](https://es.reactjs.org/docs/jsx-in-depth.html#user-defined-components-must-be-capitalized).

## Composición de componentes

Los componentes pueden referirse a otros componentes en su salida. Esto nos permite utilizar la misma abstracción de componente para cualquier nivel de detalle. Un botón, un cuadro de diálogo, un formulario, una pantalla: en aplicaciones de React, todos son expresados comúnmente como componentes.

Por ejemplo, podemos crear un componente  `App`  que renderiza  `Welcome`  muchas veces:

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return (
    <div>
      <Welcome name="Sara" />
      <Welcome name="Cahal" />
      <Welcome name="Edite" />
    </div>
  );
}

ReactDOM.render(
  <App />,
  document.getElementById('root')
);
```

[**Pruébalo en CodePen**](https://es.reactjs.org/redirect-to-codepen/components-and-props/composing-components)

Por lo general, las aplicaciones de React nuevas tienen un único componente  `App`  en lo más alto. Sin embargo, si se integra React en una aplicación existente, se podría empezar de abajo hacia arriba con un pequeño componente como  `Button`  y poco a poco trabajar el camino a la cima de la jerarquía de la vista.

## Extracción de componentes

No tengas miedo de dividir los componentes en otros más pequeños.

Por ejemplo, considera este componente  `Comment`:

```jsx
function Comment(props) {
  return (
    <div className="Comment">
      <div className="UserInfo">
        <img className="Avatar"
          src={props.author.avatarUrl}
          alt={props.author.name}
        />
        <div className="UserInfo-name">
          {props.author.name}
        </div>
      </div>
      <div className="Comment-text">
        {props.text}
      </div>
      <div className="Comment-date">
        {formatDate(props.date)}
      </div>
    </div>
  );
}
```

[**Pruébalo en CodePen**](https://es.reactjs.org/redirect-to-codepen/components-and-props/extracting-components)

Acepta  `author`  (un objeto),  `text`  (un string), y  `date`  (una fecha) como props, y describe un comentario en una web de redes sociales.

Este componente puede ser difícil de cambiar debido a todo el anidamiento, y también es difícil reutilizar partes individuales de él. Vamos a extraer algunos componentes del mismo.

Primero, vamos a extraer  `Avatar`:

```jsx
function Avatar(props) {
  return (
    <img className="Avatar"
      src={props.user.avatarUrl}
      alt={props.user.name}
    />
  );
}
```

El  `Avatar`  no necesita saber que está siendo renderizado dentro de un  `Comment`. Esto es por lo que le dimos a su propiedad un nombre más genérico:  `user`  en vez de  `author`.

Recomendamos nombrar las props desde el punto de vista del componente, en vez de la del contexto en el que se va a utilizar.

Ahora podemos simplificar  `Comment`  un poquito:

```jsx
function Comment(props) {
  return (
    <div className="Comment">
      <div className="UserInfo">
        <Avatar user={props.author} />
        <div className="UserInfo-name">
          {props.author.name}
        </div>
      </div>
      <div className="Comment-text">
        {props.text}
      </div>
      <div className="Comment-date">
        {formatDate(props.date)}
      </div>
    </div>
  );
}
```

A continuacion, vamos a extraer un componente  `UserInfo`  que renderiza un  `Avatar`  al lado del nombre del usuario:

```jsx
function UserInfo(props) {
  return (
    <div className="UserInfo">
      <Avatar user={props.user} />
      <div className="UserInfo-name">
        {props.user.name}
      </div>
    </div>
  );
}
```

Esto nos permite simplificar  `Comment`  aun más:

```jsx
function Comment(props) {
  return (
    <div className="Comment">
      <UserInfo user={props.author} />
      <div className="Comment-text">
        {props.text}
      </div>
      <div className="Comment-date">
        {formatDate(props.date)}
      </div>
    </div>
  );
}
```

[**Pruébalo en CodePen**](https://es.reactjs.org/redirect-to-codepen/components-and-props/extracting-components-continued)

Extraer componentes puede parecer un trabajo pesado al principio, pero tener una paleta de componentes reutilizables vale la pena en aplicaciones más grandes. Una buena regla en general es que si una parte de su interfaz de usuario se usa varias veces (`Button`,  `Panel`,  `Avatar`), o es lo suficientemente compleja por sí misma (`App`,  `FeedStory`,  `Comment`), es buen candidato para ser un componente reutilizable.

## Las props son de solo lectura

Ya sea que declares un componente  [como una función o como una clase](https://es.reactjs.org/docs/components-and-props.html#function-and-class-components), este nunca debe modificar sus props. Considera esta función  `sum`  :

```jsx
function sum(a, b) {
  return a + b;
}
```

Tales funciones son llamadas  [“puras”](https://es.wikipedia.org/wiki/Programaci%C3%B3n_funcional#Funciones_puras)  por que no tratan de cambiar sus entradas, y siempre devuelven el mismo resultado para las mismas entradas.

En contraste, esta función es impura por que cambia su propia entrada:

```jsx
function withdraw(account, amount) {
  account.total -= amount;
}
```

React es bastante flexible pero tiene una sola regla estricta:

**Todos los componentes de React deben actuar como funciones puras con respecto a sus props.**



