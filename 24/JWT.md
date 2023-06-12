# JWT 

**JSON Web Token** (JWT) est un standard ouvert défini dans la RFC 7519. Il permet l'échange sécurisé de jetons (tokens) entre plusieurs parties. Cette sécurité de l’échange se traduit par la vérification de l'intégrité et de l'authenticité des données.

Définit un moyen compact et autonome pour transmettre en toute sécurité des informations entre les parties en tant qu'objet JSON. Ces information peuvent être vérifiées et approuvées car elles sont signées numériquement. Les JWT peuvent êtres signés à l'aide d'un secret (algorithme HMAC) ou d'une paire de clés publique/privée utilisant RSA ou ECDSA.

Jeton signé : vérifie l'intégralité des revendication qu'ils contiennent, lorsque les jetons sont signés à l'aide de paires de clés publique/privée, la signature certifie également que seule la partie détenant la clé privée est celle qui l'a signée

jetons chiffrés : cachent ces revendication aux autres parties 


## Quand utiliser les jetons Web JSON ?

-  **Autorisation**: scénario le plus courant pour l'utilisation de JWT. Une fois l'utilisateur connecté, chaque demande ultérieure inclura le JWT, permettant à l'utilisateur d'accéder aux routes, services et ressources autorisés avec ce jeton. L'authentification unique et une fonctionnalité qui utilise largement JWT de nos jours, en raison de sa faible surcharge et de sa capacité à être facilement utilisée dans différents domaine.

- Echange d'information: Les jetons Web JSON sont un bon moyen de transmettre en toute sécurité des informations entre les parties. Étant donné que les jetons JWT peuvent être signés, par exemple à l'aide de paires de clés publique/privée, vous pouvez être sûr que les expéditeurs sont bien ceux qu'ils prétendent être. De plus, comme la signature est calculée à l'aide de l'en-tête et de la charge utile, vous pouvez également vérifier que le contenu n'a pas été falsifié.


## Quelle est la structure du jeton Web JSON ?

Dans sa forme compacte, les, jetons Web JSON se composent de trois parties séparées par des points (  `.`  ), qui sont :

	- Entête
	- Charge utile
	- Signature

Donc, un JWT ressemble généralement à ça:

           `xxxxx.yyyyy.zzzzz`

### **Entête** 

Elle se compose *généralement* de deux parties: le type de jeton, qui est JWT, et l'algorithme de signature utilisé tel que HMAC SHA256 ou RSA.

Par exemple:

````json
{
"alg": "HS256",
"typ": "JWT"
}

````

Puis, ce JSON est encodé en Base46Url pour former la première partie du JWT 


### **Charge utile**

La 2ième partie du jeton est la charge utile, qui contient les revendications. 
--> Les revendications sont des déclarations sur une entité (généralement l'utilisateur) et des données supplémentaire.
Il existe trois types de revendications: 
- enregistrées
- publiques 
- privées

#### Allégations enregistrées

Il s'agit d'un ensemble d'allégations prédéfinies qui ne sont pas obligatoires mais recommandées, afin de fournir un ensemble d'allégations utiles et interopérables.
Certain d'entre eux sont :
			- **iss** (émetteur),
			- **exp** (délai d'expiration),
			- **sub** (sujet),
			- **aud** (audience)

#### Revendication publiques

Celles-ci peuvent être définies à volonté par ceux qui utilisent les JWT. Mais pour éviter les collisions, ils doivent être définis dans le registre de jetons Web IANA JSON ou être définis comme un URL contenant un espace de nom résistant aux collisions.

#### Revendication privées

Il s'agit des revendications personnalisées créées pour partager des informations entre les parties qui acceptent de les utiliser et ne sont ni des *revendications enregistrées ni publiques*

Exemple de charge utile:

````json
{
"sub": "1234567890",
"name": "John Doe",
"admin": true
}
`````


La charge utile est ensuite encodée en **Base64Url** pour former la deuxième partie du jeton Web JSON.

=> Les jetons signés, les informations bien que protégées contre la falsification, sont lisibles par n'importe qui. Ne mettez pas d'informations secrètes dans les éléments de charge utile ou d'entête d'un jeton JWT à moins qu'ils ne soient chiffrés


### Signature

Pour créer la partie signature, vous devez prendre l'entête encodé, la charge utile encodée, un secret, l'algorithme spécifié dans l'entête et le signer.

Par exemple, si on utilise utilise l'algorithme HMAC SHA256, la signature sera créée de cette façon:

````
HMACSHA256(
	base64UrlEncode(header) + "." +
	base64UrlEncode(payload),
	secret)
`````

La signature est utilisée pour vérifier que le message n'a pas été modifié en cours de route et, dans le cas de jetons signé avec une clé privée, elle peut également vérifier que l'expéditeur du JWT est celui qu'il prétend être.





