# npm-scripts-cheatsheet

Guide d'utilisation des scripts npm, de manière compatible avec *nix et windows (sauf mention contraire).

### Bases

#### Créer une tâche
```"tache": "commande arg1 arg2 arg3 ..."```

#### Appeler une sous-tâche avec arguments
Il faut utiliser -- pour indiquer à npm que les arguments sont à passer à la commande sous jacente

```"tache": "npm run soustache -- arg1 arg2 arg3 ..."```


### Tâches multiples avec npm-run-all

#### Appeler une sous-tâche
```"tache": "npm-run-all soustache"```

#### Appeler deux tâches en série
Par défaut, les tâches sont appelées en série

```"tache": "npm-run-all tache1 tache2"```

#### Appeler deux tâches en parallèle
Utiliser -p pour passer en mode parallèle

```"tache": "npm-run-all -p tache1 tache2"```

#### Appeler deux tâches en série, puis 3 en parallèle, puis 2 en série
Utiliser -p et -s pour alterner les modes parallèle et série

```"tache": "npm-run-all tache1 tache2 -p tache3 tache4 tache5 -s tache6 tache7"```

#### Appeler une sous-tâche avec arguments
Mettre des guillemets autour de la tâche et des arguments

```"tache": "npm-run-all \"soustache arg1 arg2 arg3 ...\""```

### FAQ

* Comment watcher l'ajout / modification / suppression de fichiers ?

Utiliser chokidar-cli

* Comment lancer plusieurs tâches en série ou en parallèle ?

Utiliser npm-run-all

* Comment passer des arguments à une commande via ```npm run``` ?

Utiliser -- entre la commande et les paramètres: ```npm run tsc -- -p front```

### Rappel des paquets utiles
* del-cli: supprimer des fichiers, uniquement dans le current working directory
* dploy: déploiement via ftp / sftp
* chokidar-cli: meilleur watcher de modifications sur fichiers
* npm-run: Permet d'exécuter plus facilement une commande installée en local (à installer en global)
* npm-run-all: Permet de gérer les tâches en série ou en parallèle
* http-server: Serveur de fichiers

### Alternatives aux paquets présentés ici
* npm-run-all: parallelshell, concurrently
* chokidar-cli: watch, chokidar-cmd
* del-cli: rimraf
* http-server: lite-server

## Todo
* Variables d'environnement
* Exemples avec de vraies tâches
