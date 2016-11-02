# morpion--multi

README EDITS
Python 3 multiplayer morpion using socket threads

Projet simple à visées éducatives 
  pour moi : socket, classes, threads, gestion des inputs
  pour mes élèves : toutes les notions ci-dessus, client/serveur, listes, tuples, chaînes de caractères etc.
  
################ version 0.1 #####################
2 fichiers :
* server_morpion.py
* client_morpion.py

############### partie ##########################
Après avoir édité les ip du serveur dans les deux fichiers (par défaut localhost=127.0.0.1), le serveur se lance en premier et crée un socket acceptant les connexions.
Le client se connecte automatiquement dessus et engendre la création d'une partie de morpion.
Le client joue en premier en tapant le numéro de la case dans laquelle il souhaite jouer.
Le serveur répond à son tour.
La partie dure jusqu'au remplissement de la grille ou jusqu'à ce qu'une victoire soit déclanchée. La partie peut donc durer alors qu'un match nul est certain.
La gestion des saisies empeche (normalement) le script de planter s'il tape autre chose qu'un entier.


############### commentaires généraux ###############


partie de morpion
Par défaut la grille est une liste de taille 9 ne contenant que des 0.
Chaque joueur choisit la case sur laquelle déposer son jeton.
Selon le joueur on ajoute donc 1 ou 4.
La victoire est testée à chaque tour en faisant la somme des lignes, colonnes
et diagonales. Si une des somme vaut 3 le joueur 1 a gagné, si elle vaut 12 c'est
le joueur 2.
Si toutes les cases sont pleines : match nul.

################### serveur socket
le serveur est crée à l'initialisation du script et attend les connexions entrantes.
Chaque message reçu est traité : exception pour les erreurs de type, msg d'erreur
si la case est pleine.
Le serveur envoie à chaque interraction (du joueur 
A l'execution il crée les variables et lance jouer()

################### client socket
Le client crée 2 threads qui sont des sous-classes de Threading.thread
Le premier pour la réception et l'affichage des messages, le second pour l'envoi.
Deux threads sont nécessaires car le nombre de messages reçus est imprevisible.
Une mauvaise saisie ou une fin de partie génére un nombre non prévisible de messages.

Cette approche rend le client très facile à adapter pour d'autres usages.
Hormis la gestion de la saisie (qui empeche d'envoyer autre chose qu'un nombre
entre 0 et 8 dans une chaine), tout est réutilisable pour un client chat classique.


################## sources ################################
le client est celui du livre approrendre_python3.pdf que j'ai à peine modifié.
le morpion est personnel (voilà pourquoi il est si mal codé). La partie serveur du
client a été trouvée par hasard sur le net, celui du même manuel n'envoyait rien.



