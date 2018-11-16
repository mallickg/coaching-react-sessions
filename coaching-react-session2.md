#Jeudi 15 novembre 2018

## Nettoyage du code

- Isolation des fonctions permettant d'interagir avec le backend. Initialement dans App.js nous les avons déplacé dans http.js. Ceci afin de ne garder que l'affichage dans le composant a des fins de réutilisation.
- l'export default est inutile pour exporter une classe. Il faut eviter de mettre le mot cle default car toutes les classes ayant ce mot clé seront incluses dans le bundle.js même celle qui ne seront pas utilisé. L'objectif est de minimiser un maximum la taille du bundle.
- Ne passer que ce qui est necessaire à l'affichage du composant dans les props.
- Faire une fonction pour definir un composant et eviter de faire une classe.
- Utiliser les defaults proptypes seulement dans le cas la prop doit avoir une valeur par default comme un boolean par example.
- Suppression du this.state dans le constructeur du composant. Inutile si le state n'est pas lié aux props. Mettre plutot la declaration du state a l'exterieur du constructeur et supprimer le constructeur.
- Utiliser des constantes plutot qu'une chaine de caractères en dure dans le code.
- Utiliser un fichier de constantes, plutot que de déclarer des constantes dans les composants.
- Utiliser objects pour definir des pseudo-enum si besoin.
- Privilégier les classnames pour faire du style dynamique.
- La methode render de REACT attends systematiquement 1 et un seul noeud. Il est donc necessaire d'englober vos noeuds dans une balise Fragment plutot qu'un div qui alourderait alors le DOM.
- Principe du DataDriven : en fonction des données recu, on doit se poser la question, quel et le composant a afficher ou comment l'afficher. Ex un object ou attribut null ou une erreur venant du backend. On ne doit pas inserer des if null dans le code.
- dans le cas de composant trop gros, il peut etre necesaire de positionner le hot au niveau de l'export du composant.
- Context React API: example d'utilisation -> Récupération des droits d'accès et vérification des droits d'affichage des composants.
- Mock dans le cadre des tests unitaires : utiliser JEST et la fonction fn (voir doc Jest).

## Problèmes soulevés

- Pouvoir filtrer les résultats retournés par le backend. Notemment la problématique du retour d'un acteur. En fonction de l'application, nous voulons récupérer seulement une partie du résultat.

GraphQL -> Permettrait de filtrer les données du Backend en fonction des besoins du Front. Ceci est a implementer dans le back et le front.

- Il est possible d'atteindre les limites de la conf CRA. ex: utilisation du decorator @WithRoute pour récupérer le parametre passé dans une url depuis n'importe ou dans le code en décorant la classe du composant.

Il est possible de customizer la config de CRA(Create-React-App) avec customize-cra.

- Pouvoir partager des composants REACT entres les équipes à travers une librairies de composants.

Il est possible de creer une bibliotheque de librairies BIL grace a une librairies javascript du nom de storybook.js

- Mettre en place des linter

eslint-airbnb : trés strict, il est possible d'alléger les regles.

## Prochain TOPICs

- Allons plus loin avec le context React
- Parcourons une base de code mettant en evidence les limites de redux (problèmes de performances).
- les HOC (High order components)
- Testing


