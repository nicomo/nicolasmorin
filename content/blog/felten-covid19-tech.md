+++
title = "Ed Felten : Covid-19, Technologie, vie privée et libertés publiques"
date = 2020-04-17T07:06:30+02:00
description = "mes notes de la conférence donnée en ligne par Ed Felten, du Center for Information Technology Policy de Princeton sur Covid-19 et la technologie."
tags = [ "covid-19", "felten", "tech", "vie privée" ]
type = "post"
feature_image = "/img/felten-covid19-tech.png"
+++

_Ci-dessous mes notes de la conférence donnée en ligne par Ed Felten - [@EdFelten](https://twitter.com/EdFelten), du [Center for Information Technology Policy](https://citp.princeton.edu/) de Princeton sur le sujet en titre du billet, le 16/04/2020. La conférence a été enregistrée et sera en ligne : <https://citp.princeton.edu/event/webinar-felten-covid/>_

On parle ici de la situation après le pic de la maladie, mais avant que la question soit réellement réglée. C’est-à-dire que la question est liée à une transition longue entre le pic et la disponibilité d’un vaccin, des mois pendant lesquels il faudra gérer une « zone grise » de risque.

La technologie peut donner au public et aux responsables politiques une meilleure information sur ce qui se passe, et aussi leur permettre de plus finement gérer des restrictions partielles et adaptées à la mesure du risque à un instant donné en un endroit donné.

Quelques rappels : si R0 (le nombre de personnes infectées par une personne infectée) est supérieur à 1 la maladie se développe. L’objectif est de réduite ce chiffre. On peut limiter le nombre de personnes que chacun rencontre (confinement), mais ça ne suffira pas du fait en particulier de la contagion par des personnes asymptomatiques. On peut limiter le nombre de personnes qui sont sensibles à la maladie, parce qu’ils sont vaccinés, idéalement, ou parce qu’ils sont immunisés, ayant déjà eu la maladie. On peut enfin limiter la contamination par des mesures prophylactiques (se laver les mains, les masques, etc.).

Pour Covid-19 il est probable qu’une combinaison de ces méthodes sera nécessaire sur une longue période.

Dans ce contexte, l’apport des technologies informatiques est publiquement évoqué dans trois domaines en particulier :

1. Mobilité : fournir une meilleure compréhension des mouvements de populations
2. Créer une sorte de passeport d’immunité
3. Connaître les contacts récents d’une personne particulière en cas de maladie

## Mobilité

Un excellent exemple récent d’utilisation de données agrégées de localisation à l’échelle d’une population, c’est le _[Community Mobility Report](https://www.google.com/covid19/mobility/)_ de Google. Ces informations de localisation existent déjà, et de façon multiple : elles sont accessibles via le système d’opération du téléphone (par Google et Apple), le réseau téléphonique (en France, par Orange, Free, etc.), les apps qui utilisent massivement la localisation (Facebook par exemple). Les données sont agrégées, mais l’identification d’une personne peut souvent être connue par inférence.

En termes de vie privée, des méthodes validées existent pourtant qui ajoutent du « bruit » aux données envoyées et empêchent l’identification individuelle, tout en conservant des données agrégées correctes et utilisables. C’est la méthode appliquée par Google pour collecter les données qui servent au _Community Mobility Report_ et il est donc possible d’utiliser ces données de mobilité tout en respectant la vie privée, à condition d’utiliser ces techniques.

## Passeport d’immunité

C’est une idée à double tranchant : on pourrait avoir des situations où l’existence du passeport représente une incitation à essayer d’avoir la maladie, par exemple parce que vous avez absolument besoin du passeport pour obtenir un emploi. Par ailleurs, il sera difficile d’empêcher la fraude. C’est aussi assez difficile à mettre en place en pratique, car il faut non seulement une bonne technologie, mais il faut aussi une autorité de délivrance et des processus de validation assez lourds.

Il serait assez difficile, par ailleurs, d’éviter les discriminations sur la base de ce passeport, de sa détention ou de sa non-détention (à l’emploi par exemple).

Enfin, à ce stade les tests connus ont des taux d’erreur proches de 5 %, ce qui laisse trop de faux négatifs/positifs et créerait d’autres problèmes, comme de créer de la confusion et miner la confiance des populations dans ce passeport.

## Suivi des contacts

Ça peut déjà être fait de façon manuelle par les autorités sanitaires à l’heure actuelle, mais la technologie pourrait être d’une grande aide ici, parce qu’elle est beaucoup plus précise et complète (heure, lieu, etc.) que la mémoire des personnes, et qu’elle peut donner des informations que l’usager lui-même ne peut pas donner, par exemple la liste des inconnus que la personne a croisés au supermarché.

4 approches sont possibles si on croise les réponses à deux questions :

1. Cherche-t-on à notifier les individus concernés uniquement ? Ou aussi les autorités ?
2. Quelle approche technique retient-on ? Par détection de proximité directe de téléphone à téléphone (Bluetooth) ? Ou bien stocke-t-on les localisations d’un téléphone dans le temps, pour utiliser ensuite cet historique si la personne tombe malade ?

Dans tous les cas, si la moitié de la population installe l’application, l’application ne connaîtra 25 % des cas, puisqu’il faut que les deux personnes qui se croisent aient l’application pour qu’elle soit utile. La question du niveau d’adoption de la technologie par la population est donc sans doute le critère le plus important de succès de cette technologie. La population doit avoir _confiance_ dans la démarche, et donc savoir que le respect de la vie privée par l’application est indiscutable, et perçu comme tel : alors l’adoption sera plus facile, et donc la couverture de la population meilleure et l’incitation à installer l’application renforcée.

Si on répond à la question 2 par une solution de stockage des localisations, que ce soit par une app existante ou une nouvelle app, on a des informations plus précises : pas seulement qu’on a croisé quelqu’un qui est tombé malade, mais en plus à quel endroit le contact a eu lieu. Par contre, cette technologie est liée à la personne de façon immédiate, et il est très difficile de maintenir l’anonymat ou généralement la vie privée avec ce type de technologie. Ce qui sera probablement un obstacle à l’adoption.

Si on répond à la question 2 par une solution de proximité, voici comment ça marcherait : votre téléphone diffuse dans son environnement un numéro d’identification qui change toutes les 15 minutes, et collecte les numéros d’identification des téléphones qu’il croise. Si je tombe malade, je le signale et mes clés uniques des derniers jours sont envoyées sur un serveur, et téléchargées ensuite par tous les autres téléphones, qui comparent la liste des clés des malades connus avec celle des clés que votre téléphone a collectées. S’il _matche_, vous avez croisé un malade.

C’est la solution proposée en commun par Google et Apple.

Les clés des personnes malades peuvent être diffusées directement (à l’utilisateur final, c’est-à-dire à son téléphone), ou par l’intermédiaire d’une autorité nationale.

Il est important de comprendre que ce que proposent Google et Apple c’est une API, mais pas une application. C’est-à-dire que le système d’exploitation du téléphone (iOS, Android) propose la fonctionnalité, en un sens technique, mais qu’il faut coder une application spécifique qui va utiliser cette possibilité du téléphone. La question de savoir qui va faire cette application finale est importante, mais n’est pas déterminée à ce stade. Les Gouvernements sont sans doute mal armés pour réaliser techniquement cette application, mais c’est eux qui devront probablement, au minimum, les valider et les recommander à leur population.

Il y a des inconvénients à cette technologie. Par exemple, comment s’assurer, dans ce système, que personne n’a la mauvaise idée de se déclarer positif à tort ? Il peut y avoir des attaques de type « paparazzi » : il suffit de s’approcher régulièrement d’une célébrité pour avoir un échantillon de ses clés et donc d’être averti si l’une de ses clés est associée à un malade. Il y a aussi le problème des autres identifiants diffusés par les téléphones, qui eux ne sont pas nécessairement protégés : si on collecte les clés Covid-19 *et* les autres clés, on pourrait potentiellement « désanonymiser » une clé covid.

Il y a quelques autres scénarios d’attaque possibles, mais au final ces risques sont marginaux par rapport au bien public potentiel apporté par ces solutions et, globalement, cette solution semblerait respecter la vie privée des personnes. Ceci étant, encore une fois, pour que ça marche, il faut que les applications soient acceptées et bénéficient de la confiance du public.

## Au final, que faut-il faire ?

Travailler avec les données agrégées ? Oui.

Mettre en place un passeport d’immunité ? Ça semble une fausse bonne idée.

Le suivi des contacts ? Oui, mais c’est complexe, en partie pour des raisons techniques, mais surtout pour des questions d’organisation, et d’acceptation par les populations.

Il faut aussi avoir en tête que ce n’est sans doute pas la dernière fois qu’on est confronté à ce problème et que cette infrastructure technique sera utile à long terme. Dans ce contexte, la transparence des décisions et des choix est particulièrement importante, de même que d’ouvrir largement, pour les entités décisionnaires, le dialogue sur les choix qui seront faits.

---------------

## Compléments @nicomo

Nicky Case a fait une petite BD expliquant clairement la technologie proposée par Google+Apple : <https://ncase.me/contact-tracing/>

Si vous êtes l’État, ou au moins [beta.gouv.fr
](https://github.com/betagouv/StopCovid), la leçon à tirer, je crois, de cette conférence, c’est qu’il est important de consulter un panel large d’opinions et d’acteurs, et de ne pas essayer de faire ça entre deux portes et « entre nous » pour « aller vite » et parce qu’en France, par définition, l’État « sait mieux ». Mes [DM twitter](https://twitter.com/nicomo) sont ouvertes 😎
