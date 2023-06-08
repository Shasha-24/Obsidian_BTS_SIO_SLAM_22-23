
https://www.mongodb.com/fr-fr

aucune contrainte de structure 
on peut avoir des utilisateur avec plusieurs champs et d'autre avec 2 =>  plasticité des schéma, mélanger tout les types….etc.


## Le format JSON : pourquoi ?

- JSON est un format universel, très répandu 
- Aucune structure n'est imposée (seule condition: la syntaxe)
- Les documents permettent de regrouper des informations 
- Les bases de donnée stockant des documents permettant la gestion d'une quantité immense de données

## Basse de données

La base de données est le conteneur physique des collections. 
Chaque base de données possède ses propres fichiers dans le système de gestion de fichier sur la machine hôte


## Collection

- Une collection est un groupe de documents MongoDB. C'est l'équivalent d'une table dans un système de gestion de base de données. Les collections n'imposent pas de schéma précis .
- Les documents présents au sein d'une même collection peuvent avoir des champs différents.
- Malgré cela, tous les documents, d'une même collection sont généralement similaire ou ont un usage similaire 

## Document

Un document est un ensemble de données clé-valeur.

Le schéma des documents est dit "dynamique".



importer des données, 

https://www.kaggle.com/  

apprendre tout ce qui est traitement de données  

datasets : échantillons de données, pas très grand


## Types de données

Nativement le format JSON prend en charge:
- booléen
- numérique
- chaine de caractères
- tableau
- objet
- null (marque l'absence de valeur)

A ces types, MongoDB vient ajouter:
- le type Date: stocke sous la forme d'un entier signe de 8 octets qui represente le nombre de secondes ecoulées depuis l'epoque (epoch) uni : le 1er janvier 1970 a minuit 
- Le type ObjecId: un type interne utilisé par MongoDB pour garantir l'unicite des identeifiants generes par la base de données 
- Les types entiers NumberLong () et NumberInt (4 octets): par defaut, MDB considere que les nombres sont des nombre à virgule flottante
- le type NumberDecimal (16 octets): nombre virgule flottante de grande precision


Entier Signer:

- Soit négative soit positif 

BSON : 
- https://docs.mongodb.com/manual/reference/bson-type/



## Ligne de commande MongoDB

Utiliser MongoDB en ligne de commande :

```bash
mongo --port 27017 --dpath /data/db --logpath /tn --logappend
```

#### Se connecter :

```bash
mongo --host lien.moncluster.fr --port 27017
```

Lister les bases de données :

```bash
show databases 
show dbs
```

En général, amèrs une installation fraiche de mongodb vous avez 3 bases disponible : 'admin', 'config', 'local'

Elles servet, a gérer les rôles, lles autorasatio, la gestion de MongoSB, du paramètrage d'instance 


Pour szvoir sur qu'elle base de données on se trouve actuellement il suggit de taper la commande `db`, pour lister les collections presentes dans votre bases vous pouvez entrer: `show collection`

Pour switcher de base on utilise la commande : `use maDb`

On peut utilise use afin de se connecter  à une basse inexistante, c'est lorque vous insererez votre premier doc dans une collection de cette base qu'ellle sera créée. :

```jsx
use maBasDeDonnes
db.maColletion.insrt({"une_cle": "une valeur"})
```


````js
db.maCollection.(find)
`````



## Exercice Teams MongoDB


Créez une base de données sample nommée "sample_db" et une collection appelée "employees". Insérez les documents suivants dans la collection "employees":

{ name: "John Doe", age: 35, job: "Manager", salary: 80000 }

{ name: "Jane Doe", age: 32, job: "Developer", salary: 75000 }

{ name: "Jim Smith", age: 40, job: "Manager", salary: 85000 }

Écrivez une requête MongoDB pour trouver tous les documents dans la collection "employees".

Écrivez une requête pour trouver tous les documents où l'âge est supérieur à 33.

Écrivez une requête pour trier les documents dans la collection "employees" par salaire décroissant.

Écrivez une requête pour sélectionner uniquement le nom et le job de chaque document.

Écrivez une requête pour compter le nombre d'employés par poste.

Écrivez une requête pour mettre à jour le salaire de tous les développeurs à 80000.

![[Pasted image 20230606162053.png]]


- Utiliser **'use sample_db'**  
- **'db.employees.find()'** pour trouver tous les documents dans la collection "employees"
- **'db.employees.find({ age: { $gt: 33 } })'** pour trouver tous les documents où l'âge est supérieur à 33.
- **'db.employees.find().sort({ salary: -1 })'** pour trier les documents dans la collection "employees" par salaire décroissant.
- **'db.employees.find({}, { name: 1, job: 1 })'** pour sélectionner uniquement le nom et le job de chaque document.
- db.employees.aggregate([
  {
    $group: {
      _id: "$job",
      count: { $sum: 1 }
    }
  }
])  pour compter le nombre d'employés par poste.
- **'db.employees.updateMany({ job: "développeur" }, { $set: { salary: 80000 } })'** pour mettre à jour le salaire de tous les développeurs à 80000.




