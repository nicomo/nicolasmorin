+++
date = "2016-09-24T13:24:37+02:00"
description = "Internet cette semaine, comme si vous y étiez - 24/09/2016"
tags = ["internetzinc"]
title = "Internet zinc #24"
type = "post"
feature_image = "/img/iz-banner.png"
+++

## 1. De la programmation en milieu universitaire

Pour commencer la revue de la semaine, deux articles qui, a priori, n’ont rien à voir l’un avec l’autre, mais dimanche dernier quand je les ai lus, mon cerveau les a curieusement fusionnés en une seule entrée, double, d’Internet Zinc.

Dans [The Economist](http://www.economist.com/news/science-and-technology/21695377-professors-unprofessional-programs-have-created-new-profession-more) un papier sur une sorte de nouveaux business : les entreprises qui s’attachent à toiletter le code des programmes produits dans les universités. Si, comme moi, vous avez travaillé un peu dans les universités, vous saurez d’une part qu’il s’y produit des quantités de code informatique, et d’autre part que ce code est généralement de qualité assez médiocre.

Non pas que les universitaires soient incompétents (du moins il n’y a pas dans ce milieu plus d’incompétents qu’ailleurs), mais les conditions de production du code sont telles qu’il est difficile de faire « propre » : il est l’œuvre d’une succession de stagiaires, d’étudiants, d’enseignants qui ne peuvent y consacrer que la portion congrue de leur temps. Et l’objectif est souvent de faire une « preuve de concept », de faire marcher le bouzin : c’est une vision institutionnelle à très court terme qui fait qu’on se préoccupe peu de faire quelque chose de stable, propre et durable.

Mais il y a souvent dans ces bases de code universitaire des idées vraiment intéressantes, et l’article de The Economist décrit quelques tentatives d’entreprises qui tentent de comprendre le programme d’origine, du moins son idée centrale, et réécrivent le programme dans un langage de programmation moderne et avec la qualité attendue d’un programme destiné à être réellement diffusé dans le monde.

C’est ainsi qu’Oxford Computer Consultants a recréé, à partir de fragments universitaires, un programme aujourd’hui utilisé dans la gestion de l’infrastructure électrique en Grande-Bretagne.

En retour certaines universités tendent d’inciter leurs chercheurs à programmer proprement dès le départ. Un ancêtre, toujours vivant, de ces efforts ? Le programme Software Carpentry, issu de l’Université de Toronto et cher à au moins un lecteur de cette newsletter : [Software Carpentry](http://software-carpentry.org/) tente, depuis 1998, de diffuser les « bonnes méthodes » de programmation dans le milieu universitaire. À nous Sisyphe.

## 2. L’art de la guerre

Le [second article](https://www.schneier.com/blog/archives/2016/09/someone_is_lear.html) a été écrit par Bruce Schneier.

Ce spécialiste de la sécurité informatique explique qu’un « agent », très vraisemblablement un état, sans doute la Chine, est en train de tester la possibilité de « fermer internet ». Ne pas seulement couper internet dans tel pays, ou filtrer tel service (Facebook, Google…) dans une optique de censure, mais purement et simplement couper le réseau internet au niveau mondial.

Il s’agit d’attaques dites « distributed denial-of-service » (DDoS) : vous envoyez au serveur attaqué des demandes en nombre telles qu’il n’arrive plus à répondre. Au plus simple, pour un site web, c’est comme si vous simuliez un grand nombre d’utilisateurs se connectant en même temps sur la page, au point que le serveur s’écroule.

L’infrastructure d’internet est gérée par un assez petit nombre d’acteurs. Par exemple Verisign gère les domaines « génériques » (.com, .net, .org, etc) et si leurs serveurs s’écroulent l’essentiel des sites et des mails les plus courants sera inutilisable.

Les attaques dont parle Bruce Schneier sont des tests : on attaque non pas pour mettre le service par terre, mais pour obliger le service attaqué à répondre et à dévoiler ses défenses et leurs capacités. On multiplie les types d’attaques, on regarde comment et à quelle vitesse le système réagit si on monte progressivement le niveau de l’attaque, etc.

Il y eut, en [2007 déjà](https://en.wikipedia.org/wiki/2007_cyberattacks_on_Estonia), une attaque de ce type contre un pays : l’Estonie. Et il semble très clair désormais qu’internet, dans n’importe quelle guerre future, sera une cible de premier plan : on bombardera les immeubles, on tuera les enfants, on violera les femmes, on gazera les populations… et on coupera Gmail, la téléphonie IP, etc.

Il y a certainement en ce moment une certaine paranoïa à ce sujet : en Grande-Bretagne ces dernières semaines l’État s’est inquiété de voir que la Chine allait participer à la construction d’une centrale nucléaire (et s’il y avait un bouton à Pékin permettant de couper la centrale via internet ?), ou de voir que les caméras de surveillance installées dans le pays sont pour beaucoup fabriquées en Chine (et s’il y a une « porte dérobée » dans ces caméras ? Est-ce que la Chine nous regarde ?).

Pourquoi est-ce que mon cerveau a immédiatement connecté ces deux articles, celui de Bruce Schneier et celui sur le (mauvais) code produit dans les universités ? Parce que le code universitaire est très présent dans l’infrastructure du réseau, d’une part, et que même le code commercial est souvent de qualité discutable. internet et un grand nombre d’applications qui tournent sur internet sont faits « à l’arrache » et notre existence numérique est en fait d’une grande fragilité. Comme le disait il y a quelques mois Zeynep Tufekci dans un [article remarquable](https://medium.com/message/why-the-great-glitch-of-july-8th-should-scare-you-b791002fff03#.thejgsymj) : nous construisons des gratte-ciels de code en carton dans des zones sismiques.

## 3. Pokemon Go, c’est mai 68? Ou bien?

J’étais au Canada fin juillet, début août quand la fièvre Pokemon Go s’est emparée des masses. Certains ont vu Mai 1968, moi j’ai vu des centaines de personnes se promener dans toute la ville, les poches déformées par les batteries de rechange, à la recherche de Pokemons. La comparaison est un peu provocatrice, mais je la maintiens : Pokemon Go est le signe ponctuel d’une révolution aussi profonde que celle de mai 1968. C’est un microévénement lourd de sens : Cohn-Bendit interpellant le ministre à la piscine de Nanterre.

L’argumentation (sans la comparaison) m’est fournie par John Hanke, le patron de Niantic, la société qui fait Pokemon Go, qui était [interviewé cette semaine dans le podcast Recode/Decode](http://www.recode.net/2016/9/19/12965348/pokemon-go-trading-events-battling-niantic-john-hanke-recode-podcast). Une excellente interview, qui donne en 1 heure la meilleure lecture du phénomène que j’ai entendu jusqu’ici.

Ce qu’il faut comprendre c’est d’une part que Pokemon Go est fondamentalement différent d’autres jeux ayant eu du succès ces dernières années, par exemple Angry Bird, et d’autre part que Pokemon Go ne vient pas de nulle part, que c’est une construction qui est « dans les tuyaux » depuis une quinzaine d’années.

Commençons par le second point.

En 2001, John Hanke fonde Keyhole, une société qui fait de l’imagerie satellite à un moment où les ordinateurs personnels commencent tout juste à avoir les capacités suffisantes pour gérer ce type d’informations. Keyhole est à la limite entre le monde universitaire, qui fait de l’imagerie scientifique, et le plus grand public. Pour se situer, Encarta, l’encyclopédie de Microsoft, jusque là diffusée par CD-ROM, est disponible sur le web à partir de 2000.

John Hanke vend Keyhole à Google en 2004, juste avant que la société ne soit cotée en bourse, et Keyhole évolue au sein de Google pour devenir Google Earth (2005). John Hanke est pendant 6 ans responsable de tout ce qui touche aux cartes chez Google : Maps, Earth, Street View, maps sur mobile, etc.

En 2010 il crée une sorte de startup indépendante à l’intérieur de Google, Niantic, avec un accord de 3 ans : au bout de 3 ans, il pourra ou bien réintégrer Google ou bien devenir indépendant.

Niantic ne développe pas tout de suite Pokemon Go, mais un autre jeu, [Ingress](https://www.ingress.com/). Les grands principes sont là : réalité augmentée, jeu dans l’espace public, qui valorise le jeu coordonné en équipes (plutôt que les joueurs individuels), et la marche. Par exemple, si vous essayez de vous déplacer trop rapidement dans Ingress, en moto ou en voiture, le téléphone va détecter votre mouvement « anormal » et limiter votre capacité de jeu. Ingress rencontre un grand succès : 1 million de joueurs dans la première année.

Au bout des 3 ans convenus, Niantic devient une société indépendante, mais dont Google reste le principal actionnaire. Puis Nintendo entre au capital, Niantic fait une sorte de version Pokemon Go d’Ingress et, à l’été 2016, c’est l’explosion… que les serveurs de Niantic encaissent remarquablement bien… parce qu’ils s’appuient sur les capacités de Google.

Ce que je veux dire avec cette petite histoire, c’est que la réalité augmentée, et le succès de Niantic, viennent de loin, et selon une trajectoire familière : les débuts sont à la frontière de la recherche universitaire et de l’informatique grand public ; on se consacre à un projet techniquement difficile (la cartographie en temps réel), qui est résolu avec des investissements importants pendant une dizaine d’années (Google) ; ce travail explose enfin comme phénomène culturel quand le travail technique, scientifiques, informatique de fond a été assimilé par l’ensemble de la société (tout le monde a Google Map dans sa poche).

Et c’est exactement pour ça, pour revenir à mon premier point, que Pokemon Go n’a rien à voir avec une passade comme Angry Birds : les racines (cartographie, mobilité, temps réel) sont très profondément plantées. C’est un des premiers exemples d’un entre-tissage à grande échelle de l’informatique et de la vie sociale.

Je passe devant le Ferry Terminal à Downtown Toronto, je vois un Butterfree, tu passes au même endroit tu vois toi aussi ce Butterfree : nous sommes dans la même réalité. Personnellement, avec ses yeux rouges et sa tête ronde, ce Butterfree je lui trouve un air de Cohn-Bendit.

Autant je suis sceptique sur la diffusion de la Réalité Virtuelle au-delà de secteurs de niche, autant je pense que la Réalité Augmentée a un potentiel quasi révolutionnaire, parce que c’est fondamentalement un phénomène social, plutôt qu’un phénomène culturel.

## 4. Crédits Sésame pas sérieux s’abtenir.

Connaissez-vous les Credit Scores ? C’est très courant dans le monde anglo-saxon, en Scandinavie ou encore en Allemagne. Le principe général est que votre « crédit financier » est établi non pas directement par la banque que vous sollicitez pour un prêt, mais par une entité indépendante qui évalue votre situation financière en utilisant pour partie des données publiques, telles que votre âge, votre emploi, etc. Ces scores sont utilisés par les banques, mais aussi par les entreprises de téléphonies, les assurances, les agences immobilières, etc.

C’est une façon commode de répondre à la question : êtes-vous solvable ?

Ce principe est en train d’évoluer, comme tout le reste, avec le mobile. En particulier dans les pays qui n’ont pas de système de Credit Scores et doivent en « inventer » un.

L’émission [Spark](http://www.cbc.ca/radio/spark/327-working-less-social-credit-scores-and-more-1.3762032/need-a-loan-look-no-further-than-your-messaging-app-1.3762038), de la radio publique canadienne CBC, parle dans son dernier numéro de la façon dont le mobile est utilisé en Chine pour calculer une sorte de score.

L’app de messagerie [WeChat](https://pay.weixin.qq.com/index.php/public/wechatpay), très répandue en Chine, propose un service de paiement par mobile, et comme ils rémunèrent les entreprises pour chaque paiement, vous êtes incité, dans les boutiques et les restaurants, à utiliser ce mode de paiement plutôt que du cash ou votre carte de crédit. Du coup, WeChat a une idée assez claire de votre historique de consommation et, associé aux autres informations contenues dans votre téléphone, est en position de calculer un score de crédit. Le géant Alibaba (on dit souvent : l’Amazon chinois) propose un service similaire, baptisé « Crédit Sésame » (ce terme est un peu l’équivalent numérique des barres d’immeubles installées « rue des mimosas »). Une fois que vous avez un « crédit sésame », il peut être utilisé de multiples façons. Par exemple, beaucoup de Chinois indiquent leur Crédit Sesame dans leur profil sur le site de rencontre [baihe.com](http://baihe.com/).

Au Nigeria, [Social Lender](http://sterling.sociallenderng.com/) utilise aussi les informations du mobile et l’environnement social de son utilisateur (profils Facebook, LinkedIn, Twitter, etc.) pour calculer grâce à l’empreinte numérique de la personne un score qui lui permet d’évaluer les risques de défaut sur des projets de microcrédit. Il s’agit de petites sommes, 10 $, 40 $.

La notion d’e-réputation traîne un peu partout depuis longtemps. Souvent dans une optique « 1er monde » qui se préoccupe surtout de la réputation des riches, entreprises ou particuliers occidentaux. Ici il s’agit de quelque chose de tout à fait différent : l’e-réputation se forge sur un terrain qui a besoin d’une mesure un tant soit peu objective, ou qui en a les apparences, et n’a pas pour l’instant d’alternatives.

À noter : en Chine c’est la banque centrale qui incite fortement les entreprises de l’internet (pas les banques) à mettre en place ces systèmes.

## 5. Du cash et des intermédiaires

En tout cas, on peut utiliser une carte de crédit, un QR code ou une puce sans contact dans le téléphone, mais on utilise de moins en moins le cash.

Ce que regrette l’article [War on Cash](http://thelongandshort.org/society/war-on-cash). L’argent liquide est anonyme : la valeur est attachée à l’objet qu’on transfère ; or, dans tous les autres modes de dépense, le principe de la transaction est d’être inscrite dans un registre : on note que j’ai 5 € de moins et que vous avez 5 € de plus. Qui le note ? Le plus souvent, les banques. Une transaction immatérielle est à la fois moins anonyme et plus indirecte : je suis à la brocante, je vous achète une collection de 45 tours, je paie d’iPhone à iPhone ? C’est, par-dessus les disques qu’on échange, ma banque qui parle à votre banque. C’est, pour les auteurs de cet article un tantinet parano, mais très intéressant, ajouter une couche de magie technologique à une structure de contrôle social vieille comme le monde.

En même temps, j’ai entendu parler dans mon entourage ces derniers temps de la façon dont les émigrés (en l’espèce, les immigrés vietnamiens en France) géraient leurs transferts bancaires, et comment ils essayaient en particulier de limiter les frais bancaires associés. On m’a parlé spécifiquement de deux méthodes : Facebook et Bitcoin.

La méthode Facebook est la plus simple : des pages et des groupes en nombre servent de libre marché où on annonce vouloir transférer une somme donnée dans un sens ou l’autre. On a besoin de gérer deux choses : le change VN Dongs/Euros ; et le transfert d’une personne à une autre. Vous êtes en région parisienne et vous voulez envoyer 500 € à un grand-père à Saïgon ou Da Nang ? Vous trouvez sur Facebook quelqu’un qui, en région parisienne, a besoin de 500 € ; et cette personne a un parent qui, à Da Nang, donnera 12 M Dongs à votre grand-père. Ce n’est pas dématérialisé, il y a du cash, mais il n’y a pas d’intermédiaire : Facebook sert de place de marché.

La méthode Bitcoin consiste à acheter des bitcoins avec vos 500 € parisiens et, une fois rentré à Saïgon, à transformer vos bitcoins en Dongs. Cette fois c’est largement dématérialisé, il y a encore un intermédiaire, une banque qui accepte de prendre vos bitcoins, mais c’est un simple change entre monnaies.

C’est cette complexité de la réalité des transactions bancaires et de la gestion du crédit qui me font, de plus en plus, penser que la question de la confidentialité est de celles qui n’ont qu’une solution : que la question elle-même s’évapore progressivement, sans jamais recevoir de réponse nette, si ce n’est que les choses ont tellement évolué que la question elle-même, finalement, ne se pose plus dans les mêmes termes.

Et c’est peut-être le plus révolutionnaire dans tout ça : on ne change pas les réponses à de vieilles questions ; on change les questions.