# TP1

## Exercice 2

**Manuel**

> Which

Cette commande permet d'afficher (sur la sortie standard) le chemin complet d'un fichier. La commande peut être accompagné d'un ou plusieurs arguments (options).

Pour trouver un terme spécifique dans un manuel (man), on peut simplement faire **/terme** puis **Entrée**.
Pour parcourir les occurrences, on peut appuyer sur **n** (occurrence suivante) ou **Shift n** (occurrence précédente).

Pour quitter le manuel, il suffit d'appuyer sur la lettre **q** (quit).

Pour trouver la première page qui présente le contenu d'une section, il faut faire **man x intro**, **x** faisant référence au numéro de section. 
Ex. :  man 6 intro
[image]
Cette section décrit les jeux et les petits programmes disponibles sur le système.

**Navigation dans l'arborescence des fichiers**

Pour se diriger dans un dossier, on doit utiliser la commande **cd**. 
Ex. : cd /var/log

Pour revenir dans un dossier parent, on peut utiliser **..** (avec seulement 2 points).
Ex. : cd ..

Pour retourner dans le dossier personnel, on utilise *~*.
Ex. : cd ~

Pour revenir dans le dossier précédent (sans utiliser de chemin), on peut utiliser **-**.
Ex. : cd -

L'accès au dossier /root n'est pas autorisé car nous n'avons pas les permissions.

On ne peut pas faire de **sudo cd /root** car **cd** est une commande *builtin*, et non pas un fichier. On ne peut pas utiliser une commande après un **sudo**.

Pour créer un dossier, on peut utiliser la commande **mkdir** suivi du nom du dossier. On peut créer plusieurs dossiers en même temps en mettant les noms des dossiers les uns à la suite séparés par des espaces.
Ex. : mkdir Dossier1
Ex. : mkdir Dossier1 Dossier2

Pour créer un fichier, on peut utiliser la commande **touch** suivi du nom du fichier. On peut créer plusieurs fichiers en même temps en mettant les noms des fichiers les uns à la suite séparés par des espaces.
Ex. : touch Fichier1
Ex. : tocuh Fichier2 Fichier3

On peut rendre la création plus rapide en utilisant **{x..y}** (avec seulement 2 points), **x** et **y** faisant références aux nombres à la fin des fichiers (voir exemple ci-dessous).
Ex. : mkdir Dossier2/Dossier2.{1..2}

La commande **rm** permet de supprimer un fichier. avec d'autres arguments/options, on peut supprimer autre chose que des fichiers tels que des dossiers.

Il n'est pas possible de supprimer (juste avec le nom du fichier) un fichier présent dans un dossier dans lequel nous ne sommes pas.
Ex. : rm Fichier1

Il n'est pas non plus possible de supprimer un dossier simplement avec la commande **rm**, il faut en plus utiliser l'option **-r** suivi du nom du dossier.
Ex. : rm -r Dossier1

La commande permettant de supprimer un dossier est **rmdir nomDossier**, cependant cette commande ne fonctionne pas si le dossier n'est pas vide. 

Il faudra donc opter pour la commande **rm -r nomDossier** afin de supprimer le dossier et son contenu.

**Commandes importantes**

La commande **date** permet d'afficher la date et l'heure courante du système.

La commande **time** permet de déterminer le temps d'exécution d'une commande.

La commande **ls** permet d'afficher les dossiers et fichiers dans le répertoire courant.

La commande **la** affiche les mêmes choses que la commande **ls**, mais afficher également les fichiers commençant par un **.**, ce sont les fichiers cachés.
