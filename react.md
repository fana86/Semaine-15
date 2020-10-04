<!-- omit in toc -->
# React.js

- [Préambule](#préambule)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Petit lexique](#petit-lexique)
  - [JSX](#jsx)
  - [ReactDOM et Render()](#reactdom-et-render)

## Préambule

React est une bibliothèque JavaScript pour construire des interfaces utilisateurs. Le principe est de composer des UI complexes à partir de composants (bout de code isolés).

Avant de commencer il est de bon ton de relire un peu [la théorie JavaScript](https://developer.mozilla.org/fr/docs/Web/JavaScript/Une_r%C3%A9introduction_%C3%A0_JavaScript). Il n'est pas nécessaire d'être un pro du JS pour utiliser React, mais quelques bases sont tout de même recommandées.

Pour ce cours je vous suggère de suivre le [tutoriel officiel](https://fr.reactjs.org/tutorial/tutorial.html) de React qui est super bien fait et en français!

## Installation

1. Assurez-vous d'avoir Node d'installé.
2. Exécutez la commande suivante dans votre répertoire principal. Cela va créer une structure de base pour votre projet dans le dossier `mon-app`.

```bash
npx create-react-app mon-app
cd mon-app
npm start
```

3. Cliquez sur l'adresse local pour voir votre application.

## Utilisation

React est *rapide*. Une app réalisé avec React est capable de faire des mises à jour complexe et toujours être rapide et responsive.

React est *modulable*. A la place d'écrire de longue ligne de code, vous pouvez écrire des plus petites et des réutilisables.

React *évolutif*. Il s'adapte à tous type de projet et excelle sur les plus conséquent.

React est *flexible*. Il peut tout à fait servir à des projets qui n'ont rien à voir avec des app web.

react est *populaire*. Ce qui fait qu'il est plus facile de trouver de l'aide en ligne et également un job par après.

## Petit lexique

### JSX

Il s'agit d'une extension de syntaxe pour JavaScript. JSX à été créé pour React et ressemble à de l'HTML. Cependant il n'est pas du JS valide, le navigateur ne peut pas le lire. Ce qui veut dire qu'avant que du JSX puis arriver au navigateur, il va falloir le compiler. C'est ce que ferra React pour nous.

```html
<h1>Hello World</h1>
```

Ceci est une balise HTML tout à fait classique, mais si elle est dans un fichier .js alors c'est du JSX!

Les éléments JSX sont comme les expressions JS, ils peuvent être stockés n'importe où où une expression JS serait stockée, comme dans une variable, passé à une fonction, stocké dans un objet ou un tableau,...

```js
const navBar = <nav>I am a nav bar</nav>;

const myTeam = {
  js: <li>Julie</li>,
  css: <li>James</li>,
  photo: <li>Chris</li>,
  coms: <li>David</li>,
  boss: <li>Vincent</li>,
};
```

Il est tout a fait possible de donner des attributs à nos éléments JSX comme en HTML.

```js
const cat = <img src="img/cat.jpg" alt="cat" width="500px" height="350px" />
```

Il est également possible d'utiliser le nesting d'éléments JSX. Notez que si l'élément contient plusieurs lignes alors il faut placer le code entre parenthèses. Le tout peut évidement être enregistré dans une variable.

```js
 const theExample = (
   <a href="https://www.example.com">
     <h1>
       Click me!
     </h1>
   </a>
 );
 ```

:exclamation::exclamation::exclamation: Un point super important que l'on oublie souvent et qui est source de nombreuse erreur de compilation. Il faut que votre élément JSX ait un et un seul élément qui englobe tous les autres.

Le code suivant ne fonctionnera pas:

```js
const paragraphs = (
  <p>I am a paragraph.</p> 
  <p>I, too, am a paragraph.</p>
);
```

Tandis que celui-ci fonctionnera à merveille.

```js
const paragraphs = (
  <div id="i-am-the-outermost-element">
    <p>I am a paragraph.</p>
    <p>I, too, am a paragraph.</p>
  </div>
);
```

### ReactDOM et Render()

```js
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <h1>Render me!</h1>, document.getElementById('app')
)
```

`ReactDOM` est une librairie JS qui contient des méthodes liés à React. La plus utile pour le moment est `render`. On va passer en argument notre JSX pour que `render` l'affiche sur notre page.


---
classe de composant React/type de composant React
props
createElement()
state this.state setState
on[event] (onClick)
handle[event] (handleclick)
immutabilité
fonctions composants
key