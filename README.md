# 3.2 Intro a React I

## Introducción

En esta sesión vamos a seguir aprendiendo cómo funciona la librería [React.js](https://reactjs.org/). En concreto, vamos a ver que está basada en componentes y cómo crear un componente reutilizable.

## ¿Para qué sirve lo que vamos a ver en esta sesión?

Un **componente web** es una parte de la interfaz de una página o aplicación web que podemos reutilizar. Por ejemplo, una línea de producto de un carrito de la compra, o un elemento colapsable.

Los frameworks o librerías como React se basan en el concepto de componente. De esta forma, todo lo que vamos a crear son componentes que iremos usando para crear la interfaz deseada.

Los componentes de React, además, pueden personalizarse a través de un mecanismo llamado `props`, que no es otra cosa que pasarle valores a través de los atributos del componente HTML.

## Creando nuestro primer componente

_¡Manos a la obra!_ Vamos a crear nuestro primer componente de React. Va a ser un componente que nos muestre una imagen aleatoria de un gato usando la web de lorempixel, y que además será un enlace a una página. Primero, creamos un proyecto nuevo con `create-react-app`.

Para comenzar, vamos a crear un nuevo módulo Javascript para definir el componente. Recuerda que es buena práctica ordenar nuestros componentes en una carpeta para ellos, en `src/components` Crearemos un archivo `RandomCat.js` dentro de esta carpeta `components` recién creada. Moveremos también nuestro componente principal `App.js` a esa carpeta y actualizaremos las rutas del resto de archivos que estamos importando. Tendremos que importar React de su módulo y exportar el componente, así que partiremos de la siguiente estructura:

**RandomCat.js**:

```javascript
import React from 'react';
// ...
// ...AQUÍ ESCRIBIREMOS NUESTRO COMPONENTE
// ...
export default RandomCat;
```

Un componente en React es una vieja nuestra, una **función Javascript**, así que para crear un componente, una vez que hemos importado React y exportado nuestro componente sólo tenemos que escribir una función que tendrá por nombre el nombre de nuestro componente

```javascript
import React from 'react';

function RandomCat() {
  return (
   // AQUÍ ESCRIBIREMOS NUESTRO JSX
  )
}

export default RandomCat;
```

> Crearemos nuestros componentes siempre con **mayúscula inicial**. Así los diferenciaremos de los componentes en JSX que representan etiquetas de HTML

Como lo que queremos que haga nuestro componente es que pinte la imagen de un gatete, simplemente escribiremos en nuestro código.

```javascript
function RandomCat() {
  return (
    <a href="http://lorempixel.com">
      <img src="http://lorempixel.com/400/200/cats/" alt="Random cat" />
    </a>  
  )
}
```

_¡Ya está!_ Ahora para ver el resultado tendremos que decirle a React que lo pinte en nuestro componente principal **App.js** que es el que se encargará de montar las piezas de nuestra aplicación. Para usar nuestro recién estrenado componente RandomCat , tendremos que importarlo a App, naturalmente. Escribiremos arriba:

**App.js**:

```javascript
import React from 'react';
import RandomCat from './RandomCat';
```

> Para importar de un archivo local, utilizaremos el prefijo `./` antes de la ruta. Sin embargo, no pondremos el prefijo cuando sea una dependencia en `npm`, como nos preconfigura `create-react-app` para `react` y `react-dom`.

Solo falta el paso final: hacer que nuestro componente principal App.js retorne nuestro componente `<RandomCat>`para ello, en en el `return` de `App` llamaremos a `<RandomCat>` de esta manera:

```javascript
import React from 'react';
import RandomCat from './RandomCat';

function App() {
  return (
    <div className="App">
      <RandomCat/>
    </div>
  );
}

export default App;
```

> **IMPORTANTE**: Es muy importante tener en cuenta que a la hora de retornar elementos en nuestros componentes, estos, siempre deben ir envueltos en un único `div` contenedor, por ejemplo, si tenemos varios componentes `<RandomCat>` todos tendrían que ir dentro del mismo div antes de ser devueltos, si no se producirán errores.

#### ----------

#### EJERCICIO 1

Vamos a partir del ejercicio 1 \(o del 2\) de la sesión anterior. Siguiendo las instrucciones que acabamos de aprender vamos a crear un nuevo componente `MediaCard` que sea una tarjeta social para un usuario. Vamos a cargar ese nuevo componente desde `App.js` .

## Las `props` para personalizar un componente

Hasta aquí todo bien, pero ¿y si queremos que `RandomCat` no sea siempre igual? De la misma manera que pasamos atributos a los elementos del DOM, podemos pasar datos a los componentes de React.

```javascript
function Greeting (props) {
  return (
    <span>Hello, {props.name}!</span> // <span>Hello, María Moliner!</span>
  );
}
```

Vemos que primero debemos decirle al componente que recibirá los datos como parámetro por medio de la palabra  `props` , para más adelante darle nombre a esas `props.name` \(será el nombre que tendrá el atributo de nuestra etiqueta cuando la utilicemos\). 

Partiendo del ejemplo anterior tenemos un componente `<Greeting>` que recibirá por `props` el nombre de la persona que va a saludar.

**Greeting.js**

```javascript
function Greeting (props) {
  return (
  //Observa que he llamado name a mis props
    <span>Hello, {props.name}!</span> // <span>Hello, María Moliner!</span>
  );
}
```

En nuestro componente principal **App.js** retornaremos ese elemento pasándole a `<Greeting>` el valor que tendrán esas `props` que he llamado `name`

**App.js**

```javascript
import React from 'react';
import Greeting from './Greeting';

function App() {
  return (
    <div className="App">
      <Greeting name="María Moliner"/> //Hello María Moliner
    </div>
  );
}

export default App;
```

Una de las pocas reglas estrictas de React: **no debemos modificar nunca las `props`**, puesto que son como los parámetros que se le pasan a una función. 

