+++
title = "Internet zinc #14"
date = 2016-05-14T15:14:03+02:00
description = "Internet cette semaine comme si vous y étiez - 14/05/2016"
tags = [ "internetzinc" ]
type = "post"
feature_image = "/img/iz-banner.png"
+++

## 1. Sonic Pi

Je parle régulièrement ici de tentatives artistiques qui s’expriment sous forme numérique, par exemple Jennifer Morone, évoquée dans le tout premier numéro d’Internet Zinc.

Par ailleurs nos sociétés, qui voulaient il y a un siècle que les enfants deviennent ingénieurs grâce à Mecanno, veulent aujourd’hui toujours qu’ils deviennent ingénieurs, mais grâce à la programmation. Il n’y a qu’à voir la rubrique dédiée aux enfants sur le site Pimoroni.com ou le site https://code.org/ pour voir que l’offre pour les « enfants programmeurs » ne manque pas (surtout en Anglais il est vrai). Quand je dis que « nos sociétés » sont obsédées par les enfants-codeurs, j’exclus bien entendu le ministère de l’Éducation nationale, qui préfère laisser les parents qui savent et peuvent donner à leurs enfants l’avance numérique nécessaire par rapport aux enfants dont les parents ne savent ni ne peuvent. 

Toujours est-il que souvent les deux préoccupations (artistique et éducative) se rejoignent : presque toutes les tentatives pour amener les enfants à la programmation se présentent sous l’angle de la créativité, et même de la créativité partagée entre petits et grands.

Ma fille Miss 12 ans et moi avons trouvé notre projet de l’été, numérique comme il se doit : coder de la musique.

Nous allons utiliser le projet [SonicPi](http://sonic-pi.net/) de Sam Aaron. Créée initialement à l’University of Cambridge Computer Lab et soutenu par la Raspberry Pi Foundation, Sonic Pi est un logiciel qui permet de créer de la musique, sur un Raspberry PI, mais aussi sur un ordinateur « classique ».

Il existe des dizaines et sans doute des centaines de logiciels pour créer de la musique sur son ordinateur, mais ce projet est intéressant pour trois raisons :

- SonicPi fonctionne sur un ordinateur à 50 € qu’on peut emporter dans sa poche de blouson.
- SonicPi prend le contre-pied des autres logiciels, qui ont des interfaces entièrement graphiques et simulent même les boutons des consoles d’antan : SonicPi montre le code, et vous ne pouvez faire de la musique qu’en codant. En créant des boucles de sons, en insérant des pauses, éventuellement aléatoires, en mettant en place des conditions (si… alors), etc. Bref il ne s’agit pas d’apprendre l’usage d’un logiciel de musique, il s’agit de programmer la musique. Ce qui a aussi pour vertu, d’ailleurs, de montrer la force du lien entre musique et mathématiques.
- SonicPi, et c’est le plus impressionnant à voir, permet non seulement de programmer un morceau puis de le jouer, mais de modifier un morceau en temps réel. Votre morceau joue, et vous intervenez sur le code pour ajouter, supprimer, modifier des sons en direct. C’est-à-dire que SonicPi, de logiciel de création de musique (on programme dans un premier temps, on joue dans un second), devient instrument de musique (on joue en temps réel, le code est l’instrument). La vidéo rend la chose plus concrète : https://vimeo.com/107897082

## 2. Emojis
L’usage des emojis a explosé ces dernières années. Techniquement, un emoji est un caractère ajouté à la table Unicode, la sorte d’immense alphabet utilisé en informatique. Le code ```&#9973;``` représente un voilier (&#9973;). A charge pour votre système local, votre iPhone, votre Android, votre PC Windows, de décider du détail du dessin qu’il substitue au code : d’où les petites différences de dessins entre les emojis.

Cette semaine, Google a proposé de nouveaux emojis : des images de femmes incarnant des métiers. Une femme portant cravate pour « banquier », une femme avec un stéthoscope autour du cou pour « médecin ». L’objectif est clairement de valoriser le rôle et l’image des femmes dans ces professions.

C’est la continuation d’une évolution engagée en 2014, quand le consortium Unicode a intégré des images plus « inclusives » pour les émojis les plus courants.

{{< figure src="/img/iz14-1.png" alt="inclusive emojis" >}}

Notez d’ailleurs un détail intéressant : l’image par défaut, qui était jusqu’en 2014 le poing blanc, est désormais le poing jaune. Et les blancs ne le changent pas, ils n’utilisent pas le poing « plus blanc » : peut-être en partie parce qu’ils gardent le poing « par défaut », pensant qu’il est pour eux (« le défaut, c’est moi », marque du privilège) ; aussi peut-être parce que faire une démarche volontaire pour choisir un emoji « plus blanc » aurait des connotations peu savoureuses. C’est un exemple des effets secondaires de ces choix graphiques « inclusifs », qui ne sont pas si faciles à naviguer. Un article un peu provocateur dans The Atlantic cette semaine creuse la question de savoir pourquoi les blancs ne semblent pas utiliser les emojis blancs. Avec pour sous-titre : Est-ce que cette disparité s’explique par la honte ?

Remarque en passant, un article qui a en sous-titre un point d’interrogation a une réponse facile : non.

Mais pour en revenir aux « femmes professionnelles » proposées par Google, ça m’a fait aussi penser à la [modification apportée l’an passé par Facebook à l’icône « Amis »](https://medium.com/facebook-design/how-we-changed-the-facebook-friends-icon-dc8526ea9ea8#.k1rfs21hk), qui est passée d’une silhouette d’homme au premier plan avec une femme au second plan à l’inverse : la femme au premier plan et l’homme au second.

Les interfaces sont des constructions sociales et, sans être politiques au même titre que la fiscalité ou la diplomatie, reflètent les choix d’une société avec cette particularité que l’État, habituel mastodonte de la construction sociale, est dans le numérique un acteur mineur.

## 3. la fin du PC de bureau

J’ai un MacBook pro à la maison (OS X), un PC (Windows 10) au bureau. J’ai un téléphone Nexus 5 (Android). Quand ma tablette Nexus 7 (Android) a cassé, je n’en ai pas racheté : mon téléphone l’a remplacé, pour l’essentiel.

J’ai lu cette semaine un [billet de Steven Sinofsky](https://medium.learningbyshipping.com/my-tablet-has-stickers-8f7ab9022ebd#.rd661nsxp) qui explique qu’il a, lui, laissé tomber ses ordinateurs, de bureau ou portables, au profit d’un iPad Pro avec clavier connecté. Son billet est intéressant parce qu’il n’est pas fondamentalement technique (iOS contre OS X ou Windows) : il s’appuie sur une analyse des modifications de nos habitudes de travail.

Son argument est que les premiers outils de productivité utilisés actuellement sont le logiciel de messagerie d’une part et le navigateur web d’autre part, et que pour cet usage principal, l’ipad et son clavier connecté font l’affaire.

Tout le monde, bien sûr, ne peut pas faire ce changement : si vous êtes développeur et que vous avez besoin d’installer votre environnement de développement sur votre machine, vous allez évidemment conserver un ordinateur. Mais ces cas sont finalement assez rares. L’obstacle le plus cité est la suite Office, mais je pense que les contre-arguments sur ce point sont nombreux :

- soit vous n’utilisez pas les fonctionnalités avancées de la suite Office, et un outil cloud type Google Drive vous permettra largement de faire l’équivalent : vous n’avez pas vraiment besoin de cette suite Office
- soit vous utilisez réellement les fonctionnalités avancées de la suite office, et franchement, vous ne devriez pas. Vous vous inventez du travail et faites des fioritures inutiles avec une usine à gaz.

Il y a le cas particulier d’Excel. Vous faites des tableaux de reporting ? Avec des données croisées ? Que vous transmettez au directeur des Ventes une fois par semaine ? Peut-être, mais songez à une reconversion, car votre directeur des ventes pourra sans doute bientôt, depuis son iPad Pro justement, se connecter à un Dashboard web qui lui donne des données en temps réel. Vous vous dites peut-être que dans votre secteur industriel à vous, ça n’arrivera pas, parce que votre système n’est pas près d’avoir un dashboard web… Peut-être, dans ce cas, votre job est-il assuré au sein de votre branche, mais votre branche elle-même n’a pas d’avenir bien clair…

En tout cas, il sera intéressant de voir comment ces solutions de « tablettes de bureau » se diffusent. Car Apple, jusqu’ici, n’était pas réellement armé pour vendre aux entreprises ou aux administrations. Il faut tout un circuit commercial spécifique, un suivi particulier, etc.

Et tous les acheteurs ne seront pas à égalité par rapport à ces évolutions des outils. Cf ce tweet, le tweet de la semaine pour ce qui me concerne…

{{< tweet user="JennyBryan" id="730487929907216384" >}}

## 4. Remix OS et le laptop à moins de 100€

Dans ma liste d’ordinateurs ci dessus, j’ai volontairement cité les systèmes d’exploitation : Windows et OS X pour les ordinateurs, Android pour tablettes et téléphones. Si vous êtes Apple jusqu’au bout des ongles, avec un Mac et un iPhone, vous avez deux systèmes d’exploitation, OS X et iOS.

Le mobile prenant de plus en plus de place, il est possible que la convergence entre systèmes mobiles et desktop s’accélère, en même temps que les frontières entre ordinateur, ordinateur portable et mobile s’effacent progressivement. L’iPad Pro « monte » du secteur tablettes au secteur laptops. En sens inverse, certains ordinateurs portables « descendent » en gamme et en prix.

Voici le dernier exemple à me passer sous les yeux : le fabricant chinois de microprocesseurs ARM [AllWinner](http://armdevices.net/2016/04/22/79-remix-os-laptop-on-64bit-allwinner-a64-quad-core-arm-cortex-a53/) propose un laptop dont les spécifications techniques ne sont pas ridicules, à partir de 75 $.

Le plus intéressant, c’est le système d’exploitation : [Remix OS](http://www.jide.com/remixos), qui est une version adaptée d’Android pour les PC.

La hiérarchie est en train de s’inverser entre mobile et desktop : l’expérience utilisateur « par défaut » devient celle du mobile, qui phagocyte progressivement les systèmes d’exploitation traditionnels.

## 5. Modèle économique Optimal, sans usure.

J’écoute depuis des années l’émission de radio _On The Media_, sur WNYC, la radio publique new-yorkaise [excellente émission]. Un thème récurrent de l’émission, c’est de suivre les fermetures, fusions, licenciements, etc. dans la presse US (qui ne dispose pas des subventions publiques de la presse française) et de débattre de possibles modèles économiques pour la presse en ligne.

L’explosion des AdBlockers, ces plugins qui permettent de bloquer à la fois les publicités et les « logiciels espions » sur les sites web, a mis à nu toutes les ambiguïtés et, parfois, les hypocrisies de la presse dans ce domaine.

Une grande partie de l’économie d’internet est basé sur la publicité « ciblée ». Et pour cibler, il faut savoir qui vous êtes et ce que vous aimez, donc vous « espionner ». C’est vraiment structurel, c’est « comme ça que ça marche ». Le site du Monde.fr est l’un des pires à cet égard, à la fois parce qu’ils vendraient les données de votre grand-mère à la Corée du Nord s’ils pouvaient, c’est de loin le site de presse international qui installe le plus de mouchards, et aussi parce que par ailleurs dans leurs colonnes ils ont facilement tendance à s’offusquer des pratiques des entreprises Américaines qui exploitent nos données. Passons : mon écran n’est pas assez grand pour contenir la liste des mouchards qu’ils installent.

{{< figure src="/img/iz14-2.png" alt="mouchards sur LeMonde.fr" >}}

Il n’empêche, le blocage de la publicité pourrait poser des problèmes économiques pour nombre de publications. [Optimal.com](https://app.optimal.com/) fait une tentative astucieuse pour contourner ce problème. Vous vous abonnez au service, et créditez une certaine somme par mois ; Optimal bloque les publicités et autres mouchards, mais reverse une part de votre abonnement aux publications en fonction de votre trafic. Et vous pouvez par ailleurs, au fil de votre navigation, cliquer sur un bouton pour donner un « pourboire » à destination de cette publication particulière, qui s’ajoutera à votre abonnement (tip en Anglais n’a pas tout à fait la même connotation que pourboire en français, mais bon…).

Optimal agit donc à la fois comme un adblocker payant, et comme une centrale de micropaiement pour les publications.

Cette semaine aussi Google a annoncé interdire désormais les publicités pour les crédits à la consommation relevant de l’usure, c’est-à-dire avec des taux monstrueux. C’est la première fois que Google interdit non pas telle publicité particulière, mais toute une catégorie, en bloc, dont l’impact social est jugé trop négatif, se mettant ainsi, pour la première fois, dans la peau d’un régulateur public, prenant une décision politique.

On The Media, l’émission de radio, avait utilisé de façon humoristique, en 2009–2010, un Jingle chanté qu’ils jouaient dès que l’émission s’apprêtait à parler de ces sujets. Les paroles disaient : [Present and Future Business Models for Monetizing the Newspaper Industry](http://www.wnyc.org/story/132848-hot-off-the-presses-otms-new-jingle/) (Modèles économiques présents et futurs pour gagner de l’argent avec la presse). Ils devraient le ressortir : le paysage de la pub en ligne est en train de changer.