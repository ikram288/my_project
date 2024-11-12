# my_project
Vous êtes sur la bonne voie ! Voici comment compléter le script pour qu'il continue à demander à l'utilisateur de deviner jusqu'à ce qu'il donne la bonne réponse :

#!/bin/bash

# Fonction qui demande la devinette à l'utilisateur
function guess_files {
    # Compte le nombre de fichiers dans le répertoire actuel
    local file_count=$(ls -1 | wc -l)
    local user_guess=0

    echo "Devinez combien de fichiers se trouvent dans le répertoire actuel."

    # Boucle qui continue jusqu'à ce que l'utilisateur devine correctement
    while [[ $user_guess -ne $file_count ]]; do
        # Demande une estimation à l'utilisateur
        read -p "Entrez votre estimation : " user_guess

        # Vérifie si l'estimation est correcte, trop élevée ou trop basse
        if [[ $user_guess -lt $file_count ]]; then
            echo "Trop bas ! Essayez encore."
        elif [[ $user_guess -gt $file_count ]]; then
            echo "Trop haut ! Essayez encore."
        fi
    done

    # Message de félicitation lorsque l'estimation est correcte
    echo "Félicitations ! Vous avez deviné le bon nombre de fichiers : $file_count."
}

# Appel de la fonction
guess_files

Explications des différentes parties du code :

La fonction guess_files utilise ls -1 | wc -l pour compter les fichiers dans le répertoire actuel.

La boucle while continue tant que l'estimation de l'utilisateur (user_guess) n'est pas égale au nombre de fichiers (file_count).

Si l'estimation est incorrecte, le script indique si elle est trop élevée ou trop basse.

Lorsque l'utilisateur donne la bonne estimation, un message de félicitation s'affiche et le script se termine.


Étape suivante

Pour exécuter ce script, enregistrez-le et exécutez les commandes suivantes dans le terminal :

chmod +x guessinggame.sh   # Rend le script exécutable
./guessinggame.sh          # Lance le script
