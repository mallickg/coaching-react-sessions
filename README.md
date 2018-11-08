# Jeudi 08/11/2018

## Sujets abordés

- Presentation de l'équipe
- Presentation du contexte technique (technos, monolythique, skills developpeur)
- Discussion autour des besoins de coaching autour de REACT

Il a été décidé de commencer par une journée de coaching le jeudi 15 novembre et ensuite faire appel au coach
1 fois par semaine jusque début Decembre. (3 sessions de coaching).

### Approche migration technologique BLSNet

#### Encapsulation composants AngularJS dans REACT et inversement.

Il est impossible techniquement d'inclure un composant AngularJS dans une application REACT.
Par contre il est peut etre possible d'encapsuler un composant AngularJS dans un Web Component.  

#### Utilisation des Web Components

Pourquoi ne pas essayer les Web Components ?

#### Les composants AngularJS sont-ils Web Compliant ?

A tester si on veut pouvoir encapsuler un composant AngularJS dans un autre composant React par exemple.

### Description du socle technique REACT mis en place

#### Emmergence de questions sur l'utilité d'utiliser Redux et les middlewares.

A partir de quel moment utiliser redux ?
Réponse : Aprés avoir atteint les limites du contexte de React (React Context API).
En utilisant Redux, on arrive rapidement a vouloir utiliser des middlewares sans vraiment en avoir une vrai utilité.

#### Idem pour le composant de routing

A partir de quand doit-on utiliser un router ?
Réponse : Si on a besoin de navigation au sein même de React.

#### Doit-on succomber à l'utilisation de librairie tierce sans se poser la question de son utilité ?

Réponse: Il est préférable d'utiliser React est de s'apercevoir par soi-meme de la necessité d'utiliser une librairie tierce.

#### Doit on remplacer redux par le React Context API ?

Réponse : Oui car plus simple à utiliser dans une application de petite taille et inclus dans React.

#### Comment gérer les appels async en cascade ?

Il est possible d'imbriquer des appels http async avec les promises.
Sinon pour plus de lisibilité, il est possible d'utiliser l'operateur javascript "await".
<https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Op%C3%A9rateurs/await>

#### Comment gérer la combinaison d'appel async ?

Avec la méthode Promise.all() qui renvoi une promesse(Promise) qui est résolue lorsque l'ensemble des promesses passées en argument sont terminées ou une promesse qui echoue.

#### Comment insérer un intercepteur ?
Pour ajouter un jeton d'autentification dans un header http par example, il est nécessaire
de dire au provider http (axios par ex) quel intercepteur utiliser ?
Il faut utiliser la fonction axios.useInterceptor(Interceptor) dans la méthode 
"ComponentWillMount".

#### Quelles sont les questions à se poser pour designer son application, pour créer son arbre de composants :

Avec un pattern trés populaires quand on écrit une application React.

Smart / Dumb components :

<https://medium.com/@thejasonfile/dumb-components-and-smart-components-e7b33a698d43>

<https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0>

<https://blog.angular-university.io/angular-2-smart-components-vs-presentation-components-whats-the-difference-when-to-use-each-and-why/>

#### Quelle est la bonne approche pour le testing ?

Avant toute chose, il est necessaire de se demander quels sont les tests qui produiront de la valeur pour l'équipe.
Les tests du DOM sont a éviter car ils sont couteux à écrire et à maintenir.
Il faut priviligier les tests de la logique applicative bien plus facile à ecrire avec des librairies
comme Jest. De plus elle permet de convrir une maximum de code.
Il faudrait peut être aussi étudier cypress pour les tests d'intégration.

#### Methodes du cycle de vie des composants : doit-on encore utiliser les methodes depracated ?

L'utilisation des methodes du cycle de vie deprecated doivent être nettoyer de facon progressive et ne pas être utilisé.

#### Rendering conditionnelle : A privilégier par rapport a une approche multipage.

Si l'affichage d'une liste de composant doit être affiché sur base d'un context, il est preferable de réaliser
un rendering conditionnel (avec le ternaire ou des if en javascvript dans la méthode render).

#### Comment afficher une page en tenant compte d'un context ? (ex : retail, CIB, private banking...) ?

Construire une liste de composants avec les informations utiles pour faire du "flex rendering".
Si la page doit être customisable, il est necessaire d'y ajouter du code pouvant gérer le contenu de la liste.

#### Client caching : le state d'un composant ne remplace pas le caching client

Si l'on veut mettre en cache des informations du type libellés par exemple, il faut le faire en javascript en manipulant le local ou le session storage au retour de la collecte des informations après un appel async.

#### Tooling debbugage : React dev tools - extension chrome
Voir si on arrive à télécharger l'extension Chrome en local.

#### Personne influente dans la communité
 
Twitter : Suivre les personnes influentes sur React.

js.coach : Site mettant a dispositon une liste de composants, boilerplates, generators... pour React, React Native, Webpack, PostCss.

formidable.com  : Societe d'engineering spécialisé dans React, React Native, node.js et tout l'écosystème javascript.   








