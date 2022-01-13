---
layout: post
title: "Choisir un gestionnaire de cookies pour la conformité RGPD"
---
D’habitude omniprésent dans tout ce qui touche aux outils Web et mobile, Google ne propose pas de solution de gestionnaire de cookies (Consent Management Platform – CMP) pour faciliter sa mise en conformité au RGPD.

Conséquence de cette absence ? L’abondance voire le trop-plein de solutions avec plusieurs milliers de CMP disponibles, dont une grande partie sont [référencés sur le site de l’IAB](https://iabeurope.eu/cmp-list/), du moins ceux qui sont conformes au [Transparency and Consent Framework (TCF)](https://iabeurope.eu/transparency-consent-framework/).

Comme une présentation exhaustive de ces solutions n’est juste pas possible, j’ai pris le parti de présenter les 4 solutions que je conseillerai à des TPE ou PME pour mettre en place un gestionnaire de cookies conforme aux [recommandations de la CNIL](https://www.cnil.fr/fr/cookies-et-autres-traceurs-la-cnil-publie-des-lignes-directrices-modificatives-et-sa-recommandation).

### Tarte au citron : open source, auto-hébergé et référence CNIL

La solution [Tarte au citron](https://tarteaucitron.io/fr/), créée par le développeur français Amauri Champeaux, cumule à nos yeux la plupart des avantages qu’on peut attendre d’un CMP :
* Open source : transparence sur les traitements effectués par le logiciel, existence d’une [communauté d’utilisateurs](https://github.com/AmauriC/tarteaucitron.js/discussions) ;
* Auto-hébergé : possibilité de l’installer directement sur ses serveurs, pour une maîtrise totale des traitements ;
* Solution référente car utilisée sur le [site Web de la CNIL](https://www.cnil.fr), Autorité de Contrôle française.

Cependant comme beaucoup de solutions open source, il faut maîtriser un minimum les principes de développement informatiques pour pouvoir la mettre en œuvre en auto-hébergé.

### Orejime : open source, auto-hébergé et référence APD

La solution [orejime](https://orejime.empreintedigitale.fr/) est développée par la SCOP française Empreinte Digitale qui développe des solutions numériques responsables (RSE, Green IT etc.).
Comme Tarte au Citron, [elle est open source](https://github.com/empreinte-digitale/orejime) et disponible en auto-hébergé.

Elle est aussi très crédible, car utilisée aussi bien par l’[Autorité de Contrôle belge (APD)](https://www.autoriteprotectiondonnees.be/citoyen) que par le site Web [Service-Public.fr](https://www.service-public.fr/) en France.

![Les gestionnaires de cookies pour le RGPD]({{ site.baseurl }}/images/CMP/cookies-on-off.png "Les gestionnaires de cookies pour le RGPD"){: .center-image }

### CookieBot : SaaS mais utilisable en version gratuite

La solution SaaS [CookieBot](https://www.cookiebot.com/fr/) est éditée par la société dano-germanique Usercentric, avec un hébergement des données situé dans l’Union Européenne (Microsoft Azure en Europe, Fujitsu A/S au Danemark).

Contrairement aux solutions auto-hébergées, les solutions SaaS sont censées être plus faciles à intégrer par des profils moins techniques.

CookieBot est l’une des rares solutions SaaS qui reste conforme au RGPD dans sa version gratuite, malgré quelques limitations : 1 domaine avec moins de 100 pages Web, pas de bannières personnalisées, pas de multilingue etc.

Il s’adresse semble-t-il principalement aux petits sites Web (d’où l’offre gratuite) et aux agences Web.

### Axeptio : SaaS payant mais pas triste !

La solution SaaS [Axeptio](https://www.axeptio.eu/fr/home) est éditée par la société française Agilitation.

Si une version gratuite existe, elle est purement théorique car non conforme au RGPD (pas de stockage du consentement) et trop limitée (2 cookies, pas de consentement marketing etc.).

Ce qui la différencie des autres solutions, c’est le design « fun » des interfaces de gestion des cookies, qui s’adresse aux agences Web qui désirent en mettre plein la vue à leurs clients ! Bien loin en tous cas des interfaces austères réalisées par et pour des informaticiens…

Mais c’est aussi la preuve qu’on peut traiter un sujet sérieux (la protection des données personnelles) sans se prendre trop au sérieux.


Au final c’est quand même rassurant que dans un univers Web largement dominé par Google, il soit tout à fait possible de n’utiliser que des solutions respectueuses des données, comme par exemple un « combo » de CMP Tarte au Citron ou Orejime, avec MATOMO pour l’analytique.


Si vous voulez en savoir plus, [contactez-nous](https://claustres.com/accompagnement-rgpd/)!
