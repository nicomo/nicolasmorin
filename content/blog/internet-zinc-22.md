+++
date = "2016-09-10T09:02:39+02:00"
description = "Internet cette semaine, comme si vous y étiez - 10/09/2016"
tags = ["internetzinc"]
title = "Internet zinc #22"
type = "post"
feature_image = "/img/iz-banner.png"
+++

## 1. AlphaGo trie les concombres

Vous vous souvenez d’AlphaGo, le programme de Machine Learning de Google utilisé au début de l’année pour battre un champion de Go ? Vous vous dites qu’il a mérité sa retraite et qu’il siffle des Mojitos sur une plage tropicale ? Pas du tout : il travaille à trier les concombres dans une ferme japonaise.

Le blog de Google sur Big Data and Machine Learning a un [article sur l’utilisation de TensorFlow](https://cloud.google.com/blog/big-data/2016/08/how-a-japanese-cucumber-farmer-is-using-deep-learning-and-tensorflow), qui est le nom donné par Google à leur outil Open Source de Machine Learning, à petite échelle.

Il s’agit d’une ferme familiale, au Japon, qui cultive des concombres et a besoin de les « calibrer », c’est-à-dire de les trier par taille, forme, couleur, etc. Le fermier-bricoleur, Makoto Koike, a fabriqué une petite chaîne, avec une webcam qui photographie le concombre et une série de bras qui font tomber les concombres dans les bons paniers en fonction de leur classification. Entre les deux, un mini-ordinateur Raspberry Pi 3 pilote la chaîne et la webcam, d’un côté, et se connecte à TensorFlow de l’autre.

Makoto Koike a donné à manger 7000 images de concombres à l’algorithme et TensorFlow se sert de cette banque d’image pour catégoriser les nouvelles images qui arrivent via la webcam.

Le blog cherche évidemment à promouvoir TensorFlow et, en l’espèce, sa facilité d’utilisation, mais je trouve intéressant qu’il souligne aussi, en fin d’article, les limites de cette expérience. En particulier, Makoto Koike a 2 problèmes :

- son ordinateur n’est pas assez puissant et son débit internet est trop faible. Du coup il est obligé d’utiliser des images en basse résolution, ce qui limite la capacité de TensorFlow à correctement classifier ces satanés concombres.
- il n’a pas assez d’images : pour entraîner TensorFlow efficacement, il lui aurait fallu beaucoup plus de 7 000 images.

Mais il continue d’améliorer son projet.

Si on pense classiquement la révolution industrielle comme à une révolution de l’énergie, introduisant la vapeur, le charbon, etc. en lieu et place de la force humaine ou animale, on pense à la révolution numérique comme une révolution de l’information. Mais ce n’est pas, dans le sens trivial, parce que votre journal vous est apporté sur votre téléphone, mais plutôt parce que le monde entier est transformé en information, soulevé par abstraction et rendu ainsi calculable. Même les concombres dans une ferme familiale.

## 2. les scientifiques d’AirBnB

À l’autre bout de l’échelle dans l’utilisation des technologies d’apprentissage automatique (je lutte pour trouver un équivalent français correct à Machine Learning…) — à l’autre bout de l’échelle, donc, par rapport à la ferme japonaise, la startup AirBnB. Ils ont une équipe de 70 scientifiques dédiés à ces questions.

On peut lire sur le [blog Kaggle un article](http://blog.kaggle.com/2016/09/06/building-a-team-from-the-inside-out-alok-gupta-on-the-evolution-of-data-science-at-airbnb/) qui donne une idée plus précise du travail réalisé.

Il faut acquérir et nettoyer les données ; il faut analyser les données dans l’optique de trouver de nouvelles opportunités de développement ; il faut créer des outils et des interfaces permettant aux non scientifiques d’exploiter des données de façon plus autonomes ; enfin il faut être capable de faire des expériences pour valider ou infirmer des hypothèses.

Avec 70 employés dédiés, AirBnB est capable, bien entendu, de faire beaucoup de choses.

Par exemple développer un outil de visualisation de données, qu’ils diffusent maintenant en Open Source : [Caravel](https://github.com/airbnb/caravel).

Il est intéressant aussi de parcourir leur site http://nerds.airbnb.com/, qui contient par exemple un article sur la façon dont AirBnB peut utiliser l’analyse des données pour [évaluer les risques](http://nerds.airbnb.com/unboxing-the-random-forest-classifier/). Le risque, par exemple, qu’un locataire dégrade un appartement. D’une certaine façon, c’est un problème proche de la gestion des trolls et des agressions dans les plateformes sociales ou les commentaires en ligne. Et comme vous le verrez si vous parcourez ce dernier article, c’est un article scientifique, universitaire (plein de formules).

## 3. les économistes d’AirBnB

Car AirBnB embauche un paquet d’universitaires. Il y a quelques mois, j’avais mentionné ici qu’Uber avait débauché d’un bloc tout un laboratoire d’une université américaine travaillant sur les véhicules autonomes. Mais cette « fuite » de la recherche vers les entreprises des nouvelles technologies n’est pas limitée à quelques secteurs technologiques spécifiques.

Un [article du NYTimes](http://www.nytimes.com/2016/09/04/technology/goodbye-ivory-tower-hello-silicon-valley-candy-store.html) cette semaine examine la même problématique pour les économistes, en partant du cas de Peter Coles, qui a quitté un poste de professeur à la Harvard Business School pour aller chez AirBnB.

Les économistes d’entreprise existent depuis longtemps, mais jusqu’ici il s’agissait essentiellement de macro-économistes, qui analysaient pour les entreprises les évolutions globales des marchés. Ici, on parle de quelque chose de tout à fait différent : de microéconomistes, statisticiens, etc. qui travaillent avec des données et des algorithmes. (Pour être honnête, ça existe aussi dans les banques depuis longtemps).

Les entreprises technologiques ont tellement de données à leur disposition (qui achète quoi, qui se déplace où, qui est ami avec qui…) qu’ils ont les moyens de produire des analyses leur permettant d’adapter leur entreprise, leurs offres, etc.

Pour mesurer l’ampleur du phénomène, l’article note :

- que sur le site d’offres d’emploi d’Amazon en ce moment, il y a 34 postes d’économistes ouverts
- que certaines universités, comme Yale, adaptent leur cursus pour ajouter des programmes qui mêlent intimement économie et… Machine Learning.

## 4. no-fly zone

En Virginie, Mme Youngman, retraitée de 65 ans, nettoyait son fusil de chasse après la messe, installée tranquillement à l’arrière de sa maison. Un drone de loisir passe et repasse au-dessus de son terrain — sans doute des paparazzi visant la propriété voisine de l’acteur Robert Duvall. Son sang ne fait qu’un tour, elle charge son fusil. Elle [déclare dans Ars Technica](http://arstechnica.com/tech-policy/2016/08/65-year-old-woman-takes-out-drone-over-her-virginia-property-with-one-shot/) :

> Il est venu dans mon espace aérien, à 35 ou 30 pieds au-dessus de mes arbres, et il est resté stationnaire une seconde. Je l’ai explosé.

Y’a procès.

Je suis fasciné par l’articulation des nouvelles technologies et des faits sociaux, en l’espèce le droit.

La justice américaine a établi que quand vous êtes propriétaire d’un terrain, vous êtes aussi propriétaire de l’espace au-dessus du terrain jusqu’à 83 pieds (env. 25 m). Et par ailleurs il est établi (même procès de 1946) qu’un avion doit respecter une altitude de sécurité d’au moins 500 pieds (152 mètres). Mais que se passe-t-il entre 25 et 150 mètres ? Personne n’en sait rien. Mais dans ce pays de Common Law, on le saura vite, même s’il est possible qu’il faille du temps pour que les différentes juridictions, et donc les précédents judiciaires, s’accordent. Ou que les différentes législatures, étatiques ou fédérale, sortent des lois.

En tout cas, cette petite perle est à suivre, parmi toutes les questions que les évolutions technologiques posent ou vont poser à la société par l’intermédiaire de son droit. Ma préférée à ce stade : un clone aurait-il le droit de vote ?

## 5. J’❤ Internet

Il est facile, quand on a le nez dans internet, le web, les apps, Uber et les menaces sur l’emploi, l’espionnage, Snowden, etc. d’oublier le bonheur vrai qu’est internet.

C’est ce que m’a rappelé un article du blog [Renaissance Mathematicus](https://thonyc.wordpress.com/2015/09/04/the-internet-and-the-history-of-science-community/). L’auteur explique qu’il a commencé à travailler en histoire des mathématiques au Pays de Galles dans les années 1970 et il rappelle, pour ceux qui l’auraient, même momentanément, oublié, à quel point chacun, en ces temps anciens, était isolé. Le courrier papier était lent, le téléphone cher, et l’information rare : quand bien même vous auriez voulu prendre contact avec un chercheur en Histoire des Mathématiques en Australie, mettons, encore fallait-il savoir où et à qui s’adresser.

J’ai encore, pour ce qui me concerne, grandi dans ce monde-là. Étudiant à la fin des années 1980 et au début des années 1990 j’étais, intellectuellement, incroyablement isolé. Dans ma petite ville française de province, je n’avais que peu de moyens de savoir ce qu’il se faisait de bonne musique, de bons travaux universitaires, et de bons romans étrangers… Et si par hasard j’entendais parler de quelque chose, se le procurer était extrêmement difficile.

J’ai quitté l’université en 1995. Avant qu’internet ait un impact majeur. J’ai donc été formé à l’ancienne école. Et en termes d’accès au savoir, cette ancienne école était nettement inférieure : malgré les nostalgies qui nous entourent, cela n’est pas discutable.

Je parle souvent ici d’internet comme révolution sociale, économique, technique, etc. Mais le joli billet de Renaissance Mathematicus, qui montre comment l’arrivée d’internet a révolutionné la communication scientifique dans son domaine, est d’abord, pour la plupart d’entre nous, une révolution personnelle.

J’écris ceci assis sur ma terrasse, à regarder la mer des Caraïbes par-dessus mon écran, en écoutant de vieux albums de McCartney et Georges Harrison, et aussi des nouveautés de groupes de gamins de 19 ans basés à New York. Tout ce que je lis, tout ce qui alimente cette lettre hebdomadaire, tout arrive à moi via internet : les films, la musique, les articles, les conférences. Quand j’ai fini d’écrire je programme la parution pour samedi matin 8 heures, heure de Paris ; et tandis que je dors (2 h du matin heure de Martinique), vous êtes un peu moins de 140 à la recevoir.

L’utilisation d’algorithmes dans une ferme du Japon, deux articles sur la façon dont on travaille sur les données dans une entreprise californienne, un procès, l’histoire des mathématiques. Manuel Valls peut s’exciter sur l’utilisation de Telegram par les djihadistes : pour ce qui me concerne, après 20 ans de connexion, je suis comme Renaissance Mathematicus, je continue de m’émerveiller d’internet.

Peace & Love, Yo.