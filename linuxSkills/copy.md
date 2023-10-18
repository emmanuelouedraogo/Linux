# Copy Files and Directories in Linux

## introduction au CP

La commande ```cp``` est utilisée pour copier un ou plusieurs fichiers sur un système Linux vers un nouvel emplacement. Elle est similaire à la commande ```mv```, sauf qu'elle ne déplace ni ne supprime le fichier d'origine, qui reste en place. Comme la plupart des commandes Linux, ```cp``` est exécuté à l'aide de la ligne de commande d'un terminal système. La commande ```cp``` permet aux utilisateurs de copier un fichier soit dans le même répertoire, soit dans un emplacement différent. Il est également possible de donner à la copie un nom différent de celui du fichier original. L'option -r permet à la commande ``cp`` de fonctionner de manière récursive et de copier un répertoire ainsi que tous les fichiers et sous-répertoires qu'il contient. ```cp``` dispose d'un certain nombre d'options, permettant aux utilisateurs de l'exécuter de manière interactive, d'utiliser le mode détaillé ou de conserver les attributs de fichier de l'original. Les utilisateurs doivent disposer des privilèges sudo pour copier les fichiers protégés. Sinon, sudo n'est pas obligatoire.

## How to Use the cp Command to Copy Files and Directories in Linux

cp est souvent utilisé conjointement avec la commande ls. ls répertorie le contenu du répertoire actuel. Ceci est pratique pour confirmer le nom et l’emplacement exacts des fichiers et répertoires sources. Certaines des options de commande cp les plus importantes sont les suivantes : 
```-f``` : force une copie en toutes circonstances. 
```-i``` : exécute cp en mode interactif. Dans ce mode, Linux demande une confirmation avant d'écraser les fichiers ou répertoires existants. Sans cette option, Linux n'affiche aucun avertissement. 
```-p``` : préserve les attributs de fichier du fichier d'origine dans la copie. Les attributs de fichier incluent les horodatages de création et de dernière modification du fichier, l'ID utilisateur, l'adresse IP du groupe et les autorisations de fichier. 
```-R ```: copie les fichiers de manière récursive. Tous les fichiers et sous-répertoires du répertoire source spécifié sont copiés vers la destination. 
```-u ```: écrase le fichier de destination uniquement si le fichier source est plus récent que le fichier de destination. 
```-v ```: exécute cp en mode détaillé. Ce mode fournit des informations supplémentaires sur le processus de copie. Ceci est utile pour suivre la progression lors de la copie d’un grand nombre de fichiers. Les options 
```-H```, ```-L``` et ```-P``` indiquent comment la commande cp doit traiter les liens symboliques. Consultez la page de manuel cp pour une description complète de cp et des liens symboliques. Les options pour cp varient selon les distributions Linux.

## How to Copy a File in Linux
La commande cp fonctionne dans le contexte du répertoire de travail actuel. Cependant, les fichiers peuvent être spécifiés à l'aide d'un chemin absolu ou relatif. Voici la commande cp de base pour copier un fichier dans le même répertoire.

```cp [options] sourcefile targetfile```

L'exemple suivant montre comment créer une copie de sauvegarde de clock.txt nommée clock.txt.bak.

```cp clock.txt clock.txt.bak```

Pour copier un fichier protégé appartenant au compte root, utilisez sudo.

```
cd /etc 
sudo cp bash.bashrc bash.bashrc.bak
ls -l bash.*
```

Pour vous protéger contre un écrasement accidentel, utilisez l'option interactive -i. Le système Linux demande une confirmation avant d'écraser les fichiers existants.

```cp clock.txt clock.txt.bak -i```

Utilisez l'option -p pour conserver les attributs de fichier du fichier d'origine dans la copie. Par exemple, Ubuntu attribue au duplicata le même horodatage que l'original.


```cp clock.txt clock.txt.bak -p```

La commande -v renvoie chaque opération de copie sur la sortie standard. Cela peut être pratique pour suivre les opérations qui copient des centaines ou des milliers de fichiers.

```cp -v clock.txt clock.txt.cp```

If you accidentally make an unwanted copy of the wrong file, remove the copy using the rm command.

```sudo rm bash.bashrc.bak```

## How to Copy a File to a Another Directory in Linux
Voici le modèle pour copier un fichier dans un répertoire sous Linux.
```cp sourcefile target_directory_path```

Pour donner un nouveau nom à la copie, ajoutez le nom au chemin du répertoire cible.

```cp sourcefile target_directory_path/targetfile```

