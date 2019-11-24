# VIM

* Mode interactif : c'est le mode par défaut par lequel vous commencez. En lançant Vim, vous êtes donc en mode interactif.

Dans ce mode, vous ne pouvez pas écrire de texte (oui, je sais, il s’agit d’un comble pour un éditeur de texte !). N'essayez donc pas d'appuyer sur des lettres au hasard car vous risqueriez de faire n'importe quoi !Le mode interactif est un mode puissant qui permet de se déplacer dans le texte, de supprimer une ligne, copier-coller du texte, rejoindre une ligne précise, annuler ses actions, etc. Chaque action peut être déclenchée en appuyant sur une touche du clavier (par exemple, on appuie surupour annuler la dernière action).

* Mode insertion : celui-là, c'est celui que vous connaissez ! Vous tapez du texte et ce dernier s'insère à l'endroit où se trouve le curseur.

Pour entrer dans ce mode, il existe plusieurs possibilités. L’une des plus courantes est d'appuyer sur la touchei(insertion). Pour en sortir, il faut appuyer sur la toucheEchap.


* Mode commande : ce mode permet de lancer des commandes telles que « quitter », « enregistrer », etc. Vous pouvez aussi l'utiliser pour activer des options de Vim (comme la coloration syntaxique, l'affichage du numéro des lignes…). Vous pouvez même envoyer des commandes au shell (la console) telles quels,locate,cp, etc.

Pour activer ce mode, vous devez être en mode interactif et appuyer sur la touchedeux points« : ». Vous validerez la commande avec la toucheEntréeet reviendrez alors au mode interactif.

Je résume. Vim possède trois modes (figure suivante) : interactif, insertion et commande. Vous démarrez en mode interactif. Le seul mode que vous connaissez et qui ne sera pas nouveau pour vous est le mode insertion. Les deux autres modes (interactif et commande) vont quelque peu vous surprendre.


# Le déplacement
h,j,k,l : *se déplacer dans tous les sens*
En mode interactif, il est possible de déplacer le curseur au sein du texte. Pour cela, on utilise les touches :

h : aller à gauche ;

j : aller en bas ;

k : aller en haut ;

l : aller à droite.

## 0et$ : se déplacer en début et fin de ligne

Pour placer le curseur au tout début de la ligne, appuyez sur0en mode interactif.
La toucheOrigineque vous avez peut-être l'habitude d'utiliser fonctionne aussi. Cependant, retenez plutôt qu'il faut utiliser0, ça vous sera utile par la suite.

De même, pour se rendre en fin de ligne, appuyez sur la touche$.
Là encore, la toucheFinfonctionne elle aussi, mais essayez de prendre l'habitude d'utiliser$ ; ce sera payant, vous allez voir.



## :w : enregistrer le fichier

Pour enregistrer votre fichier, vous devez être au préalable en mode interactif (appuyez surEchappour vous en assurer).

Appuyez ensuite sur la touchedeux points« : » pour passer en mode commande, puis tapezw(write) suivi du nom du fichier. La commande doit s'afficher en bas.

Dans mon cas, j'ai donc tapé:w monfichier(figure suivante). Appuyez ensuite sur la toucheEntréepour valider. Le bas de l'écran doit indiquer que le fichier a été écrit (written) :

## :q : quitter

Maintenant que vous avez enregistré, vous pouvez quitter Vim en tapant:q.

Vim vous interdit de quitter si vous n'avez pas enregistré vos changements. Vous pouvez toutefois forcer la fermeture du logiciel en ajoutant un point d'exclamation à la fin ::q!. Cette fois, il n'y aura aucune erreur.



##  :wq : enregistrer puis quitter

C'est la combinaison des deux commandes que nous venons de voir. Vous enregistrez et quittez immédiatement Vim lorsque vous tapez:wq.

## Les opérations standard (copier, coller, annuler…)

Nous avons vu l'essentiel des commandes les plus courantes. Nous allons maintenant découvrir une série de commandes un peu plus complexes parmi lesquelles la fusion de fichiers, la recherche, le remplacement, le découpage de l'écran (split), etc.

Toutes ces commandes se lancent depuis le mode interactif.


# / : rechercher un mot

Si vous tapez/, vous passez en mode recherche. Le curseur se place en bas de l'écran (vous indiquant que vous êtes passés en mode commande).
Écrivez ensuite le mot que vous recherchez, par exemple « remplir » :/remplir. Tapez ensuite surEntréepour valider.

Le curseur se place alors sur la prochaine occurrence de « remplir » dans le fichier.
Pour passer à la prochaine occurrence du mot, plus bas dans le fichier (s'il apparaît plusieurs fois), appuyez surn. Pour rechercher en arrière, appuyez surN(Maj + n).




### :s : rechercher et remplacer du texte

Pour rechercher et remplacer du texte, c'est un peu plus compliqué. Il y a en effet plusieurs façons d'effectuer le remplacement.

La plus simple façon d’effectuer une recherche consiste à taper:s/ancien/nouveaupour rechercher « ancien » et le remplacer par « nouveau ». Le problème… c’est que cela ne remplacera que la première occurrence d'« ancien » par « nouveau ».

* :s/ancien/nouveau : remplace la première occurrence de la ligne où se trouve le curseur ;
* :s/ancien/nouveau/g : remplace toutes les occurrences de la ligne où se trouve le curseur ;
* :#,#s/ancien/nouveau/g : remplace toutes les occurrences dans les lignes n° # à # du fichier ;
* :%s/ancien/nouveau/g : remplace toutes les occurrences dans tout le fichier. C'est peut-être ce que vous utiliserez le plus fréquemment.

### :r : fusion de fichiers
Avec:r, vous pouvez insérer un fichier à la position du curseur. Vous devez indiquer le nom du fichier à insérer, par exemple ::r autrefichier.

L'autocomplétion avecTabfonctionne là aussi, donc pas besoin d'écrire le nom du fichier en entier !

Le découpage d'écran (split)

## Le découpage d'écran (split)

Vim possède une fonctionnalité pratique : il permet de découper l'écran et d'ouvrir plusieurs fichiers.

:sp : découper l'écran horizontalement

:vsp : découper l'écran verticalement


### Les principaux raccourcis en écran splitté

Chaque morceau de l'écran (correspondant à un fichier) est appelé viewport.
Voici une liste de raccourcis pratiques que vous pouvez utiliser lorsque l'écran est splitté (scindé).

* Ctrl + wpuisCtrl + w : navigue de viewport en viewport. Répétez l'opération plusieurs fois pour accéder au viewport désiré.

* Ctrl + wpuisj : déplace le curseur pour aller au viewport juste en dessous. La même chose fonctionne avec les touchesh,ketlque l'on utilise traditionnellement pour se déplacer dans Vim.

* Ctrl + wpuis+ : agrandit le viewport actuel.

* Ctrl + wpuis- : réduit le viewport actuel.

* Ctrl + wpuis= : égalise à nouveau la taille des viewports.

* Ctrl + wpuisr : échange la position des viewports. Fonctionne aussi avec « R » majuscule pour échanger en sens inverse.

* Ctrl + wpuisq : ferme le viewport actuel.


### :! : lancer une commande externe

Il est possible d'écrire des commandes traditionnelles du shell directement dans Vim. Pour cela, commencez par taper:!suivi du nom de la commande.

Essayez par exemple de taper:!ls. Vous afficherez alors le contenu du dossier dans lequel vous vous trouvez !
Cette fonctionnalité est bien pratique pour effectuer quelques actions sans avoir à quitter Vim.


