# Guide de prise en main rapide de Centreon

Centreon est une solution de supervision informatique(supervision des applications, des systèmes et des réseaux) disposant d'un noyau gratuit et open source basé sur Nagios.
À ce noyau, il est possible de rajouter des modules complémentaires soit parmi ceux d'une importante palette de modules à valeur ajoutée payants distribués par l'éditeur soit parmi ceux fournis gratuitement par des contributeurs sur GitHub ou encore d'en créer soi-même.

Pour plus d'infos quant aux différences avec Nagios, un comparatif élaboré est disponible à l'adresse suivante:
https://www.centreon.com/blog/blog-vous-aimez-nagios-vous-allez-adorer-centreon/


################################

Centreon est constitué de trois composants open source:
 * **Centreon Web**: c'est l'interface de visualisation
 * **Centreon Engine**: c'est le moteur de collecte de données (basé sur celui de Nagios)
 * **Centreon Broker**: c'est le gestionnaire d'événements

Note: À la base, il n'était constitué que du premier et servait donc de surcouche pour Nagios. Il est maintenant un outil bien plus complet.

Assez parlé, on passe au concret!

## LES PRÉREQUIS

La plateforme ne fonctionne que sur des architectures Linux 64 bits et l'installable n'est disponible que pour les distros RedHat et CentOS mais il est possible d'utiliser les appliances ou de procéder à une installation sur une autre distribution à partir des sources.

Les dépendances pour l'installation sont les suivantes:

	Programme		Version

	Apache			2.4
	GnuTLS			>= 2.0
	Net-SNMP		5.7
	openssl			>= 1.0.1k
	PHP				7.2
	Qt				>= 4.7.4
	RRDtools		1.4.7
	zlib			1.2.3

Le volume de stockage à prévoir peut être défini à partir du tableau disponible à l'adresse suivante:
https://docs.centreon.com/current/en/installation/prerequisites.html#centreon-server-requirements  
Un fichier Excel est aussi mis à disposition pour effectuer ce calcul plus aisément.


L'interface Web de Centreon nécessite une resolution d'écran de 1280 x 768 au minimum et ne fonctionne que sur les navigateurs suivants:
 * **Google Chrome**
 * **Mozilla Firefox**
 * **Apple Safari**

## PROCESSUS D'INSTALLATION

	(À venir)

## CONFIGURATION

	(À venir)

## CONFIGURATION ALERTING & NOTIFICATIONS

Comme dans toutes les solutions de monitoring, Centreon définit le statut des ressources supervisées en utilisant les indicateurs suivants:
* **Les statuts d'hôte**
	*	**UP**			: Hôte disponible et accessible
	*	**DOWN**		: Hôte indisponible
	*	**UNREACHABLE**	: Hôte inaccessible

* _**Les statuts de service**_
	*	**OK**			: Service fonctionnel
	*	**WARNING**		: Service ayant atteint les critères d'alerte définis comme dangereux
	*	**DOWN**		: Service ayant atteint les critères d'alerte définis comme critiques
	*	**UNKNOWN**		: Status du service impossible à vérifier

Un état **SOFT** sera attribué à la ressource pour des incidents nécessitant une confirmation.  
Une fois confirmé, le statut assigné à la ressource sera plutôt **HARD**.

Dès lors qu'un incident est confirmé, il déclenche une alerte à laquelle on peut associer le processus de notification.


################################

[La chaîne YouTube officielle de Centreon](https://www.youtube.com/c/Centreon-Monitoring/videos)
