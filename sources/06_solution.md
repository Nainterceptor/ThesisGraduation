
Les solutions qui ont été trouvées
==================================

## Réduction du nombre d'acteurs impliqués

Lors de la conception d'une nouvelle fonctionnalité, de nombreux acteurs
sont impliqués. Après identification du besoin par l'équipe commerciale, 
un micro cahier des charges est créé, des maquettes sont ensuite créées 
par notre designer. Ensuite l'équipe technique entre en jeu, il faut 
modéliser la fonctionnalité, puis concevoir son programme coté serveur
(Il s'agit de la partie métier de la fonctionnalité, le serveur s'occupe
de gérer toute la logique métier, les contrôles, les droits, etc...). 
L'équipe backend[^backend] doit concevoir cette partie mais également la
documentation qui va servir de contrat d'API : Qu'est ce qui doit être
envoyé au serveur comme donnée.
Une fois tout cela fait, les équipes mobiles peuvent travailler en
parallèle pour concevoir l'interface sur les différents systèmes
supportés (iOS et Android). 
La conception du backoffice[^backoffice] peut également démarrer. Pour
rappel nous en avons deux : Le premier pour notre usage interne, le
second pour la gestion par les restaurateurs.

[^backend]: Il s'agit de la partie non visible, par opposition au
frontend, le backend est le programme serveur. Backend/frontend est à ne
pas confondre avec backoffice/frontoffice.
[^backoffice]: Le backoffice désigne l'interface de gestion du produit,
accessible par l'organisation, par opposition au frontoffice.

Pour rappel, notre expérience utilisateur tourne autour d'un chat, lieu
d'échange entre les clients d'une table (qui font des demandes), le
serveur (qui y répond), et Hungry Up (qui dispense des conseils, envoie
des informations contextuelles...). La première force de ce chat réside
dans son expérience. Ce chat est historiquement exploité comme un
artifice visuel, les requêtes transitant entre le serveur et
l'application représentent une demande, et les messages sont générés sur
l'application. Cette méthode permet de changer l'apparence ultérieurement
mais ne permet pas d'exploiter les avantages énormes d'un chat. En effet,
dans cette recherche d'amélioration de productivité, j'ai défini une
nouvelle version, qualifiée de refonte technique, de l'application : la
version 1.2.

Dans cette version, on augmente notre prise de risque sur l'interface
chat, en calquant l'échange entre l'application et le serveur comme un
service de messagerie classique... A quelques différences près.
En effet, dans notre système, l'échange va se passer de la manière suivante :

L'utilisateur va ouvrir l'application, se connecter à sa table. A partir
de là, la liste des actions possibles va être chargée sur son téléphone,
et alimenter la barre d'action en bas de l'application. L'avantage de
cette récupération dynamique de cette barre d'action est la
personnalisation suivant les besoins de l'utilisateur, et les
configurations du restaurant. On peu ainsi imaginer une configuration
différente suivant le restaurant : gastronomique, bistronomique, bar,
fast casual[^fast-casual]...

[^fast-casual]: Anglicisme désignant les restaurants sans service à
table, à mi chemin entre le fast food et l'expérience traditionnelle
d'un restaurant.

Une action correspond à une demande de l'utilisateur, celle ci embarque
un nombre de prérequis pour être lancée, ces derniers peuvent être soit 
transparent pour l'utilisateur (demande de ses coordonnées GPS), soit 
interactif (demande d'entrer un nom). 

Le déclenchement d'une action permet au service de signaler la demande 
au serveur, et de générer deux messages : Le premier correspondant à 
celui envoyé par l'utilisateur, le second étant la réponse à 
l'utilisateur. Pour faire patienter l'utilisateur lors de la génération 
de son propre message, on exploite un pictogramme pour générer sa bulle 
de message temporaire, ce dernier représente l'action demandée, et sera 
remplacé par son message texte dès qu'il aura été reçu par 
l'application, cette génération est quasi instantanée, mais 
les aléas réseau nous forcent à prévoir ce délais.

Chaque message en retour peut être accompagné d'une liste d'actions
possibles, des choix supplémentaires servant à répondre dans le cas où
une demande de complément d'informations est nécessaire (par exemple, le
client demande un burger, on va lui demander la cuisson de sa viande).

Ainsi, on identifie deux types d'échanges : Les messages, et les
actions. La flexibilité et l'astuce se trouve sur le fait que tout est
généré coté serveur, seule les prérequis d'actions doivent être
implémentés coté application. On passe ainsi d'un modèle complexe de
développement où pour chaque évolution, les développeurs de l'application
sont mobilisés à une modèle plus léger où la majorité des évolutions
peuvent être effectuées sur la backend de l'application, et où seulement
les interfaces spécifiques et la gestion de nouveaux types de prérequis
(par exemple l'implémentation d'une fonctionnalité d'une application
tierce) doivent mobiliser ces équipes de développement mobile. Comme ce 
coùt est généralement en fonction des plateformes supportées, cela
réduit également la probabilité de bugs sur une plateforme, le nombre de
tests à effectuer à chaque nouveau développement, etc...


## Automatisation

Depuis mon intégration au projet, j'essaye d'incorporer ma vision d'un
projet technologique. Cela passe par un principe simple : Si on doit 
faire une chose plus d'une fois, alors c'est qu'elle doit être 
automatisable et automatisée. Ainsi, à date, une grand nombre de choses, 
que ce soit des outils de développement ou des processus rébarbatifs 
sont dors et déjà automatisés. Les avantages sont un gain de temps sur 
le moyen et long terme et une réduction du risque d'erreurs. Le 
principal avantage est justement la perte de temps sur le court terme 
car la rentabilité de cette automatisation nécessite qu'elle soit 
utilisée de nombreuses fois. En ce sens, il y a un certain nombre 
d'automatisations qui ont été mises en place avec ou sans succès.

La première mécanique concernait la génération des chevalets. 
Historiquement, un code permettait de se connecter à la table sur
laquelle on était assis. On devait alors imprimer des supports que l'on 
appelait maladroitement chevalets (Il s'agit en réalité souvent 
d'auto-collants, ou de petits supports en forex[^forex]). Ainsi, notre 
designer passait du temps sur la création de chacun de ces chevalets, 
devant être personnalisés avec le numéro du restaurant puis avec le 
numéro de chacune des tables. En vue de ce temps passé, j'ai mis en 
place un outil permettant de générer ces chevalets à partir des 
configurations entrées au préalable sur notre backoffice. Ce PDF généré 
pouvait être alors envoyé en l'état à l'imprimeur. Il se trouve que ce
choix bien que faisant gagner du temps de manière quasi immédiate, n'a 
jamais été rentabilisé, nous sommes revenus sur cette décision de 
personnaliser les chevalets à ce point.

[^forex]: Le PVC expansé, plus communément appelé Forex® est un matériau 
léger et rigide, souvent utilisé pour la signalétique.

Une seconde automatisation concernait l'encodage des images pour notre
aperçu des plats, il était plus simple et rapide de ne pas mettre en 
place à date une mécanique de redimentionnement à la volée des images de
ces plats. Il fallait alors demander à ce que chaque image mise en ligne 
sur la plateforme soit correctement dimensionnée. L'équipe commerciale 
qui s'occupe de cette charge de travail étant sur Mac OS, il était aisé 
de fournir un script permettant d'automatiser le redimentionnement et la 
conversion de ces images. (Il était important pour moi que les images 
soient en encodage dit progressif, c'est à dire que l'image se charge 
non pas ligne par ligne, mais "couche" par "couche", ce qui en résulte 
une image floue qui devient de plus en plus nette pendant son 
téléchargement. Ce type d'expérience sur les réseaux mobiles est 
importante, car moins frustrante.) Il s'agit là d'une automatisation de
moyen terme, servant à palier de manière rapide à un besoin, mais la
solution long terme sera de mettre en place ce système de traitement à 
la volée. 

Les actions possibles dans le chat sont caractérisées par un pictogramme,
notre graphiste aurait du faire appel à l'équipe technique pour chaque
nouveau pictogramme produit, il fallait une astuce afin de pouvoir 
mettre à jour de manière dynamique ces pictogrammes. Les contraintes 
sont simples, que ce soit sur iOS ou Android, la manière la plus rapide 
de charger une image c'est de l'avoir en plusieurs exemplaires (suivant 
la taille de l'image), et embarquée dans l'application. Certains 
formats, dit vectoriels, permettent de ne pas avoir une image mais une 
forme, ce qui permet d'avoir qu'une seule image pour tous les formats.
Le support de ce type de format est limité par les compilateurs, qui en 
réalité génèrent à la compilation les fichiers aux différents formats. 
Charger une image depuis le réseau aurait pu être une solution, mais ce 
type de chargement est lent, et risque de produire une mauvaise 
expérience utilisateur. Après recherches, j'ai pu confirmer que de par 
mon expérience du web, la solution commune pour les sites internet 
pouvait être applicable à notre application. L'astuce est simple : On 
créé une typographie avec ces pictogrammes. 

Basiquemment, une typographie c'est une suite de formes associées à des
codes représentant un caractère. Dans cette table de caractères 
possibles, il n'y a pas que les lettres latines, mais bien plus, ce qui 
nous laisse une large possibilité de pictogrammes sans pour autant 
augmenter le poid du transfert. On va alors donner un numéro de version 
à une typographie. A la connexion à la table, en même temps que la liste
des actions, on va donner la version minimale de la typographie à avoir, 
si la version minimale est supérieure à la version actuellement sur 
l'application, il suffit de récupérer la dernière version. Ainsi, notre 
graphiste peut créer en autonomie une nouvelle version de la 
typographie. Au niveau de la sélection des pictogrammes dans le 
backoffice, on exploite les informations de cette même typographie afin 
de proposer le choix du pictogramme.

Enfin, la prise des captures d'écran de l'application était un point 
essentiel à automatiser. Lors de la publication d'une application, sur 
chaque plateforme de téléchargement (App store, Google Play store), il 
faut renseigner un certain nombre de captures d'écran, généralement un 
minimum de trois. Afin que l'application soit validée, ces captures 
d'écran doivent être fidèles à l'application, ce qui nécessite de les 
mettre à jour régulièrement (à chaque nouvelle version). De plus, pour 
être attractif, il est recommande de faire d'autres petites choses : 
Mettre la capture d'écran dans un contexte (dans un faux iphone pour 
iOS par exemple), d'avoir une barre de status propre (Avec une heure 
fixe, ma batterie à 100%, etc...), et enfin d'ajouter une fond et un 
texte court de présentation. Il faut évidemment que tout ça soit fait 
pour chaque langue dans laquelle l'application est disponible. Ce 
travail peut vite devenir chronophage, en effet pour un support de 5 
langues, avec 5 captures d'écran, il faudrait faire 25 captures d'écran,
puis les traiter une par une, et ce à chaque version. Tout ce système a 
été automatisé, ce qui permet un gain de temps considérable. C'est 
l'automatisation avec le plus court retour sur investissement, il a été 
rentabilisé presque immédiatement. Comme pour les autres automatisations,
il réduit également le risque d'erreurs, mais dans ce cas précis, il
supprimer la frustration de cette tâche.

## Processus de conception

Un axe bien connu de la conception logicielle, est la mise en place d'un environnement d'intégration ou de déploiement continu. 

## Réduction de l'interruption