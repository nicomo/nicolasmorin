+++
date = "2016-11-19T08:00:00+02:00"
description = "Internet cette année comme si vous y étiez - 19/11/2016"
tags = [ "internetzinc", "machine learning", "securité", "ethnologie", "musique" ]
title = "Internet zinc #32"
type = "post"
image = "img/iz-banner.png"

+++

## 1. Sécurité, en pratique

La semaine passée, j’ai indiqué quelques moyens simples d’un peu mieux sécuriser votre pratique internet. C’était rapide, dans une lettre déjà assez longue et déprimante. Mais ça vaut le coup d’y revenir plus en détail : les articles n’ont pas manqué, dans l’ambiance de cette semaine, pour vous aider dans tout ça.

Parmi cette abondance, je retiens deux articles simples. Quincy Larson vous explique comment <a href="https://medium.freecodecamp.com/tor-signal-and-beyond-a-law-abiding-citizens-guide-to-privacy-1a593f2104c3#.i6d9gdam1" alt="encrypter votre vie">encrypter votre vie en moins d’une heure</a>.

Il commence par recommander, comme je l’ai fait la semaine passée, d’utiliser l’authentification double pour vos emails (mot de passe + SMS ou autre lien avec le téléphone). Ça a fait débat : vous donnez votre téléphone aux mêmes personnes qui ont déjà votre mail ; google (pour Gmail) et les autres ne sont pas fiables. Peut-être, mais je recommande la même chose que Quincy Larson quand même. Votre petit fournisseur de mails indépendant sera plus facilement hacké que Google, et il n’a pas les moyens de contester une décision en justice, ce que Google (ou un autre « gros ») pourra peut-être faire. Mais le fond de l’affaire, c’est que le mail n’est pas facile à sécuriser : si vous voulez vraiment comploter, utiliser un autre moyen de communication.

Encryptez votre disque dur d’ordinateur : Windows et macOS le proposent en standard, vous n’avez aucune excuse pour ne pas le faire.

Encryptez votre téléphone : c’est aussi standard sur les versions récentes d’iOS et Android. Aussi : éteignez votre téléphone avant de passer une frontière ou une sécurité d’aéroport.

SMS : utilisez Signal.

J’avais oublié la navigation web la semaine dernière : il recommande d’utiliser Tor. Pour le coup son explication est simple, ce qui est assez rare, et pour votre ordinateur et pour votre téléphone.

Dans un autre article, <a href="https://medium.com/@TeacherC/90dayactionplan-ff86b1de6acb#.f08wa982a">Candace Williams complète</a> : utiliser un réseau privé virtuel (VPN). Ça brouille les pistes et ça vous permettra de contourner les interdictions de pays pour regarder votre série TV préférée, double bonus.

Le consensus qui émerge semble :

- VPN, par exemple https://www.tunnelbear.com/
- Tor, dont la facilité d’utilisation est encore insuffisante, je trouve
- 2 facteurs d’authentification pour les mails
- <a href="https://whispersystems.org/">Signal</a> pour les SMS et les appels.

En sachant que rien de tout cela n’est entièrement fiable. Si vous voulez raconter des secrets à quelqu’un, mieux vaut le rencontrer.

Une autre piste serait d’admettre que la sécurité n’est pas 100 % possible, et qu’il faudrait ajouter une « couche d’obscurcissement ». C’est l’idée de Conor Friedersdorf dans <a href="http://www.theatlantic.com/technology/archive/2016/10/the-future-of-privacy-is-plausible-deniability/504776/">un article de The Atlantic</a> du mois dernier, qui imagine un service, auquel vous pouvez vous abonner, qui insère dans vos mails authentiques un certain nombre de faux mails, et effectue sur les principaux moteurs de recherche des requêtes « bidon » en votre nom. Confronté à une accusation quelconque, vous pouvez nier : je suis client d’Obscurcissement Co., ce n’est pas mon mail.

J’avais de mon côté imaginé il y a quelques mois quelque chose de proche pour les réseaux sociaux : vous connectez vos comptes sociaux au service et on crée un autre flux qui mêle vos vrais messages et d’autres, pris à d’autres personnes ou inventés.

Autre élément de sécurisation possible : segmenter les usages. Arrêtez d’utiliser votre compte Google perso pour du boulot, faites une boite mail séparée pour les usages de type réseau sociaux et pour les liens familiaux, etc.

Et j’arrête là avec la (saine) parano, mais comme j’avais été un peu vite là-dessus la semaine dernière, je pense que ça valait le coup d’y revenir.

En tout cas il est toujours difficile d’écrire cette lettre à l’ère Trump + 2 semaines. Parce que le moral n’y est pas, mais aussi parce que toutes les sources internet que je consulte habituellement sont saturées par cette question.

Essayons néanmoins.

## 2. la ligne de front de la connectivité

Jan Chipchase est le fondateur d’un studio de recherche ethnographique, [Studio Radiodurans](http://www.studiodradiodurans.com/), dont j’ai déjà parlé ici quand ils ont diffusé, libres de droits, un lot de photos magnifiques sur Myanmar. Ils publient des études étonnantes, sur l’usage de Facebook chez les fermiers du Myanmar, les transferts d’argent par téléphone au Somaliland, etc.

Jan Chipchase publie là une liste de [61 observations sur le futur](http://www.studiodradiodurans.com/61-glimpses-in-the-future ) à partir d’un voyage au Tadjikistan et dans l’ouest de la Chine. L’introduction, en quelques lignes, dit tout de leur démarche : « J’ai pensé séparer cette liste entre technologie et comportements, mais c’est beaucoup plus intéressant de mêler les deux. »

Et il y a quelques perles dans cette liste.

> La Chine est sans doute la société de consommation au niveau de confiance le plus limité au monde. Si un produit peut être contrefait, il le sera. Par nécessité, ils ont les consommateurs les plus avertis au monde.

Il mentionne aussi qu’en 2009 suite à des émeutes, le gouvernement chinois a coupé Internet dans la province de Winjiang pendant un an, et qu’aujourd’hui la connectivité est si intégrée à tous les aspects de la société qu’une coupure de cette nature empêcherait l’Etat de contrôler la population, plutôt qu’elle ne gênerait les opposants. Que par contre l’État mise sur le contrôle des déplacements des personnes, avec des contrôles d’identité aux stations-service par exemple.

Encore, ville de 4,3 millions d’habitants au centre de la Chine, a une attitude aussi cool que Tokyo. Enfin que les moines tibétains préfèrent iOS [qui a géré avant Android, et mieux dans un premier temps, l’alphabet tibétain].

Et son entrée numéro 1 : 

> si vous voulez comprendre comment notre planète va évoluer au 21e siècle, passez du temps en Chine, Inde, Indonésie, au Nigéria et au Brésil.

## 3. Musique de jeux vidéos

Un court [article du Guardian](https://www.theguardian.com/music/2016/nov/07/abbey-road-studio-final-fantasy-xv-soundtrack-london-philharmonic-orchestra) nous apprend que le légendaire studio Abbey Road est de plus en plus utilisé pour des enregistrements de partitions de musiques de jeux vidéos. L’article mentionne quelques compositeurs et quelques signes de la reconnaissance progressive de ces musiques. Une compilation des « Meilleures musiques de jeux vidéos » qui atteint le hit-parade des albums US, un concert de musique de jeux au Barbican, etc.

L’article mentionne aussi quelque chose de plus intéressant : le jeu influe sur la musique en ce sens que par rapport à un film, il y a moins de notions d’un arc narratif, avec début, milieu et fin, et qu’en conséquence les partitions sont elles-mêmes moins narratives.

L’article m’a aussi attiré l’œil, car j’ai acheté cette année mon premier album de musique de jeux. La bande-son de Fez (super jeu par ailleurs), par Disasterpeace. Ce musicien vient de sortir une autre bande-son pour le jeu Hyper Light Drifter. Et comme toute musique aujourd’hui, on la trouve sur [YouTube](https://www.youtube.com/watch?v=bq7a_ktfYck).

## 4. Machine Learning et diagnostique

[InformationWeek](http://www.informationweek.com/big-data/big-data-analytics/stanford-study-will-inspire-any-it-pro-intrigued-by-machine-learning/d/d-id/1326695    ) signale cette semaine une étude publiée en août dernier dans Nature Communications qui regarde dans quelle mesure un algorithme peut détecter des cellules cancéreuses sur une photographie.

L’étude est restreinte aux cellules de cancers du poumon et cherche un résultat assez fin, pas seulement oui ou non, mais aussi le niveau du cancer (types I à IV, en termes de gravité). Ce que j’ignorais, d’abord, c’est que la pratique actuelle, où un médecin, dans un premier temps, regarde visuellement la photographie, donne des résultats très décevants : plusieurs pathologistes ne seront d’accord sur le diagnostique que dans 60 % des cas.

L’algorithme, sur un lot d’un peu moins de 10 000 images, a trouvé la bonne réponse dans 75 % des cas. Par ailleurs, il a évidemment trouvé la réponse beaucoup plus vite que le pathologiste.

Cet exemple est sans doute une bonne illustration de ce qu’on peut espérer du machine learning : c’est un formidable outil pour réaliser avec fiabilité des tâches d’analyse préliminaires qui vont nous aider à faire notre travail. Ici, aider le médecin à diagnostiquer.

Je pense qu’il faut penser à l’Intelligence artificielle/Machine Learning de la façon suivante. Est-ce une tâche intellectuelle effectuée par un humain en moins de 2 secondes ? Par exemple analyser une image de cellule de poumon et décider si la cellule est cancéreuse? Alors ça peut être fait par l’IA.

En tout cas cette étude, qui montre ce que peuvent apporter de positif les technologies de Machine Learning, nous change un peu de la vision apocalyptique de l’informatique qui nous cerne en ce moment. Youpi.

## 5. La 2de vie du mail

Avez-vous remarqué que l’email ne veut pas mourir ? C’est une bête coriace. Il y a eu toute une époque, mettons ces 10 dernières années, où on pouvait l’imaginer disparaissant : les blogs, les SMS, les outils de chat lui menaient la vie dure. Et puis non : j’ai fermé mon blog il y a plusieurs années, et j’écris une newsletter. On croit rêver.

Dans [A List Apart, un article](http://alistapart.com/article/the-coming-revolution-in-email-design) nous explique même qu’il est au bord d’une révolution, d’une renaissance. L’article est destiné aux développeurs web, il est un peu technique, mais l’idée principale c’est que le mail pourrait se rapprocher beaucoup du web.

Actuellement, un mail peut contenir du HTML, mais de façon très limitée. Par exemple Gmail n’autorisait pas jusqu’ici les développeurs à détecter, dans le code de leur email, la taille de l’écran sur lequel il est en train de s’afficher. Il ne peut pas s’adapter et, si vous lisez le mail, conçu pour un ordinateur, sur un téléphone, le résultat sera désastreux.

Cet aspect-là est en train de changer, et que vous lisiez cette lettre d’info sur un grand écran ou un téléphone, elle devrait s’afficher correctement…

D’ailleurs, digression statistique, voici la répartition de vos usages du mail :

Desktop : 72,5 %

- Gmail : 51,7 %
- Apple Mail : 9,4 %
- Thunderbird : 6,0 %
- Outlook 2016 : 2,0 %
- Outlook 2013 : 2,0 %

Mobile : 27,5 %

- iPhone : 20,8 %
- Chrome Mobile : 4,0 %
- Android : 1,3 %
- Windows Phone : 1,3 %

Mais les développeurs commencent à aller au-delà de cette gestion des tailles pour amener d’autres attributs du web dans le mail : les transitions et les animations, qui rendent le mail plus joli et plus ergonomique, mais aussi permettent d’insérer dans le mail, dans l’exemple de l’article, des présentations de produits ou de logiciels.

Enfin, des actions arrivent qui restent à l’intérieur du mail : avoir un mail avec une présentation de produit… et un bouton pour l’acheter sans sortir du mail.

Microsoft et Google semblent réinvestir dans le mail, y compris dans un client comme Outlook…

Outlook ! L’avenir n’est pas toujours ce qu’on croit.
