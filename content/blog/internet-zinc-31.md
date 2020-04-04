+++
date = "2016-11-12T08:00:00+02:00"
description = "Internet cette année comme si vous y étiez - 12/11/2016"
tags = ["internetzinc"]
title = "Internet zinc #31"
type = "post"
feature_image = "/img/iz-banner.png"
+++

## 1. Oh, la belle bleue ! Ah non, tiens, c’est rouge…

J’ai suivi les élections américaines derrière mon ordinateur. Et il est certain qu’on pouvait tout à fait suivre les événements sans télévision. Il y avait abondance d’informations et de commentaires de toutes sortes. Toute la journée Google News Lab, qui avait un partenariat avec des médias traditionnels (la radio publique WNYC, la chaine de télévision hispanophone Univision, le quotidien USA Today…), a mis en ligne des cartes identifiant les problèmes de file d’attente, d’intimidation devant les bureaux de vote, etc. ABCNews a diffusé toute la journée et la soirée en direct sur sa page Facebook. Il y a eu aussi l’expérience intéressante d’ExitPollLive, une application d’un jour, très simple : vous ouvrez l’app, vous cliquez sur la tête du candidat pour lequel vous avez voté, vous avez 30 secondes pour expliquer votre choix à la camera. Le résultat est un flux ininterrompu de témoignages.

J’ai regardé pendant peut-être une demi-heure en fin d’après-midi et c’était assez fascinant. Assez inquiétant aussi : beaucoup de témoignages en faveur de Trump (pas un politicien, va nettoyer le système, etc.), en faveur de candidats tiers (Clinton est corrompue, Trump est un salaud, je vote pour XY), beaucoup de conneries (j’ai mis mon nom sur le bulletin, j’ai voté Lincoln, etc.).

Le site slate.com avait aussi une expérience intéressante : un partenariat avec la startup [VoteCastr](http://www.slate.com/votecastr_election_day_turnout_tracker.html) qui essayait de prédire le résultat du vote sans attendre 20h, tout au long de la journée, en utilisant des données historiques (élections passées), économiques et sociologiques, les sondages, et aussi le taux de participation des différents contés en fonction de leur profil sociologique.

Après 20h, les résultats ont commencé à arriver, et les choses les plus intéressantes, une fois éliminés les commentaires sans fin d’abcnews et consorts, étaient les choses les plus factuelles :

- le blog de http://fivethirtyeight.com/, qui avait les résultats au fur et à mesure, mais aussi plein d’autres informations sur, par exemple, le taux de chômage dans l’est de l’Ohio, le pourcentage de femmes diplômées au Texas, etc.
- le site du NYTimes avait les visualisations les plus jolies et le site à l’ergonomie la mieux faite. Des données détaillées, oscillant à mesure qu’arrivent de nouvelles informations, etc. C’était bien beau…

![nytimes](/img/nytimes_201611.png)

Quelques heures plus tard Trump triomphait.

## 2. Data Science mon cul!

La naïve promesse d’algorithmes tous puissants, ayant accès à des quantités invraisemblables de données et prédisant de façon quasi déterministe toute notre vie, de nos goûts en matière d’e-commerce à nos élections, s’est évaporée.

Nate Silver et ses statisticiens à http://fivethirtyeight.com/ avaient un job : prédire le résultat du jour. Échec total. Pourquoi ? Au fond parce que ça n’a jamais été qu’une agrégation de sondages avec quelques données de chômage par-dessus pour cacher la misère.

Le discours autour de ces sondages a changé, il s’est technicisé : quand jadis on donnait le résultat au public, maintenant on fait de longs billets techniques pour expliquer comment on est arrivé au résultat. Ce qui est certainement une bonne chose : quelqu’un peut aller vérifier en cuisine comment est faite la saucisse. Mais qui a un effet pervers : ça a l’air compliqué donc ça a l’air valide.

La présentation a aussi beaucoup changé, l’aspect dynamique des représentations en particulier donnant l’illusion d’une adaptation constante à la réalité.

Ces deux évolutions vont dans le même sens : l’autorité de la donnée est renforcée. Mais comme la réalité du résultat s’est chargée de nous le rappeler cette semaine, à la fin c’est rien que des sondages.

L’historien [Allan Lichtman](http://www.nytimes.com/2016/11/10/arts/yes-he-thought-trump-would-win-no-he-didnt-use-hard-data.html) avait, lui, le bon résultat et le NYTimes lui demande ce qu’il pense de tout ça. Sa méthode est beaucoup plus simple, une série de 13 questions Oui/Non portant sur la situation politique, économique, etc. Par exemple : « l’économie est-elle en récession ? ». Sa conclusion est que la situation était propice à une attaque de l’extérieur et que Trump avait toutes ses chances. Concernant le mouvement de Data Science dans des domaines comme les sciences politiques, ici les élections, son opinion est assez claire aussi, me semble-t-il : cela ne sert à rien tant que vous ne posez pas les bonnes questions, et pour poser ces questions, il faut faire appel à un historien plutôt qu’à un statisticien.

Amen.

## 3. Internet sent-il le fumier?

Je n’ai pas très bien pris le résultat. J’ai fait une partie de mes études en Angleterre, je parle anglais, je vais régulièrement aux États-Unis, ma bibliothèque est peut-être aux 2/3 constituée de livres anglophones, le matin je regarde le NYTimes et le Guardian, et une fois de temps en temps, de loin en loin, Le Monde. Le monde anglo-saxon est une sorte de seconde patrie, pour ce qui me concerne. Ça me cause parfois des problèmes d’ailleurs, quand je suis, sur certains sujets comme la liberté de parole par exemple, plus proche de valeurs américaines que de valeurs françaises — qui peuvent parfois être assez éloignées, en fait.

Bref, je suis resté en position fœtale pendant plusieurs jours, ne me relevant de temps en temps que pour regarder des vidéos de Richard Feynman sur YouTube.

Ci-dessous, 10 minutes de Feynman sur la méthode scientifique : ça vous fera le plus grand bien ; je vous attends.

{{< youtube 0KmimDq4cSU >}}

Je me suis relevé vendredi matin. Comment Trump a-t-il pu gagner ? Que signifie sa victoire ? Il y a toutes sortes de réponses, bien entendu, qui touchent à l’économie, aux relations internationales, à la structure des partis politiques, aux institutions, à mille causes.

Ici, je ne parle que d’une chose : internet. La question est donc de savoir si internet a contribué à la victoire de Trump.

De nombreux doigts accusateurs sont pointés vers Facebook, avec des titres rageurs comme « [Trump a gagné grâce à Facebook](http://nymag.com/selectall/2016/11/donald-trump-won-because-of-facebook.html) » dans NYMag ou « [Facebook a laissé tomber l’Amérique cette année](http://mashable.com/2016/11/09/facebook-kill-news-feed-trump/#6wp2Gof3Umq6) » dans Mashable.

Ce qui est ironique, c’est que l’accusation classique contre Facebook, ou Google, était plutôt jusqu’ici d’influencer le vote en faveur de Clinton. Maintenant on les accuse d’avoir fait le lit de Trump : malheureusement, cette seconde accusation me semble beaucoup plus crédible que la première.

Par exemple les fausses news disant que le Pape avait appelé à voter Trump ont été vues des millions de fois dans les dernières 48 heures avant le vote, beaucoup plus que n’importe quel article de fond du NYTimes. Les médias sociaux ont été « militarisés » par l’extrême-droite.

Facebook répond pour l’instant à ces accusations par un argument qui est constant dans leur positionnement, depuis plusieurs années : nous sommes une plateforme, nous sommes neutres, et il n’y a aucune preuve que nos algorithmes influent en quelque façon que ce soit sur les perceptions du public.

C’est un déni de responsabilité. Comme l’explique bien Zeynep Tufekci, si vraiment Facebook avait si peu d’influence, ils ne vaudraient pas 350 milliards de $.

Il n’en reste pas moins que les réseaux ont été instrumentalisés — militarisés — par l’extrême droite. Ce n’est pas un accident isolé : c’est un angle mort d’internet qu’on aurait dû comprendre il y a bien longtemps. La promesse d’internet, d’une désintermédiation, d’un espace technique permettant à chacun de s’exprimer en faisant sauter les verrous institutionnels, a été trahie : les extrémistes ont déversé des torrents de fumier dans ces tuyaux, et Facebook ne peut pas nier l’odeur. Mais c’est un problème général d’internet : vous avez lu les commentaires sous un article du Monde ?

Pour autant il est impossible de revenir sur cette désintermédiarisation : un article de NiemanLabs explique bien que les forces à l’œuvre dans ce processus sont importantes ; c’est une question structurelle ; juste dire qu’on va par un coup de baguette magique redonner son autorité à la presse ou, encore pire, « encadrer » ou « réguler » la parole sur internet ne marchera pas.

Par contre, un travail de fonds est nécessaire pour reconnaitre qu’internet n’est pas une plateforme : c’est un espace social.

Et cette analyse devrait être étendue (il me faudrait 10 lettres pour le faire) à bien d’autres secteurs d’internet. Par exemple, OTTO, le semi-remorque autonome, a fait ce mois-ci son premier transport officiel, 20.000 bouteilles de bière transportées et livrées sans chauffeur — si l’on compare la carte des résultats électoraux avec celle des métiers on constate que Trump a remporté tous les états où le métier le plus courant est… chauffeur routier. Nos concitoyens n’en ont rien à foutre des voitures autonomes, ils veulent savoir « comment le gamin va s’en sortir ».

## 4. La logique ou la guerre.

J’aime cette citation de Paul Valéry, dont j’(ab)use souvent :

> Entre les hommes il n’existe que deux relations : la logique ou la guerre. Demandez toujours des preuves, la preuve est la politesse élémentaire qu’on se doit. Si l’on refuse, souvenez-vous que vous êtes attaqué et qu’on va vous faire obéir par tous les moyens.

Si, comme on le dit souvent depuis quelque temps, nous sommes dans une époque post-factuelle, où la vérité (le pape n’a pas appelé à voter Trump) est noyée dans des torrents d’inanités, de mensonges, d’attaques, alors c’est la guerre.

Pour ce qui me concerne, internet est le champ de bataille.

Les conséquences d’une présidence Trump pourraient être énormes pour internet. Il est un partisan résolu de la surveillance d’internet, de la censure des médias et d’internet, du contrôle par l’état américain de l’infrastructure d’internet, etc.

Pour nous limiter à internet, donc, le problème principal est sans doute qu’il va pouvoir s’appuyer, pour la mise en place de ces idées, sur un complexe sécuritaire mis en place et soutenu par ses prédécesseurs, George W. Bush et Barack Obama. La NSA est maintenant à son service. C’est un des aspects les plus déprimants de toute cette affaire : un gouvernement démocrate (et démocratique) a laissé passer une opportunité unique de limiter la surveillance de masse ; au contraire, elle a été légitimisée, légalisée sous son mandat ; elle est maintenant léguée, sous forme d’une « nouvelle normalité » de surveillance, à un dictateur en herbe.

Notons que le problème est exactement le même dans nombre d’autres états démocratiques : GCHQ en Grande-Bretagne, des services similaires en Australie, en Nouvelle-Zélande, au Canada, en France. En France surtout, l’année 2016 a été terrible pour les libertés individuelles, les libertés sur internet et l’état de droit. Des élections présidentielles ont lieu en mai prochain. Marine Le Pen est bien positionnée dans les sondages. Elle pourrait hériter de l’appareil sécuritaire mis en place par Sarkozy puis Hollande/Valls.

Comme dans toutes les guerres, les lignes de front vont bouger. La répartition des forces est souvent présentée de la façon suivante : GAFA, autres entreprises internet plus petites, société civile, états. La tentation est grande pour la société civile de s’allier avec l’État — démocratique — contre les GAFA. Mais l’État est aussi l’un des adversaires les plus dangereux d’internet et de ses libertés, comme on vient de le voir. Que se passe-t-il si l’État se met d’accord avec les GAFA aux dépens de la société civile ? Ce qui est très possible, par exemple quand l’État demande, hors système juridique, aux GAFA de réguler les « discours haineux ».

La société civile seule ne remportera pas cette guerre. Elle est trop faible, elle a besoin à la fois de diviser l’adversaire et d’avoir des d’alliés, qu’il lui faudra aller chercher au sein des GAFA et des sociétés internet, au sein des États.

J’attends de voir comment va réagir chacun des GAFA. Je ne suis pas optimiste pour Facebook, comme vous l’aurez compris. On verra dans les semaines et les mois à venir ce qu’il en est pour les autres. Si Amazon, Google et Apple « tombaient » tous les trois du côté de l’État, la bataille deviendrait très difficile.

## 5. Que faire ?

L’élection de Trump fait suite au Brexit, à des années d’érosion des libertés démocratiques. Je ne crois pas que c’est un accident, je ne crois pas non plus que l’effet serait en réalité limité. Ça sent la fin d’époque. Et le plus grand danger d’un système autocratique, c’est peut-être sa capacité à faire passer l’anormal pour un nouveau normal à se couler discrètement dans le moule de la réalité. Par exemple, au hasard, à faire durer un état d’urgence pendant 12 mois et à intégrer ses attributs dans la loi « de tous les jours ».

Que faire ?

Vous pouvez commencer par vous protéger. Il n’est pas réaliste de demander à la population dans son ensemble de devenir experte en cryptographie, d’installer des clés sécurisées, etc.

Mais quelques mesures simples peuvent aider. Utiliser, pour vos SMS et si possible vos appels téléphoniques, une application encryptée, par exemple WhatsApp (sans faire le lien entre compte WhatsApp et compte Facebook svp) ou Signal, utiliser Gmail si vous voulez, mais sécurisez correctement votre compte avec une authentification double (mot de passe + SMS). Essayez d’avoir des mots de passe dignes de ce nom. Utilisez par exemple une application comme 1Password pour les gérer et utiliser un mot de passe « master » correct. Par exemple les premières lettres d’une phrase facile à retenir pour vous, AdPFagsp80 pour « Ainsi donc Phileas Fogg avait gagné son pari », tirée du Tour du Monde en 80 jours.

Si votre téléphone ou votre ordinateur a des mises à jour à faire, faites-les rapidement : le plus souvent elles bouchent des trous de sécurité.

Quant au matériel la règle est assez simple : plus il est récent, plus il est haut de gamme, plus il est sécurisé. Personnellement, j’ai un Android haut de gamme, encrypté par défaut. J’attends de voir comment les choses tournent, mais il est possible que j’achète un iPhone à l’avenir, et un nouveau Mac Book Pro, mieux sécurisé que ses prédécesseurs.

La tentation est forte, le problème touchant internet, de dire qu’il faudrait s’organiser sur internet. C’est une erreur. Ne mettez pas en ligne votre stratégie sur internet, pas plus que vous ne mettriez (j’espère) des photos de votre enfant de 4 ans sur son pot avec son nom marqué en dessous et une géolocalisation attachée au cliché. Ne discutez pas tactique non plus sur un espace public comme internet. Travaillez dans des cercles étroits, construisez des réseaux de soutien, regardez de qui se passe autour de vous, n’acceptez pas la normalisation de l’anormal.

En attendant, j’ai fait 2 dons ce matin : un à l’ACLU, l’autre à la Quadrature du Net.

À la semaine prochaine et, comme disait Edward R. Murrow, « Bonsoir, et bonne chance ».