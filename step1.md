## Déclarer une variable

la déclaration des variable en shell sont assez special la sythaxe est la dernière

  message='Bonjour tout le monde'
  variable='valuer'

il ne faut surtout pas mettre d'espace entre la variable et le = et la string


### pour afficher

pour afficher les valeur il suffi de faire un echo

  echo Salut tout le monde

la commade echo permet tout simplement d'écrire dans un output (le terminale).
dans le code au dessus le echo ne foctionne pas comme voulu, chaqun des mots sont pris indépendament, il sont chaqun des parramétre de echo.
pour qu'il soit reconnue comme string il faut mettre des guillemets pour qu'il soit compris comme une seul string.

  echo "Salut tout le monde"

pour fair des saut à la ligne il faut ajouter un parramétre -e a echo puis mettre \n ou l'on veut faire le saut a la ligne.

  echo -e "Message\nAutre ligne"
  Message
  Autre ligne

#### Afficher une variable

pour afficher les variable il suffit de mettre la variable précédé du signe $

  message='Bonjour tout le monde'
  echo $message
 
pour afficher un message avec une variable et du texte préremplie,

  message='Bonjour tout le monde'
  echo "Le message est : $message"

mais attention avec les simple quotes les variable ne sont pas interpreté
avec les bat quotes les les variable a l'intérieu sont interpreté, oui !!! interpreté !!! un exemple.

  message=`pwd`
  echo "Vous êtes dans le dossier $message"

le message qu'il renvoie

  Vous êtes dans le dossier /home/mateo21/bin 

## read : demander une saisie

pour affecter une variable il suffi de mettre read devant, on peut meme affecter plusieurs variables en meme temps.

  read nom prenom
  echo "Bonjour $nom $prenom !"

il aussi plusieurs parramétre qui permet d'ajouter plus specificité a la saisie par exemple.

`-p` le parramétre permet d'ajouter du texte au moment de la saisie.

  read -p 'Entrez votre nom : ' nom
  echo "Bonjour $nom !"

`-n` permet de mettre une limite au champ saisie

  read -p 'Entrez votre login (5 caractères max) : ' -n 5 nom
  echo "Bonjour $nom !"

`-t` limite le temps de saisie
    
    read -p 'Entrez le code de désamorçage de la bombe (vous avez 5 secondes) : '  -t 5 code
    echo -e "\nBoum !"

`-s` n'affiche pas la saisie

    read -p 'Entrez votre mot de passe : ' -s pass
    echo -e "\nMerci ! Je vais dire à tout le monde que votre mot de passe est $pass ! :
    

### effectuer des calcules 

bash ne permet pas de manipuler des nombres comme dans pleins d'autres langague, mais n'est craite il y a moyen de calculé.
avec les let, je te fait un petit exemple.

    let "a = 5"
    let "b = 2"
    let "c = a + b"
    echo $c
    
* l'addition : + ;

* la soustraction : - ;

* la multiplication : * ;

* la division : / ;

* la puissance : ** ;

* le modulo (renvoie le reste de la division entière) : %.

      let "a = 5 * 3" # $a = 15
      let "a = 4 ** 2" # $a = 16 (4 au carré)
      let "a = 8 / 2" # $a = 4
      let "a = 10 / 3" # $a = 3
      let "a = 10 % 3" # $a = 1

pour les division le résulta renvoyé est toujours un entier.

il est aussi possible d'incrémenter les valeur comme ça.

    let "a = a * 3"
    
    let "a *= 3"

### Les variables d'environement

actuellement les variables creé dans les programmes ne sont accécible qu'à l'intérieu des programmes.
c'est pour cela qu'il y a une chose magnifique qui s'appel les variables d'environement, pour les voir il suffi de faire la commade `env`.
et parmi c'est variables il en n'a des très utiles, et même nous vérons comment en creé.
parmis les plus utiles il y a.

* `shell` qui indique dans quel type de shell le programme tourne
* `PATH` contien une liste de chemin pour les fichier qui veulent être exevuté en global, par exemple je pourrais mettre l'un de mes chemin a l'intérieu pour que je ne renseigne le chemin du shell.
* `EDITOR` et l'éditeur qui souvre par défaut
* `HOME` c'est le chemin du home
* `PWD` le chemin dans le quel est excuté le code
* `OLDPWD` c'est le chemin prècèdent



