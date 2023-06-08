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
