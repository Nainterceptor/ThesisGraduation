
Méthodes traditionnellement utilisées
=====================================

Pour accélérer sur un projet, deux axes principaux sont étudiés : 
l'augmentation des ressources pour mener à bien la tâche, et la 
réduction du volume de travail à fournir sur la tâche.

Il existe d'autres moyens qui relèvent de l'optimisation du temps passé,
des non dits, ou encore des bonnes pratiques. Toutes les méthodes qui
suivent ont été rencontrées lors de recherches préliminaires sur ce qui 
se fait actuellement. Elles sont pour la majorité le fruit de discussions 
auprès de mes pairs.

## Le recrutement

L'augmentation de ressources se fait traditionnellement par le 
recrutement de nouvelles personnes dans une équipe. Effectivement, plus il y 
a de personnes, plus on peut fragmenter le travail à faire, et ainsi en 
exécuter davantage en simultané. Dans une startup, les choses se compliquent, 
en effet, n'ayant pas encore de modèle économique stable et de marché 
clair, la startup va devoir s'entourer d'une équipe robuste et avec une forte adaptivité au changement. 
Or, d'après Paul Graham[^PaulGraham], la première cause d'échec d'une 
startup est le relationnel entre les membres de l'équipe. Or, cette 
équipe a été constituée après un processus de recrutement. Ainsi, la 
première cause d'échec se trouve être indirectement le recrutement. 

[^PaulGraham]: Paul Graham est le fondateur de YCombinator, un des 
incubateurs les plus réputés au monde.

Généralement, un processus de recrutement part de la définition du besoin, 
on va chercher alors à savoir quel type de ressource on recherche, 
quelles sont ses compétences nécessaires et compétences appréciées. 
Cette identification se matérialise à travers la création d'une fiche de 
poste. C'est un non-dit, mais il est important de clarifier quel est le 
profil humain souhaité. En effet, il est souhaitable que le candidat 
partage les valeurs et la culture de l'entreprise afin que la 
communication soit efficace et fructueuse.

Après cette étape préliminaire, le travail de recrutement commence. Il 
est impérieux de sourcer (référencer) les candidats potentiels. Il est 
vain de penser qu'une startup n'ayant pas encore d'attractivité ou de 
traction puisse poster une offre sur internet et avoir des candidatures 
de manière naturelle. C'est au manager d'aller chercher par effet de 
réseau des salariés. Il est possible par exemple de regarder les 
nouveaux sortants d'une école réputée, ou d'écumer les meetings sur les 
sujets souhaités, par exemple.

Ensuite, après avoir pris contact avec toutes ces personnes, il faut les 
évaluer, afin de vérifier leurs références, leur CV, mais surtout 
qu'elles savent bien faire ce qu'elles prétendent maîtriser. J'ai du revoir 
cette étape après un échec dans mon processus de recrutement, où j'avais 
sous-estimé ce besoin d'évaluation. Je me suis alors rendu compte 
qu'intégrer une personne ayant des lacunes devient très rapidement un 
gaspillage de temps. Pour ma part, concernant cette partie technique, 
j'apprécie de faire de la revue de code[^codeReview] sur un projet open source envoyé par 
le candidat, en préliminaire d'un entretien où il sera demandé de 
résoudre un problème commun. 

[^codeReview]: Il s'agit de revoir le code produit par une autre personne, afin de faire une critique objective de sa qualité globale. Dans de nombreuses organisations, de manière régulière une réunion est faite sur un point particulier de code, afin de débattre de son intérêt et de son optimisation.

Enfin, il arrive l'étape de l'intégration, ça y est, elle est là, le 
contrat est signé, et il faut maintenant assurer. Démontrer que la société 
est stable, qu'elle marche, même quand ce n'est pas le cas. Pour cela, 
il est important d'attacher de l'importance au cadre dans lequel le 
salarié va évoluer. Par exemple, son poste de travail doit être propre et 
prêt, avec tous les éléments configurés pour travailler dès sa prise de poste.

Le recrutement étant alors un facteur de coûts supplémentaires, mais également de danger, 
son objectif est d'augmenter la capacité de traitement de la charge de 
travail. Ne peut-on pas simplement la diminuer ?

## Réduire le périmètre technique

Le plus simple pour mener à bien un projet, quand on ne peut pas se 
permettre de recruter, est de répartir la charge de travail. Il n'est 
jamais nécessaire de sortir tout d'un coup. Il faut se focaliser sur les 
parties du produit qui génèrent le plus de valeur. En effet, quelle 
partie du produit fait vendre ? Quelle partie sert d'agrément ? Le 
produit va alors être découpé en liste de tâches. Cette liste sera alors 
priorisée, les tâches y seront classées en fonction de leur importance. Ensuite on 
y inscrit les objectifs. Il n'est, par exemple, peut-être pas nécessaire 
de passer 3 jours sur la création d'un compte utilisateur si cette 
dernière n'apporte rien à l'expérience utilisateur.

Dans tous les cas, il faut toujours se poser la question de l'utilité de
la tâche. Peut-on la remettre à plus tard ? Peut-être peut-on prendre 
des raccourcis techniques afin de la traiter plus rapidement, mais de 
manière moins optimale ?

## Contracter de la dette technique

Le fait de traiter une tache plus rapidement, dans l'objectif de la 
finaliser plus tard, ou même de la refaire plus tard, car non optimale,
s'appelle la contraction de dette technique. Ce temps gagné est à 
considérer comme un prêt qu'il faudra rembourser ultérieurement. 

Quand du temps est à gagner sur une tâche, et qu'il se pose la question 
de la contraction de dette technique, il faut alors se projeter dans le 
futur : quel en est l'impact ? Cela me fait gagner du temps maintenant, 
combien de temps cette dette va me faire perdre avant remboursement (La 
dette technique est remboursée quand elle a été absorbée, généralement 
quand la partie du projet a été refondue) ?

Ainsi, il est compliqué de contracter une dette technique sur les étapes 
préliminaires, qui serviront de structure au projet, car elles vont 
être le socle du projet. Contracter de la dette sur les fondations du 
projet implique que ce dernier en sera dépendant, le coût de 
remboursement sera très élevé pour un gain généralement minime.

## Prendre plus rapidement les décisions

Pour cela, Seth Godin, auteur de plusieurs livres, résume des leviers
d'optimisation sur son blog (Voir Webographie). Selon lui, il faudrait
prendre les décisions plus vite, dans le bon ordre, une seule fois,
quand cela est nécessaire, et sans demander à tout le monde. L'idée est 
très simple : plus je passe de temps à statuer, plus ça me coûte de 
temps, plus j'ai de personnes à démarcher, plus ça me coûte de temps, 
plus je sollicite d'avis, plus ça me coûte de temps...

## Mettre les prestataires sous pression

Il s'agit d'une solution bien trop utilisée à mon gout. Quand une 
startup travaille avec un prestataire, il est habituel de tout négocier, de 
tout traquer, l'objectif étant d'avoir le meilleur rapport qualité et quantité pour le même prix.

Pour avoir été prestataire sur de précédentes missions, et donc
avoir été des deux côtés de la barrière, je vois cette méthode d'un 
mauvais oeil. En effet, un prestataire a beau être prestataire, il n'en reste pas moins
humain. Le risque de cette stratégie est qu'il soit rapidement démotivé. 
Une personne démotivée travaille moins bien et contracte de la dette 
technique sans aucun calcul. Il n'est pas rare que du travail fait par 
un prestataire ne soit à refaire complètement.

Un prestataire considéré uniquement comme tel ne fera 
également pas remonter beaucoup d'information, or, un prestataire est 
généralement compétent, il est dommage de ne pas faire fructifier cette 
compétence à travers du conseil qui sera fourni de manière gratuite lors 
d'une relation bien construite.

Enfin, toutes ces négociations se trouvent prendre du temps, ce temps 
est alors perdu, pour le client, mais également pour le prestataire. Une 
relation saine commence par une négociation courte, en effet, sur du 
travail au forfait, il est bien vu qu'un cadeau soit fait sous condition 
que le temps passé en gestion de projet soit réduit. Il est 
compréhensible que le temps économisé au prestataire sur sa prospection 
soit réinvesti dans le temps passé sur le projet.

## Laisser les autres investir dans la recherche et développement

La manière simple de concevoir un projet reste l'observation de la 
concurrence et la copie. Il est évident que quand Apple sort un nouveau 
téléphone, fruit de sa recherche annuelle, un fabricant tiers va 
pouvoir construire une copie en moins d'un mois, car il bénéficiera du 
temps passé sur les concepts.

Je n'apprécie pas beaucoup cette manière de faire, pour moi, la 
concurrence doit se battre, il serait dommage de rester spectateur, en 
attendant l'innovation à copier. De plus, le temps nécessaire à un 
concurrent pour copier un produit reste le temps où le marché peut être 
plus facilement conquis.

Il est cependant intéressant de conserver une vision de ce que fait la 
concurrence. En effet, si l'utilisation est similaire, il sera plus 
facile de convertir les clients de ce concurrent en clients potentiels.

## Validations à postériori

Il est commun, car culturel, en France, qu'une décision prise soit 
validée auparavant par la hiérarchie. Ces validations créent des
processus souvent lourds ou complexes pour une startup. Il peut être 
intéressant de faire la démarche inverse, ne rien valider et traiter à
postériori les événements. Cela renforce en même temps le sentiment de 
confiance perçu par les salariés.

Cette vision est partagée par Oussama Ammar, co fondateur de The Family,
qui pousse la question à l'extrême en incluant les budgets dans cette 
validation à postériori. En effet, pour lui, il suffit de répondre à la
question "Cet achat sert-il l'intérêt de l'Entreprise ?" afin de savoir
si l'achat devrait être validé ou on.

Le temps gagné a posteriori est énorme. Premièrement, il y a le temps de 
formalisation de cette validation. En effet, lors d'une validation par 
la hiérarchie, cela nécessite de produire des documents écrits pour 
formaliser toute cette demande.

Ensuite, arrive le temps des échanges. Pourquoi veut-on acheter cela ? 
Quel est le retour sur investissement ?

Lors d'une validation à posteriori, cela est beaucoup plus simple, car 
seule une étape de validation existe. Ainsi, les salariés de confiance 
qui sont habilités à faire des achats ont juste à se poser une question
simple : mon achat sert-il les intérêts de l'entreprise ?
La direction est évidemment informée de ces achats.

## Environnement d'intégration continu

Un dernier axe bien connu de la conception logicielle est la mise en 
place d'un environnement d'intégration ou de déploiement continu. Notre
projet n'a pas fait exception à cette règle. Un projet de développement
inclut des étapes de contrôle, de suivi de qualité, de test... Ces 
étapes prennent beaucoup de temps, mais avec les outils adaptés, il est
possible de rendre ces tâches moins lourdes. C'est là qu'intervient l'environnement 
d'intégration continu. Le principe est simple : quand une fonctionnalité 
est produite, on va lancer des tests de manière automatique afin de 
tester l'intégration de la fonctionnalité et l'acceptation de cette 
dernière par le système, dans le but d'éviter à tout prix une 
régression. Cette étape peut partiellement remplacer la section de tests dans 
la célèbre roue de Deming (iso 9001). 

![Roue de Deming (Wikipedia)](sources/images/Roue_de_Deming.png)

Sur le projet Hungry Up, j'ai fait le choix de l'open source pour ces
services, en évitant les services sur lesquels le contrôle de la donnée 
n'est pas assuré. L'avantage est d'avoir l'esprit serein, mais ce n'est
pas sans inconvénient : la maintenance du service est alors à notre
charge, et généralement les outils sont moins complets que leurs
concurrents et plus complexes à mettre en place.
