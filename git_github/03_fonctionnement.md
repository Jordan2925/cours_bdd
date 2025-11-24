# Démarrer un dépôt Git
Un dépôt Git correspond à l’ensemble des fichiers d’un projet importés dans Git. Il existe deux manières de créer un dépôt :

 - Importer un répertoire existant dans Git.
 - Cloner un dépôt déjà existant, ce qui permet de récupérer tout son contenu et son historique.

Avant de pratiquer, il est utile de comprendre comment Git gère les informations et organise le travail.

# La gestion des informations selon Git
Contrairement à d’autres systèmes de gestion de versions, Git ne voit pas les données comme une suite de fichiers modifiés, mais comme une série d’instantanés (snapshots).

À chaque validation (commit), Git capture l’état complet du projet et enregistre une référence vers cet instantané.

Ces instantanés sont stockés dans une base locale, sur votre machine.

Résultat : la plupart des opérations peuvent être effectuées sans connexion à un serveur central, ce qui rend Git rapide et agréable à utiliser.

# Les états des fichiers
Dans Git, un fichier peut être :

 - ### Suivi : il faisait partie du dernier instantané enregistré.
 - ### Non suivi : il n’a pas encore été indexé ni validé.

Lorsqu’on crée un dépôt à partir d’un répertoire existant, tous les fichiers sont d’abord non suivis. Il faut donc les indexer puis les valider. En revanche, lorsqu’on clone un dépôt, l’historique complet est copié : les fichiers sont déjà validés par défaut.

Un fichier suivi peut ensuite passer par trois états :

 - Modifié (modified) : le fichier a été changé mais pas encore indexé.
 - Indexé (staged) : le fichier est prêt à être inclus dans le prochain instantané.
 - Validé (committed) : le fichier est enregistré dans la base locale.

## Le cycle est donc : modification → indexation → validation.

# Les zones de travail dans Git
Chaque projet Git est organisé en trois espaces :

## Répertoire de travail (working tree)

C’est la version du projet que vous manipulez sur votre disque.

Les fichiers proviennent de la base compressée du dépôt.

## Zone d’index (staging area)

Fichier spécial qui liste ce qui sera inclus dans le prochain commit.

C’est une étape intermédiaire entre modification et validation.

## Répertoire Git (repository)

Le cœur du système.

Contient toutes les métadonnées et la base de données des objets du projet.

# Processus de travail typique
 - Vous modifiez ou créez un fichier dans le répertoire de travail.
 - Vous l’indexez pour l’ajouter à la zone d’index.
 - Vous le validez (commit) pour l’enregistrer définitivement dans le dépôt Git.

Ce cycle se répète à chaque évolution du projet, garantissant un suivi précis et fiable des modifications.
