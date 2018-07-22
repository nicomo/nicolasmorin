+++
date = "2016-10-22T16:18:01+02:00"
description = "Internet cette semaine, comme si vous y 22/10/2016"
tags = ["internetzinc", "programmation"]
title = "Internet zinc #28"
type = "post"
image = "img/iz-banner.png"
+++

Cette semaine j’étais en déplacement : j’ai manqué de temps et, surtout, j’ai manqué de connexion internet suffisante pour faire mon travail habituel de lecture, synthèse, etc. Du coup pour cette semaine, exceptionnellement, je vous propose une édition différence d’Internet Zinc, que j’écris dans mon avion de retour à la maison — sans connexion — et qui n’a qu’un seul sujet : QU’EST-CE QU’UN PROGRAMME ?

## 1. Infrastructure matérielle

Il y a 18 mois Paul Ford a publié un article, en Anglais, dans Bloomberg, intitulé : [What is Code?](https://www.bloomberg.com/graphics/2015-paul-ford-what-is-code/) Dans de nombreuses conversations depuis lors, je me suis rendu compte que cette notion cruciale était mal comprise, et que cette compréhension limitée expliquait en partie pourquoi on avait du mal à anticiper l’importance des transformations techniques et sociales induites par le code. Du coup, sans traduire (ni même relire, à dire vrai — je suis dans l’avion), le papier de Paul Ford, je veux tenter ma propre explication en prenant comme fil rouge l’exemple d’une application sur laquelle il m’arrive de travailler de loin en loin (et qui ne verra peut-être jamais le jour : c’est avant tout un terrain d’apprentissage et d’exercices).

Pour cet article, les termes de code, de programme et d’application seront considérés comme synonymes — ce qu’ils ne sont pas en réalité, bien entendu.

J’ai évidemment besoin d’un ordinateur pour programmer, et vous avez besoin d’un ordinateur (qui peut être un téléphone) pour utiliser mon programme. Mon programme est un site web : j’ai besoin d’un ordinateur qui soit en ligne 24 h/24 pour que vous puissiez vous y connecter et l’utiliser. Mon programme peut aussi être utilisé sous forme d’une application téléchargeable sur votre téléphone : cette application est un sous-programme, séparé, mais qui communique avec mon programme principal sur le serveur.

Avant même que je commence à travailler, toute une infrastructure matérielle est donc nécessaire. Ces ordinateurs eux-mêmes dépendent des progrès continus des microprocesseurs, des processus industriels de fabrication de l’électronique, des écrans, du verre, des baisses de coûts de la mémoire, etc. Mon programme, sur lequel je n’ai pas encore commencé de travailler, dépend donc des progrès de l’industrie chinoise de ces 30 dernières années, et de la diffusion progressive de ces matériels dans toutes les sociétés, en Occident et ailleurs.

Pour que je puisse mettre mon programme en ligne, et que vous puissiez l’utiliser, j’ai besoin aussi de la présence continue d’internet. Je compte sur le fait qu’on peut y accéder 24 h / 24 à un coût forfaitaire. Ce programme prendrait sans doute la forme d’un site web, à côté de mon site web perso, qui est sur un serveur que je partage avec d’autres internautes. Il contient mon site et d’autres sites. Vous tapez http://www.nicolasmorin.com et une multitude de serveurs qui gèrent le trafic internet transforment cette adresse en l’adresse d’une machine physique : ils transfèrent votre demande de consultation jusqu’à « mon » serveur puis transfèrent la réponse, ma page web, en sens inverse. Je ne sais pas où est physiquement cette machine. Je crois que c’est en France.

La plupart des développeurs sont en bout de chaîne. Vous vous souvenez de Steve Ballmer, l’ancien patron de Microsoft, sautant sur scène comme un déchaîné dans une chemise trempée de sueur ? Que hurle-t-il ? « Développeurs, développeurs, développeurs ! » Pour exploiter une infrastructure donnée, il vous faut des développeurs, mais en même temps les programmes que vous pouvez faire ne peuvent dépasser les capacités de l’infrastructure existante. Par exemple, je peux rêver d’un programme qui, dans mon domicile, mesure en permanence la consommation électrique de chaque objet branché au réseau électrique, et puisse commander chacun de ces objets pour optimiser ma consommation. Je ne peux pas, car ces objets, ma bouilloire par exemple, mon four, mon réfrigérateur, mes lampes, ma climatisation… n’ont pas encore été transformés en ordinateurs. Il y a un seul compteur électrique chez moi, il est à l’entrée de la maison ; je n’ai pas un compteur/capteur par objet.

Moralité : j’ai besoin d’une énorme infrastructure matérielle pour faire mon programme et je ne peux faire de programme que pour cette infrastructure-là. C’est un prérequis : on n’a pas encore commencé de réfléchir au programme lui-même…

## 2. Infrastructure logicielle

Maintenant que nous avons une infrastructure matérielle avec laquelle travailler, on peut faire un programme.

Tout le monde a appris à l’école ou à la TV que les ordinateurs sont « binaires » et parlent en 0 et 1. Tout le monde entend aussi parler ici ou là d’une multitude de langages de programmation, et qu’il s’en créé toujours de nouveaux : Fortran, C, C++, Java, Perl, PHP, Python, JavaScript… La liste est sans fin.

Tout le monde a une idée d’à quoi ressemble du code produit par un développeur. Par exemple, tout le monde reconnaîtra ce qui suit comme étant « un programme » :

```go
package main
import “fmt”
func main() {
    fmt.Println (« Hello, 世界 »)
}
```

Ce programme imprime _Hello, 世界_ à l’écran. Clairement, il n’est pas fait de 0 et de 1. C’est qu’un langage de programmation n’est pas juste une suite de règles pour programmer, c’est aussi un programme en tant que tel, dont le rôle principal est, justement, de transformer ce qu’écrit le développeur en 0 et 1. Le langage de programmation que j’utilise pour mon projet s’appelle Go. Quand je lui donne le programme ci-dessus, écrit en respectant les obligations qu’il m’impose, le langage Go va le transformer, en deux étapes.

D’abord, il en fait une version dite d’assembleur intermédiaire. Pensez-y de la façon suivante : votre programme sera peut-être installé sur une machine qui a un microprocesseur amd64. Celui-ci attend une façon d’encoder les 0 et 1 qui lui est propre. Un autre processeur aura une autre façon de gérer les 0 et 1. Go fait donc une version « générique » de cet encodage d’abord, avant, à partir de cette version intermédiaire, de faire une version spécifique pour telle ou telle machine. (Je simplifie un peu, c’est l’idée générale.)

La force d’un langage de programmation tient donc à deux choses : ce qu’il permet au développeur de faire, mais aussi la façon dont il transforme le langage du développeur en langage machine.

On peut y penser de la façon suivante : le développeur est en terrasse, il dispose d’une bonne vue d’ensemble ; le programme gère les étages inférieurs, et est en contact avec les sous-sols, où tourne la chaudière, où sont connectés le tout à l’égout, l’électricité, etc. Le développeur ne s’occupe que de ce qu’il veut bricoler sur sa terrasse : il compte sur le langage de programmation pour gérer le reste. À la fin, on descend toujours en sous-sol, au niveau de la machine.

Le plus souvent, d’ailleurs, le langage de programmation ne fera pas tout lui-même, et délèguera certaines fonctions à d’autres programmes. Par exemple, je veux que vous puissiez consulter mes pages web : vous interrogez une adresse, je vous renvoie une page. J’ai peut-être programmé la page en question en Go, mais Go délègue à un autre programme (en général Apache) cette fonction de recevoir les demandes et renvoyer les pages. Les concepteurs de Go ont prévu comment dialoguer avec Apache pour remplir cette fonction. Et si je veux stocker des données, c’est le même principe : ils n’ont pas refait un système de bases de données de A à Z, ils ont prévu comment dialoguer avec les gestionnaires de base de données les plus courants. En tant que développeur Go, je dois aller voir dans la documentation avec quels systèmes de base de données je peux parler, et comment leur parler « en Go ».

Vous avez remarqué ? Je n’ai toujours pas commencé mon programme : j’avais d’abord besoin de toute une infrastructure matérielle, j’ai aussi besoin de toute une infrastructure logicielle.

Le programme que j’écris n’est jamais isolé, c’est, fondamentalement, un levier ajouté à une énorme machine, faite d’autres leviers, poulies, pistons et courroies. Un petit bateau qui navigue sur une mer de code.

## 3. Analyser la réalité

J’ai une idée générale des besoins de mon programme : j’ai choisi un langage de programmation, Go, je sais que j’aurais besoin de stocker des données et choisi PostgreSQL comme base de données, je sais que le tout prendra la forme d’une page web, mise en ligne sur un serveur (machine) et servie par un serveur (logiciel).

Mon programme a une fonctionnalité en apparence simple : vous pouvez envoyer un message à un ami, qui lui sera délivré avec un délai qui sera fonction de la distance physique entre vous. Un programme de messagerie qui annule l’instantanéité du web : un message envoyé de Paris à Sydney mettra (beaucoup) plus de temps à parvenir à son destinataire qu’un message envoyé de Paris à Aubervilliers.

C’est ici qu’intervient l’abstraction dont je parlais tout à l’heure. Le programme mime clairement quelque chose du monde réel : le courrier papier et sa matérialité, qui tient compte des distances. Mais pour reproduire ce phénomène, j’ai besoin de le saucissonner en entités les plus petites possible et de transformer chaque partie en une sorte d’atome de sens ou de fonction.

_Vous pouvez envoyer un message à un ami_ : vous. J’ai besoin de pouvoir distinguer vos messages de ceux de votre voisin. Mon service ne peut pas être anonyme et il faut donc pouvoir créer un compte. Du coup il faut sans doute pouvoir aussi supprimer un compte. Et le modifier, si vous voulez par exemple changer votre nom d’utilisateur.

_à un ami_ : vous n’écrivez pas à n’importe qui, mais à vos amis. Qui sont vos amis parmi tous les utilisateurs du service ? J’ai besoin d’en avoir une trace. Vous pouvez ajouter des amis quand vous vous inscrivez, vous pouvez aussi en ajouter plus tard. Que faire si vous voulez écrire à un ami qui n’est pas utilisateur du service ? Pouvez-vous l’inviter ? A priori être ami requière aussi que la seconde personne *valide* ce lien, même si ce n’est pas elle qui l’a initié : si je suis votre ami et que vous n’êtes pas le mien, nous ne sommes pas amis. Par contre, couper ce lien ne nécessite l’action que de l’une des deux personnes.

_un message_ : hum… Texte ? Texte et image ? Vidéo ? Quelle longueur maxi ? Vous devez pouvoir enregistrer des brouillons, et qui sont un message distinct des messages envoyés. Vous êtes seul à pouvoir voir et éditer vos brouillons, plusieurs personnes peuvent voir un message envoyé : au moins vous, et celui qui l’a reçu. Peut-on répondre à un message ? Oui, ce serait logique, mais du coup il faut pouvoir lier un message (réponse) à un autre message, et ne pas en faire un « nouveau » message. Peut-on supprimer un message? Est-ce que ça supprime toute la discussion, y compris les réponses écrites par votre correspondant? Tant de questions…

_qui sera délivré dans un délai tenant compte de la distance entre vous_. Quelle est la distance entre vous ? Pour le savoir, j’ai besoin de savoir d’où part le message, et où il est censé être acheminé. On peut imaginer deux solutions : vous déclarez une adresse « par défaut », et tous vos messages partiront de ce point du globe, même si vous êtes à 10 km de là quand vous cliquez sur le bouton ; et vous ne pourrez collecter votre courrier entrant que si vous êtes à proximité de ce point. Vous relevez, dans un sens très matériel, votre boite à lettres : il faut être à côté. Ou bien je prends en compte, à chaque fois, votre localisation réelle à un instant T pour calculer les distances. Dans tous les cas, j’ai besoin de votre géolocalisation.

Ce travail d’analyse est méthodique mais assez simple. Par contre, même s’il mime une situation réelle, le courrier papier, il a sur la réalité un effet particulier : je ne parle plus de la poste de Fort-de-France, qui collecte la boite au coin de ma rue, et du facteur parisien qui délivre l’enveloppe et qui sait, peut-être, que Mme Groudiev est en vacances à Dubrovnik cette semaine et qu’il vaut mieux laisser l’enveloppe chez le concierge. Je parle d’un système forcément générique, qui peut s’appliquer à tous les utilisateurs et toutes les situations. Le programme n’est plus seulement une abstraction de la réalité. Si vous utilisez mon programme, il est à lui-même sa réalité, et vous agissez à l’intérieur des contraintes qu’il propose : dans un certain sens, et pour les fonctions qu’il rend, il est votre nouvelle réalité.

## 5. nano-legos de code

Mais passons maintenant un peu plus au détail, par exemple à la création de votre compte.

Il y a 10 ans, ce processus aurait sans doute pris la forme suivante : un formulaire de quelques champs, où vous auriez créé un login, choisi un mot de passe et, peut-être, saisi une adresse mail que j’aurais stockée en base de données.

Mais voici comment je procède en fait :

- Vous arrivez sur la page d’accueil : êtes-vous déjà connecté ou non ? Pour le savoir, je regarde dans votre navigateur si vous avez un cookie qui vient de mon site… (vous vous souvenez des débats sur les cookies ? Intrusion dans la vie privée ? Un député quelconque voulait les interdire ? Cela semble un autre siècle… et ça l’est.)
- Pas de cookie : je vous redirige vers la page login, qui a 3 boutons : Continuer avec Google, Continuer avec Facebook, Continuer avec Twitter. Vous cliquez sur le premier.
- Nous faisons ensemble la « danse de l’authentification » : il y a plusieurs aller-retour entre les serveurs de Google et mon serveur, pour échanger diverses clés encodées qui valident que je suis bien l’application que je prétends être, qui précisent de quelles informations j’ai besoin, etc. De votre côté, vous voyez une fenêtre qui vous demande d’autoriser mon application et vous détaille les informations que vous allez me transmettre. Vous dites oui. Toujours.
- Je récupère votre profil Google, votre nom, sexe, email, identifiant Google, photo d’avatar et liste de contacts.
- Je cherche dans ma base de données : cet utilisateur existe-t-il déjà ? Est-ce que je connais son mail ? Ou son identifiant Google ? Si oui : je dépose un cookie sur votre navigateur et je vous renvoie vers la page d’accueil, vous êtes connecté.
- Sinon, je dois créer un nouveau compte pour vous. Le username que vous utilisez dans Google est-il disponible dans ma base de données ? Ca n’est pas sûr : peut-être quelqu’un utilise-t-il le même user name que celui que vous avez dans Google, quelqu’un qui se serait inscrit par twitter par exemple ? S’il est pris, je génère un username aléatoire pour vous. Comment ? J’ai une longue liste de couleurs, et une longue liste d’animaux, je les combine au hasard et j’ajoute un nombre : vous êtes YellowShark123. Ça vous va ? OK, je crée votre compte dans la base de données, je dépose un cookie sur votre navigateur et je vous redirige vers la page d’accueil. Bienvenue.
- Par la même occasion, Google m’a donné la liste de vos amis. Je peux vous signaler ceux qui sont déjà là… et vous suggérer d’inviter les autres ? N’avoir personne à qui écrire, c’est triste.

Cet exemple de la création de comptes illustre deux choses : le programme est fonction de l’infrastructure, et il est fait d’une myriade d’infimes décisions. Mon petit bateau navigue ici sur les flots de l’authentification Google, qui me fournit votre identité et celle de vos amis. J’utilise cette infrastructure parce qu’elle est commode et sécurisée : en particulier je n’ai pas besoin de gérer de mots de passe, je délègue cette responsabilité, dont je ne veux pas, à Google ; et pour vous c’est un mot de passe de moins, en même temps qu’une sécurité supplémentaire.

Mais mon petit bateau de code lui-même est fait de multiples pièces qui s’emboîtent et interagissent. Générer un username au hasard est une sorte de mini-programme à l’intérieur de mon application, qui passe ensuite la main à un autre mini-programme, qui enregistre votre compte dans la base de données. Toutes les parties de mon code dialoguent entre elles comme mon programme dans son ensemble dialogue avec d’autres programmes : les serveurs de Google, la base de données, etc.

## 5. En vérité…

En vérité, il est très rare qu’un programme ressemble à ce que je viens de décrire. Du moins il n’y ressemble pas longtemps. C’est ici un petit projet personnel, qui part de zéro et pour lequel je suis le seul développeur. L’énorme majorité des programmes n’est pas de cette nature.

N’importe quel programme un peu ambitieux est le fruit du travail collaboratif de plusieurs développeurs : développer est un sport d’équipe. Avec tout ce qu’implique le terme : programmer implique des coûts de coordination, la mise en place de mécanismes de décision, des choix collectifs (ou autoritaires) de grandes orientations. Quel langage ? Go ? Java ? Node? PHP ? Quelle base de données ? MySQL ? Postgres ? MongoDB ? Quelle structuration de l’application? Et ainsi de suite. Et comme tout environnement social, il génère tensions, frustrations, colères, claquements de portes tout autant qu’émulation, solidarité, sentiment d’accomplissement… Un programme est le fruit de son environnement social et la littérature sur les méthodologies de gestion de projet de développements informatiques remplit des rayonnages et des rayonnages.

La plupart des programmes, aussi, consistent en évolutions d’un programme existant. L’analogie classique est celle du navire, qu’on doit repeindre sans le sortir de l’eau. Vous devez trouver des solutions pour le faire évoluer sans trop casser l’existant. On fait très rarement table rase. En conséquence, notre mer de code est, comme la mer que je survole en ce moment en avion, pleine de déchets : du code mort, ou à tout le moins de technologies obsolètes, qu’on continue d’utiliser. Je voudrais faire mon projet en langage Go, mais il s’agit de faire évoluer une application qui existe depuis 15 ans, initialement écrite en PHP. Je pourrais peut-être isoler une partie du bateau, mettons les mats et voiles, et remplacer mon PHP par du Go sans toucher à la coque, à condition que le tout continue de s’emboîter correctement… et en espérant que petit à petit j’aurais de plus en plus de Go et de moins en moins de PHP ? C’est rarement faisable. Alors j’essaie de toiletter et moderniser mon application tout en conservant PHP.

---

Dans tout ce texte, j’ai parlé de ce qu’était un programme. Je n’ai pas parlé de la technique, de ce qu’est une « classe », ou une « fonction », une « variable », etc. À quoi ça ressemble concrètement de programmer ? Ce sera peut-être pour un autre article.

En attendant, j’ai essayé dans cet article de vous faire sentir pourquoi les programmes absorbent progressivement la réalité tout entière :

- L’infrastructure matérielle a un effet cumulatif : sa progression n’est pas juste de plus grande puissance des processeurs, comme on le dit souvent. C’est aussi sa dissémination. La puissance de calcul augmente, certes, mais c’est surtout qu’elle se miniaturise tout en étant de moins en moins cher. Il devient possible d’insérer un ordinateur dans votre montre, dans votre théière, dans l’interrupteur qui commande les lampes de votre salon. Ils peuvent être connectés, certes, mais ils peuvent surtout être programmés. Le développement de cette infrastructure change les questions qu’on peut se poser, et les problèmes qu’on peut vouloir résoudre par la programmation. Et je parierais volontiers, aussi, qu’une fois ces ordinateurs banalisés, on cessera d’y penser comme des ordinateurs.
- La logique est la même avec l’infrastructure logicielle — qui est aussi partiellement une infrastructure de données : les couches logicielles se superposent historiquement les unes aux autres comme les couches sédimentaires qui forment la terre sur laquelle on marche. Elles changent profondément le relief et, elles aussi, influent grandement non seulement sur ce qu’il est techniquement possible de faire, mais aussi sur les problèmes qu’on peut vouloir résoudre par la programmation.
- Le programme lui-même permet de découper le monde qu’on souhaite explorer en petites entités abstraites : les développeurs prennent indépendamment des millions de petites décisions dont les résultats, les applications qu’ils produisent, modifient profondément la réalité en retour, sans que jamais personne n’ait pris de « grandes décisions » à l’égard du mondenouveau qui en résulte.

C’est à cause de ce dernier point que je suis souvent sceptique quand j’entends les appels à « discuter au fond » l’impact de tel ou tel développement informatique sur les sociétés. Ces appels sont souvent légers en terme de propositions concrètes, et lourds de menaces en terme de tentatives de contrôle étatique des technologies.

Un tel dialogue n’est certainement pas impossible, mais je n’ai pas d’idée claire de la forme concrète que pourrait prendre une discussion de ce type. Ma nature m’incline à privilégier les démarches simples et modestes. Par exemple : introduire des cours d’éthique dans les formations informatiques, pour aider les développeurs à comprendre l’impact réel des myriades d’infimes décisions qu’ils prennent quand il produisent du code.
