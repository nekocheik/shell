# Introduction aux scripts shell

## Introduction

Pour beaucoup shell c'est linux, mais en vrai c'est plus l'architechture unix qui permet de faire des commande.]
la philosophie de unix c'est que tout les choses que l'on peut faire avec une interface graphique, nous pouvons aussi le faire avec des commande.
beaucoup d'appilication mac et linux ne sont que le front de sertaint scripts shell.

il existe plusieurs normes shell,bash n'est pas la seul il y a le sh, tcsh, ash, sh, csh, mais la différence n'est pas trés grande,
les script sont casiment similaire.

le premier des shell c'est sh il est installer sur tout les evironement unix mais il est aussi le moins riche.
est la normes aujourd'hui c'est bash. mais bash n'est pas disponible sur tout les navigateur notament sur sertaint os propriétaire, comme AIX, SOLARIS

## petit tips

`Ctrl + R` se souvenir quelles étaient les dernières commandes tapées (
`Tab` autocompléter une commande ou un nom de fichier
`Ctrl + Z` gérer les processus (envoi en arrière-plan, mise en pause

 Le .bashrc est le fichier de configuration du bash que Linux vous fait utiliser par défaut. Chaque personne peut avoir son .bashrc pour personnaliser son invite de commandes, ses alias, etc.

 ----
## Création du fichier
Commençons par créer un nouveau fichier pour notre script. Le plus simple est d'ouvrir Vim en lui donnant le nom du nouveau fichier à créer :
    $ vim essai.sh

J'ai donné ici l'extension .sh à mon fichier. On le fait souvent par convention pour indiquer que c'est un script shell, mais sachez que ce n'est pas une obligation. Certains scripts shell n'ont d'ailleurs pas d'extension du tout.
J'aurais donc pu appeler mon script essai tout court.

## indiquer le nom du shell

    !/bin/bash

## Les commentaires

    ## Affichage de la liste des fichiers
## Donner les droits d'exécution au script

    $ ls -l
    total 4
    -rw-r--r-- 1 mateo21 mateo21 17 2009-03-13 14:33 essai.sh

Pour connaitre les droit d'écriture d'un fichier il faut regarder -rw-r--r--
le r signifi droit de l'ecture 
le w ecritur 
le x signifi exécution du fichier

    $ chmod +x essai.sh

et maintenant on donne tout les droit 

    $ ls -l
    total 4
    -rwxr-xr-x 1 mateo21 mateo21 17 2009-03-13 14:33 essai.sh

## Exécution de débogage

    $ bash -x essai.sh


## Créer sa propre commande
https://openclassrooms.com/fr/courses/43538-reprenez-le-controle-a-laide-de-linux/42867-introduction-aux-scripts-shell#/id/r-2284152

## Commandes pour débuter

Plus tard, vous ferez probablement de gros scripts et risquerez de rencontrer des bugs. Il faut donc dès à présent que vous sachiez comment déboguer un script.
Il faut l'exécuter comme ceci :

`cd`  change le répertoire courant.
---
`ls`  affiche le contenu d'un répertoire

*	cd .. va dans le répertoire parent du répertoire courant

`cp`  copie un ou plusieurs fichier

* cp toto /tmp
  copie le fichier toto dans le répertoire /tmp
* cp toto titi
  copie le fichier toto sur le fichier titi
* cp -R /home/user /tmp/bak
- copie le répertoire /home/user ainsi que tout ce qu'il contient dans /tmp/bak

`rm` efface un ou plusieurs fichiers

* rm toto titi
  efface les fichiers toto et titi
* rm -f toto titi
  efface les fichiers toto et titi sans demander confirmation

`rm -rf` efface un répertoire et son contenu
* rm -rf /tmp/
- efface (sans demander de confirmation) tous les fichiers et répertoires de
/tmp

`mkdir`	crée un répertoire

* mkdir /home/user/mes_documents 
  crée le répertoire mes_documents dans le sous répertoire /home/user (éviter de mettre des espaces dans les noms de fichiers ou de répertoires)

`rmdir` efface un répertoire s'il est vide

* rmdir /home/user/.nsmail
  efface le répertoire .nsmail de /home/user si celui-ci est vide

`mv` déplace ou renomme un ou des fichiers
* mv tata titi
- renomme tata en titi
* mv * /tmp/bak
- déplace tous les fichiers du répertoire courant vers le répertoire /tmp/bak

`find`  trouve un fichier répondant à certains critères

find /home -name "\*bash\*"
trouve tous les fichiers contenant le mot bash dans leur nom se trouvant dans le répertoire /home

`locate` trouve un fichier d'après son nom

`chmod` modifie les permissions d'un fichier

* chmod o+r /home/user
  autorise les autres (o=other) (ie: ceux qui ne sont ni le propriétaire, ni membre du groupe propriétaire) à lire (r=read) le répertoire /home/user

* chmod a+rw /home/user/unfichier
  autorise tout le monde (a=all) à lire et écrire (w=write) dans le fichier /home/user/unfichier

`chown` modifie le propriétaire d'un fichier

* chown user unfichie
rend user propriétaire de unfichier

`chgrp` modifie le groupe proprétaire d'un fichier

* chgrp -R nobody /home/httpd
  rend le groupe : nobody (un groupe ayant très peu de droit sur un système linux) propriétaire de /home/httpd ainsi que tout les fichiers qu'il contient (-R)

`ln -s` crée un lien vers un fichier

* ln -s /dev/fd0 /dev/disquette
crée un lien vers /dev/fd0 (le lecteur de disquette) nommé /dev/disquette. La manipulation de /dev/fd0 et /dev/disquette (sauf l'effacement).

`grep` recherche une chaine dans un fichier (en fait recherche une expression régulière dans plusieurs fichiers)

* grep chaine \*.txt
- recherche la chaine 'chaine' dans tous les fichier se terminant par .txt.

`which` trouve le répertoire dans lequel se trouve une commande

* which emacs
  retourne le nom du répertoire dans lequel se trouve la commande emacs.

`cat` affiche un fichier à l'écran

* cat ~/.bashrc
  affiche le contenu du fichier ~/.bashrc
