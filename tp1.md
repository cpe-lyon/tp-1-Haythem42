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

Pour créer un dossier, on peut utiliser la commande **mkdir** suivi du nom du dossier. On peut créer plusieurs fichiers en même temps en mettant les noms des dossiers les uns à la suite séparés par des espaces.
Ex. : mkdir Dossier1
Ex. : mkdir Dossier1 Dossier2

Pour créer un fichier, on peut utiliser la commande **touch**
