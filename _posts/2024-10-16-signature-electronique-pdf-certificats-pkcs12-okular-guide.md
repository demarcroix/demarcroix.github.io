---
layout: post
title: "Maîtrisez la signature électronique des PDF avec Okular et un certificat PKCS12"
description: "Découvrez comment signer vos PDF de manière sécurisée grâce à la technologie PKCS12. Ce guide pratique, centré sur les outils Okular et Firefox sous Windows, vous aidera à rester conforme au RGPD tout en protégeant l'intégrité de vos documents."
---
Dans le cadre de la dématérialisation numérique, la signature électronique suscite l'intérêt des Délégués à la Protection des Données (DPO). En effet, le Règlement Européen sur la Protection des Données (RGPD) requiert notamment la signature de nombreux Accord de Traitements de Données (DPA) avec les Sous-traitants. Nous nous proposons ici de vous éclairer sur le fonctionnement et la mise en œuvre pratique de la signature électronique des documents PDF à l'aide de certificats PKCS12 stockés sur Firefox et de la visionneuse de PDF Okular.

Okular et Firefox sont des outils gratuits et multiplateformes: Windows, Linux, Mac... Nous présenterons ici la démarche sous Windows, mais qui potentiellement sera très proche sur les autres plateformes. Quant à l'obtention d'un certificat PKCS12, contrairement aux idées reçues il n'est pas nécessaire de passer par un (coûteux) organisme tiers. Vous pouvez le générer par vous-même comme déjà évoqué dans le cadre de notre article à propos de [la sécurisation des e-mails avec SMIME]( {{ site.baseurl }}/Securisez-vos-e-mails-avec-s-mime-pour-RGPD/ "Sécurisez vos e-mails avec S-MIME pour qu'ils soient RGPD-compatibles !").

![RGPD et IA]({{ site.baseurl }}/images/okular-pdf-signature-pkcs12.jpg "Signez vos PDF avec Okular et PKCS12"){: .center-image }

Nous explorerons d'abord le principe de fonctionnement de la signature électronique de PDF, avant de nous pencher sur sa mise en œuvre pratique à l'aide d'outils comme Okular et Firefox sous Windows.


## Le principe de fonctionnement de la signature électronique

### Comprendre la signature électronique

Vous pensiez peut-être que la signature électronique et la signature par insertion d'une simple image de signature dans un document avaient la même valeur probante? Or ce n'est pas le cas.

En effet, l'insertion d'une image de signature ne garantit pas que le reste du document ait fait l'objet d'une modification postérieurement à sa signature.

La signature électronique semble fonctionner de manière analogue à une signature manuscrite sur un document papier. Cependant, elle offre un niveau de sécurité et de vérification d’identité notablement supérieur. En effet, l'utilisation d'un certificat numérique garantit à la fois l'authenticité du signataire et l'intégrité du document postérieurement à sa signature.

Les certificats PKCS12 jouent ici un rôle crucial. PKCS12 est un standard de format qui permet de stocker et de transférer des informations sensibles telles que des clés privées et des certificats publics. Ces certificats sont comme une carte d'identité numérique pour votre signature électronique.

### Pourquoi la signature électronique est-elle un must du point de vue du RGPD ?

La signature électronique s'inscrit parfaitement dans la logique du RGPD en assurant que les documents restent intègres tout au long de leur cycle de vie. Le DPO a ainsi la garantie que le document n'a pas été modifié depuis sa signature : si ce n'était pas le cas, par exemple en cas de contentieux suite à une violation de données chez le Sous-traitant, les clauses de notification et d'assistance prévues dans le DPA pourraient être remises en cause par l'une des parties.

Le processus de signature électronique implique la création d'un hachage du document, qui est ensuite chiffré à l'aide d'une clé privée. Ce hachage chiffré constitue la signature numérique et peut être comparé à une empreinte digitale unique du document. **Toute modification ultérieure de ce document rendrait la signature invalide, garantissant l'intégrité de son contenu**.

Rappelons toutefois que dans le cadre du RGPD, le DPO n'est pas habilité à signer directement ces DPA, car cela constituerait un conflit d'intérêt avec sa mission de contrôleur de la conformité RGPD: seul un représentant du Responsable du Traitement d'une part, et celui du Sous-traitant d'autre part, pourront utiliser cette solution de signature électronique.

## Mise en œuvre pratique sous Windows avec Okular et Firefox

### Pourquoi doit-on installer Firefox en plus d'Okular ?

La mise en œuvre de la signature électronique d'un fichier PDF avec Okular est aussi simple qu'efficace, notamment grâce à son interface intuitive. [Okular](https://okular.kde.org/fr/) est un visualiseur de documents numériques (PDF, ePub, Markdown...) qui offre un support natif pour la signature électronique des PDF.

De son côté, [Firefox](https://www.mozilla.org/fr/firefox/) facilite la gestion des certificats PKCS12: ainsi, lorsque vous utilisez d'autres applications comme Okular, avoir ces certificats gérés dans Firefox permet leur réutilisation sécurisée sans nécessiter de configuration complexe.

Si vous avez déjà installé Firefox, vous n'aurez bien entendu pas à le réinstaller pour bénéficier de cette fonctionnalité de gestion des certificats PKCS12.

### Comment installer votre certificat PKCS12 dans Okular ?

Voici comment procéder en pratique :

- **Installation Préalable** : assurez-vous que Firefox et Okular sont installés sur votre système Windows, et que votre certificat PKCS12 est accessible sur un répertoire de votre poste de travail.
- **Importation de votre Certificat PKCS12 dans Firefox** : si votre certificat PKCS12 n'est pas déjà installée dans Firefox, accédez au menu des paramètres de Firefox, puis allez à la section "Vie privée & Sécurité". Cliquez sur le bouton "Afficher les certificats", puis sélectionnez l'onglet "Vos certificats". Cliquez enfin sur "Importer...", puis sélectionnez votre certificat PKCS12 pour le rajouter dans cet onglet.
- **Chargement du Certificat** : lancez Okular, sélectionnez dans le menu "Configuration" le choix "Configurer les moteures de rendu..." puis cliquez sur le bouton "PDF". Vous accédez alors aux "Certificats disponibles", où votre certificat numérique en format PKCS12 devrait déjà figurer: c'est votre clé privée nécessaire à la signature électronique. Si rien ne s'affiche, il faudra introduire manuellement le lien vers la base de signature de Firefox dans le champ "Personnalisé", puis fermer et réouvrir Okular afin de voir si le certificat a bien été chargé.
- **Processus de Signature** : ouvrez un fichier PDF, sélectionnez dans le menu "Outils" le choix "Signature numérique en cours..." puis suivez les instructions pour appliquer votre signature au document ouvert. Une fois ce process achevé, Okular vous proposera de sauvegarder le PDF signé.

La signature électronique des PDF via des certificats PKCS12 représente donc une avancée significative pour les professionnels soucieux de respecter le RGPD. En combinant les capacités de logiciel comme Okular et les fonctionnalités de Firefox, on crée un environnement où l'intégrité des contrats est placée au cœur du processus de gestion documentaire du RGPD.
