## LES BOUCLES

nous avons déja vu pas mal de choses mais le truc qui serait pas mal, sa serait d'automatisé un peut notre script.
pour rendre un script autonome, il faut forcément le bouclé.

	while [ -z $reponse ] || [ $reponse != 'oui' ]
	do
		read -p 'Dites oui : ' reponse
	done


c'est cool ça mais moi ce que je préfèr c'est de bouclé dans un tableau, mais tkt il y a la solution.

	for variable in 'valeur1' 'valeur2' 'valeur3'
	do
		echo "La variable vaut $variable"
	done

enfin non là c'est juste pour bouclé avec un liste de valeur.

on peut même bouclé dans un ls c'est cool ? non ?

	liste_fichiers=`ls`

	for fichier in $liste_fichiers
	do
		echo "Fichier trouvé : $fichier"
	done


Il existe aussi le for classique

	#!/bin/bash
	for i in `seq 1 10`;
	do
		echo $i
	done

# LES FONCTION

 déclaration méthode 1

	maFonction ()

	{
	bloc d’instructions 
	}

appel de ma fonction

	maFonction
