
#  TP1

##  Exercice 2

> Manuel

- Which

Cette commande permet d'afficher (sur la sortie standard) le chemin complet d'un fichier. La commande peut être accompagné d'un ou plusieurs arguments (options).

Pour trouver un terme spécifique dans un manuel (man), on peut simplement faire **/terme** puis **Entrée**.

Pour parcourir les occurrences, on peut appuyer sur **n** (occurrence suivante) ou **Shift n** (occurrence précédente).

Pour quitter le manuel, il suffit d'appuyer sur la lettre **q** (quit).

Pour trouver la première page qui présente le contenu d'une section, il faut faire **man x intro**, **x** faisant référence au numéro de section.

Ex. : man 6 intro

[image]

Cette section décrit les jeux et les petits programmes disponibles sur le système.


> Navigation dans l'arborescence des fichiers

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


> Commandes importantes

La commande **date** permet d'afficher la date et l'heure courante du système.

La commande **time** permet de déterminer le temps d'exécution d'une commande.

La commande **ls** permet d'afficher les dossiers et fichiers dans le répertoire courant.

La commande **la** affiche les mêmes choses que la commande **ls**, mais afficher également les fichiers commençant par un **.**, ce sont les fichiers cachés.

Le programme ls se situe dans **/usr/bin/ls**. Pour trouver son chemin d'accès, on peut utiliser ma commande **which ls** (ou potentiellement la commande **whereis ls**).

La commande **ll** n'a pas de manuel, car c'est un alias qui correspond à la commande **ls -alF**.

On peut afficher le contenu d'un dossier avec la commande **ls nomDossier**. Cependant, cette commande affiche les fichiers et répertoires. Pour n'afficher que les fichiers, nous pouvons utiliser la commande **find repertoire -type f**.
Ex. : ls /bin
Ex. : find /bin/ -type f

La commande **ls ..** permet de lister les fichiers et répertoires du répertoire parent.

La commande **pwd** (print working directory) permet d'afficher le chemin complet du répertoire courant.

La commande **echo 'bip' > plop** permet d'écrire directement le mot 'bip' dans le fichier plop (créer automatiquement s'il n'existe pas). Réexécuter la commande une deuxième fois écrase ce qui était écrit précédemment. Au final, nous aurons tout simplement le mot 'bip' écrit dans le fichier plop.

La commande **echo 'bip' >> plop** permet d'écrire à la suite de ce que contient le fichier plop le mot 'bip'. En exécutant cette commande 2 fois. Nous aurons le mot 'bip' 3 fois dans le fichier plop.

**>** permet donc d'écrire par dessus dans un fichier et **>>** permet d'écrire à la suite**.

La commande **sleep 10 | echo 'toto'** écrit le mot 'toto' puis nous n'avons aucune réponse (une pause) pendant 10 secondes.

La commande **file** permet d'indiquer le type d'un fichier en parcourant son contenu.

En créant un lien (physique) entre 2 fichiers (avec la commande **ln fichier1 fichier2**), les 2 fichiers auront le même contenu. Lorsqu'on modifie le contenu d'un des 2 fichiers, l'autre fichier lié est également modifié.

Si on supprime l'un des fichiers, le lien est brisé mais le second fichier n'est pas supprimé pour autant.

Pour créer un lien symbolique, il faut ajouter l'option **-s** à la suite de **ln**. Le fichier lié par lien symbolique est coloré en bleu.

Avec un lien symbolique, si on modifie le contenu de **lien_phy**, cela modifie également **lien_sym**. L'inverse est régit de la même manière.
Si l'on supprime le fichier **lien_phy**, le lien symbolique n'existe plus. Le nom du fichier **lien_sym** devient rouge et son contenu devient vide. Il n'existe plus.

Lors d'un défilement à l'écran, on peut mettre en pause le défilement avec le raccourci clavier **Ctrl s**. Pour reprendre le défilement, on utilise **Ctrl q**.

Pour afficher les n premières lignes d'un fichier, on peut utiliser la commande **head cheminFichier -n nombreLignes**.
Ex. : head /var/log/syslog -n 5

Pour afficher les n dernières lignes d'un fichier, on peut utiliser la commande **tail cheminFichier -n nombreLignes**.
Ex. : tail /var/log/syslog -n 15

Pour afficher des lignes dans un intervalle, on peut combiner les commandes **head** et **tail**.
Ex. : head -n 20 /var/log/syslog | tail -n 10+

La commande **dmesg** permet d'afficher la mémoire tampon de message noyau. La commande **dmesg | less** permet d'effectuer l'analyse de tous les journaux et de les afficher en termes de pages.

Le fichier /etc/passwd contient les informations relatives aux utilisateurs.
La commande qui permet d'afficher la page de manuel de ce fichier est **man 5 passwd**.

Pour afficher seulement la première colonne triée par ordre alphabétique inverse, on peut utilise la commande **cat /etc/passwd | cut -d ':' -f 1 | sort -r**.

Pour avoir le nombre d'utilisateurs ayant un compte sur la machine, on peut utiliser la commande **wc -l /etc/passwd**.

En utilisant les commandes **man -k conversion** ou **apropos conversion**, nous pouvons avoir la liste des manuels dans lesquels figure le terme conversion. Pour en savoir le nombre, nous pouvons ajouter un pipe suivi de **wc -l**.
Ex. : man -k conversion | wc -l

Pour rechercher tous les fichiers se nommant passwd, on peut utiliser **find / -name passwd**.

Pour ajouter le résultat de notre recherche dans un fichier, il suffit d'ajouter **> nom_fichier**.

Pour trouver l'alias à l'aide de la commande **grep**, on peut utiliser la commande **grep -R ' ll'.

La commande **locate nomFichier** nous permet d'afficher le chemin de ce fichier.
Ex. : locate history.log est dans /var/log/apt/history.log

Après avoir créé un fichier, la ccommande **locate nomFichier** ne trouve pas le fichier car ce dernier n'est pas enregistré dans la base de données que parcourt la commande.

## Exercice 3

Pour copier un fichier d'un chemin et le mettre dans notre dossier personnel, on peut utiliser la commande **cp**.
Ex. : cp /var/log/syslog ~/

Pour remplacer toutes les occurrences d'un mot dans 'nano', on peut utiliser **Ctrl \** et remplacer le mot qu'on veut remplacer par le mot en question.

Pour déplacer plusieurs lignes, On va utiliser **Ctrl ^** pour sélectionner les lignes voulues, puis **Ctrl k** pour couper, et **Ctrl u** pour coller à l'emplacement désiré.

Pour annuler l'action et donc revenir en arrière, on peut utiliser **Alt u**.

Enfin, pour enregistrer les modifications et quitter nano, on fait **Ctrl o** pour enregistrer et **Ctrl x** pour sortir de 'nano'.

## Exercice 4

Pour faire une recher dans 'nano', on peut utiliser le raccourci **Ctrl w**.

La commande source .bashrc nous permet d'activer les modifications faites dans .bashrc sans avoir à se déconnecter et se reconnecter.

La ligne pour faire cet affichage ressemble à : PS1='${debian_chroot:+($debian_chroot)}\[\033[35m\][\A]\[\033[00m\] - \[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[36m\]\w\[\033[00m\]\$ '
