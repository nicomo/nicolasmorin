+++
date = "2016-10-15T10:30:09+02:00"
description = "Internet cette semaine, comme si vous y étiez - 15/10/2016"
tags = ["internetzinc"]
title = "Internet zinc #27"
type = "post"
feature_image = "/img/iz-banner.png"
+++

## 1. Blockchain

Trois articles et une vidéo sur Blockchain sont passés sur mon écran dans la semaine, rien que ça. J’ai parlé parfois allusivement de Blockchain, mais je n’ai pas souvenir de l’avoir expliqué ni d’avoir consacré une (partie importante) d’une édition d’Internet Zinc à ce sujet.

C’est l’occasion.

Tout le monde, je pense, a entendu parler de Bitcoin : c’est une monnaie (que vous pouvez échanger pour des dollars, des euros, etc. à un certain taux, fluctuant) et c’est un système de paiement : je peux payer un service ou un bien en bitcoins plutôt qu’en euros — si mon vendeur accepte cette monnaie.

Blockchain est la technologie sur laquelle s’appuie bitcoin, et que je veux vous expliquer le plus simplement possible — mais en précisant dès l’abord que la même technologie peut être utilisée à autre chose qu’à payer en bitcoins, comme on va le voir.

Blockchain est un système distribué de validation et de stockage d’information.

Décryptons. J’ai un terrain, magnifique, avec vue sur la mer, 1000m2. J’en suis propriétaire. Je veux en transmettre la propriété à ma fille. Actuellement je fais enregistrer un acte à un notaire, qui transmet l’information à l’Etat, qui met à jour le cadastre, me taxe et délivre un titre de propriété à ma fille. C’est un processus centralisé, qui dépend entièrement de l’intermédiaire principal, l’État, qui sert à la fois d’autorité de validation (la donation est valide et acceptée) et de sauvegarde (cadastre et titre de propriété explicitent et enregistrent la nouvelle situation : c’est désormais ma fille qui est propriétaire). Mon identité, et celle de ma fille, ont été toutes les deux validées, elles aussi, par un système centralisé : une série de documents (pièces d’identité, livret de famille) délivrés par l’État et qui attestent de qui nous sommes et de notre lien de filiation.

Tout ce système est à la fois pratique (une seule autorité), coûteux (cette autorité a besoin de faire fonctionner un grand nombre de services — état civil, cadastre, etc. Un État), et fragile (si l’État dont je dépends dysfonctionne ou même disparait — je suis, mettons, Syrien — je n’ai aucun recours et je perds tous ces attributs : titre de propriété, papiers d’identité, etc.).

Imaginez que vous avez une sorte de registre électronique, une sorte de vaste tableur Excel, distribué : il en existe des centaines, des milliers de copies sur autant d’ordinateurs dans le monde. S’il y a une transaction enregistrée sous forme, si on veut, d’une nouvelle ligne (num. 987.567.123) dans l’ordinateur #128 423, il la transmet à plusieurs autres ordinateurs, qui travaillent à « vérifier » cette transaction, transmettent à leur tour à d’autres qui vérifient, etc. Les transactions peuvent dans une certaine mesure se chevaucher, mais à un moment, chacun va reconstituer l’ordre des transactions — des lignes dans le tableur. Une fois qu’il est établi que notre ligne 987 567 123 est valide, et qu’elle succède bien à la ligne 987 567 122, il devient impossible de falsifier le tableur — chaque ordinateur du réseau ayant une copie, en croissance, donc, du tableur de la ligne 1 à la ligne 987 567 123…

Blockchain a « validé », sans faire appel à une autorité centrale, notre transaction. Et c’est fondamentalement à ça que ça sert : valider un enregistrement de façon distribué, sans autorité validatrice.

Ci-dessous, une conférence d’Alex Tapscott, auteur du livre Blockchain Revolution, qui explique bien, sans trop de technique, les idées auxquelles on peut réfléchir à propos non pas de bitcoin, mais de blockchain.

{{< youtube 3PdO7zVqOwc >}}

## 2. blockchain

Alex Beregszaszi a participé à un « camp de développement » autour de Blockchain où ils ont tenté quelques expériences d’usage de la technologie. Son [article dans Medium](https://medium.com/@alexberegszaszi/building-decentralized-reputation-management-as-a-smart-contract-6d60b0c7bd0#.5etsguxs9) donne quelques exemples.

Imaginez une blockchain dédiée à la notion de réputation. Votre identité y est validée, et un certain nombre de vos transactions, en particulier en ligne, y sont enregistrées. Par exemple quand vous commentez sur un blog on enregistre, et si votre commentaire est supprimé parce qu’offensant c’est aussi enregistré. Vous louez un AirBnB pour le week-end, et après votre départ le loueur vous met un commentaire favorable parce que vous avez rendu l’appartement nickel : c’est enregistré. Etc., etc.

L’accumulation dans le blockchain de tous ces points d’informations permet de calculer une sorte de réputation. Et on peut venir lire ce blockchain pour autoriser toutes sortes de services.

Par exemple, pour louer un AirBnB, on peut vouloir avoir votre score de réputation. Mais pour commenter dans un blog, on peut se contenter de voir que vous existez en tant qu’individu et que vous n’êtes pas un robot spammeur.

Pensez à tout ce qu’on peut vouloir valider et vous verrez à quoi blockchain peut servir : les transactions financières, l’enregistrement de documents, de biens, de transactions non financières, la validation d’une identité, la validation d’une « réputation », un registre de vote (j’ai voté, moi, une fois et une seule fois). Valider, autre exemple, la liste historique de tous les propriétaires, depuis la vente initiale en passant par toutes les reventes, d’une arme à feu. Ou valider un contrat. Ou valider les données brutes d’une expérience scientifique pour empêcher leur falsification.

J’utilise l’exemple d’AirBnB à dessein : il y a quelques semaines je signalais ici qu’ils travaillaient sur cette question de réputation en mêlant votre historique dans AirBnB proprement dit et vos comptes Facebook et Twitter pour, au minimum, valider votre identité.

Or un [article de The Stack](https://thestack.com/security/2016/03/09/what-airbnbs-blockchain-authentication-proposal-means-for-privacy-online/) cette semaine explique qu’AirBnB songe, pour réaliser cet objectif, à s’appuyer sur une blockchain… L’article pointe aussi le revers de la médaille : dans un blockchain tout s’enregistre, rien n’est falsifiable… Donc rien n’est oublié. Ce qui ne plaira pas à l’Union européenne et pose certainement des questions de confidentialité.

Mais plus le temps passe plus j’ai le sentiment que cette question des données personnelles est de ces questions qui, comme les questions philosophiques selon Wittgenstein, ne se résolvent jamais vraiment. Si ce n’est par dissolution, quand on en vient à penser que la question ne se plus dans les termes qu’on imaginait initialement, qu’elle ne se pose d’une certaine façon plus du tout.

Une question résolue quand on en vient à penser qu’elle n’a plus tellement de sens.

## 3. Ello?

Vous vous souvenez quand Facebook a interdit les pseudonymes et forcé chacun à utiliser son identité « officielle » ? C’est la même logique : ils avaient besoin de gérer identité et réputation et avaient ce choix un peu grossier. Qui avait posé plein de problèmes : que faire pour les dissidents dans les pays autoritaires ? Que faire pour les transsexuels ?

Les trans avaient été au premier rang de l’opposition à cette mesure. C’était en octobre 2014. Et tout le monde, d’un coup, avait « fui » vers Ello, un réseau social qui permettait les pseudonymes, n’avait pas de publicités, récoltait le minimum de données, etc.

Deux ans plus tard, un [article d’Alexis Sobel Fitts dans Backchannel](https://backchannel.com/the-bizarre-second-life-of-the-utopian-facebook-killer-67f79ceb134e#.d44194c2l) revient sur l’histoire d’Ello. Elle capture parfaitement le dilemme auquel se sont heurtés les créateurs du réseau : avant cet épisode, il y avait 30 000 utilisateurs. Au moment de l’explosion, ils ont ajouté jusqu’à 50 000 utilisateurs par jour et sont devenus un phénomène.

Mais Ello n’avait pas été créé pour être un anti-Facebook : c’était un réseau social dédié essentiellement aux personnes branchées sur l’art contemporain. Que faire ? Rester dans cette ligne initiale ? Ne pas s’occuper de ces nouveaux usagers, ne pas ouvrir aux investisseurs qui viennent frapper à votre porte ? Ello a essayé d’accueillir les usagers venant de Facebook, et accepté un investissement de 11 millions de dollars.

Aujourd’hui, Ello est… un réseau social focalisé sur l’art contemporain. Et l’article explique bien la difficulté qu’ont eue les créateurs du site : comment tirer parti de ce moment de bonne fortune sans se laisser embarquer dans l’histoire que d’autres veulent écrire sur vous — en l’espèce, que vous êtes l’anti-Facebook !

Article intéressant aussi comme exemple concret de toutes les décisions stratégiques difficiles à prendre dans l’urgence de la vie d’une startup.

## 4. Recrute web designer

James Ruhaut travaille dans une agence de design web. Il participe souvent aux recrutements dans son entreprise et a proposé la semaine passée sur reddit à qui voudrait de passer en revue son portfolio de candidat.

3 jours et 50 portfolios plus tard, il a publié son analyse dans un [court article](https://medium.freecodecamp.com/i-reviewed-fifty-portfolios-on-reddit-and-this-is-what-i-learned-e5d2b43150bc#.osyr4umhf).

Je précise ce qu’on attend par portfolio ici : c’est un peu le CV en ligne du développeur web, avec des sites qui fonctionnent.

Il y a des petites astuces intéressantes dans ses retours. Par exemple et en particulier : ne cédez pas complètement aux modes. Les petites (je suis à compétence 85 % pour CSS), et les grandes (utiliser Bootstrap et JQuery pour tous les sites que vous faites : montrez que vous êtes capable de coder un site sans ces béquilles).

Mais aussi : vous n’avez fait aucun site pour mobile ? Vous pouvez sortir, on vous appellera.

Ce qui me frappe le plus dans cette présentation d’une démarche de recrutement dans le design web, ce sont deux choses, qui sont liées :

- tout se voit : le recruteur veut voir le code que vous avez produit ces dernières années (sur Github), il veut jouer avec les sites que vous avez produits, etc. Et pendant l’entretien, désormais, il n’est pas rare qu’il vous demande de faire des exercices devant lui, de résoudre des problèmes pour voir comment vous vous y prenez. Il est très très difficile, dans ces conditions, de masquer ses (éventuelles) incompétences : le marché est très transparent pour l’embaucheur.
- L’embaucheur se fout de vos diplômes comme de sa dernière chemise. C’est vrai pour le design web, pour l’informatique en général, de plus en plus. Et je soupçonne que ce sera vrai, dans le futur, dans de plus en plus de domaines. Ce qui posera certainement des challenges nouveaux aux universités, qui vivent en partie du monopole sur la délivrance des diplômes qu’elles délivrent. Des diplômes qui, au train où vont les choses, ressembleront bientôt à des titres d’emprunt russe.

## 5. Checklist

Pour finir Tanya Johnson, qui est Product Manager, partage un tableur bien utile si vous lancez un nouveau produit numérique/site web : la [checklist](https://docs.google.com/spreadsheets/d/1T_dtCX9uMUohPLwF8U8k0G2JVvb90qdkO65UH3Ah1qI/edit?usp=sharing) de tous les petits trucs autour du produit proprement dit à ne pas oublier au moment du lancement.

Par exemple les tests de sécurité ont été faits, la sauvegarde faite et un test de récupération de données validé.

Il y a 31 lignes…