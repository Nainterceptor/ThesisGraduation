
Les solutions qui ont été trouvées
==================================

L'amélioration de l'efficience d'Hungry Up passe par un ensemble d'améliorations, regroupées ici en trois sous-ensembles correspondant à leurs domaines : les solutions techniques, organisationnelles et de ressources humaines. Chacune de ces solutions participe à l'amélioration de la productivité, à différentes échelles. Dans une recherche de gain de temps et de productivité, il est difficile de trouver uniquement des points permettant de gagner beaucoup de temps, il s'agit principalement de petits changements, qui, ensemble, permettent une économie.

## Solutions techniques

### Automatisations

Depuis mon intégration au projet, j'essaye d'apporter ma vision d'un
projet technologique. Cela passe par un principe simple : si on doit 
faire une chose plus d'une fois, alors c'est qu'elle doit être 
automatisable et automatisée. Ainsi, à date, un grand nombre de choses, 
que ce soit des outils de développement ou des processus rébarbatifs 
sont d’ores-et-déjà automatisés. Les avantages sont un gain de temps sur 
le moyen et long terme et une réduction du risque d'erreurs. Le 
principal avantage est justement la perte de temps sur le court terme, 
car la rentabilité de cette automatisation nécessite qu'elle soit 
utilisée de nombreuses fois. En ce sens, il y a un certain nombre 
d'automatisations qui ont été mises en place avec ou sans succès.

#### Génération automatique des chevalets

La première mécanique concernait la génération des chevalets. 
Historiquement, un code permettait de se connecter à la table sur
laquelle on était assis. On devait alors imprimer des supports que l'on 
appelait maladroitement chevalets (il s'agit en réalité souvent 
d'auto-collants, ou de petits supports en forex[^forex]). Ainsi, notre 
designer passait du temps sur la création de chacun de ces chevalets, 
devant être personnalisé avec le numéro du restaurant puis avec le 
numéro de chacune des tables. En vue de ce temps passé, j'ai mis en 
place un outil permettant de générer ces chevalets à partir des 
configurations entrées au préalable sur notre backoffice. Ce PDF généré 
pouvait être alors envoyé en l'état à l'imprimeur. Il se trouve que ce
choix bien que faisant gagner du temps de manière quasi immédiate, n'a 
jamais été rentabilisé, nous sommes revenus sur cette décision de 
personnaliser les chevalets.

[^forex]: Le PVC expansé, plus communément appelé Forex® est un matériau 
léger et rigide, souvent utilisé pour la signalétique.

#### Encodage des visuels

Une seconde automatisation concernait l'encodage des images pour notre
aperçu des plats, il était plus simple et plus rapide de ne pas mettre en 
place à date une mécanique de redimensionnement à la volée des images de
ces plats. Il fallait alors demander à ce que chaque image mise en ligne 
sur la plateforme soit correctement dimensionnée. L'équipe commerciale 
qui s'occupe de cette charge de travail étant sur Mac OS, il était aisé 
de fournir un script permettant d'automatiser le redimensionnement et la 
conversion de ces images. (Il était important pour moi que les images 
soient en encodage dit progressif, c'est-à-dire que l'image se charge 
non pas ligne par ligne, mais "couche" par "couche", ce qui en résulte 
une image floue qui devient de plus en plus nette pendant son 
téléchargement. Ce type d'expérience sur les réseaux mobiles est 
importante, car moins frustrante.) Il s'agit là d'une automatisation de
moyen terme, servant à pallier de manière rapide à un besoin, mais la
solution à long terme sera de mettre en place ce système de traitement à 
la volée. 

#### Gestion des pictogrammes

Les actions possibles dans le chat sont caractérisées par un pictogramme,
notre graphiste aurait dû faire appel à l'équipe technique pour chaque
nouveau pictogramme produit, il fallait une astuce afin de pouvoir 
mettre à jour de manière dynamique ces pictogrammes. Les contraintes 
sont simples, que ce soit sur iOS ou Android, la manière la plus rapide 
de charger une image c'est de l'avoir en plusieurs exemplaires (suivant 
la taille de l'image), et embarquées dans l'application. Certains 
formats, dits vectoriels, permettent de ne pas avoir une image, mais une 
forme, ce qui permet d'avoir qu'une seule image pour tous les formats.
Le support de ce type de format est limité par les compilateurs, qui en 
réalité génèrent à la compilation les fichiers aux différents formats. 
Charger une image depuis le réseau aurait pu être une solution, mais ce 
type de chargement est lent, et risque de produire une mauvaise 
expérience utilisateur. Après recherches, j'ai pu confirmer que de par 
mon expérience du web, la solution commune pour les sites internet 
pouvait être utilisée pour notre application. L'astuce est simple : on 
crée une typographie avec ces pictogrammes. 

À la base, une typographie est une suite de formes associées à des
codes représentant un caractère. Dans cette table de caractères 
possibles, il n'y a pas que les lettres latines, mais bien plus, ce qui 
nous laisse une large possibilité de pictogrammes sans pour autant 
augmenter le poids du transfert. On va alors donner un numéro de version 
à une typographie. Lors de la connexion à la table, en même temps que la liste
des actions, on va donner la version minimale de la typographie à avoir, 
si la version minimale est supérieure à la version actuellement sur 
l'application, il suffit de récupérer la dernière version. Ainsi, notre 
graphiste peut créer en autonomie une nouvelle version de la 
typographie. Au niveau de la sélection des pictogrammes dans le 
backoffice, on exploite les informations de cette même typographie afin 
de proposer le choix du pictogramme.

#### Automatisation des captures d'écran

Enfin, la prise des captures d'écran de l'application était un point 
essentiel à automatiser. Lors de la publication d'une application, sur 
chaque plateforme de téléchargement (App store, Google Play store), il 
faut renseigner un certain nombre de captures d'écran, généralement un 
minimum de trois. Afin que l'application soit validée, ces captures 
d'écran doivent être fidèles à l'application, ce qui nécessite de les 
mettre à jour régulièrement (à chaque nouvelle version). De plus, pour 
être attractif, il est recommandé de créer un environnement : 
Mettre la capture d'écran dans un contexte (dans un faux iPhone pour 
iOS par exemple), d'avoir une barre de statuts propre (avec une heure 
fixe, ma batterie à 100%, etc...), et enfin d'ajouter un fond et un 
texte court de présentation. Il faut évidemment que tout cela soit fait 
dans chaque langue pour laquelle l'application est disponible. Ce 
travail peut vite devenir chronophage, en effet pour un support de 5 
langues, avec 5 captures d'écran, il faudrait faire 25 captures d'écran,
puis les traiter une par une, et ce à chaque version. Tout ce système a 
été automatisé, ce qui permet un gain de temps considérable. C'est 
l'automatisation avec le plus court retour sur investissement, il a été 
rentabilisé presque immédiatement. Comme pour les autres automatisations,
il réduit également le risque d'erreurs, mais dans ce cas précis, il
supprime la frustration de cette tâche répétitive.

#### Automatisation des processus de déploiement

Notre solution repose sur des serveurs hébergés chez AWS[^AWS],
un fournisseur de ressources dynamiques dites de "Cloud computing". Son 
offre repose sur deux briques de base : EC2, son offre de calcul, il 
s'agit des serveurs visant à générer la puissance de calcul et S3, son 
offre de stockage. AWS est également constitué d'un panel de services 
exploitant ces deux briques, qui vont faciliter la mise en place de 
serveurs, en abstraire la gestion, etc... L'intérêt majeur de ces 
services pour le client est leur simplicité d'utilisation. L'intérêt 
primordial pour Amazon est de rendre les clients dépendants de ces services. 
Il y a ainsi un juste milieu à arbitrer afin de perdre le moins de temps,
mais de rester le moins dépendant.

[^AWS]: Amazon Web Services.

Premier outil utilisé : Elastic beanstalk. Ce service AWS permet de
définir des scripts de configuration qui vont décrire l'environnement 
dans lequel le projet doit s'exécuter. La force du service est d'avoir 
un outil en lignes de commande qui permet au développeur de mettre à jour 
sa plateforme et de la configurer dans avoir à naviguer sur le site 
d'AWS. C'est un réel gain de temps. De plus, il est simple d'exploiter 
cet outil pour créer des routines et automatismes. J'ai choisi ce 
service principalement, car je le connaissais déjà, ce qui m'a permis de 
monter une infrastructure scalable[^scalable] et sur mesure très 
rapidement. Une fois que nous aurons plus de ressources, il s'agira ici 
d'un point d'investissement important afin de stopper notre dépendance à 
ce service, et pouvoir faire jouer la concurrence en terme de Cloud 
computing.

[^scalable]: Anglicisme, qualifie un produit pouvant monter en charge 
simplement et sans intervention humaine. Ici, cela signifie que 
l'application pourra passer de 10 à 1 000 000 d'utilisateurs quotidiens 
sans en souffrir outre mesure.

Ensuite, notre base de données documentaire, MongoDB, a été choisie en 
premier lieu pour sa simplicité de configuration, de déploiement, et sa 
réputation de scalabilité. Elle est déployée directement dans EC2, mais 
cette fois à l'aide d'un outil payant de MongoDB. L'avantage de cet 
outil est qu'il sert d'abstraction entre le déploiement et le 
fournisseur de Cloud, il est ainsi simple de passer d'un fournisseur de 
Cloud à un autre. Un deuxième avantage est d'avoir de fait un contact 
commercial chez MongoDB, en effet il est important d'exister auprès d'un 
éditeur pour négocier un partenariat plus facilement. MongoDB propose du 
support, de la formation, et une quantité d'autres services autour de son 
outil gratuit.

Enfin, nous utilisons EC2 pour plusieurs autres services à la criticité
moindre. Ces services n'ont pas besoin d'être disponibles 24/7, les
données sont donc sauvegardées, mais nous n'avons pas besoin de mettre en 
place d'outils de haute disponibilité. Par contre, afin de faciliter un 
redéploiement, de pouvoir remonter le service rapidement en cas de 
panne, etc... Leur déploiement a été scripté afin d'être automatisé, via
Ansible[^ansible]. Ainsi, il suffit de créer une nouvelle machine virtuelle et de 
lancer le script afin que le service s'installe et se configure 
automatiquement.

[^ansible]: Ansible est un outil de déploiement automatisé ayant été racheté récemment par Red Hat

Pour l'anecdote, Ansible est également utilisé en interne pour la 
configuration des postes de développement. Ainsi, nous avons deux 
ordinateurs sous linux pour les stagiaires en développement web, ces 
derniers possèdent leurs scripts de déploiement, ce qui permet de maintenir
à jour cette configuration. Même le raspberry dont l'unique rôle est 
de faire apparaître, sur un écran au sein de la société, les statistiques 
de base de l'application (en temps réel), possède son script de 
déploiement. Ainsi, si on doit créer ultérieurement un nouveau type de 
configuration d'ordinateur, on peut partir du même script en modifiant 
uniquement ce qui diffère entre les deux environnements.

### Automatisation de la configuration des tablettes

Hungry Up met à disposition des restaurateurs des tablettes configurées 
pour afficher leur panel de gestion du service. Sur ce panel il leur est 
possible d'accepter ou refuser une demande. 

Il était important pour moi de trouver une manière de ne pas perdre de 
temps sur la configuration des tablettes. En effet, pour chaque tablette 
il fallait : 

* Restaurer la tablette aux paramètres d'usine.
* Retirer les logiciels livrés avec la tablette
* Configurer le wifi
* Configurer un compte Google
* Installer les applications nécessaires (Firefox, Teamviewer, ...)
* Supprimer le compte Google
* Installer le fond d'écran Hungry Up (qui sert à appuyer notre image de 
marque)
* Retirer la configuration du wifi

Toutes ces étapes se trouvent être longues, et font perdre un temps 
considérable pour chaque nouvelle tablette à configurer. Nous avons 
acquis les 20 premières tablettes, préconfigurées avec les instructions 
ci-dessus. Cependant cette configuration induisait un surcoût de 20 
euros par tablette, ce qui augmentait sensiblement nos frais. De 
plus, dans le cas où la tablette d'un restaurant était récupérée, il 
fallait tout refaire manuellement. J'ai alors cherché des moyens 
d'automatiser ces configurations, afin de faire des économies, et 
surtout de gagner en flexibilité.

Parmi les solutions existantes, il figure ce que l'on appelle le MDM[^mdm], proposé 
par beaucoup de services, dont Cisco Meraki. Le problème de ces SaaS 
est qu'ils coûtent cher. Il s'agit d'un tarif mensuel par matériel. 
Leur avantage étant de pouvoir gérer de manière identique un large parc 
hétérogène de matériels. L'idée derrière le MDM est plutôt de venir en
renfort sur du BYOD[^byod] : les salariés d'une société qui utilisent 
leur propre matériel peuvent ainsi récupérer toutes les configurations 
de la société pour leurs tablettes et téléphones personnels, de manière 
sécurisée.

[^mdm]: Mobile Device Management
[^byod]: Bring your own device

Je suis alors parti du principe que nos tablettes Android sont de base
sous linux, il est alors théoriquement possible d'y gérer une 
configuration via Ansible par exemple. Le problème à cela est qu'il est 
du coup nécessaire d'y avoir une connexion SSH, et donc que la tablette 
soit rootée [^rootDevice], ce qui implique d'introduire dans le parc de 
tablette des failles de sécurité.

[^rootDevice]: Rooter un périphérique Android signifie d'y acquérir, 
généralement par l'utilisation d'une faille de sécurité, les 
autorisations super-utilisateur, dans l'objectif de débrider le 
périphérique.

À cours d'idées, j'ai demandé à mes confrères qui travaillent dans 
l'administration système & réseau de la célèbre liste de diffusion FRnOG 
s’ils connaissaient des solutions permettant de répondre à mes critères. 
Après de nombreux échanges, on m'a conseillé de regarder les services de 
la société GenyMobile.

Je connaissais déjà GenyMobile, il s'agit d'une société 
fournissant une expertise Android, j'avais souvent recommandé à mes 
étudiants en développement Java et Android d'utiliser l'outil GenyMotion, 
qui sert d'émulateur Android. Cet émulateur était bien plus performant 
que l'émulateur fourni par Google. J'ai un profond respect pour le 
travail fourni par GenyMobile, qui est toujours de qualité, de plus il 
s'agit d'une autre startup française.

GenyMobile propose deux types d'offres répondant à ma problématique. La 
première, GenyMaster, consiste à concevoir un système Android 
personnalisé. Ce système inclura un système de gestion des mises à jour, 
et permet également d'avoir une configuration par défaut. GenyMaster est 
utilisé par de gros clients, et il s'agit d'une solution très couteuse. 
Dans notre cas, nous prenons des tablettes à bas coût, il n'est donc pas 
adapté d'utiliser une solution aussi chère pour cela.
 
La seconde offre, GenyDeploy, est celle que j'ai retenue dont le produit 
consiste en la création de fichiers de déploiement permettant de 
configurer un appareil. Le produit utilise le mode debug de la tablette 
pour la configurer, le processus de déploiement est alors très simple : 
il suffit de prendre une tablette, d'activer le mode debug, et de le 
brancher à un ordinateur. Ce dernier va détecter qu'un nouveau 
périphérique est branché, et va le configurer automatiquement. À l'issue 
de cette configuration, GenyDeploy va retirer le mode debug. Nous avons 
également une station de recharge, il s'agit tout simplement d'un 
adaptateur USB pour secteur, comportant 5 ports USB. Ainsi, lorsque nous recevons une tablette, nous la configurons puis nous la mettons à recharger. Nous la 
rangeons alors dans notre stock, toutes les tablettes sont prêtes à être 
prises par les commerciaux. Ultime étape, les commerciaux renseignent 
la tablette sur un tableau Trello servant à la gestion de stock 
(simplifié, nous n'avions pas de temps à perdre pour un système plus 
complexe tel que GLPI) une fois qu'elle est déployée chez un client.

![Solution de déploiement Genydeploy](sources/images/screenshot-genydeploy.png)

De plus, l'offre est très simple, chaque configuration de nouveau 
périphérique revient à environ 6 euros, support compris. La 
reconfiguration d'un périphérique, déjà configuré il y a moins de six 
mois, est gratuite.

## Solutions organisationnelles

### Dégradation du périmètre fonctionnel

Réduire un périmètre fonctionnel permet de tenir des délais, mais ne
fait pas réellement aller plus vite, il s'agit en réalité de retirer des
fonctionnalités d'un cahier des charges afin de réduire la charge de 
travail. Une méthode plus intelligente consiste en le fait de dégrader 
ce périmètre fonctionnel pour une application, en favorisant la 
conception d'une autre. En réalité, le gain se fait en tirant profit 
du mode agile de la startup, et son adaptation rapide au terrain. 

Lors de la conception d'une fonctionnalité, le retour des utilisateurs
mène souvent à des modifications. Le problème est que si les 
différentes plateformes sont au même niveau de développement les unes 
des autres, chaque retour doit être traité deux fois. L'idée derrière
cette dégradation est de rendre artificiellement une plateforme en
retard sur une autre. Par exemple, et c'est notre décision, en affectant
deux développeurs sur l'application iOS, et une seule sur l'application
Android. Ainsi, l'application iOS avance bien plus vite, et une nouvelle
version y est publiée plus rapidement. Suivant les retours des
utilisateurs, nous effectuons des correctifs puis nous sortons une nouvelle
version. L'application Android, elle, étant retardée, se retrouve avec
ses spécifications déjà corrigées. 

Dans notre cas, pour pouvoir se réserver la possibilité de rattraper le
retard sur l'application Android, l'équipe mobile se compose d'un
développeur iOS, d'un développeur Android, et d'un développeur
iOS/Android. De plus, l'écart entre les versions est également créé par
l'expérience des développeurs, le développeur Android étant débutant.

### Modélisation des processus métier

Un autre facteur d'amélioration consiste en la modélisation des 
processus métier. En effet, dans notre fonctionnement originel on définit 
un besoin, ensuite une maquette est produite par le graphiste, et cette 
maquette sert de cahier des charges pour la production. Il y a un effet 
conséquent d'interprétation entre le besoin et l'élément final produit. 
De nombreux retours sont faits, et beaucoup de questions émergent. 
Encore une fois, ce phénomène d'aller-retour est très coûteux en temps. 
De plus, la rédaction de documents formels décrivant une fonctionnalité 
se trouverait être une perte de temps, car sur un fonctionnement où l'on 
développe en interne, le temps de rédaction d'un côté puis le temps de 
compréhension de l'autre rendrait le tout assez long. 

Pour moi, la meilleure manière était donc de modéliser cela de manière 
graphique. En effet, l'homme analyse beaucoup plus facilement et 
rapidement une donnée graphique qu'un texte. 

Ainsi, on distingue deux types de productions graphiques. La première, 
les mockups, permet de valider l'expérience utilisateur avant toute 
production graphique. Ainsi, on gagne du temps sur la production des 
éléments graphiques, car on peut travailler plus efficacement, en 
annotant directement le mockup, valider la meilleure présentation,
mais également la présentation la plus rapide à mettre en place.

Pour la seconde, il s'agit de la véritable modélisation de processus 
métier, par la conception d'un diagramme respectant des codes de formes. 
Pour cela, nous utilisons une application web : draw.io, qui nous permet 
d'avoir l'application de manière gratuite et partout. Il est simple de 
réfléchir en réunion sur une tablette à un processus métier. Ces 
processus sont donc plus macro, ils ne vont pas traiter l'expérience 
utilisateur, mais plutôt la navigation au sein de l'application, ou 
encore des enchainements logiques.

Par exemple : l'utilisateur s'inscrit, puis il se connecte à un 
restaurant, ensuite une question lui est posée, il peut y répondre par oui ou 
non. S’il répond oui, cela déclenchera un événement.

Dans cette phrase, une grande partie des informations est inutile : les 
conjonctions de coordination, la ponctuation... Transposer ce type de 
réflexion sous forme graphique assure une meilleure lisibilité de la 
complexité. Limiter les phrases permet de traduire plus facilement aux 
équipes ne parlant pas français, voire même de produire directement des 
documents en anglais de manière plus aisée.

Mais ce n'est pas l'intérêt principal, en réalité, cet exercice me 
permet de faire faire le développement directement par le métier. 
Ces processus métier sont en effet directement transposables en code. 
Ainsi, le développeur va aller beaucoup plus vite et diminuer le nombre
d'erreurs qui est généralement imputable à la mauvaise compréhension du 
besoin exprimé.

### Réduction de l'interruption

Le principal paradoxe de notre société est que, bien qu'étant une 
entreprise du numérique, on ne digitalise que très peu les échanges. 
Ainsi, souvent il s'agit de conversations orales, pas toujours 
opportunes. Il n'est donc pas rare d'être interrompu pendant son travail 
par une question posée, etc... Ce problème vient, je pense, 
principalement du fait que les locaux sont dans un espace ouvert et 
restreint ce qui favorise ce type d'échanges. 

Ces interruptions sont très dangereuses pour la productivité. En effet, 
d'après une étude de 2013 du Michigan State University[^MSU], une interruption de moins de 3 
secondes engendre un taux d'erreur doublé. Le temps moyen pour retrouver
sa concentration initiale après interruption, observée par Gloria Mark, 
une universitaire californienne, serait de 25 minutes en moyenne. Enfin, 
une troisième étude de 2005, qualifiée dans un rapport de Basex, 
montrait que ces interruptions faisaient perdre aux salariés environ 28% 
du temps de travail.

[^MSU]: le Michigan State University (MSU) est une prestigieuse université fondée en 1855. Il s'agit de la 6ème plus importante université en nombre d'étudiants.

Ces effets sont quantifiables, mais d'après Christophe André, psychiatre 
à l’Hôpital Sainte-Anne, ces stimuli diminuent le bien-être, et 
augmentent l’épuisement cognitif, l’anxiété et le stress, l’énergie 
mentale, quant à elle, diminue. Cela se traduit par l'épuisement en 
fin de journée. 

Des effets à long terme s'installent également : le cortisol[^cortisol] 
entrave les défenses immunitaires et la qualité du sommeil. Ainsi, c'est 
notre capacité à prendre la bonne décision qui se trouve impactée.

[^cortisol]: Il s'agit de l'hormone du stress.

Il faut considérer la date de ces études : les chiffres ont probablement 
augmenté depuis, avec l'avènement des réseaux sociaux, des chats 
d'entreprise, etc...

On ne peut couper la communication physique, il faut alors l'optimiser. 
Ainsi, à but d'expérience, j'ai fait une semaine de télétravail la 
première semaine d'août. Ma performance a été très largement augmentée 
par l'absence de présence physique. 

Ce mode n'est pas adapté aux périodes où mon équipe est sur place, en 
cas de besoin d'aide il faut trouver un moyen de s'isoler numériquement 
et physiquement. La société devant déménager en septembre, c’est 
l'occasion parfaite de cloisonner un peu plus les équipes. C'est un 
premier pas. Ensuite, l'utilisation du mode "Ne pas déranger" de macOS 
est intéressant car il bloque les notifications des différents 
logiciels. Il est intéressant de penser une nouvelle manière de fonctionner et de la promouvoir : on avance et travaille sur une tâche, une fois qu'elle est
finie ou que l'on s'autorise une pause, on regarde les notifications en
attente dans la barre des tâches.

Le problème réside dans l'habitude humaine, qui est compliquée à faire 
changer. En effet, il est très tentant d'aller voir à intervalle régulier
et court ses mails, le chat, etc... Pire, un collègue qui ne voit pas 
de réponse immédiate trouve plus simple de se lever pour aller 
interagir physiquement avec la personne. La perte de temps est alors 
augmentée.

Dans son livre "The Time bandit", Edward G. Brown, consultant en 
productivité pour les plus grandes sociétés américaines, parle de 
solutions comme les "Time locks", des espaces de temps partagés pour la
communication, l'objectif est simple : prévoir une plage horaire pour 
les communications, et en dehors de ces plages horaires, ne pas 
interrompre les personnes. Le point important que j'ai constaté et qui 
est soulevé par Brown est qu'il est contre-productif de refuser à une 
personne de communiquer même si on a demandé explicitement de ne pas le 
faire. En effet, l'interruption est déjà faite, et cela ajoute de la 
frustration. Le risque serait alors de complexifier les relations entre 
les personnes au sein de la société, et donc de diminuer sa 
productivité. Il ne faut jamais dire non à un "Time bandit", 
paradoxalement. Il s'agit d'une solution que nous allons tenter de
mettre en pratique.

Je n'ai pas trouvé de solution finale pour l'instant, cependant je pense
que c'est une question assez centrale et stratégique qui doit poser 
problème à beaucoup d'autres structures.

J'ai également remarqué que la messagerie d'entreprise, Slack,
est utilisée à mauvais escient, pour suivre des process, transmettre des 
documents... Le tout dans l'objectif de faire avancer le travail. Je 
pense que cet outil ne devrait pas être utilisé en remplacement des 
mails, l'interruption y est plus grande. Un mail pose plus de réflexion, 
tant pour le fond que la forme, c'est plus fluide à lire et comprendre, 
car la personne n'envoie pas ses idées au fur et à mesure, mais prend le 
temps de les organiser et les poser. A contrario, la majorité des appels 
téléphoniques ou des interruptions orales pourraient être transformés en 
envoi de messages instantanés. Car souvent le format écrit évite les 
divergences de la conversation. 

## Solutions ressources humaines

Un certain nombre de solutions concernent les ressources humaines. 
Généralement il s'agit de l'augmentation des effectifs, ou encore de la
réduction de leur charge de travail. Ici, les deux étant compliqués,
il fut nécessaire de trouver une solution complémentaire.

### Réduction du nombre d'acteurs impliqués

Lors de la conception d'une nouvelle fonctionnalité, de nombreux acteurs
sont impliqués. Après identification du besoin par l'équipe commerciale, 
un micro cahier des charges est créé, des maquettes sont ensuite créées 
par notre designer. Ensuite, l'équipe technique entre en jeu, il faut 
modéliser la fonctionnalité puis concevoir son programme côté serveur
(Il s'agit de la partie métier de la fonctionnalité, le serveur s'occupe
de gérer toute la logique métier, les contrôles, les droits, etc...). 
L'équipe backend[^backend] doit concevoir cette partie, mais également la
documentation qui va servir de contrat d'API : Qu'est-ce qui doit être
envoyé au serveur comme donné.
Une fois tout cela fait, les équipes mobiles peuvent travailler en
parallèle pour concevoir l'interface sur les différents systèmes
supportés (iOS et Android). 
La conception du backoffice[^backoffice] peut également démarrer. Pour
rappel, nous en avons deux : le premier pour notre usage interne, le
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
service de messagerie classique... À quelques différences près.
En effet, dans notre système, l'échange va se passer de la manière suivante :

L'utilisateur va ouvrir l'application, se connecter à sa table. À partir
de là, la liste des actions possibles va être chargée sur son téléphone
et alimenter la barre d'action en bas de l'application. L'avantage de
cette récupération dynamique de cette barre d'action est la
personnalisation suivant les besoins de l'utilisateur, et les
configurations du restaurant. On peut ainsi imaginer une configuration
différente suivant le restaurant : gastronomique, bistronomique, bar,
fast casual[^fast-casual]...

[^fast-casual]: Anglicisme désignant les restaurants sans service à
table, à mi-chemin entre le fast food et l'expérience traditionnelle
d'un restaurant.

Une action correspond à une demande de l'utilisateur, celle-ci embarque
un nombre de prérequis pour être lancée, ces derniers peuvent être soit 
transparents pour l'utilisateur (demande de ses coordonnées GPS), soit 
interactif (demande d'entrer un nom). 

Le déclenchement d'une action permet au service de signaler la demande 
au serveur et de générer deux messages : le premier correspondant à 
celui envoyé par l'utilisateur, le second étant la réponse à 
l'utilisateur. Pour faire patienter l'utilisateur lors de la génération 
de son propre message, on exploite un pictogramme pour générer sa bulle 
de message temporaire, ce dernier représente l'action demandée, et sera 
remplacé par son message texte dès qu'il aura été reçu par 
l'application, cette génération est quasi instantanée, mais 
les aléas réseau nous forcent à prévoir ce délai.

Chaque message en retour peut être accompagné d'une liste d'actions
possibles, des choix supplémentaires servant à répondre dans le cas où
une demande de complément d'information est nécessaire (par exemple, le
client demande un burger, le type cuisson de sa viande lui sera demandée).

Ainsi, on identifie deux types d'échanges : les messages et les
actions. La flexibilité et l'astuce se trouvent sur le fait que tout est
généré côté serveur, seuls les prérequis d'actions doivent être
implémentés côté application. On passe ainsi d'un modèle complexe de
développement, où, pour chaque évolution, les développeurs de l'application
sont mobilisés, à un modèle plus léger, où, la majorité des évolutions
peuvent être effectuées sur le backend de l'application. De plus, seules
les interfaces spécifiques et la gestion de nouveaux types de prérequis
(par exemple l'implémentation d'une fonctionnalité d'une application
tierce) doivent mobiliser ces équipes de développement mobile. Comme ce 
coût est généralement en fonction des plateformes supportées, cela
réduit également la probabilité de bugs sur une plateforme, le nombre de
tests à effectuer à chaque nouveau développement, etc...

Cette solution à mi-chemin entre solution technique et solution
ressource humaine est un des vecteurs majeurs de cette accélération.

### Externalisation et recrutement

L'externalisation, en soi, est un sujet délicat : peut-on se séparer de
la compétence clef, coeur de métier d'une société ? Dans notre cas, nous 
fournissons une application mobile, est-il dont raisonnable d'externaliser le
développement mobile ?

Notre stratégie de base était d'externaliser ces compétences le temps 
d'avoir les fonds nécessaires à leur internalisation. Il était hors de
question de rester chez notre prestataire pour des questions de qualité/prix. 
Cette question de la perception de la valeur est centrale : est-ce que 
le coût vaut réellement le travail produit ? Les éléments de réponse 
peuvent venir en se posant les bonnes questions : suis je prêt à 
accepter une qualité moindre ? Quelle est la valeur que je donnerais à 
cette qualité produite ?

Concernant ce prestataire, son coût élevé ne semblait pas être justifié
par la qualité de sa prestation : nous avions perdu beaucoup de temps à
trouver des problèmes qui auraient pu être détectés en amont. C'était 
alors le moment de partir à la recherche d'une compétence permettant de 
continuer le travail. Il s'est ainsi posé un certain nombre de 
questions, dont la centrale était : doit-on continuer à externaliser ?

Dans la prolongation de cette recherche d'accélération, quel est le
meilleur moyen de ne pas être ralenti, pour quels sacrifices et à quel 
coût ? 

Les avantages d'une prestation sont nombreux : il n'est pas nécessaire 
de passer par de longs processus de recrutement, il est possible de 
demander un engagement de résultat, et il est également possible 
d'augmenter le nombre de ressources disponibles pour le projet de 
manière simple et opaque. En revanche, un prestataire doit passer du
temps à trouver des clients, c'est pour cela qu'il est généralement plus
cher qu'un salarié. L'arrivée de la ressource est donc moins chère, mais
le long terme l'est, quant à lui, beaucoup plus.

En effet, un processus de recrutement est coûteux sur le secteur du
numérique, c'est un processus généralement assez long, qui comporte du
risque. Ainsi le nombre d'agences de recrutement a explosé ces dernières 
années. En moyenne il est demandé plus de 10 000 euros par recrutement 
effectué grâce à l'agence. Ce coût semble important, mais il est à 
relativiser avec le temps important que prend un recrutement dans le 
numérique.

Ainsi, après avoir échangé avec Thomas Guenoux, co-fondateur de KRDS et 
de Commitstrip, il m'a gracieusement conseillé sur nos méthodes de 
recrutement, il est en effet important pour ce secteur d'approcher des 
développeurs, de les contacter directement, un à un, via des réseaux 
sociaux professionnels par exemple. De plus, le budget fixé pour ce 
recrutement était de 36 000 euros par an, bruts, Thomas m'a ainsi 
confirmé que quand le budget est aussi bas, il est essentiel pour la 
société de trouver des avantages tiers pour faire levier sur le 
recrutement. Ces avantages tiers peuvent être par exemple l'accès à une
salle de sport, des boissons à volonté, du matériel performant, un cadre 
de vie agréable... 

Ensuite vient la question de la possibilité d'externaliser une
compétence. Pour ma part, je me suis demandé : est-ce que le produit
concerné par la compétence contient notre métier ? Contient-il un
avantage concurrentiel ? Le produit est-il exposé ?

En réalité, sur notre modèle de conception, les applications mobiles
restent des coquilles vides, toute la logique métier et de contrôle se
trouve sur le backend. La valeur stratégique de la société s'y trouve
donc. De plus, les applications mobiles sont décompilables, il est
possible de retrouver une partie du code source grâce à des outils dits
de décompilation. Il faut alors considérer ce type d'application comme
déjà perdue. Le backend quant à lui, bien que pouvant être compris par
rétro-ingénierie, il contient toute notre logique métier, nos processus,
nos données...

Après ces analyses, je me suis posé comme limite à la possibilité
d'externaliser, de ne pas externaliser le backend, bien trop dangereux.
En effet, le backend contient toute notre logique métier, nos données,
et une partie de nos logiques d'expérience utilisateur.
En revanche, je ne voyais aucun problème à externaliser la partie 
mobile. Il est même possible de pousser un peu cette analyse. Ainsi, on 
pourrait externaliser la production de nos backoffices (restaurant et 
administrateur), ces derniers fonctionnent de la même manière que 
l'application mobile : ils sont une simple interface qui va interroger 
l'API afin de pouvoir exécuter une action.

Je me suis alors mis à la recherche de freelances pour la conception 
des applications mobiles dans un premier temps. Je me suis alors 
trouvé confronté à un problème majeur de coûts. En effet, à Paris, les 
développeurs mobiles demandent allègrement 350 à 550 euros par jour de
prestation, pour un niveau junior[^junior]. Le risque était alors de 
s'exposer à un coût mensuel de plus de 14 000 euros par mois, pour le 
développement de l'application iOS et Android. Ce tarif se trouve être 
très largement hors de notre budget, il nous fallait trouver une 
alternative. 

[^junior]: Pour moi, le niveau junior regroupe les développeurs de 1 à 
3 ans d'expérience. Il suit le niveau "Débutant", et précède les niveaux 
"intermédiaire" puis "senior".

Tout d'abord, une solution était de tolérer le télétravail, en effet, le 
coût de la vie est bien plus élevé à Paris, ce qui explique ces tarifs. 
Ainsi, travailler avec des personnes en province pouvait permettre 
d'économiser beaucoup.

Enfin, dans le prolongement de cet axe, la délocalisation du travail se 
trouve être une solution acceptable à priori, pour bénéficier de tarifs 
plus attractifs, le risque étant de ne pas tomber sur une compétence 
trop en marge de la qualité souhaitée.

Je me souviens avoir travaillé par le passé avec des prestataires en 
Inde et au Maroc, et j'en garde un très mauvais souvenir. J'ai alors axé 
ma recherche sur des tarifs excluant le low cost. En effet, l'idée est 
de bénéficier de compétences à un tarif avantageux, et non pas d'avoir 
des ressources de développement au prix le plus bas possible.

Après avoir comparé des dizaines d'offres de pays très divers 
(Madagascar, Mexique, Tunisie, Chine...), une société a retenu mon 
attention. Startechup est une société gérée par un expatrié français, 
familier du monde des agences et du développement, établi aux 
Philippines. Ses références sont intéressantes, sa société ayant par 
exemple travaillé sur l'application Somfy. Startechup propose des 
ressources compétentes de niveau intermédiaire et sénior, pour des 
tarifs moitié moins chers que des débutants à Paris. 

La République des Philippines est un pays très tourné vers 
l'international, ainsi leur langue historique, le Filipino, s'est 
trouvée, en 1987, rejointe par l'anglais comme langue nationale. La 
grande majorité des Philippins sont donc bilingues, ce qui facilite bien
plus les échanges qu'avec un autre pays. Cela tombe bien, pour des 
raisons de conventions, tout le code produit pour l'application est en 
anglais. C'était un choix par habitude, et cette aventure me montre 
toute l'utilité d'une telle décision.

Startechup propose deux types d'offres : des ressources dédiées ou des 
développements classiques basés sur un cahier des charges. Un problème 
identifié très tôt après mon arrivée chez Hungry Up est que très peu de 
spécifications sont faites pour une fonctionnalité. Bien souvent, il 
s'agit de maquettes qui font office de cahier des charges, par manque de 
temps. Ce manque de spécifications mène à des désaccords, puis à des 
changements de dernière minute. Il est très compliqué pour moi de 
conserver une bonne relation avec un prestataire si ce dernier travaille 
au forfait et que les spécifications servant de base au contrat ne sont 
pas claires. La mise à disposition de ressources dédiées semble donc 
bien plus adaptée, car on peut faire évoluer les tâches de manière aussi 
agile que le projet s'articule. De plus, les ressources dédiées se 
trouvent être moins chères pour deux raisons : il n'y a pas de gestion 
de projet à effectuer pour l'agence et le risque d'un dépassement de 
temps passé sur une tâche se trouve déplacé de l'agence vers le client. 
Ce dernier point m'intéresse beaucoup, car il va être un véritable levier 
pour moi de responsabilisation de nos équipes internes. En effet, il 
va être possible de montrer et de quantifier l'impact de notre 
désorganisation sur les coûts de production. L'objectif de cette prise 
de conscience étant de limiter les retours sur décision, entre autres.

J'ai alors décidé de prendre deux ressources sur un engagement d'un 
mois : un développeur Android Junior et un développeur iOS/Android 
sénior, le rôle de ce second étant d'avancer sur l'application iOS, mais 
également de pouvoir aider le développeur Android si besoin.

Il fut nécessaire pour moi de mettre en place des outils de gestion et 
de contrôle qui n'étaient pas nécessaires avant. En effet, les agences 
avec lesquelles nous travaillions avaient, en interne, tous les outils de 
développement et de gestion de projet. J'ai donc préféré un 
fonctionnement simple et standard avec Trello, pour la gestion des 
tâches à faire, sur un modèle très SCRUM[^scrum]. De plus, ce fut l'occasion 
pour moi d'installer un serveur de gestion de versions (Gogs, pour le 
système de gestion de versions Git), et un système d'intégration 
continue (Strider). Ce dernier me renvoyant en temps réel les résultats 
sur Slack. Enfin, ne connaissant pas la politique du pays ou des pays 
par lesquels transitent les données, j'ai préféré opter pour une méthode 
de communication chiffrée de bout en bout[^e2ee] entre le prestataire 
et notre équipe. Ainsi, le choix de Wire, logiciel conçu par les mêmes 
personnes que Skype et partiellement opensource (le logiciel est 
opensource, le serveur ne l'est pas), fut assez évident.

[^scrum]: La méthodologie de travail SCRUM est un cadre souple basé sur la finalisation rapide et itérative de fonctionnalités.
[^e2ee]: Le chiffrement de bout en bout (Abrégé E2EE pour end-to-end 
encryption) est un principe où seuls les logiciels client qui 
communiquent entre eux ont une clef permettant de déchiffrer un message. 
Ainsi, ni le réseau ni le serveur ne peuvent connaitre le contenu d'un 
message.

Après un mois de prestation, et après avoir validé la compétence des 
prestataires, afin d'aller plus vite, le choix a été fait de prendre une
ressource supplémentaire. Nous sommes donc actuellement sur un modèle
d'un développeur iOS, un développeur Android, et un développeur
ambivalent. Nous nous sommes également engagés sur une durée plus longue
de prestation, ce qui nous permet d'avoir des tarifs légèrement plus
intéressants. Au final, cette prestation se trouve être un des coûts les
plus importants du projet, mais il s'agit surtout d'un excellent rapport 
qualité/prix.

Startechup se trouvant à Cebu City, il y a 6 heures de décalage horaire. 
Il est nécessaire de faire de cette contrainte un atout. Ainsi, ma 
principale préoccupation était qu'ils aient plusieurs tâches sur 
lesquelles travailler dans le cas où, pour une tâche, ils étaient en 
attente de renseignements complémentaires. Leur consigne étant alors de passer à une autre 
tâche en cas de manque d'informations. Je me réserve ainsi du temps dans
la matinée pour faire un point avec eux, et pour répondre à leurs 
questions. La fin d'après-midi me permet de faire des revues de code de
leur travail, ou encore de faire des tests fonctionnels sur les 
fonctionnalités produites. Ainsi je leur fais mes retours qui seront 
traités pendant la nuit. De cette manière, le décalage horaire est plus 
une force qu'une limitation.
