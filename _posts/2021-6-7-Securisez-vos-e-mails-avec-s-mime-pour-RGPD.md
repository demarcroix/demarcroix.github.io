---
layout: post
title: "Sécurisez vos e-mails avec S-MIME pour qu'ils soient RGPD-compatibles !"
---
Le cryptage de bout en bout tend à devenir la norme sur les applications mobiles de messagerie : WhatsApp, Messenger, Telegram, Signal...

De son côté, le plus ancien et le plus répandu des protocoles de messagerie, l'e-mail, continue de diffuser sur Internet une grande quantité de messages et pièces jointes sans aucun cryptage.

Alors que plus de 300 milliards d'e-mails sont échangés chaque année dans le monde [Source Statistica](https://fr.statista.com/statistiques/583905/nombre-d-e-mails-par-jour-dans-le-monde--2019/).

C'est devenu un outil de travail nécessaire pour réaliser de nombreuses tâches administratives ou commerciales, ou même simplement personnelles dès que l'on fait de nouvelles rencontres.

Tout cela étant encore accentué depuis 2020 avec le Covid-19, qui a favorisé le télétravail et la dématérialisation des procédures, qui souvent passent par des échanges d'e-mails quand elles n'ont pas été suffisamment anticipées en amont.

L'e-mail est donc un "tuyau" dans lequel circulent énormément de données personnelles, sensibles ou non, qui questionnent par conséquent sur leur protection - et donc leur rapport au RGPD (Règlement Européen sur les Données Personnelles).

Le premier niveau de sécurisation de ces e-mails est le protocole de chiffrage TLS qui tend à se généraliser chez les fournisseurs d'e-mail, mais qui nous allons le voir présente des limites auquel le protocole S/MIME peut pallier.

Nous allons donc essayer d’y voir plus clair avec cet article.

### Les limites du TLS

Le protocole TLS (Transport Layer Security) permet d'envoyer des données chiffrées à un serveur e-mail, de la même façon qu'un site Web "https" crypte les données transmises dans les deux sens.

Cela fonctionne aussi bien sur un Webmail (https) qu'avec un client e-mail, comme Outlook ou Thunderbird.

Toutefois il présente deux limites : la première limite concerne la diffusion des e-mails en dehors de la plateforme considérée.

En effet, tant que vous envoyez des e-mails à des correspondants qui font partie de la même plateforme e-mail (Gmail, Yahoo! Mail., SFR Mail..) la confidentialité vis-à-vis des tiers est normalement protégée lors de vos échanges.

Par contre, si vous écrivez à quelqu'un qui n'est pas sur la même plateforme d'e-mail, il existe un risque important qu'à l'occasion du transfert d'une plateforme à l'autre, voire de la plateforme de votre correspondant à son client e-mail, les informations transitent en clair sur les réseaux.

[Google fournit un outil](https://transparencyreport.google.com/safer-email/overview?hl=fr) qui permet d'évaluer les risques de perte de confidentialité de Gmail sur les réseaux: pour faire court, un utilisateur de Gmail a globalement **1 chance sur 10** d'avoir une perte de confidentialité lors de l'échange de ses e-mails avec un tiers.

La seconde limite est la capacité de ces plateformes à accéder à vos informations, notamment quand il s'agit de solutions d'origines américaines soumises au **CLOUD (Clarifying Lawful Overseas Use of Data) Act**, adopté le 23/03/2018, juste deux mois avant l'entrée en vigueur du RGPD (24/05/2018).

Cela permet concrètement aux autorités américaines (FBI, CIA, NSA...) d'accéder en toute légalité à tout document, dont les e-mails, qui sont hébergés par des sociétés américaines, et ce partout dans le monde...

Or le protocole TLS se contente d'assurer la confidentialité des transferts de données sur les plateformes e-mails, pas de sécuriser les données hébergées sur ces plateformes: pour cela, il faudrait que les e-mails soient eux-mêmes cryptés.

C'est ce qu'il est possible de faire avec le protocole S/MIME, standardisé en 1999 par [l'IETF](https://www.ietf.org/) mais malheureusement encore peu répandu dans le grand public.

### Le cryptage asymétrique des e-mails avec S/MIME

S/MIME est une solutions de cryptage asymétrique standardisées qui repose sur le couple clé privée/clé publique: la clé privée de l'émetteur de l'e-mail permet de signer son message pour l'authentifier, le contenu du message envoyé est crypté quant à lui avec la clé publique du destinataire.

![Cryptage et signature S/MIME]({{ site.baseurl }}/images/SMIME/signatue-cryptage-email-smime "Signature et cryptage des e-mails avec SMIME"){: .center-image }

Le problème est que  plupart des Webmails ne proposent pas S/MIME en standard, voire ne le proposent pas du tout!

Par exemple, c'est possible de crypter avec S/MIME avec Gmail, mais uniquement en version professionnelle. Je n'ai rien trouvé de tel sur Yahoo! Mail, en gratuit ou payant. Rien vu non plus sur les Webmails d'Orange ou de SFR...

Heureusement, les deux principaux clients emails Outlook et Thunderbird proposent S/MIME en standard dans leurs dernières versions.

Encore faut-il avoir un certificat S/MIME me direz-vous?

###  Comment obtenir son certificat S/MIME ?

Divers services plus ou moins payants permettent de générer les certificats S/MIME : [Actalis](https://www.actalis.it/en/certificates-for-secure-electronic-mail.aspx), [Sectigo](https://sectigo.com/ssl-certificates-tls/email-smime-certificate), [SSL.com](https://www.ssl.com/fr/client-mime-et-certificats-de-signature-de-documents/)...

Mais peu de gens savent que l'on peut se passer de ces générateurs de certificats avec un logiciel gratuit comme OpenSSL, [disponible ici pour Windows 10](https://slproweb.com/products/Win32OpenSSL.html), et devenir aussi sa propre autorité de certification!

[Un article résume assez bien la méthode à suivre](https://www.dalesandro.net/create-self-signed-smime-certificates/), mais il faut toutefois reconnaître que ça reste encore assez technique, limite pénible et en tous cas peu adapté au grand public.

Et quand vous aurez enfin généré votre certificat S/MIME, il faudra encore l'installer dans le client de messagerie, par exemple sur [Thunderbird](https://www.ssl.com/fr/comment/installer-un-certificat-mime-s-et-envoyer-des-e-mails-s%C3%A9curis%C3%A9s-dans-mozilla-thunderbird-sur-windows-10/) ou [Outlook](https://www.ssl.com/fr/comment/installation-du-certificat-mime-s-envoi-de-courrier-%C3%A9lectronique-s%C3%A9curis%C3%A9-Outlook-Windows-10/).

Avec patience et méthode je suis finalement arrivé au bout de ce processus, mais finalement je me sens un peu seul dans ce cercle vertueux de la sécurisation des e-mail, car maintenant il faut que je trouve des correspondants qui auront eux aussi fait l'effort de mettre en place le cryptage d'email S/MIME...

Si vous désirez en savoir plus, [contactez-nous](https://claustres.com/accompagnement-rgpd/)!
