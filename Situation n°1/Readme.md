BTS SERVICES INFORMATIQUES AUX ORGANISATIONS	SESSION 2022
Épreuve E5 - Administration des systèmes et des réseaux (option SISR) 
ANNEXE 7-1-A : Fiche descriptive de réalisation professionnelle (recto)

DESCRIPTION D’UNE RÉALISATION PROFESSIONNELLE	N° réalisation : 1
Nom, prénom : LIOTTARD Cantin	N° candidat : 2145656516
Épreuve ponctuelle	0
Contrôle en cours de formation	1
Date : 12 / 04 / 2022
Organisation support de la réalisation professionnelle : Société AssurMer

Intitulé de la réalisation professionnelle : Mise en place d’un VPN SSL pour accéder aux ressources de l’entreprise tant logiciel qu’au niveau des données sur les serveurs.
Période de réalisation : 	 Lieu : Pontoise
Modalité :	1  Seul(e)		0  En équipe

Compétences travaillées
	1 Concevoir une solution d’infrastructure réseau
	1 Installer, tester et déployer une solution d’infrastructure réseau
	1 Exploiter, dépanner et superviser une solution d’infrastructure réseau

Conditions de réalisation  (ressources fournies, résultats attendus)

Avoir l'infrastructure d'assurmer fonctionnel
Avoir configurer Pfsense
Infrastructures relié à internet
Client W10 (pour la phase de test)

Description des ressources documentaires, matérielles et logicielles utilisées 

Ressources fournies
Topologie réseau
Plan d'adressage IP
Documentation Pfsense
Documentation OpenVPN
Documentation VPN SSL
Procédure de réalisation dans le descriptif de la réalisation professionnel.

Résultats attendus
Permettre aux collaborateurs nomades ou en télétravail d'accéder aux ressources d'Assurmer tant logiciels qu’au niveau des données sur les différents serveurs.


Modalités d’accès aux productions  et à leur documentation 

Url : https://github.com/Cantin-L/E5


BTS SERVICES INFORMATIQUES AUX ORGANISATIONS	SESSION 2022
Épreuve E5 - Administration des systèmes et des réseaux (option SISR) 
ANNEXE 7-1-A : Fiche descriptive de réalisation professionnelle 
(verso, éventuellement pages suivantes)

Descriptif de la réalisation professionnelle, y compris les productions réalisées et schémas explicatifs


Objectif :
L’objectif de cette mission est de permettre aux collaborateurs nomades ou en télétravail d'accéder aux ressources d'Assurmer.


 

 

Étapes :
I. La gestion des certificats
II. Créer les utilisateurs locaux
III. Configurer le serveur OpenVPN
IV. Exporter la configuration OpenVPN
V. Modifier les règles de firewall pour OpenVPN
VI. Tester l'accès distant depuis un poste client

Explication détaillée
I. La gestion des certificats
Tout d'abord nous devront créer une unité de certification sur pfsense.
Système > unité de certification

Nous la nommerons CA-ASSURMER, puis sauvegarderons.

Ensuite nous devons créer un certificat serveur.
Nous la nommerons VPN-SSL-CERT, nous sélectionnerons aussi l'unité de certification créer au-dessus. Enfin nous validerons la création du certificat serveur.
II. Créer les utilisateurs locaux
Nous allons créer un utilisateur qui aura les accès pour la connexion VPN.
Système > gestion des utilisateurs.
Surtout il ne faudra pas oublier de cocher la création d'un certificat d'utilisateur.

III. Configurer le serveur OpenVPN
Nous allons alors configurer le VPN
VPN > OpenVPN
Pour la création il faut bien créer un Serveur VPN. Puis accès distant (SSL/TLS + authentification d’utilisateur).
Il faudra bien sélectionner l'unité de certification et le certificat de serveur créer précédemment.
Remplir les informations suivantes
IPV4 TUNNEL NETWORK : 20.0.0.0/24
IPV4 LOCAL NETWORK : 192.168.200.0/24
CURRENT CONNECTIONS : 20
Dans les paramètres clients il faudra cocher IP Dynamique.

Ensuite il faudra cocher le : Provive a default domain name to clients puis rentré notre domaine mcl.fr et notre serveur DNS 172.16.0.1
La configuration est maintenant terminée.

IV. Exporter la configuration OpenVPN
Il faut alors exporter la configuration pour cela nous allons installer un paquet qui s'appelle openvpn-client-export.
Système > Manageur des paquets > paquets disponibles.
Une fois installé retourner dans VPN > OpenVPN > Client Export.
On télécharge l'exécutable pour Windows.

V. Modifié les règles de firewall pour OpenVPN
Modifié la règle WAN pour protéger notre infrastructure.
Nous devons modifier le port d'attaque d'openvpn car nous avons mis un port spécial !

VI. Tester l'accès distant depuis un poste client
Il suffira d'exécuter l'exécutable sur le poste client faire suivant pour installer OpenVPN puis rentré les informations d'authentification puis le tour est joué ! 
Il faut ouvrir un cmd et taper ipconfig /all puis si nous avons une adresse IP comme 20.0.0.1 en tant que préférée c’est que tout marche vous aurez accès à toutes les ressources comme si vous étiez en agence.
L'accès VPN SSL pour vos utilisateurs nomades ou en télétravail est désormais fonctionnel !


