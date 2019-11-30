## Les variables des paramètres

le truc bien avec les scripts shell c'est qu'il est possible d'ajouter des paramètres pour pouvoir le rendre modulables.
mais comment récuperer des paramètres dans le scripts
comme ça !

* $# : contient le nombre de paramètres ;

* $0 : contient le nom du script exécuté (ici ./variables.sh) ;

* $1 : contient le premier paramètre ;

* $2 : contient le second paramètre ;

$9 : contient le 9e paramètre.

c'est variables contient les paramètres.

il est possible de déclarer que 9 variables, mais en générale on les utililse un n'à un.
mais comment faitons, c'est très simple avec shift on peut décaler les variables de un.

#!/bin/bash

    echo "Le paramètre 1 est $1"
    shift
    echo "Le paramètre 1 est maintenant $1"

## les tableau

    tableau=('valeur0' 'valeur1' 'valeur2')

    # pour afficher la valeur2

    ${tableau[2]}
      
    # pour affecter une valeur

    tableau[2]='valeur2'

    # afficher tout un tableau

    tableau[*]


## les conditions

les conditions 

    if [ test ]
    then
            echo "C'est vrai"
    fi

il est possible d'écrire le  then sur la même ligne mais a ce moment il faut ajouter un point virgule.

    if [ test ]; then
            echo "C'est vrai"
    fi

    if [ $nom = "Bruno" ] 


## else

    else

    elif [ autre_test ] 

## les type de conditions,

avec les script shell on peut vérifier dans une condition,
les chaine de caracter 
les nombres
les fichiers

#!/bin/bash

    if [ -z $1 ]
    then
            echo "Pas de paramètre"
    else
            echo "Paramètre présent"
    fi

-z $chaine
Vérifie si la chaîne est vide.

-n $chaine
Vérifie si la chaîne est non vide.

## Tests sur des nombres

$num1 -eq $num2

Vérifie si les nombres sont égaux (equal). À ne pas confondre avec le « = » qui, lui, compare deux chaînes de caractères.

$num1 -ne $num2

Vérifie si les nombres sont différents (nonequal).
Encore une fois, ne confondez pas avec « != » qui est censé être utilisé sur des chaînes de caractères.

$num1 -lt $num2

Vérifie sinum1est inférieur ( < ) ànum2(lowerthan).

$num1 -le $num2

Vérifie sinum1est inférieur ou égal ( <= ) ànum2(lowerorequal).

$num1 -gt $num2

Vérifie sinum1est supérieur ( > ) ànum2(greaterthan).

$num1 -ge $num2

Vérifie sinum1est supérieur ou égal ( >= )


     #!/bin/bash

    if [ $1 -ge 20 ]
    then
            echo "Vous avez envoyé 20 ou plus"
    else
            echo "Vous avez envoyé moins de 20"
    fi



    -e $nomfichier

Vérifie si le fichier existe.

-d $nomfichier

Vérifie si le fichier est un répertoire. N'oubliez pas que sous Linux, tout est considéré comme un fichier, même un répertoire !

-f $nomfichier

Vérifie si le fichier est un… fichier. Un vrai fichier cette fois, pas un dossier.

-L $nomfichier

Vérifie si le fichier est un lien symbolique (raccourci).

-r $nomfichier

Vérifie si le fichier est lisible (r).

-w $nomfichier

Vérifie si le fichier est modifiable (w).

-x $nomfichier

Vérifie si le fichier est exécutable (x).

$fichier1 -nt $fichier2

Vérifie sifichier1est plus récent quefichier2(newerthan).

$fichier1 -ot $fichier2

Vérifie sifichier1est plus vieux quefichier2(olderthan).


## test conditionnel

il est aussi possible de faire plusieurs tests.
il n'est pas très différents des autres tests, il se met entre deux condition.


	if [ $# -ge 1 ] && [ $1 = 'koala' ]
	then
		echo "Bravo !"
		echo "Vous connaissez le mot de passe"
	else
		echo "Vous n'avez pas le bon mot de passe"
	fi


## les conditions avec le case.

nous avons vu les conditions avec les if mais il y a aussi les conditions avec les case qui permet de faire des test en cascade.
petit exemple.

	case $1 in
		"Bruno")
			echo "Salut Bruno !"
			;;
		"Michel")
			echo "Bien le bonjour Michel"
			;;
		"Jean")
			echo "Hé Jean, ça va ?"
			;;
		*)
			echo "J'te connais pas, ouste !"
			;;
	esac1


	case $1 in
		"Chien" | "Chat" | "Souris")
			echo "C'est un mammifère"
			;;
		"Moineau" | "Pigeon")
			echo "C'est un oiseau"
			;;
		*)
			echo "Je ne sais pas ce que c'est"
			;;
	esac
	En résumé

	
