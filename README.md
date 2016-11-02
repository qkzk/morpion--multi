# morpion--multi

README EDITS
Python 3 multiplayer morpion using socket threads

Projet simple à visées éducatives 
  pour moi : socket, classes, threads, gestion des inputs
  pour mes élèves : toutes les notions ci-dessus, client/serveur, listes, tuples, chaînes de caractères etc.
  
version 0.1
2 fichiers :
* server_morpion.py
* client_morpion.py

Déroulé d'une partie

Après avoir édité les ip du serveur dans les deux fichiers (par défaut localhost=127.0.0.1), le serveur se lance en premier et crée un socket acceptant les connexions.
Le client se connecte automatiquement dessus et engendre la création d'une partie de morpion.
Le client joue en premier en tapant le numéro de la case dans laquelle il souhaite jouer.
Le serveur répond à son tour.
La partie dure jusqu'au remplissement de la grille ou jusqu'à ce qu'une victoire soit déclanchée. La partie peut donc durer alors qu'un match nul est certain.
La gestion des saisies empeche (normalement) le script de planter s'il tape autre chose qu'un entier.

Contenu
à décrire
