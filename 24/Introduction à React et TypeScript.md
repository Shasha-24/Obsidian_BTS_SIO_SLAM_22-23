
## **Introduction à React et TypeScript :** 

React est une bibliothèque JavaScript populaire pour la création d'interfaces utilisateur réactives. TypeScript est un sur-ensemble de JavaScript qui ajoute des fonctionnalités de typage statique. L'utilisation de TypeScript avec React permet de détecter les erreurs de typage à la compilation et d'améliorer la maintenabilité du code. Dans ce cours, nous allons apprendre les concepts de base de React avec TypeScript.

**Installation de l'environnement de développement :** Pour commencer, vous devez installer Node.js et npm (Node Package Manager) sur votre machine. Une fois cela fait, vous pouvez créer un nouveau projet React en utilisant la commande suivante dans votre terminal :
````
```

`npx create-react-app mon-projet --template typescript`

````


Cela créera un nouveau dossier "mon-projet" avec une configuration TypeScript préconfigurée.

## **Composants React :** 

Les composants sont les blocs de construction fondamentaux de React. Ils permettent de découper l'interface utilisateur en morceaux réutilisables et indépendants. Voici un exemple de composant React simple en TypeScript :

````
`import React from 'react';  type MyComponentProps = {   name: string; };  const MyComponent: React.FC<MyComponentProps> = ({ name }) => {   return <div>Hello, {name}!</div>; };  export default MyComponent;`
`````



Dans cet exemple, nous déclarons un composant `MyComponent` qui reçoit une propriété `name` de type `string`. Le composant affiche ensuite "Hello, {name}!" à l'écran.

# **Utilisation des composants :** 


Une fois que vous avez créé un composant, vous pouvez l'utiliser dans d'autres composants ou dans le point d'entrée de votre application. Voici un exemple d'utilisation de `MyComponent` dans un autre composant :

````tsx

`import React from 'react'; 
import MyComponent from './MyComponent';  
const App: React.FC = () => {   
return <MyComponent name="John" />; };  

export default App;

````

Dans cet exemple, nous importons `MyComponent` depuis le fichier `MyComponent.tsx` et l'utilisons dans le composant `App`. Nous passons la propriété `name` avec la valeur "John" à `MyComponent`.

**État et gestion des événements :** React permet de gérer l'état de vos composants et de réagir aux événements utilisateur. Voici un exemple de composant qui utilise l'état et gère un événement de clic :



`import React, { useState } from 'react';  const Counter: React.FC = () => {   const [count, setCount] = useState(0);    const increment = () => {     setCount(count + 1);   };    return (     <div>       <p>Count: {count}</p>       <button onClick={increment}>Increment</button>     </div>   ); };  export default Counter;`

Dans cet exemple, nous utilisons le crochet `useState` pour déclarer une variable d'état `count` et une fonction `setCount` pour la mettre à jour. Lorsque l'utilisateur clique sur le bouton "Increment", la fonction `increment` est appelée, ce qui incrémente la valeur de `count` et déclenche un rendu mis à jour de l'

../ c'est la racine

cd / => racine du disque dur

routeur provider
au minimum 2 élément
path => chemin 

root 

## ROUTEUR

ne pas mettre a la racine 


un formulaire sert à


l'inference de type est une fonvtionnalité type script 
pipe => |

erreur => utilise des Hook dans une structure de contrôle diff 

encapsuler le code avec le CSS


Vite: Vite est un outil de développement rapide pour les applications web basées sur JavaScript et TypeScript

type Props = {
onAgree : () => {}
}

type Props = {
onAgree: () => void
}

Toujours mettre : c'est pour le type 

et les () aussi c'est obligatoire


commande qui créer un fichier


npm init -y => y= oui accepter toute les valeurs par défauts (comme ça on a pas a accepter toute les question elle sont direct accepter )

npm Install express (installer express)

Application web

## Nodemon 

npm i -D nodemon 

## MERN

mongo, express,  React, Node JS

Pourquoi on choisis cette stack ?

parce qu'il y a du JavaScript de partout  





