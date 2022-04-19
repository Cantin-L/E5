BTS SERVICES INFORMATIQUES AUX ORGANISATIONS	SESSION 2022
Épreuve E5 - Administration des systèmes et des réseaux (option SISR) 
ANNEXE 7-1-A : Fiche descriptive de réalisation professionnelle (recto)

DESCRIPTION D’UNE RÉALISATION PROFESSIONNELLE	N° réalisation : 2
Nom, prénom : LIOTTARD Cantin	N° candidat : 2145656516
Épreuve ponctuelle	0
Contrôle en cours de formation	1
Date : 12 / 04 / 2022
Organisation support de la réalisation professionnelle : Société AssurMer

Intitulé de la réalisation professionnelle : 
Réception des mails d’alerte en lien avec GLPI (ticket) et les alertes Nagios.
Période de réalisation : 	 Lieu : Pontoise
Modalité :	1  Seul(e)		0  En équipe

Compétences travaillées
	1 Concevoir une solution d’infrastructure réseau
	1 Installer, tester et déployer une solution d’infrastructure réseau
	1 Exploiter, dépanner et superviser une solution d’infrastructure réseau

Conditions de réalisation  (ressources fournies, résultats attendus)

Avoir l'infrastructure d'assurmer fonctionnel
Avoir configurer DMZ
Serveur SNMP (Nagios XI)
Serveur de messagerie linux (IRedMail via SOgo)
Serveur Broker (pour la phase de test)

Description des ressources documentaires, matérielles et logicielles utilisées 

Ressources fournies
Topologie réseau
Plan d'adressage IP
Documentation IRedMail
Procédure création de ticket

Résultats attendus
Permettre aux techniciens qui reçoivent des tickets via GLPI de recevoir un mail d’alerte qu’un nouveau
ticket lui a été affecter.
Et aussi lorsqu’une machine tombe ou a un souci sur Nagios il y a un message d’alerte qui est
envoyé sur le compte nagios@mcl.fr.
Modalités d’accès aux productions  et à leur documentation 

Url : https://github.com/Cantin-L/E5


BTS SERVICES INFORMATIQUES AUX ORGANISATIONS	SESSION 2022
Épreuve E5 - Administration des systèmes et des réseaux (option SISR) 
ANNEXE 7-1-A : Fiche descriptive de réalisation professionnelle 
(verso, éventuellement pages suivantes)

Descriptif de la réalisation professionnelle, y compris les productions réalisées et schémas explicatifs


Objectif :
L’objectif de cette mission est de permettre aux serveur Nagios d’envoyer des alertes en cas de problème sur les Serveurs supervisés. Et en même temps d’envoyé un mail lors de l’affectation d’un ticket a un technicien. 

Description : 

Nous devons vérifier le bon fonctionnement du serveur de messagerie. Nous avons créé deux nouveaux utilisateurs nagios@mcl.fr et glpi@mcl.fr. Qui seront nos deux utilisateurs pour le reporting 
des tickets et des alertes.

Ensuite il faut aller respectivement sur les deux serveurs et paramètres le système de messagerie.
Avec les informations suivantes.
L’hôte est avec l’adresse ip 172.16.68.3 (DMZ) protocole SMTP TLS sur le port 587.


Phase de testing : 

Pour vérifier si notre nouvelle configuration fonctionne, nous utiliseront le système de test sur nagios et glpi. Puis nous sélectionnerons une machine de l’infrastructure supervisé par le serveur smnp et nous allons volontairement l'éteindre ou arrêter un de ses services pour que le Nagios envoie une alerte, l’utilisateur Nagios@mcl.fr devrait recevoir un mail d’alerte sur le serveur de messagerie concernant l’arrêt d’un service ou d’une machine. 
Pour le test du service GLPI nous affectons un ticket a un technicien et ensuite nous allons voir sur sa boite mail s’il le reçoit bien.

