+++
date = "2016-10-29T11:07:26+02:00"
description = "Internet cette semaine, comme si vous y étiez — 29/10/2016"
tags = ["internetzinc", "IA", "Data Science", "photographie", "Shenzen"]
title = "Internet zinc #29"
type = "post"
feature_image = "/img/iz-banner.png"
+++

## 1. Data Scientist : en fait.

J’ai lu pas mal sur le sujet Data Science cette semaine. Le sujet étant à la mode, il y a des quantités invraisemblables de contenus en ligne dans lesquels il n’est pas toujours facile de se repérer. À commencer par la question de savoir ce qu’est un « Data Scientist ».

La meilleure intro croisée cette semaine date de juin 2015. Il s’agit d’un article de Robert Chang sur son expérience de [Data Scientist chez Twitter](https://medium.com/@rchang/my-two-year-journey-as-a-data-scientist-at-twitter-f0c13298aee6#.ff2wajz71).

Le terme n’identifie pas vraiment encore un métier, il subsiste un certain flou, et les situations concrètes sont très diverses.

Robert Chang a une définition pragmatique très utile, qui prend en compte le « style » de la personne et la taille de l’entreprise/du projet.

C’est un continuum, depuis le statisticien qui sait nettoyer des quantités importantes de données et connaît le domaine d’expertise auquel on veut appliquer ces analyses, jusqu’au développeur qui connaît les statistiques, mais vise d’abord à produire des outils permettant d’exploiter ces statistiques.

Mais la différence principale tient au contexte : la taille de l’entreprise et le niveau déjà atteint en termes de structuration et de volume des données.

Petites entreprises ou début de projet Données : le travail consiste essentiellement à :

- extraire des données (logs serveurs, fichiers Excel, exports issus de logiciels métiers, etc.)
- transformer des données (nettoyer, lier entre elles, valider, etc.)
- charger des données dans un système local, souvent une base de données dans un premier temps

Taille moyenne : se mettre d’accord sur les principales questions qu’on veut poser aux données, et créer les outils permettant de poser (et reposer) ces questions. Des tableaux de bord, des visualisations, des rapports automatisés.

Grandes entreprises : si les données deviennent vraiment très volumineuses, l’architecture classique avec bases de données ne suffit plus, il faut utiliser d’autres outils (MapReduce, Hadoop, tout un bestiaire du Big Data), et les compétences elles aussi se spécialisent. Vous pouvez recruter un ingénieur Machine Learning, un spécialiste extraction de données, etc. Qui sont tous, si on veut, des Data Scientists.

L’intérêt de l’article c’est aussi qu’au-delà des définitions, Robert Chang donne aussi, dans le contexte de Twitter où il travaille, des exemples concrets de ce que fait un Data Scientist. La démarche, finalement, est simple et claire, même si la réalisation peut être extrêmement complexe.

Tout part d’une bonne question. Par exemple : « Pourquoi y a-t-il plus de comptes multiples par personne dans certains pays que dans d’autres ? »

Le travail consiste alors, d’abord, à voir de quelles données on aurait besoin. Existent-elles ? Si elles sont possibles à produire et comment ? Qui, au sein de l’entreprise, a besoin de pouvoir répondre à cette question ? Quelle est la meilleure façon de leur diffuser cette réponse (à jour) ?

Etc.

Sacré boulot.

## 2. Intelligence articielle : en fait.

Une abondance de données est également indispensable dans un autre secteur, qui se trouve être en incroyable expansion : l’Intelligence Artificielle. On en entend parler au journal du soir, mais c’est souvent sous forme d’une bouillie un peu indistincte.

J’ai croisé cette semaine un site qui permet de mieux se rendre compte de ce dont il s’agit en fait.

[Artificial Intelligence — Open Network](http://ai-on.org/projects) vient d’être lancé ce mois-ci, animé en particulier par François Chollet, auteur du logiciel de Deep Learning [Keras](https://keras.io/) et membre de l’équipe Deep Learning chez Google.

Le principe est simple :

- des problèmes sont mis en ligne, que divers acteurs, chercheurs, etc. cherchent à résoudre en utilisant les outils de l’intelligence artificielle ;
- des « aspirants Data Scientists » se portent volontaires pour tenter de résoudre tel ou tel problème ;
ils sont assistés, encadrés et soutenus par des scientifiques plus reconnus dans le domaine.

La liste des problèmes disponibles est parfaite pour toucher très concrètement du doigt en quoi consiste l’intelligence artificielle.

Deux exemples:

- Dans le domaine biomédical, identifier les articles scientifiques qui sont à risque de rétractation pour permettre ensuite un examen plus précis (et humain). Le problème peut tenir aux données source de l’article, à une intention de fraude, etc.
- utiliser des millions d’images d’IRM cardiaques pour repérer automatiquement le ventricule droit dans l’image et évaluer son volume pour détecter certaines maladies cardiaques.

Dans le même genre, j’ai vu aussi cette semaine dans The Guardian un article sur une tentative faite au University College London pour analyser des documents de procès permettant de déduire le jugement rendu.

On voit que toutes ces problématiques sont proches : on utilise des quantités importantes de données et on leur applique des algorithmes probabilistes pour arriver à un résultat.

Peut-être devrait-on moins dire que le logiciel « mange le monde », mais plutôt que le monde est ramené à la statistique — ce que Robert Musil avait dit, déjà. Et que c’est efficace.

## 3. Dépenser $50 à Shenzen

Je ne sais pas si vous vous souvenez de cette [vidéo de Wired sur Shenzhen](https://www.youtube.com/watch?v=hp6F_ApUq-c&index=5&list=LLoOA987bnc0z7PmSAzM4Kyw) que j’avais signalée il y a quelques mois. Cette semaine un article en complément : [Ce qu’on a pour 50 $ à Shenzhen](https://shift.newco.co/what-50-buys-you-at-huaqiangbei-the-worlds-most-fascinating-electronics-market-f0384d9fca32#.d0teoxyis). Un ingénieur qui travaille à Shenzhen pour créer un nouveau clavier d’ordinateur ergonomique a proposé à ses acheteurs un petit deal rigolo : je vous propose d’acheter pour 50 $ de merdes électroniques à Shenzhen, un peu au hasard, et je vous les envoie. Les 25 premières demandes étant arrivées dans l’heure, il s’est arrêté là, et le dimanche suivant, il est allé faire ses courses pour ses 25 clients :

- une lampe LED montée sur USB (0,11 $)
- un éventail monté sur USB (0,45 $)
- une fausse SD Card de 32 Gb, dont la taille réelle est de 8 Gb, dont il découvre qu’on lui aurait vendu au même prix si elle avait vraiment les 32 Gb (2,13 $)
- des badges de conférence, à accrocher à la poitrine, où le texte peut être programmé et affiché sur un écran LED (4,20 $)
- un câble lightning/microUSB (0,75 $)
- le clou du spectacle : une smartwatch (9,74 $), dont il découvre que le coût de fabrication est de 6 $.
- un mini-drone (9,74 $)

Le port vers l’Ouest coûte autour de 28 $.

## 4. Lever 10$M

La publication et le commentaire d’un « deck », c’est-à-dire d’un PowerPoint expliquant comment on a levé x millions de dollars est un art maintenant bien établi.

Et si certains sont trop généraux pour être honnêtes, d’autres sont tout à fait intéressants.

Je vois seulement cette semaine [celui publié en août par Mathilde Collin](https://medium.com/@collinmathilde/front-series-a-deck-f2e2775a419b#.akrt5fe1o), qui a levé 10 $ M pour frontapp, qui propose de nouvelles solutions au problème de la messagerie d’entreprise.

L’article, court, et les diapos, courtes aussi, valent la peine.

Quelques leçons, pour ce qui me concerne :

- tout le monde a des idées (et des opinions) : vous voulez lever des fonds ? Venez avec des *faits*. Des données solides, mais bien sélectionnées, pas une avalanche d’indicateurs : des faits ordonnés dans une direction, des faits qui font sens.
- le fait le plus important est aussi le plus simple, et le moins facile à « bidonner » : vous levez des fonds parce que vous avez déjà des réalisations, un historique que vous pouvez montrer.

Ce second point est important parce qu’il est souvent masqué par le discours général sur les startups, de kickstarter, etc. qui peut donner l’impression que « d’un coup » les choses peuvent exploser pour ton projet.

Mathilde Collin explique qu’elle a levé ces fonds en quelques semaines, et beaucoup, qui lisent peut-être un peu vite, s’imaginent que ce genre de chose peut arriver du jour au lendemain, sans se rendre compte des efforts de longs termes qu’il y a derrière, dans 99 % des cas.

Elle peut lever 10 M$ en quelques semaines *parce* qu’elle bosse beaucoup et bien depuis longtemps sur ce sujet, et qu’elle peut le prouver.

J’y ai pensé cette semaine aussi en entendant parler d’un kickstarter fait par deux étudiants d’une école de management de Lyon qui se contentait de mettre un boitier en plastique autour d’un raspberry pi préchargé avec l’émulateur de jeux [lakka.tv](http://lakka.tv/). Tout le travail est dans l’émulateur… et nos étudiants se contentent de packager le travail des autres. 

Ils s’imaginent que ce genre de succès se réchauffe au micro-ondes ; l’article de Mathilde Collin montre que c’est une méprise : il ne faut pas confondre la rapidité de l’explosion avec la rapidité du projet global, qui est presque toujours un travail de longue haleine.

Félicitations, donc, avec retard, à M. Collin et à son équipe pour sa levée de fonds.

## 5. Le logiciel mange… la photographie

Dans Medium [Steven Sinofsky s’extasie](https://medium.learningbyshipping.com/photos-how-tools-start-a-revolution-d9370a1ca1bc#.dnhf5jk4c) sur la qualité des photos de son iPhone 7. [Matt Haughey s’extasie](https://twitter.com/mathowie/status/791048483448852480) de son côté sur les photos de son Google Pixel.

C’est vrai que c’est beau…

Sinofsky pense que c’est une « révolution ». Le terme est galvaudé de nos jours, surtout dans les domaines technologiques, mais après tout : est-ce vrai ? Il insiste en particulier sur un « effet spécial » produit par ces deux téléphones : le bokeh, qui est le flou que vous avez en second plan des bonnes photographies. Une bonne photographie gère bien la profondeur de champ et avec ces téléphones, quand vous prenez un portrait, le second plan est en effet flou.

La citation ci-dessous illustre la façon dont ça fonctionne et pourquoi c’est important.

Pour produire cet effet, Apple utilise les informations de profondeur des deux caméras, un logiciel de Machine Learning qui calcule le sujet principal de la photo (la sélection lasso de Photoshop, si on veut), et un logiciel qui fait le rendu de l’arrière-plan) — qui n’est pas un simple flou, mais un flou calculé en fonction de la profondeur de champ.

Et finalement, c’est le sens de son article, et de beaucoup de comparatifs entre iPhone 7 et Pixel publiés ces dernières semaines : les caméras ont incroyablement progressé, certes, mais dans le haut de gamme des téléphones, elles se valent. Ce qui fait un bon appareil photo — téléphone, maintenant, c’est l’intelligence logicielle. 

On est loin de l’outil « yeux rouges » de jadis : le logiciel, en temps réel, calcule la photo, détoure les visages, repère des premiers plans, des seconds plans, améliore les uns, floute les autres.

Et plusieurs articles vus récemment notent d’ailleurs que les photographes amateurs attendent des améliorations de leur appareil-photo/téléphone via des mises à jour logiciel.

Sachant que le tout tient dans la poche, je peux très bien imaginer une télévision ou généralement une entreprise de médias envoyant son reporter sur le terrain avec un iPhone ou un Google Pixel, sans cameraman, sans photographe.

Je peux aussi imaginer le service communication de la grande entreprise XYZ se passant des services d’une boîte de production pour produire le diaporama et les 10 minutes de film, avec interview, de l’Assemblée générale des actionnaires.

Il y a des difficultés économiques dans l’air pour ceux qui vivent de ce type de prestations. Et du plaisir à n’en plus finir pour tous les amateurs qui vont produire photos et vidéos avec ces outils…

Pour finir la semaine en beauté, ci-dessous une vidéo tournée avec un téléphone Google Pixel.

{{< youtube 42silsqv1co >}}