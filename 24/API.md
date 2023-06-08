Node + Express

Elle répond au requête 
créer des routes pour les requête http

requête http qu'on renvoie au client 

Requête http:


l'architecture RESTful est un model d'architecture de développement de services web 

**REST** : (Representational State Transfer), définit un standard et des contraintes tels que:
- l'utilisation d'URI pour identifier les ressources
- l'utilisation de méthodes HTTP (GET, POST, PUT, DELETE, etc...) pour effectuer des opérations sur ces ressources
- La représentations des ressources au format JSON ou XML 

Les APIs (Application programming interface)
sont des 'interfaces' qui permettent a des applications de communiquer entre elles. On s'en sert notamment afin d'échanger des donnés.

Afin d'échanger des données on utilise des format universel, c'est souvent du JSON.

Voici un exemple de JSON qui représente un étudiant ISITEH:

```JSON
{
	"lastname": "DJEBLI",
	"firstname": "ayoub"
	"age": 19,
	"adresse": {
		 "rue": "2 rue de la paix",
		 "ville": "Paris"
		 "pays": "France"
	 },
	 "phoneNumbers": [
		 {
			 "type": "mobile",
			 "num": "0836656565",
			 
		 },
		 {
			 "type": "fixe",
			 "num": "3630"
		 }
	 ]
}
```


chemin => trajet

controlleur => logique (gère)


Endpoint : point d'entrée unique vers une ressource, il est constitué d'un verbe qui désigne une méthode http et d'une url (uri).

## Body-Parser 

Installer:

```shell
 npm install body-parser
```


Les codes https :

- 2XX:    Tout c'est bien passeé (200:    ok, 201:   Created)
- 3XX:    Redirection
- 4XX:    Erreur due au client (404:    Not found, )
- 5XX:    Erreur due au serveur

## Crud

Pour chaque ressource vous devez mettre en place en CRUD 
- Create:
- Read:
- Update:
- Delete  


middleware: 
Un **middleware** est un logiciel qui fournit des services et fonctionnalités unifiés aux applications, pour permettre aux équipes de développement et d'exploitation de créer et déployer des applications plus efficacement. Un **middleware** joue le rôle de lien entre les applications, les données et les utilisateurs. 

body-parser est un middleware

fonction qui recupère la requête et qui passe au prochain middleware

fonction sur le chemin de la requête http, prend les parametre (req, res, next)

/:id : Paramètre d'url spécifique a express, récuperer un id unique 





