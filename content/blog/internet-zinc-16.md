+++
date = "2016-05-28T08:00:00+02:00"
title = "Internet zinc #16"
description = "Internet cette semaine comme si vous y étiez - 28/05/2016"
tags = [ "internetzinc" ]
type = "post"
image = "img/iz-banner.png"
+++


## 1. Le web de contenu ne veut pas mourir

Craig Mod mène une sorte de vie idéale : il partage son temps entre le Japon, où il fait de longues randonnées sur les sentiers des temples bouddhistes, et New York City ; il écrit et il fait des projets web.

Il y a quelques années il a entamé un projet intéressant : hi.co. C’était tout à la fois un site web, un réseau social, une plateforme de blog fortement orientée sur le thème du voyage et du lieu.

J’en avais fait un usage détourné, traduisant en Anglais et publiant au jour le jour, avec la date d’origine, une partie du Journal de Flaubert voyageant en Égypte.

La semaine passée, Craig Mod a annoncé qu’au 1er Sept. 2016, [hi.co fermerait ses portes](https://medium.com/@craigmod/archiving-our-online-communities-e5868eab4d9a#.rq3tnldok). Ils ont 200.000 visiteurs par mois, ce qui est clairement insuffisant pour poursuivre. Il explique bien qu’ils sont tombés dans un moment de transition : l’idée était de commencer sur mobile, en déplacement, sur le terrain, dans un lieu, avec un « moment » qu’on documente avec une photo, une note rapide, et qu’on va ensuite compléter sur un PC. Mais entre temps le mobile s’est imposé, et on ne va plus « compléter sur un PC ».

Le plus intéressant, c’est la façon de fermer hi.co qu’ont choisie Craig Mod et ses collègues.

En partenariat avec Norsam Technologies et les Los Alamos Laboratories, ils vont graver l’intégralité du contenu de hi.co sur des disques de nickel. En 5 copies. Les mêmes disques qui ont été placés sur Voyager et envoyés dans l’espace en 1977. Leur durée de vie est de 10.000 ans.

La Bibliothèque du Congrès a accepté de prendre un des cinq disques de hi.co.

S’il y a quelqu’un dans la salle qui travaille à la Bibliothèque nationale de France ou à la Bibliothèque et Archives Nationales du Québec… il reste 4 disques.

C’est une magnifique fin, bien sûr. Et si voulez laisser un peu de vous sur un disque en nickel à la Bibliothèque du Congrès, l’accès à hi.co reste ouvert jusque fin août.

## 2. Qu’est-ce que programmer en 2016?

Le podcast de l’agence Postlight, dont j’avais déjà brièvement parlé en mars, a accueilli cette semaine Natalie Podrazik. Elle est développeuse, spécialisée dans les apps sur iOS, dans une petite agence new-yorkaise (10 personnes).

L’interview est passionnante.

Les détails sont passionnants : elle raconte la façon qu’elle a d’espionner les gens qui utilisent leur iPhone dans les transports en commun — et les différences d’usage dans le bus par rapport au métro (offline), etc.

L’arc de son parcours est aussi passionnant. Natalie Podrazik a un master d’informatique, où elle a fait en particulier beaucoup de programmation en C. Et elle explique très bien comment, en une dizaine d’années, son métier a changé.

Explication point trop technique.

Un langage de programmation est lui-même un programme, qui permet à un développeur de donner des instructions à l’ordinateur. Ils ont leurs spécificités : certains sont bien adaptés pour parler à un navigateur web ou une base de données (les langages utilisés prioritairement pour le web, PHP par exemple). D’autres, à l’autre bout de l’échelle, sont bien adaptés pour parler au matériel qui est sur l’ordinateur, manipuler la mémoire, gérer les disques durs, ce genre de chose. Il y a ce qui est « en haut » (web, par ex) et ce qui est « en bas » (mémoire par exemple). Et généralement, quand on est en bas on est très formel (on ne fait pas n’importe quoi, c’est bien rigoureux ces affaires-là), et en haut c’est plus « free-style ».

Je caricature, mais vous voyez l’idée.

C'est « en bas ». Quelqu’un qui développe en C a rarement l’occasion de voir des utilisateurs de son programme dans l’autobus.

Et c’est fondamentalement ce qui a changé avec l’iPhone. Qui, initialement, se programmait dans un langage appelé Objective-C, qui est une « extension » de C.

Des gens comme Natalie Podrazik, qui venaient de la culture du langage C, se sont donc retrouvés à programmer en Objective-C des apps pour iPhone et iPad. Or dans ce contexte, Apple contrôle une grande partie de ce que vous pouvez faire. Par exemple la façon dont sont gérées les notifications est contrainte : c’est la même pour toutes les apps, vous ne pouvez pas « faire votre sauce ». Et au bout, il y a des utilisateurs : Madame Michu.

Natalie Podrazik le dit très bien : avant elle avait l’habitude de faire des applications « en bas », qui lui faisaient en cas d’erreur des messages du type « crash mémoire processus #12345321 ». Maintenant Mme Michu laisse un commentaire dans l’app store disant : « marche pô ».

Résultat, notre développeur C fait maintenant non seulement encore un quasi-C, mais est aussi obligé de gérer toutes les interfaces, l’expérience utilisateur et sa psychologie. Il faut maîtriser un spectre de compétences beaucoup plus important que jadis, et même pour quelqu’un qui, comme elle, est spécialisé iOS, c’est devenu tellement énorme qu’il est difficile de tout connaître.

## 3. Cambriolage de bitcoins

Eric Voorhees est le patron de ShapeShift, une société qui est spécialisée dans le « change cryptomonétaire ». Il y a Bitcoin, mais il y a aussi Litecoin, et Ethereum, et d’autres. Si vous avez des Bitcoins que vous voulez changer en Litecoins, ShapeShift vous fait le change.

Dans un [billet qui se lit comme une nouvelle policière](http://moneyandstate.com/looting-of-the-fox/), il décrit cette semaine comment sa société s’est fait cambrioler : environ 200.000 $ partis en fumée.

Je vous épargne les détails (qui sont passionnants pourtant, et simplement expliqués), mais en gros leur responsable serveurs (Bob) leur a d’abord volé un certain nombre de bitcoins, puis s’est enfui. Ils ont changé les clés, verrouillé leur sécurité, etc., mais Bob avait eu le temps d’installer un malware sur une machine de bureau (un programme qui lui permettait de voir l’écran d’un collègue, et quand celui-ci a nettoyé sa clé pour en créer une nouvelle, « propre » après la fuite de Bob, ce dernier n’avait qu’à lire la nouvelle clé à l’écran), qui lui a permis de revenir discrètement et virtuellement dans les murs. Enfin, pas lui directement : le Russe auquel il a revendu les informations est revenu pour un second cambriolage.

Moralité :

- les emmerdes viennent presque toujours de l’intérieur
- même quand vous travaillez sur un sujet sensible comme Bitcoin, la pression du quotidien fait que vous ne mettez sans doute jamais assez vos affaires au carré — du moins pas assez tôt.

Encore, là ce n’était que 200.000 $. Le mois dernier, la banque centrale du Pakistan s’est fait voler 81 millions de $ par des hackers, vraisemblablement en provenance de Corée du Nord.

## 4. Velvet Drone

John Cale est connu pour le son « drone » de son violon sur les albums du Velvet Underground.

Je découvre cette semaine une expérience qu’il a réalisé au Barbican Center de Londres avec Liam Young… et de vrai drones. C’est un spectacle de musique qui inclut des drones, qui volent dans la salle, relaient la voix de John Cale, amplifient le bruit de leurs hélices, tournent autour les uns des autres, dialoguent entre eux, avec la scène et la musique, etc.

C’est une expérience fascinante, bien expliquée dans une vidéo de 10 minutes.

{{< youtube y4QQzzU2diM >}} 

## 5. TerraPattern

Pour finir un nouveau projet, orienté sur la recherche : [TerraPattern](http://www.terrapattern.com/) est un moteur de recherche qui vous permet de pointer un carré sur une carte d’images satellites et de rechercher tous les carrés “similaires”.

Pointez sur un bouquet d’arbres dans un parc et vous récupérez tous les arbres d’une ville sur une carte. Ou pointez un parking, vous aurez tous les parkings de la ville, et ainsi de suite.

Les résultats sont exportables et exploitables en dehors du site, qui vise les journalistes et les chercheurs. Intéressant pour les chercheurs, et pour les autres, vous pouvez vous perdre dans les images pour une heure sans même vous en rendre compte.