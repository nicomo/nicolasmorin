+++
date = "2016-06-11T08:00:00+02:00"
title = "Internet zinc #18"
description = "Internet cette semaine comme si vous y étiez - 11/06/2016"
tags = [ "internetzinc" ]
type = "post"
image = "img/iz-banner.png"
+++

## 1. Des femmes

Cette semaine Hillary Clinton a plus ou moins bouclé la primaire démocrate et, sauf accident de dernière minute, elle sera la candidate de ce parti pour les élections de novembre. C’est une première : si on prend en considération les démocrates et les républicains seulement, il y a eu deux femmes candidates au poste de vice-président, Sarah Palin en 2008 et Geraldine Ferraro en 1984 ; mais il n’y avait jamais eu de candidate de ces partis au poste de Président.

Pour fêter cet événement, j’ai regardé un peu quelques sites intéressants qui aident les femmes dans le secteur Tech aux États-Unis.

[Girls Who Code](https://girlswhocode.com/) fait remarquer qu’en 1984 les femmes représentaient 37 % des diplômés en Informatique, et que ce chiffre est descendu à 18 % et c’est ce pourcentage qu’elles veulent changer. Leur stratégie est double.

Pour les filles à partir de 12 ans, Girls Who Code organise des « clubs » : ils sont gratuits, et le matériel informatique est fourni, ils durent 2 heures par semaine tout au long d’une année scolaire, ils sont organisés le plus souvent directement au sein d’une école, hébergés dans une bibliothèque publique, des centres d’accueil et de loisirs, etc. Il s’agit de réaliser un projet, en petits groupes, qui permet d’apprendre la programmation.

Pour les filles de 16–18 ans, Girls Who Code propose un programme d’été de 7 semaines, du lundi au vendredi de 9 h à 16 h. C’est aussi gratuit, et l’organisation peut même prendre en charge certains frais, d’hébergement ou de transport par exemple. Les stages sont hébergés au sein d’entreprises du secteur Tech. Il s’agit à la fois d’apprendre de l’informatique « pure », et aussi de se familiariser avec le secteur professionnel de l’informatique.

Une autre organisation vise non plus les enfants, mais les femmes qui veulent être chefs d’entreprises dans le secteur Tech : [Women Who Startup](http://www.womenwhostartup.co/) est basée à Denver (Colorado). Denver, soit dit en passant, est un écosystème de startups extrêmement dynamique, en partie du fait de la présence sur place de la firme d’investissement [The Foundry group](http://www.foundrygroup.com/), et de [TechStars](http://www.techstars.com/), un accélérateur de startups par ailleurs détenteur, si on peut dire, de la « franchise » des startups week-ends.

Bref, Women Who Startup fait du réseau, du soutien, de l’entraide pour femmes entrepreneuses Tech.

On peut citer aussi [Girl Develop It](https://www.girldevelopit.com/), présent dans 53 villes américaines, qui fait aussi de la formation en développement pour les femmes, mais vise les adultes. GDI collabore avec d’autres organisations comme [Women in Tech NYC](http://www.womenintechnyc.com/), qui offre un panel de services depuis la formation, jusqu’au réseau, au conseil d’entreprise, etc., toujours pour les femmes, mais à New York.

Ces organisations se sont beaucoup développées aux États-Unis ces dernières années, et je suis personnellement très optimiste sur le développement de la place des femmes dans le secteur informatique… qui en a bien besoin.

Évidemment, il y a eu ces dernières années, et il y aura encore dans les années prochaines, des déchainements réguliers contre les femmes dans ce secteur, mais personnellement j’interprète ça comme les derniers soubresauts d’un machisme en déclin. Comme les blancs sudistes des romans de Faulkner. Ce qui indique aussi à quel point ils peuvent, malgré tout, rester dangereux.

Mais toutes les organisations citées ici ont un poids cumulatif, et je suis, encore une fois, optimiste à ce sujet.

## 2. Brève visite à Android

Je poursuis dans ma série récurrente de réflexions sur le métier et les compétences de développeur — que voulez-vous, il se passe quelque chose d’intéressant à ce sujet sur mon écran chaque semaine.

Il s’agit cette fois d’un podcast, Under The Radar, fait par Marco Arment et David Smith, deux développeurs indépendants spécialistes des applications iOS. Marco Arment, en particulier, est connu pour l’application instapaper, qui permet de sauvegarder n’importe quelle page web pour la ligne plus tard, hors ligne.

Dans cet épisode, [David Smith fait du développement Android](https://www.relay.fm/radar/30). Il explique avoir fait une seule app rapide il y a plus de 4 ans, et s’être ensuite consacré exclusivement à iOS. Quatre ans après, il prend 2 semaines pour refaire un tour de l’environnement Android et dans ce podcast il propose une analyse assez équilibrée de cette expérience, qui permet aussi aux non-développeurs de comprendre un peu mieux ce que veut dire développer (pour Android).

La majorité des développeurs travaille en utilisant un integrated development environment (IDE), qui est un peu le « traitement de texte » du développeur, qui propose des fonctionnalités de vérification du code, d’autocomplétion, etc. Pour Android, il y a un IDE spécifique : Android Studio (l’équivalent chez Apple pour iOS s’appelle XCode). David Smith commence par ça : sa surprise à constater la qualité d’Android Studio. Vu du point de vue de Google, c’est un point important : si vous voulez que les développeurs fassent des apps de qualité pour Android, il faut leur donner des outils de travail de qualité.

Il souligne en particulier la qualité des émulateurs. Vous ne pouvez pas avoir dans votre tiroir 50 téléphones ou tablettes Android pour tester votre application, et Android Studio gère des émulateurs qui vous permettent de simuler, par exemple, un Nexus 5x, ou un vieux HTC Droid.

Puis vient, justement, la question de la « fragmentation » d’Android. Le problème est historiquement le suivant : Apple fabrique seul les machines iOS (vous ne pouvez pas acheter un « iPhone par Motorola»), et il n’y a qu’un nombre très limité de tailles d’écran. Quand vous faites une application, vous savez à l’avance sur quelles tailles d’écran elle devra s’afficher, et c’est plus facile à gérer. De même pour la version d’iOS : Apple met tout le monde à jour plus ou moins en même temps. Sur Android, il y a des milliers, littéralement, de machines aux tailles toutes différentes, et aux versions d’Android toutes différentes.

David Smith explique que cet inconvénient, Google a su le tourner en avantage sur certains aspects : en particulier, la mise en page est extrêmement souple et fluide et s’adapte aux différentes tailles d’écran un peu comme un site web, parce que c’était pour eux une contrainte dès le départ. Côté Apple par contre, la simplicité initiale s’est un peu complexifiée avec l’ajout de nouvelles tailles d’écrans, de la montre, etc. Mais Apple n’avait pas dès le départ cette notion de maquette fluide, et tente de l’ajouter maintenant a posteriori.

Mais la fragmentation reste un problème : le Google Play Store vous dit, en administrateur, combien de modèles de machines connues sont compatibles avec votre code. Pour l’app de David Smith : 12 346. Plus de 10 000 modèles de machines Android hantent le monde. Et en conséquence, pour un développeur, c’est un environnement beaucoup moins sécurisé : il est toujours possible que votre code plante sur une machine que vous ne connaissez pas.

Dernier point, que David Smith ne mentionne pas, mais que je me permets d’ajouter : la documentation. Elle est (pour iOS aussi sans doute, mais cette fois c’est moi qui ne connais pas) incroyablement complète et détaillée, avec des tutoriels, des exemples, et un site de référence qui s’apparente à une sorte d’encyclopédie d’Android. Qui vous dit par exemple que la pour que votre app interagisse avec le lecteur d’empreintes digitales présent sur certains modèles (mon Nexus 5x par exemple), il faut utiliser la Classe FingerprintManager, et qui vous explique par le menu ce qu’elle fait et comment.

Développer aujourd’hui, c’est aussi dans une proportion très très importante se documenter : lire, lire, lire, et apprendre « comment fonctionnent les choses ».

## 3. Less is more (parfois)

Adrian Colyer a un blog intéressant, mais ardu : 5 fois par semaine, il publie un billet qui résume et discute une publication scientifique dans le domaine de l’Informatique. En début de semaine, il a détaillé une [étude quantitative sur les problèmes de productivité et de coordination des développeurs de projets Open Source](https://blog.acolyer.org/2016/06/06/from-aristotle-to-ringelmann). Les auteurs étudient 580.000 contributions (commits, dans le jargon) à 58 des projets les plus populaires sur le site de code GitHub.

L’idée générale est tirée d’une étude de 1913 par Ringelmann qui montre que les performances individuelles diminuent quand le nombre de participants à un projet augmente. Ce qu’ont confirmé, pour le secteur informatique, nombre d’études empiriques depuis les années 1980 : au-delà d’un certain nombre, finalement assez faible, de développeurs, ajouter un développeur supplémentaire aura pour effet de dégrader la productivité du groupe, parce que le temps de coordination et les difficultés de communication vont compenser négativement l’ajout d’une ressource humaine.

Une tentative de contourner ce problème consiste à faire un logiciel qui soit le plus « modulaire » possible et permette, par son architecture, de diminuer les besoins de coordination entre différents petits groupes de développeurs travaillant chacun sur son module.

Ce que cherche à faire cette étude, c’est de voir si ces contraintes existent de la même façon pour les logiciels libres. Il y a certainement des particularités dans ces projets : il y a un grand nombre de contributeurs « de passage » par rapport à un projet commercial, qui contribue une part très faible du code. Mais il n’empêche, l’étude montre que la règle reste valable dans ce cas particulier : même dans le logiciel libre, ajouter des ressources (bénévoles) réduit la progression du projet. Pourquoi ? Toujours la même histoire : le logiciel libre est fait, pour un très fort pourcentage de son code, par un petit noyau de personnes, avec un grand nombre de personnes contribuant à la marge ; mais gérer ces personnes qui travaillent à la marge « mord » sur la productivité du noyau dur des contributeurs. A fortiori, il semble donc que chercher à recruter activement un plus grand nombre de contributeurs soit une erreur (du moins passé une certaine taille).

Un papier intéressant qui confirme que le logiciel libre ne s’abstrait pas si facilement des invariants de la gestion des groupes, et que l’informatique, même « libre », c’est 2/3 de « politique organisationnelle » pour 1/3 de code — et un zeste de citron.

## 4. Identité

魏 冕 — Mian Wei est un designer et artiste multimédia qui étudie à la Rhode Island School of Design. Il a publié sur son site un projet d’étudiant vraiment passionnant, intitulé : [Prothèse de remplacement pour authentification biométrique par empreinte digitale](http://mian-wei.com/#/identity/).

Les téléphones qui se débloquent par scan de l’empreinte digitale (iPhone et Nexus récents) sont moins sécurisés qu’on le croit en principe. Le problème de l’empreinte, c’est qu’elle est personnelle, certes, mais vous ne pouvez pas vraiment en changer ni la modifier ; et par ailleurs en l’utilisant vous donnez votre empreinte à {Apple || Google}. Et ce n’est pas super sécurisé, finalement : l’an passé, des chercheurs japonais ont réussi à rentrer dans un iPhone en forgeant une empreinte à partir d’une photo et de gummy bears fondus…

Mian Wei propose une réflexion intéressante à ce sujet en proposant, dans son projet, d’utiliser une sorte de prothèse, qui se présente sous la forme d’une boite de sparadraps qu’on colle sur son index pour utiliser avec le téléphone pour, mettons, une journée, et qu’on jette ensuite. Son slogan : « A fingerprint a day, keeps the spies away » (une empreinte par jour contre les espions), qui est un détournement du diction Anglais « An apple a day keeps the doctor away ».

Allez voir son site, il y a plein de projets vraiment intelligents : http://mian-wei.com/

## 5. La Petite Mort

Et maintenant, quelque chose de complètement différent, parlons sexe.

La Petite Mort est un jeu fait par un petit studio danois indépendant, [Lovable Hat Cult](http://lovablehatcult.dk/). Techniquement, le jeu part d’un algorithme, appelé Cellular Automata, qui permet de simuler la réponse aux stimuli d’un organisme par propagation de cellule en cellule. C’est utilisé en biologie, en particulier. Ici, l’algorithme est utilisé pour simuler la stimulation d’un sexe féminin par le contact du doigt sur la surface de l’écran. Un [article du Guardian](https://www.theguardian.com/technology/2016/jun/06/female-orgasm-simulator-la-petite-mort-apple) explique très bien le projet, qui est à la limite de l’art, de l’érotisme, du jeu vidéo classique, et de l’étude. Car c’est un jeu où vous pouvez, bien sûr, perdre : si le sexe n’apprécie pas vos mouvements, il vous le fera savoir. Je devrais dire : les sexes, car il y en a plusieurs (comme des niveaux ? Level 1, Level 2?), et chacun a ses particularités et le jeu requiert, comme dans la vie, attention et expérimentation.

Un joli projet : L’Origine du Monde, multiplié, « vivant » dans votre téléphone.

{{< vimeo 154840989 >}}