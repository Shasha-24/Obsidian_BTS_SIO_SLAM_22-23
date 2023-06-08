# Introduction à React

******************************

React est une bibliothèque JavaScript open-source largement utilisée pour la création d'interfaces utilisateur interactives. Elle permet de construire des applications web modernes en utilisant des composants réutilisables. L'un des principaux avantages de React est sa capacité à mettre à jour de manière efficace et optimisée uniquement les parties de l'interface utilisateur qui ont changé, plutôt que de recharger toute la page.

Dans cette introduction à React, nous allons aborder les points suivants :

1. **Avantages de React** : Nous allons découvrir les principaux avantages offerts par React, tels que la modularité, la réutilisabilité des composants, la facilité de gestion de l'état et la performance.
    
2. **JSX (JavaScript XML)** : JSX est une extension de syntaxe utilisée par React pour décrire la structure des composants. Nous allons explorer le JSX et comprendre comment il permet d'intégrer du code JavaScript dans du code HTML.
    
3. **Composants** : Les composants sont les éléments de base de React. Nous allons apprendre à créer nos propres composants, qui sont essentiellement des fonctions ou des classes qui renvoient du JSX.
    
4. **Imports et Exports** : Nous allons voir comment importer et exporter des modules dans React, ce qui permet d'organiser et de réutiliser efficacement notre code.
    
5. **Utilisation des props** : Les props (propriétés) sont des paramètres que l'on peut passer à nos composants pour les personnaliser et les rendre plus flexibles. Nous allons apprendre à utiliser les props pour transmettre des données et configurer nos composants.
    
6. **Gestion de l'état avec le State** : Le State est un concept clé de React qui nous permet de gérer l'état interne d'un composant. Nous allons découvrir comment utiliser le hook useState pour créer et mettre à jour le State de nos composants.
    
7. **Gestion des événements** : React nous permet de réagir aux événements utilisateur, tels que les clics de souris ou les saisies de clavier. Nous allons apprendre comment utiliser les événements en React et comment créer des gestionnaires d'événements.
    

# React et le DOM

Avant d'entrer dans les détails de React, il est important de comprendre comment JavaScript manipule le DOM (Document Object Model). Le DOM représente la structure d'une page HTML sous forme d'un arbre d'objets JavaScript. Il permet de manipuler et de modifier dynamiquement le contenu et l'apparence d'une page web.

L'une des principales caractéristiques de React est l'utilisation d'un DOM virtuel (Virtual DOM). Plutôt que de manipuler directement le DOM réel, React crée une représentation virtuelle de l'interface utilisateur dans la mémoire. Cette représentation virtuelle est ensuite comparée à la version réelle du DOM, et seules les différences sont appliquées. Cela permet d'optimiser les performances en évitant de recharger toute la page à chaque mise à jour.

# JSX (JavaScript XML)

React utilise une syntaxe appelée JSX, qui ressemble à du HTML mais qui est en réalité une extension de JavaScript. Le JSX permet d'écrire du code JavaScript et du code HTML dans un seul fichier. Voici quelques points clés à retenir

Voici un exemple de code JSX :

```jsx
`import React from 'react';  function App() {   const name = 'John Doe';   return <h`
```




# API


API : application web

get/uri = req ----> JSON = res

fichier d'entrée : Index.js, App.js etc... 


Index.js, App.js, main.js... :
|
|--> moddels : gère db => mongoose
|
Route --> express.routeur()
         | --> Controller
|
|Express() => app.listen(3003)
|

Next => fonction qui prend la requête et la passe a la fonction suivante.


Fonction qui prend la requête, la réponse et la fonction suivante :

````js
(req, res, next) => {

  console.log(req.test);

  next();

}
`````

req.test : objet 


recuperer la requete et l'envoyer a tout les sevices
