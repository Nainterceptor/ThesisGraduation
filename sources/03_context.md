Analyse du contexte
===================

## Hungry Up, Le produit

Hungry Up est une application mobile native[^native], actuellement
disponible sur iOS et Android. Son objectif est de fluidifier l'expérience
en salle dans les restaurants par la digitalisation des actions de base.
Par exemple, il est plus aisé de demander à un serveur de venir nous voir 
via l'application que de l'interpeler. En procédant ainsi, on réduit la
frustration mais également les temps  d'attente au restaurant. Ce qui 
permet aux restaurants d'enregistrer un panier moyen plus important et 
un plus grand nombre de couverts lors des services importants. A minimat,
on permet aux personnes d'avoir une meilleure expérience du restaurant.

[^native]: 
On parle d'application native quand le langage de développement utilisé
est celui prévu pour la technologie. Par opposition aux applications hybrides
où la conception est faite sur une autre technologie puis convertie de manière
automatique. Il en résulte généralement une meilleure fluidité et un 
poids global plus léger.

Le marché de la foodtech[^foodtech] à Paris vise principalement à externaliser
la nourriture produite par les restaurants, notamment par le biais de la livraison.
L'actualité est propice à cette orientation, les restaurants enregistrent
une baisse de la fréquentation liée aux différents attentats. Pour qu'Hungry Up
puisse fonctionner, un second métier nous incombe : Rendre à nouveau attractif
les restaurants.

La première solution pour se regain d'attractivité est la reduction de la 
frustration, une seconde solution a été trouvée : le référencement des meilleurs
plats.

[^foodtech]: On parle de foodtech pour désigner les technologies associées 
à l'univers de l'alimentation.

Le restaurant partenaire doit afficher un tableau de bord Hungry Up afin
d'y voir toutes les demandes de l'application. Ce tableau de bord affiche la donnée
en temps réel.

Notre UX[^UX] reste un facteur différenciant de notre application et est
surtout le fruit d'une longue réflexion afin de trouver une solution à
la problématique majeure des chatbots : L'augmentation du nombre
d'intéractions pour arriver à une information. (Voir webographie,
"L’IA, ce nouveau Clippy ?") En effet, afin d'être compris par une IA,
il est nécessaire de formuler ses interaction, en toute lettre. Deux
grandes solutions s'offrent alors à nous si on ne souhaite pas sacrifier
l'expérience du chat : Permettre l'utilisation d'acronymes, ou du fameux
"langage SMS", ayant pour vocation la réduction du temps passé à formuler
un message, ou l'utilisation d'idéogrammes.

[^UX]: User eXperience ; Expérience utilisateur

Cette seconde possibilité se trouve très élégante. Influencée par l'idée
des langues asiatiques, où une idée correspond à un caractère, on se
retrouve avec un langage beaucoup plus logique et concis.
La matérialisation de cette idée peut se faire par la création de 
pictogrammes qui vont remplacer le clavier virtuel du téléphone. 

## Hungry Up, startup avant tout

Le financement du projet est classique pour une startup en
recherche de modèle économique, la société a fait une première levée de
fonds à sa création, aidée par l'expérience de son directeur dans
l'entreprenariat qui pu convaincre plus facilement des investisseurs en
présentant les chiffres de ses précédentes entreprises. Sur une telle
première levée de fonds, en réalité une levée de confiance, on mise avant 
tout sur l'équipe fondatrice que sur le projet. Les investisseurs savent
que le projet va changer, évoluer, et gagner en maturité. Il n'est donc
pas pertinent d'investir sur l'idée alors que celle ci par définition va
évoluer. On préfère donc investir sur une équipe.

Une série A[^ASerie] est prévue pour le début de l'année 2017. Pour
pouvoir réussir cette levée et assurer un avenir à la société, on se doit
d'avoir une croissance à montrer. Le produit évoluant, se trouvent deux
contraintes :

* Aller au plus vite dans l'évolution du produit, afin d'avoir un produit
qui colle aux besoins et qui se vende bien
* Economiser, afin d'avoir assez de fonds jusqu'à la levée de 2017.

Pour évoquer cette dualité, je vais parler d'efficience, et de perception
de la valeur.
En effet, on ne va pas nécessairement chercher à avoir le prix le plus
bas pour une chose donnée, mais on va chercher à avoir un ROI[^ROI] 
important, mais également à récupérer toujours le meilleur et le plus 
pour un budget donné.

[^ASerie]: processus de levée de fonds suivant le capital amorçage, où
on propose d'investir sur l'avenir de la société en échange d'actions.
[^ROI]: Return on investment ; Retour sur investissement.

## L'historique du projet : Une conception par des prestataires

Le prototypage et la première orientation a été faite avant mon
intégration au projet. J'ai donc récupéré sur le tas tous ces actifs et
contrats en cours. J'ai donc rapidement dressé un état des lieux. Un
premier prestataire, AppSolute, a créé la première version de 
l'application, que je nomme version 0. Ce prototype bien que simple a
eu pour objectif de tester le marché. La partie serveur, responsable
de la rétention des données, mais également de la mise à disposition de 
l'application web utilisable par les restaurants, a été faite par une
autre société Lyonnaise nommée Asolution. Le développement de la version 1, 
la version actuelle de l'application, avait été confié à une troisième
société du nom de Soluti.

Je n'ai presque pas eu à faire à AppSolute, juste quelques échanges de 
mail afin de récupérer le code source, et effectuer le transfert de 
paternité des applications sur l'App Store[^appstore] et le Play Store[^playstore]. 
Je n'ai pas grand chose à dire sur ce projet que j'ai récupéré et à peine
survolé. Le seul point négatif relevé est la nomenclature utilisée pour
l'identifiant technique des applications. Il faut s'avoir que coté Apple
et Google, ces identifiants servent à lier les utilisateurs ayant
téléchargés l'application à l'application elle même. Ces identifiants
contenaient le nom du prestataire, ce qui ne se fait généralement pas
pour ce type de prestation. J'ai du créer de nouvelles applications pour
la version 1 du projet, ce qui a impliqué la perte de l'historique des
utilisateurs sur l'application. Ce ne fut finalement pas important car
ce nombre d'utilisateurs était très restreint. Je pense que ce choix de
renommage était peut important du fait que le projet en était qu'à ses 
balbutiements, le renommer plus tard aurait été problématique.

[^appstore]: L'App Store est la place de marché des applications
installables sur le système iOS d'Apple.
[^playstore]: Le Play Store est la place de marché des applications
installables sur le système Android de Google.

Autre point important de cette décision, la consultation des données de
création de compte sur la partie serveur. Il a été constaté que la
majeure partie de ces comptes créés pour pouvoir utiliser l'application
étaient en réalité des comptes de test, mais il n'y avait pas beaucoup
de comptes légitimes. Leurs adresses mail ont été récupérées dans
l'objectif de prévenir les dits utilisateurs du besoin de télécharger la
nouvelle application. Il est par ailleur intéressant de constater que
cette étape de création de compte étant obligatoire se trouvait
bloquante pour la plupart des utilisateurs pour qui ce n'est pas le
moment opportun de créer un compte alors qu'on est présent à table. 
Cette étape a été supprimée de la version 1.

A mon arrivée, j'ai rapidement constaté un problème de productivité et 
de communication entre les deux agences restantes. L'une avait un temps
limité par semaine pour la production des points d'API[^endpoints]
utilisés par l'application, ce qui limitait la productivité de la
seconde agence. J'ai donc demandé l'accès à cette plateforme afin de 
travailler par moi même sur le projet et tenter d'améliorer la rapidité
de production de l'application.

[^endpoints]: On parle de points d'API (pour Application Programming
Interface : Interface de programmation) pour désigner l'adresse
(comprendre adresse web) sur laquelle se connecte un programme pour
communiquer.

Un premier problème de formation a été rencontré, je n'avais aucune idée
du fonctionnement et la hierarchisation de leur programme, développé en
PHP[^PHP], aucun framework[^framework] opensource n'avait été utilisé.
Tout le développement était issu d'un développement spécifique.
Malheureusement, cette partie, coeur de leur innovation, était
inaccessible. Ce qui masquait en grande partie le fonctionnement. La 
possibilité qui s'offrait à moi était de procéder par mimétisme pour les
fonctionnalités similaires pour les modifications, et par ingénerie 
inverse[^retroengineering] pour les fonctionnalités innovantes.

[^PHP]: Le PHP est un langage web très populaire représentant plus de 82%
des programmes créés coté serveur (voir Webographie, PHP - Wikipedia).
[^framework]: Ensemble de standards, librairies, et bonnes pratiques
aidant à la conception logicielle.
[^retroengineering]: Il s'agit de l'étude de l'existant afin d'en
deviner, d'en étudier, le fonctionnement interne.

Après un certain temps passé à comprendre le système, je me suis rendu 
compte qu'il était très éloigné de l'état de l'art[^stateofart]. J'ai
donc pris la liberté de réaliser une analyse, une sorte d'audit, du code
en question. La raison étant simple : cette partie est la partie critique
de notre produit, il doit être le plus sain possible. 

[^stateofart]: On parle de l'état de l'art pour désigner le niveau
technologique communément rependu à l'heure actuelle.

Ma première surprise fut sur la segmentation des données. En effet,
toutes les données de leurs différents clients étaient stockées sur un
même environnement, mais surtout avec des identifiants donnant accès à
toutes les données de la plateforme. Ce qui rendait très vulnérable la 
valeur principale de l'entreprise : Ses données. De plus, certains mots
de passe étaient renseignées en clair[^clear]. Certains autres étaient
négligemment cryptés[^cryptage]. En réalité, ces derniers étaient 
sensibles à de comparaisons avec des tables de référence. Cette méthode
est maintenant commune et admise. Des solutions techniques existent,
par l'utilisation de "grains de sel"[^salt] par exemple. Un test a été
fait sur une dizaine de mots de passe pour valider ce constat, plus de 
la moitié d'entre eux ont été trouvés.

[^clear]: Sans aucune forme d'obfuscation de la donnée. Elle se trouve
consultable sans aucun filtre.
[^cryptage]: Mot contreversé en Français, il est utilisé pour désigner,
en opposition au décryptage, une méthode de chiffrement sans clef,
ayant pour but de fournir une signature correspondant à un contenu,
sans possibilité d'en faire l'opération inverse.
[^salt]: L'idée est d'ajouter une texte aléatoire avant cryptage afin
de générer de l'entropie : Un même contenu peut voir plusieurs résultats
si le grain de sel n'est pas identique.

Le second problème concernait la qualité du projet. La dette technique 
contractée par la prestation était très importante. Il est commun sur le
langage utilisé d'utiliser les norme dites PSR[^PSR], ces normes sont 
votées au sein d'un groupe regroupant les principaux acteurs du secteur,
dans un but de favoriser l'interopérabilité du code. Parmi ces
signataires, on trouve par exemple Drupal, Symfony (Sensiolabs), Joomla,
Magento, Prestashop... Ne pas utiliser ces normes entrave la
compréhension du code, mais n'est pas fatal pour un projet, à condition
d'avoir une cohérence sur ses règles de propreté du code. Ce n'était pas
le cas ici, deux scripts ne semblant pas régis par les mêmes règles.
De plus, le coeur de l'application n'était pas accessible, rendant tout
audit impossible. Il est important pour un projet de ce niveau d'avoir
accès à la totalité du fonctionnement de l'application. J'ai évalué le
risque de portes dérobées ou tout simplement de faille dans ce code
masqué comme étant important, notamment de par la présence de failles
dans le code visible. Enfin, toujours dans cette lignée des non respect
de normes, la RFC 2616 (Voir webographie), norme qui décrit les échanges
web entre un serveur et un client via le protocole HTTP [^HTTP] n'était 
pas non plus respectée. Il était de fait très compliqué pour Soluti, le
prestataire en charge de la partie mobile, de connecter les interactions
mobiles avec le traitement sur le serveur.

[^PSR]: PHP Standards Recommendation (Voir webographie)
[^HTTP]: Il s'agit d'un protocole d'échange de données très répandu sur
Internet, c'est avec ce protocole que l'on accède à l'immense majorité
des pages web.
[^backdoor]: On parle de porte dérobée (backdoor) pour mentionner un
 accès caché et non documenté.

Je n'ai pas considéré les pertes en terme de performances lors de mon
analyse, considérant que la rapidité de prototypage et l'importance de
débloquer le travail de Soluti était plus important.

La dernière problématique soulevée était la présence de vulnérabilitées
techniques et de manque de stabilité. Le projet comportait beaucoup de 
failles communes, permettant entre autre d'exposer toute les données
client. De plus, les échanges avec cette API n'était pas chiffrés, 
exposant tous les échanges sur le réseau. Dans ma démarche de qualité et
de respect des utilisateurs, j'ai considéré ces problématiques comme
étant bloquantes. Ma première réaction fut de les quantifier pour les
corriger. Malheureusement, leur présence était trop importante, et je ne
pouvais quantifier ce que je ne voyais pas. J'ai donc pris la décision
de contacter le directeur de cette agence afin de lui faire part de mes 
constats. Mon manque de diplomatie, et ma franchise, ont eu l'effet de
braquer le prestataire qui nous demanda le règlement de la prestation,
en refusant de continuer le travail. Nous étions le 25 avril 2016,
la sortie prévue de l'application devait se dérouler le 2 mai.
