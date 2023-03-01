---
layout: post
title: "SMS frauduleux et protection des données personnelles"
---
Les SMS frauduleux sont une forme de cybercriminalité qui utilise les messages texte des téléphones mobiles pour tromper les destinataires en leur faisant croire qu'ils ont besoin de divulguer des informations personnelles, de payer des frais ou de cliquer sur un lien. Ils prennent souvent la forme de messages légitimes d'une entreprise (téléphonie, énergie, télévision payante...) ou d'un organisme public (ANTAI, AMELI, impôts...), mais ils sont en réalité conçus pour voler vos informations personnelles ou votre argent. Les cybercriminels utilisent des techniques sophistiquées pour cibler des personnes spécifiques et leur envoyer des SMS frauduleux personnalisés, dans une logique souvent quasi industrielle avec des envois se comptant souvent par centaines de milliers...

Faire le tour d'un tel sujet en un seul article sera forcément réducteur, mais notre objectif ici sera de présenter les principaux enjeux liés aux SMS frauduleux: les violations de données personnelles au sens du Règlement Européen sur la Protection des Données (RGPD/GDPR), et notamment leur impact psychologique et financier pour les personnes concernées.

Tout d'abord, nous allons présenter les différents types de SMS frauduleux et comment les cybercriminels obtiennent les numéros de téléphone cibles. Ensuite, nous examinerons les risques liés aux SMS frauduleux, notamment les conséquences pour les utilisateurs cibles, les risques pour les entreprises et organisations et comment ils peuvent compromettre la sécurité des données personnelles. Enfin, nous discuterons des mesures que les utilisateurs peuvent prendre pour se protéger des SMS frauduleux, notamment les bonnes pratiques pour protéger son téléphone, comment identifier les SMS frauduleux et les différencier des messages légitimes et que faire en cas de réception d'un SMS frauduleux.

## 1. Origine des SMS frauduleux

Les SMS frauduleux sont des messages texte envoyés sur les téléphones mobiles qui tentent de tromper les destinataires en leur faisant croire qu'ils ont besoin de divulguer des informations personnelles, de payer des frais ou de cliquer sur un lien.

Les SMS frauduleux peuvent sembler être des messages légitimes d'une entreprise ou d'une organisation de confiance (entreprises ou organismes publics), mais ils sont en réalité conçus pour voler des informations personnelles ou de l'argent:  ils jouent souvent comme toute escroquerie sur l'urgence d'une opération à réaliser, par exemple payer une contravention routière à l'ANTAI avant sa majoration, ou profiter de ses Crédits Personnels de Formation (CPF) avant leur prochaine expiration...

Ils peuvent également être utilisés pour propager des logiciels malveillants ou des virus sur les téléphones (cheval de Troie, cryptovirus...), souvent en lien avec un "pot de miel" comme l'accès gratuit à un site phonographique ou à des bonus gratuits sur des jeux en ligne.

### 1.1. Les différents types de SMS frauduleux

Il en existe de différents types, notamment:
* **Les SMS d'hameçonnage (_phishing_)** : ils tentent de vous faire cliquer sur un lien qui vous redirige vers un site Web frauduleux où vous êtes invité à divulguer des informations personnelles telles que votre nom, adresse e-mail, numéro de téléphone, mot de passe...
* **Les SMS d'arnaque** : ces SMS tentent de vous faire payer des frais pour un produit ou un service que vous n'avez jamais acheté ou demandé. Par exemple, on vous signale qu'on a cherché à vous livrer un colis de grande valeur qui a déjà été présenté à plusieurs reprises à votre domicile sans succès, et il faudra payer quelques euros pour pouvoir le récupérer...
* **Les SMS d'usurpation d'identité** : ces SMS se font passer pour des messages légitimes d'une entreprise ou d'une organisation de confiance, mais ils sont en réalité conçus pour voler des informations personnelles ou de l'argent: ANTAI pour des contraventions routières, nouvelle vignette Crit'Air, abonnement Netflix, opérateurs téléphoniques, renouvellement de votre carte vitale (AMELI)...

Quelques exemple de **vrais** SMS frauduleux: n'essayez surtout pas de tester les liens Web!

![Exemples de SMS frauduleux]({{ site.baseurl }}/images/sms-frauduleux/exemples-de-sms-frauduleux.png "Exemples de SMS frauduleux"){: .center-image }

Liste non exhaustive, la créativité des cybercriminels étant malheureusement assez remarquable, en particulier pour la qualité de la scénarisation de l'escroquerie: par exemple ils peuvent partir du renouvellement de votre carte Vitale, pour vous demander le paiement d'une dizaine d'euros par carte bancaire, qui bizarrement échoue. Ensuite vous êtes rappelé par un conseiller de votre banque (un cybercriminel...), qui bien sûr est comme vous surpris de l'échec du paiement CB, et vous demande de faire de votre côté un test avec votre compte en ligne sur le Web ou le mobile, en validant un virement de plusieurs milliers d'euros "qui ne sera pas effectué réellement"...

Ce type d'arnaque est possible parce que la banque du porteur de CB peut être identifiée à partir du numéro de sa carte bancaire, permettant ainsi de rappeler la cible au nom de sa banque. La CNIL a d'ailleurs consacré [une page entière aux durées de conservation et modalités de protection des numéros de cartes bancaires](https://www.cnil.fr/fr/le-paiement-distance-par-carte-bancaire) en 2018, mesures [confirmées depuis par la CNIL des CNIL européenne (le CEPD/EDPB)](https://edpb.europa.eu/our-work-tools/our-documents/recommendations/recommendations-022021-legal-basis-storage-credit-card_fr) en 2021.

### 1.2. Comment les cybercriminels obtiennent-ils les numéros de téléphone ?

Les méthodes des cybercriminels pour obtenir des numéros de téléphones mobiles sont multiples, citons par exemples:
* **Le piratage de bases de données** : d'entreprises ou d'organismes publics qui stockent des informations personnelles. La collecte d'information des cybercriminels va souvent bien au delà du simple numéro de téléphone: nom, prénom, adresse, liste d'achats (site e-commerce) etc. Ce qui permet des scénarisations d'arnaques très sophistiquées, par la très bonne connaissance du profil de la cible à partir de ses données personnelles.
* **L'utilisation de logiciels malveillants** : pour accéder aux contacts sur le téléphone d'une personne et obtenir ainsi des numéros de téléphone. Les applications mobiles peuvent comporter intentionnellement ou non ce genre de "fonctionnalités": attention donc aux éditeurs "exotiques" qui proposent monts et merveilles avec leurs apps gratuites...
* **L'utilisation de listes de numéros de téléphone volés** : les cybercriminels peuvent acheter des listes de numéros de téléphone volés par exemple sur le Dark Web, où ils bénéficient d'une certaine forme d'anonymat et donc d'impunité, avec souvent paiement en Bitcoins intraçables.
* **L'utilisation d'IMSI Catcher** :  ce sont des dispositifs utilisés pour intercepter les communications mobiles en se faisant passer pour un relais d'opérateur mobile, par une attaque classique de type _man in the middle_. Ils peuvent envoyer des SMS frauduleux en usurpant l'identité de l'opérateur mobile, notamment en utilisant une faille de sécurité de la norme 2G. Une telle fraude a été observée début 2023 en région parisienne, avec [une voiture qui en se déplaçant avait capté 16 000 numéros de mobiles et envoyé plus de 400 000 SMS frauduleux](https://www.leparisien.fr/faits-divers/arnaque-aux-sms-la-voiture-espionne-avait-aspire-les-donnees-de-16-000-franciliens-19-02-2023-VOMKOISIEJEH3KTJAH4N6BKG3Y.php)...

Dans tous les cas, les utilisateurs de téléphone mobile doivent être vigilants et suivre les bonnes pratiques de sécurité énumérées dans la section 3.1. de cet article.

## 2. Les conséquences des SMS frauduleux

### 2.1. Conséquences psychologiques et financières pour les personnes ciblées

Les conséquences pour les utilisateurs cibles de SMS frauduleux peuvent être graves pour les personnes concernées, citons notamment :
* **L'usurpation d'identité** : les cybercriminels peuvent utiliser les informations personnelles volées pour s'approprier l'identité de la personne et commettre des fraudes en son nom sans être inquiété. Par exemple, [comme le rappelle la Banque de France](https://particuliers.banque-france.fr/info-banque-assurance/arnaques-les-bons-reflexes/usurpation-didentite-et-problemes-bancaires-que-faire), pour obtenir un prêt à la consommation avec un établissement financier en ligne, ou simplement ouvrir un compte bancaire et émettre des chèques qui reviendront impayés...
* **Les pertes financières** : l'objectif des SMS frauduleux peut aussi être d'obtenir un acte de paiement (CB, virement, Bitcoin...) de la part de la personne concernée, avec des scénarios plus ou moins sophistiqués. La "qualité" de leur ingénierie sociale est capable de recouper des informations issues de logiciels malveillants ou de virus, ou plus simplement de la consultation de vos profils sur les réseaux sociaux. Les progrès de l'IA générative permet des _deepfakes_ inimaginables il y a quelques années, par exemple [l'utilisation de la voix générée par une IA comme identification biométrique pour accéder frauduleusement à un compte bancaire](https://www.vice.com/en/article/dy7axa/how-i-broke-into-a-bank-account-with-an-ai-generated-voice).
* **Les affections psychologiques** : c'est la conséquence des deux précédentes, avec une culpabilité renforcée par la honte de "s'être fait avoir bêtement"... C'est pourquoi le RGPD étudie les conséquences d'une violation de données personnelles sous l'angle de l'affection psychologique de la personne concernée, notamment quand sont réalisées des Analyses d'Impact relatives à la Protection des Données (AIPD). Car les conséquence peuvent être dramatiques: [un ouvrier agricole se serait suicidé suite à une usurpation d'identité qui l'a endetté à hauteur de 180 000 euros](https://www.ladepeche.fr/2022/12/21/qui-etait-regis-paluzzano-louvrier-agricole-crible-de-dettes-qui-a-mis-a-fin-a-ses-jours-10753197.php).

Le vrai danger est de sous-estimer le fait qu'on puisse devenir une cible des cybercriminels, parce qu'on croit qu'ils vont aller arnaquer plus riches ou plus crédules que soi : en pratique ils travaillent de façon quasi industrielle en ratissant le plus large possible, et se soucient peu des conséquences pour les personnes concernées.

### 2.2. Conséquences pour les organismes publics ou privés

La captation de données personnelles a de plus en plus pour objectif de s'attaquer aux organismes publics et privés, comme par exemple dans le domaine de la santé où des hôpitaux et cliniques sont victimes de cryptovirus qui rendent inaccessibles les données de santé, en vue d'obtenir une rançon pour les déchiffrer (ransomware).

En effet, alors qu'il y a encore une vingtaine d'années les organisations cybercriminelles ciblaient principalement les individus pour obtenir des "petits" paiements dépassant rarement quelques milliers d'euros, la tendance actuelle est plutôt de s'attaquer à des organismes publics et privés pour obtenir des rançons de plusieurs millions d'euros! Ainsi, [le Centre Hospitalier Sud-Francilien s'était vu demander en août 2022 une rançon de 10 millions de dollars](https://siecledigital.fr/2022/08/23/essonne-le-centre-hospitalier-sud-francilien-victime-dune-cyberattaque-majeure/) par des cybercriminels...

Et en cas de non-paiement, voire y compris en cas de paiement, ces données personnelles de clients, patients ou usagers seront revendues sur le Dark Web : les cybercriminels sont donc quasiment toujours gagnants...

Les conséquences pour ces organismes sont multiples:
* **Perturbation de l'activité** : les infrastructures informatiques deviennent inutilisables, et le recours à des processus à base de stylo et de papier permettent de pallier au plus pressé. Mais dans les hôpitaux et cliniques, les conséquences peuvent être de reporter les opérations les moins urgentes, ou d'envoyer les patients qui nécessitent des soins urgents dans d'autres établissements. Avec parfois des conséquences dramatiques, comme cette [allemande qui est décédée en 2020 faute d'avoir pu être prise en charge par l'Hôpital de Düsseldorf, victime d'un ransomware](https://siecledigital.fr/2020/09/18/une-femme-decede-au-cours-dun-ransomware-dans-un-hopital-allemand/). Ou de mettre en grande difficulté les entreprises et leurs salariés, comme cela a été le cas par exemple pour la société [Lise Charmel qui s'est retrouvée en redressement judiciaire en février 2020](https://www.zdnet.fr/actualites/lise-charmel-l-entreprise-lyonnaise-en-redressement-judiciaire-suite-a-un-ransomware-39900133.htm), suite à une attaque de type ransomware 4 mois plus tôt: elle a dû licencier une centaine de ses collaborateurs dans les mois qui ont suivi, [même si elle a pu au final sortir de ce redressement judiciaire](https://business.lesechos.fr/entrepreneurs/gestion-finance/0700049870440-lingerie-lise-charmel-sort-amaigrie-mais-remusclee-du-redressement-judiciaire-345421.php).
* **Responsabilité juridique** : l'organisme peut être condamné en cas de violation de données personnelles s'il n'a pas mis en place les mesures techniques et organisationnelles nécessaires à la protection des données personnelles. Ainsi, en décembre 2021 [la société SLIMPAY a été condamnée par la CNIL à hauteur de 180 000 euros pour ne pas avoir suffisamment protégé les données personnelles de ses utilisateurs](https://www.cnil.fr/fr/violation-de-donnees-sanction-de-180-000-euros-lencontre-de-la-societe-slimpay).
* **Perte de réputation** :  en s'attaquant à des organismes de plus grande taille, l'information sur la compromission de données personnelles devient généralement publique et largement diffusée dans les médias, et entache au final la confiance qu'on pouvait leur porter. Ce qui peut en plus le cas échéant être aggravé en cas de condamnation par la CNIL pour négligences dans la protection des données personnelles qu'ils hébergeaient.

Là encore, la sous-estimation du risque cyber est souvent un facilitateur pour les cybercriminels. Dans le cas des hôpitaux et cliniques, les équipements dédiés à la santé des patients sont priorisés par rapport à la sécurisation des systèmes d'informations, ce qui en font des cibles de choix.

## 3. Comment se protéger des cybercriminels ?

### 3.1. Quelques bonnes pratiques à respecter quand vous recevez un SMS

Quand vous recevez un SMS:
* **Ne divulguez jamais vos données personnelles** :  ne répondez pas à des SMS demandant votre numéro de sécurité sociale, votre mot de passe, votre numéro de CB etc. Plus généralement, ne partagez jamais vos informations personnelles avec des personnes ou des entreprises que vous ne connaissez pas ou en qui vous n'avez pas confiance.
* **Vérifiez toujours l'expéditeur** : avant de cliquer sur un lien dans un SMS, assurez-vous que l'expéditeur est légitime. Toutefois, certaines méthodes frauduleuses comme celles utilisant des IMSI Catchers ou du SMS _spoofing_, peuvent donner l'impression de provenir d'un expéditeur légitime...
* **Ne cliquez jamais sur les liens sans réfléchir** : ne cliquez sur un lien dans un SMS que si vous êtes certain qu'il provient d'un expéditeur légitime.

L'ensemble de ces mesures de précaution, qui découlent en fait du simple bon sens, concernent d'ailleurs aussi bien les SMS frauduleux que les e-mail frauduleux.

### 3..2. Quelques bonnes pratiques pour protéger ses données personnelles

Sur votre téléphone mobile:
* **Installez un antivirus** : il vous protègera des logiciels malveillants et des virus, aussi bien sur les liens de SMS frauduleux que lors de la navigation sur des sites Web avec votre smartphone. Attention toutefois à ne pas se reposer uniquement sur cette protection, qui n'est malheureusement pas parfaite.
* **Protégez correctement vos données personnelles** : utilisez des mots de passe forts pour tous vos comptes, en évitant d'utiliser des informations personnelles évidentes comme votre date de naissance ou votre nom. Pour vous en souvenir, des applications mobiles dédiées vous permettrons de les gérer. Vous pouvez consulter à ce sujet les [recommandations de la CNIL](https://www.cnil.fr/fr/mots-de-passe-une-nouvelle-recommandation-pour-maitriser-sa-securite). Utilisez quand c'est possible la lecture d'empreinte digitale, pour éviter que des tiers puissent vous voir taper le code d'accès à votre téléphone mobile ou à une application. Utilisez quand c'est possible une identification à double facteur (2FA), pour ne pas faire reposer la sécurisation des accès sur la seule connaissance des mots de passe.
* **Evitez de stocker des informations sensibles** : par exemple, ne pas y stocker votre votre numéro de sécurité sociale, la copie de votre carte d'identité ou votre numéro de CB, sans les avoir préalablement chiffrés.

### 3.3. Signaler les SMS frauduleux au 33700

Pour travailler à la sécurisation de votre téléphone mobile de façon collective, vous pouvez [signaler un SMS frauduleux au 33700](https://www.33700.fr/identifier-et-signaler-un-spam-sms/#comment-signaler-spam-sms).

La procédure se déroule en 2 étapes (gratuit pour les grands opérateurs téléphoniques):
* **Transférer le SMS frauduleux au 33700**, sans y rajouter de commentaires ;
* **Répondre au message envoyé dans la foulée par le 33700**, avec le numéro qui est à l'origine du SMS frauduleux.

Si l'expéditeur des SMS frauduleux fait l'objet de nombreux signalements, il pourra être blacklisté par les opérateurs. Bien sûr, les organisations cybercriminelles qui utilisent des techniques de types SMS _spoofing_ ou IMSI Catcher ne seront pas directement impactées par ces mesures...


Le RGPD a permis de prendre conscience de l'importance à protéger nos données personnelles, mais ces dernières restent malgré tout constamment sous la menace de SMS frauduleux. Au delà des personnes concernées, leur violation peuvent aussi impacter  la réputation et l'activité des organismes publics et privés. La sécurisation de nos téléphones mobile est au final une responsabilité partagée de bonnes pratiques entre des individus et des organismes publics et privés: nous devons tous faire notre part pour éviter que nos données personnelles tombent aux mains des organisations cybercriminelles.
