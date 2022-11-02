---
layout: post
title: "RGPD et pseudonymisation ou anonymisation des données de santé"
---


Je suis souvent confronté à cette réflexion par des professionnels des métiers de la santé: "il n'y a plus de données personnelles de patients (nom, prénom, date de naissance, numéro de SS etc.) dans ces données de santé, DONC c'est un traitement de données anonymes"...

Et logiquement, ils en déduisent qu'il n'est plus nécessaire de prendre de précautions renforcées pour protéger ces données personnelles, comme par exemple un hébergement externalisé certifié HDS (Hébergement de Données de Santé).

Malheureusement, ce n'est pas si simple.

En fait c'est typiquement une des difficultés du Règlement Européen sur les Données Personnelles (RGPD), celle d'utiliser des mots du langage courant avec un sens bien spécifique:
* la notion de **données personnelles** est très large, et va bien au-delà des données directement identifiantes ; et la CJUE tend qui plus est à élargir ce spectre dans son [arrêt du 01/08/2022](https://curia.europa.eu/jcms/jcms/p1_3839338/fr/) sur la déduction d'informations sensibles dans le cadre d'un traitement de données personnelles.
* la notion d'**anonymisation** suppose qu'il ne soit plus possible de réidentifier la personne concernée, ce qui est contradictoire par exemple avec la nécessité d'effectuer un rapprochement post traitement pour rattacher ce traitement de données au bon patient...

Nous verrons dans cet article les différentes méthodes permettant d'assurer la confidentialité des données de santé, notamment la pseudonymisation et l'anonymisation, les problématiques liées de réidentifications, ainsi que l'importance de l'étude de l'impact potentiel sur les personnes concernées.


## 1. La pseudonymisation, simple mesure de sécurisation des données personnelles

La notion de pseudonymisation sous-entend que les données personnelles sont toujours **individualisées**, même si les éléments d'identification directe de la personne concernée (nom, prénom, numéro de sécurité sociale, date de naissance, sexe, adresse postale...) du jeu de données initial ont été retirés ou masqués (remplacés par "NIR", "NOM", "PRENOM" etc. comme le recommande notamment la CNIL dans son [référentiel concernant les entrepôts de données de santé](https://www.cnil.fr/sites/default/files/atoms/files/referentiel_entrepot.pdf)).

Néanmoins, il y a toujours un élément (un index) qui permet de **réidentifier** les individus dans la base de données pseudonymisées, par **rapprochement** avec une autre base de données qui lie cet index aux informations d'identification directe de la personne concernée.

Il s'agit donc d'une simple mesure de sécurisation des données, **réversible** comme l'est un chiffrage de données, utile notamment dans les cas de sous-traitance ou de recherche sur les données personnelles de santé.

Par exemple, dans le cas d'un Centre d'Imagerie Médicale (CIM), la pseudonymisation est utilisée pour transmettre l'image médicale (IM) d'un patient à un sous-traitant qui va réaliser une pré-interprétation de celle-ci grâce à de l'intelligence artificielle.

Le traitement du sous-traitant se fait dans uns infrastructure conforme HDS, **car la pseudonymisation des IM ne change pas leur statut de données personnelles de santé**.

Une fois le traitement terminé, le pré-diagnostic est retourné au CIM, qui peut ensuite le réattribuer au bon patient, grâce à la base de données d'identification qui permet ce rapprochement.

Le schéma suivant présente ce processus de pseudonymisation-réidentification:

![Schéma CIM et pseudonymisation]({{ site.baseurl }}/images/rgpd-sante/cim-im-pseudonymisee.png "Schéma CIM et pseudonymisation"){: .center-image }

On pourrait objecter que rien ne ressemble plus à une radio de poumons, qu'une autre radio de poumons, et que seul le CIM dispose de la base de correspondances nécessaire pour faire le rapprochement.

Mais en réalité, le fait que ces données de santé soient **individualisées** les expose à un risque de réidentification par **recoupement**, c'est à dire en comparant par exemple ces radios avec d'autres radios, en croisant ce résultat avec une base de rendez-vous d'un prestataire tiers du CIM qui a été piratée etc.

## 2. Le difficile challenge de l'anonymisation

Contrairement à la pseudonymisation, l'anonymisation de données personnelles doit être irréversible.

Le G29, Groupement de l'article 29 regroupant les autorités de contrôle de la protection des donnéess personnelles préalablement au RGPD/GDPR et CEPB/EDPB [avait donné son avis en 2014 ce que devaient être des données anonymisées](https://www.cnil.fr/sites/default/files/atoms/files/wp216_fr.pdf):
* **Individualisation impossible**, contrairement justement à la pseudonymisation,
* **Corrélation impossible**, i.e. aucun lien entre des ensembles de données distincts concernant un même individu,
* **Inférence impossible**, i.e. pas possible de déduire de nouvelles informations sur un individu.

Si un seul de ces trois critère n'est pas rempli, on peut considérer que ces données ne sont pas anonymisées _stricto sensu_, et donc qu'il s'agit toujours de données personnelles.

### 2.1. Les méthodes d'anonymisation par randomisation

Les différentes méthode de randomisation étudiées par le G29 sont les suivantes:
* **randomisation par ajout de bruit**, notamment en réduisant la précision/granularité des données personnelles pour réduire les risques de réidentification ; par exemples, réduire la précision de l'a taille d'un individu de +/- 10 cm,  réduire la précision sur le poids d'un individu de +/-10 kg .
* **randomisation par permutations**, pour corréler artificiellement les données entre des individus différents, par exemples en permutant les tailles et poids des individus.
* **randomisation par confidentialité différentielle**, pour rajouter un bruit mathématique aux données personnelles qui n'altérera pas le traitement  de ces données. On est proche dans l'esprit du chiffrage de ces données personnelles, en optimisant le niveau de bruit pour ne pas nuire au résultat du traitement de ces données. C'est une solution promue notamment par [Google en open source](https://github.com/Google/private-join-and-compute) pour garantir la confidentialité des données personnelles dans le Big Data/Open Data.

Si un humain peut difficilement effectuer une réidentification à partir de ces données, elles présentent un biais logique qui est de **continuer à individualiser les données personnelles sources**.

Le tableau suivant synthétise les conclusions du G29 sur les méthodes de randomisation:

![Tableau anonymisation par randomisation]({{ site.baseurl }}/images/rgpd-sante/anonymisation-randomisation.png "Tableau anonymisation par randomisation"){: .center-image }

Le cas Netflix est une bonne illustration des problématiques de randomisation par ajout de bruit, où [Arvind Narayanan et VitaliyShmatikov](https://www.cs.utexas.edu/~shmat/shmat_oak08netflix.pdf) ont réussi à **réidentifier jusqu'à 99% des 500 000 individus** d'une base pseudonymisée de plus de 100 millions d'évaluations de films, avec pourtant rajout de bruit sur les notes et dates, simplement en la croisant avec une base de notations publique de films tierce IMDB...

### 2.2. Les méthodes d'anonymisation par généralisation

Le principe d'anonymisation par généralisation est de **supprimer l'individualisation des données personnelles**, notamment en les regroupant sous forme de **cohortes** de même caractéristiques pour qu'il ne soit plus possible de les réidentifier.

Les différentes méthodes de généralisation étudiées par le G29 sont les suivantes:
* **k-anonymat**: il s'agit d'effectuer des agrégations avec au moins k individus, en réduisant la granularité de leurs données personnelles pour qu'ils partagent les mêmes valeurs. Par exemple, regrouper les individus par fourchettes d'âge à la place de leur date de naissance, ou des fourchettes de poids ou de tailles.
* **l-diversité/t-proximité**: il s'agit de pallier aux attaques par inférences du k-anonymat en s'assurant que les attributs des cohortes aient au moins l valeurs différentes (l-diversité) et que leur distribution ne dépasse pas un seuil t (t-proximité).

A ces deux méthodes de généralisation, nous rajoutons comme le fait par exemple le spécialiste du traitement de données [PALANTIR](https://blog.palantir.com/au-del%C3%A0-de-lanonymisation-palantir-mode-d-emploi-no-3-b0af71e4c980) les **données synthétiques**, qui reposent sur la génération de nouvelles séries de données corrélées aux données originales, notamment:
* **Réseaux Antagonistes Génératifs** (ou **GAN**), antagonistes car mettant en compétition un réseau neuronal "générateur" et un réseau neuronal "discriminateur" dans un process d'apprentissage par les machines (machine learning). Au fil de l'apprentissage, le générateur va créer de nouvelles données, dont la pertinence sera validée par le réseau discriminateur.
* **Auto Encodeurs Variables** (ou **VAE**), où un "encodeur" va déterminer dans un premier temps caractéristiques moyennes et spécificités (ou variances) des données initiales, qui sont ensuite "décodées" pour générer de nouvelles données au caractéristiques proches.

Avec des données synthétiques, on ne traite plus des données originales des patients, ce qui rend impossible l'individualisation ou la corrélation; toutefois si la répartition de la nouvelle série de données est très proche de la série d'origine, l'inférence reste possible par du recoupement avec des données tierces.

Le tableau suivant synthétise les performances respectives des différentes solutions de généralisation:

![Tableau anonymisation par généramisation]({{ site.baseurl }}/images/rgpd-sante/anonymisation-generalisation.png "Tableau anonymisation par généralisation"){: .center-image }

En fin de compte, il n'y a pas de méthode d'anonymisation parfaite ou idéale car la réidentification peut dans certains cas être possible, quel que soit le procédé d'anonymisation utilisé, notamment grâce au recoupement avec des données tierces.

[La CNIL conclut à ce sujet](https://www.cnil.fr/fr/recherche-scientifique-hors-sante/enjeux-avantages-anonymisation-pseudonymisation) qu'"À défaut de remplir parfaitement ces trois critères, il doit être démontré, via une évaluation approfondie des risques d’identification, que le **risque de réidentification avec des moyens raisonnables est nul**."

[PALANTIR](https://blog.palantir.com/au-del%C3%A0-de-lanonymisation-palantir-mode-d-emploi-no-3-b0af71e4c980) ne parle pas d'ailleurs anonymisation stricto sensu dans son article, "Puisque le terme d’anonymisation peut comporter un sens usurpé de sécurité en suggérant que les données ne peuvent être ré-identifiées, Palantir recommande que les organisations lui substituent le terme “**dé-identification**”. Concernant les techniques en elles-mêmes, "(...) chacune présentant avantages et inconvénients, permettant de **sensiblement réduire** les risques de réidentification". (mis en gras par nous)

## 3. Pseudonymisation, anonymisation et analyses d'impacts dans la recherche en santé

La problématique de l'anonymisation dans la recherche, c'est qu'en réduisant la granularité des données personnelles de santé voire en les généralisant complètement, on risque de perdre aussi en pertinence des résultats...

Le **Health Data Hub** (HDH) a évoqué cette problématique [des données anonymes en santé](https://www.health-data-hub.fr/actualites/guides-donnees-de-sante-anonymes), qui passe en pratique par un nécessaire compromis entre ces deux questions:
* a-t-on besoin de préserver la **granularité** des informations au niveau des individus ?
* a-t-on besoin de **partager** simplement et largement les données ?

La **pseudonymisation** s'impose quand conserver la granularité des données individuelles est nécessaire pour réaliser les études, ou qu'il faut avoir la possibilité de réidentifier ultérieurement les patients: étude des parcours de soins, études cliniques au sein d'un établissement de santé...

L'**anonymisation** s'impose dès lors que l'on n'a pas besoin de données identifiantes, ou que le partage large et simple des données est une nécessité: statistiques anonymes, partage de résultats dans le cadre de la recherche pour en assurer la reproductibilité...

Toutefois, il est utile de rappeler que la **notion de risque mitige un évènement redouté** (ici la réidentification) avec sa **probabilité de réalisation**, mais aussi avec son **impact** sur les personnes concernées (les patients).

Ainsi, le [Guide d'évaluation du caractère anonyme d'un jeu de données dans le cadre d'un projet de recherche](https://www.health-data-hub.fr/sites/default/files/2022-09/Guide%20d%E2%80%99%C3%A9valuation%20du%20caract%C3%A8re%20anonyme%20d%E2%80%99un%20jeu%20de%20donn%C3%A9es%20v2%20%281%29.pdf) donne quelques conseils, notamment concernant l'analyse de risque de réidentification pour le patient (ou Analyse d'Impact sur la Protection des Données, AIPD).

Pour illustrer son propos, le HDH reprend notre cas des patients d'un CIM, mais cette cette fois les IM ne sont plus pseudonymisées quand elle sortent du PACS, mais "anonymisées" (plus d'index permettant le recoupement comme avec la pseudonymisation) pour être rendues disponibles pour des chercheurs.

En fait, nous parlerons ici plus de **déidentification** comme le fait PALANTIR, car si il n'y a plus d'index comme dans l'IM pseudonymisée, l'IM en elle-même n'a pas subit la moindre modification pour éviter un rapprochement ultérieur avec les images du PACS du CIM. Le rapprochement des IM étant possible sans difficultés majeures, on pourrait considérer d'ailleurs qu'on est toujours dans un cas particulier de **pseudonymisation**, et donc qu'il s'agit toujours de données personnelles de santé.

Le schéma suivant présente ce processus de déidentification-réidentification:

![Schéma CIM et anonymisation]({{ site.baseurl }}/images/rgpd-sante/cim-im-anonymisee.png "CIM et anonymisation"){: .center-image }

Si l'on reprend l'AIPD proposée par le HDH, cela donne le tableau (TRES simplifié) suivant:

![Tableau AIPD en santé]({{ site.baseurl }}/images/rgpd-sante/aipd-sante.png "Tableau AIPD en santé"){: .center-image }

Ainsi, quoique la réidentification grâce au PACS du CIM soit quasi certaine à partir des images déidentifiées, le risque lié au traitement reste au final acceptable, notamment parce que la sécurisation du PACS qui pourrait permettre ce rapprochement est excellente, et que l'impact sur les personnes concernées en cas de rapprochement est considérée comme négligeable.


Au final le RGPD ne donne pas de recettes miracles pour protéger les données de santé, mais il oblige les chercheurs à un minimum de réflexions ex ante sur la meilleure façon de procéder en fonction des objectifs recherchés, tout en anticipant avec des AIPD sur les impacts potentiels de ces traitements pour les personnes concernées.

Et comme je l'avais écrit dans une précèdent article, [DPO et professionnels de santé sont fait pour s'entendre]({{ site.baseurl }}/dpo-et-professionnels-de-sante-sont-ils-faits-pour-s-entendre/), car la vision du Délégué à la Protection des Données qui défend l'intérêt des patients apporte sa contribution pour assurer la cohérence globale du projet de recherche.
