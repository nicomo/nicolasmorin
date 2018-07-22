
+++
date = "2016-10-01T11:18:21+02:00"
description = "Internet cette semaine, comme si vous y étiez - 01/10/2016"
tags = ["internetzinc"]
title = "Internet zinc #25"
type = "post"
image = "img/iz-banner.png"
+++

## 1. DDoS — exemple

J’ai parlé la semaine dernière des attaques Distributed Denial of Service (DDoS) : je ne refais pas l’[explication](https://medium.com/internet-zinc/internet-zinc-24-e74731e6f316#.fj8vp3lpv) de 
ce qu’est une DDoS — faut suivre. Par contre il y a eu cette semaine un exemple parfait.

Résumé.

La victime, Brian Krebs, est un journaliste indépendant spécialisé justement sur les questions de sécurité 
informatique. Son blog, [Krebs on Security](http://www.krebsonsecurity.com/), a été attaqué par l’intermédiaire d’une DDoS. Son hébergeur, Akamai l’a 
défendu 48 heures puis, le coût de cette défense augmentant, a pris la décision, économique, de simplement virer 
Krebs on Security de ses serveurs. Le site est resté HS pendant 48 heures avant d’être à nouveau hébergé, cette fois 
par Google.

Une histoire riche comme un mille-feuille à la crème de banane. Regardons un peu sous chaque feuille.

Il semble que l’attaque soit liée à deux articles sur une entreprise, vDOS, qui offre son expertise et ses services 
de DDoS. Vous les payez, ils attaquent qui vous voulez. Deux responsables de la société ont été arrêtés en Israël. 
Ce type d’entreprise louche n’aime évidemment pas la publicité. Et l’objectif de cette attaque est de porter 
atteinte à la capacité de KrebsOnSecurity de s’exprimer : si aucun hébergeur ne veut de vous, votre liberté 
d’expression est anéantie. Les attaques informatiques de ce type sont fondamentalement des outils de censure.

Les hébergeurs n’ont pas de mission publique de défendre la liberté d’expression : ce sont des entreprises, qui vont 
arbitrer entre leur image (défenseurs de leurs clients, de la liberté, etc.) et la réalité de l’impact économique 
d’une attaque de ce type : si les ressources nécessaires pour contrer l’attaque deviennent trop importantes, comme 
c’était le cas ici, l’hébergeur n’a pas d’autre choix que de jeter l’éponge et couper le site attaqué de son réseau. 
Ce que comprend tout à fait Krebs, qui était hébergé gratuitement par Akamai.



Le site de Brian Krebs a été remis en ligne grâce à [Project Shields](https://projectshield.withgoogle.com/public/), un projet de Google qui offre, justement, un 
hébergement spécifique aux journalistes victimes de DDoS.

La taille de Google lui donne un statut très particulier. Est-ce une entreprise privée qui fait, elle aussi, un 
calcul entre son image et ses coûts ? Bien entendu. Mais l’équation est différente pour Google : les moyens dont ils 
disposent sont si importants qu’il serait plus pertinent, à mon sens, de les comparer non pas à une autre entreprise,
 comme Akamai, pourtant déjà très importante, mais à État-nation.

Digression : ce serait un « exercice de pensée » intéressant que de réfléchir à la possibilité, au moins théorique, 
de considérer à l’avenir des entreprises comme Google comme de nouvelles sortes d’États sans territoires.

Pour finir, sur un plan plus technique, deux dernières couches à notre mille-feuille :

le volume de l’attaque est un nouveau record : aux environs de 600 Gbs au plus fort de l’attaque. C’est un volume 
difficile à concevoir : chaque seconde, votre serveur reçoit des données représentant environ 50 films en streaming 
ultra HD. Ce niveau d’attaque s’approche dangereusement du niveau où le reste de l’usage d’internet est affecté : 
non pas seulement ce site, ou les sites chez un hébergeur donné, mais tout le monde est ralenti.

pour cette attaque, pour la première fois, semble-t-il, un grand nombre d’objets connectés ont été enrôlés. Votre 
webcam mal sécurisée, votre TV connectée, votre frigo « numérique », votre montre fitness, l’autoradio de votre 
voiture, etc. Ces objets sont souvent produits par des entreprises pour lesquelles le logiciel n’est pas leur cœur 
de métier ou leur compétence principale… et la qualité du code s’en ressent, de même que la rapidité des mises à 
jour de sécurité, etc.

Le meilleur article que j’ai vu sur cet épisode cette semaine est celui d’Ars Technica : [Why the silencing of 
KrebsOnSecurity opens a troubling chapter for the ’Net](http://arstechnica.com/security/2016/09/why-the-silencing-of-krebsonsecurity-opens-a-troubling-chapter-for-the-net/)

## 2. Docteur? C’est la noiraude. J’voudrais une montre…

En tout cas, il semble inévitable qu’il y ait très rapidement un beaucoup plus grand nombre d’objets informatisés 
et/ou connectés dans notre environnement, et que leur rôle soit de plus en plus intimement lié à notre quotidien.

Bloomberg Technology avait cette semaine un [article sur les évolutions de la montre d’Apple](http://www.bloomberg.com/news/articles/2016-09-26/apple-said-to-expand-healthkit-from-tracker-to-diagnosis-tool). Celle-ci a évidemment, 
à mesure que les modèles et leur logiciel progressent, de plus en plus de capacités. Et il est probable que ces 
capacités changent de nature. Jusqu’ici en effet, il s’agit essentiellement de collecter des données à peu près 
brutes : nombre de pas, battements cardiaques, etc. La suite logique, c’est d’interpréter ces données : comprendre 
que si votre rythme cardiaque pendant un effort de course est de 140, et qu’il vous faut 4 minutes et 28 secondes 
pour revenir à votre rythme moyen de 70, ça n’est pas la même chose que s’il vous faut 22 minutes. Dans le second 
cas, consultez votre médecin.

L’article cite en exemple une étude conjointe d’Apple et de l’Université Johns Hopkins qui utilise l’accéléromètre 
et la mesure du rythme cardiaque pour déterminer les éléments précurseurs d’une attaque.

Car le problème technique (intéressant) à résoudre, c’est celui des données : quelles données sont pertinentes, et 
validées, pour un usage clinique ? La montre n’est qu’un outil, qui n’a de valeur qui si les données sont collectées 
et exploitées de façon intelligente.

Si vous visitez votre cardiologue et qu’il peut voir votre profil cardiaque complet sur le dernier mois, c’est 
potentiellement un outil intéressant dans la relation patient-médecin. Maintenant s’il voit des quantités 
invraisemblables de données qui ne le concernent pas, il est peu probable qu’il puisse exploiter les quelques 
données qui, noyées dans cette masse, pourraient l’intéresser.

Dans la même logique, Fortune Mag a un [article sur l’assureur Aetna](http://fortune.com/2016/09/27/insurer-apple-watch-fitbit/), qui devrait lancer bientôt aux États-Unis un 
programme de subvention à l’achat de l’Apple Watch pour ses 23 millions de clients.

Dans une lecture dystopique de la situation, on peut imaginer qu’Aetna, voyant que je n’ai pas assez marché ce 
trimestre, augmente ma prime d’assurance.

Dans une lecture utopique, on peut penser qu’Aetna et moi avons un intérêt commun : que je sois en bonne santé et, 
si j’ai un pépin quelconque, un arrêt cardiaque par exemple, que ma montre le détecte immédiatement pour alerter les 
secours, me sauver la vie, limiter les coûts associés à mes soins…

## 3. Twitter est ma TV

J’ai regardé le débat Trump — Clinton de lundi soir, en direct : c’est un des avantages d’habiter dans le même 
fuseau horaire que la cote est des États-Unis. Enfin, j’ai regardé les 20 premières minutes (y’a des limites).

Pour les jeunes (pas moi) ou les branchés (moi) qui n’ont pas de télévision, il y avait plein de solutions pour 
regarder le débat par internet. On pouvait le regarder sur le site de NBC, sur Facebook, sur le site CSPAN 
(équivalent américain de La Chaîne Parlementaire), sur Twitter, etc.

Je l’ai regardé sur Twitter sur mon téléphone.

Globalement c’était très bien fait.

D’abord quand le débat démarre, on vous le signale relativement sobrement.

{{< figure src="/img/iz25-1.png" >}}

Vous avez ensuite la vidéo en haut de l’écran, dont la qualité, franchement, était parfaite, et les tweets qui 
s’actualisent en temps réel en dessous.

{{< figure src="/img/iz25-2.png" >}}

Maintenant ce que j’ai regretté, c’est que le flux de tweets sous la vidéo n’est pas *le mien*. Ce ne sont pas les 
gens que je suis. Ce qui dans un certain sens est intéressant parce qu’on ne veut pas rester enfermé dans sa bulle, 
mais en l’espèce ça partait dans tous les sens. Au final, je suis passé sur mon ordinateur pour ouvrir deux fenêtres 
twitter : une avec la vidéo, une de ma timeline avec les gens que je suis. Et qui étaient vachement plus 
intéressants que le flux général : eh, je les suis pour une raison.

Ce qui est certain c’est que les flux twitter apportent un élément de commentaire et, souvent, de fact-checking qui 
rend la chose vraiment plus intéressante que de simplement suivre le débat à la télévision.

Quelques jours plus tard, Nathan Heller avait un [billet sur le site du New Yorker](http://www.newyorker.com/culture/cultural-comment/the-first-debate-of-the-twitter-election) où il défendait l’idée que si 
l’élection de Roosevelt dans les années 1930 était l’élection de la radio, et celle de Kennedy dans les années 1960 
celle de la télévision, celle-ci est celle des réseaux sociaux et, tout particulièrement, de twitter.

Tout à fait d’accord.

Et par la même occasion Twitter devient enjeu de pouvoir. Le lendemain du débat, le hashtag #TrumpWon était dans les 
« tendances », contre toute évidence. Explication ? Les premiers tweets utilisant ce hashtag ont été publiés de 
façon coordonnée, et trouveraient (conditionnel) leur origine à… St Petersbourg. Il est de notoriété publique que la 
Russie tente de peser sur l’élection.

{{< figure src="/img/iz25-3.png" >}}

## 4. Mémoires d’un nécromancien

C’est le titre de la lecture de la semaine, un [billet de blog de Pieter Hintjens](http://hintjens.com/blog:125). Qui est de la taille d’un petit 
livre, en vérité. Pieter Hintjens est informaticien (magicien, nécromancien) depuis 35 ans. Il a été diagnostiqué en 
avril dernier d’un cancer en phase terminale. Ce sont, d’une certaine façon, ses mémoires professionnelles.

Nous sommes à ce moment où toute une génération qui a créé l’informatique telle qu’on la connait aujourd’hui, à 
partir des années 1970–80, commence à disparaître. C’est aussi la première génération qui a passé toute sa vie 
professionnelle, du début à la fin, dans l’informatique.

Ces mémoires sont fascinantes à plusieurs titres. Sur le plan technique, parce qu’il décrit des systèmes historiques 
(j’aime l’histoire des technologies). Mais surtout il parle en priorité de l’informatique d’entreprise : elle est 
moins décrite dans les livres d’histoires, mais c’est celle à laquelle sont confrontés le plus souvent les 
développeurs. L’informatique d’entreprise est presque par définition obsolète, et elle est l’otage, quasi 
systématiquement, de considérations économico-politiques qui n’ont rien à voir avec la technique.

Ce que décrit très bien le billet de Pieter Hintjens qui, par exemple, ne porte pas les consultants dans son cœur : 
« des menteurs professionnels ». C’était vrai dans son expérience, dans les années 1980–90, ça reste vrai dans mon 
expérience, dans les années 2000–2010. Pourquoi ? Parce que le client s’imagine que le consultant répond de façon 
neutre à la question posée, en adoptant le point de vue et l’intérêt du client, et que c’est en fait rarement le 
cas. Le consultant a ses propres intérêts à prendre en compte, qui peuvent parfois entrer en conflit avec ceux du 
client. Par exemple si on a le choix entre un projet simple, mais sans éclat, et un projet plus long qui vous 
permettra d’étendre la durée de votre prestation chez le client, ma foi…

Le rôle des considérations financières ; la lutte constante entre des systèmes obsolètes très implantés dans 
l’organisation et des systèmes dont il est évident, a posteriori, qu’on aurait dû les retenir bien plus tôt…

Il y a beaucoup de choses dans ce long billet.

Y compris la mention dans les années 1980, d’un « format préhistorique appelé EDIFACT »… que j’utilise encore en 
2016 dans un des systèmes que je gère.

## 5. Projets 20%

[Sam Soffes](https://soff.es/) est un développeur qui fait des applications iOS depuis 2008. Sur Twitter en début de semaine, il 
mentionne qu’on peut se connecter pour le voir éditer en temps réel sa « liste de projets perso ».

Il utilise pour ça l’application sur laquelle il travaille en ce moment : [Canvas](https://usecanvas.com/). C’est un éditeur de texte (en 
apparence) très simple, qui permet à une équipe de s’organiser, prendre des notes de réunion, faire des listes de 
tâches de façon collaborative. On est à plusieurs à pouvoir éditer le document en temps réel. Une fonctionnalité qui 
existe dans Google Drive, mais qui est proposée ici dans une application autonome.

Sa liste de projets concerne des idées d’applications sur lesquelles il aimerait travailler. J’ai trouvé ça 
intéressant parce que ça souligne un point sur lequel le public se méprend très souvent concernant les startups, ou 
la créativité en ligne en général : l’idée n’est souvent pas si importante qu’on croit.

Je veux dire par là que l’idée ne représente que la portion congrue d’une startup ou d’un projet quelconque. 
Arbitrairement, je serais tenté de dire que c’est 5 % pour l’idée, 45 % pour les personnes et leurs compétences, et 
50 % d’exécution. J’entends par exécution à la fois l’huile de coude pour réaliser le projet, et la capacité à le 
faire de façon focalisée et efficace, sans trop de « perte ».

Et dans ce contexte, partager ses idées à l’avance est utile. Quelqu’un, certes, pourrait vous « piquer » l’idée, 
mais ce n’est que piquer 5 % du projet, ça ne lui donne pas vraiment d’avantage s’il lui manque les 95 % restants. 
Et en sens inverse, vous pouvez avoir un retour sur vos idées qui vous aide à mieux les calibrer si besoin.

J’ai moi aussi sous le coude une [liste de « projets 20 % »](https://docs.google.com/document/d/17eSNQw47VzW_9sHvUoNVTsQLgchNv0WxwGZLBu0CP54/edit?usp=sharing). Je viens de la publier, et chacun peut la commenter : cf 
nicomo side-projects.

Le fichier contient pour l’instant :

- app mobile Le Paris de Balzac
- Minymapp : Webapp de messagerie sensible à la géolocalisation
- Ce que je lis : big data
- un livre d’artiste sur téléphone
- 8-bit Requiem
- un tour du monde des aéroports

Détails dans le fichier : les commentaires sont bienvenus.