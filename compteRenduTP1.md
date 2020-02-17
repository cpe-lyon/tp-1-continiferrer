
# Compte-Rendu TP1 / Contini E. Ferrer H. / Groupe 5

RDV sur [CPE e-campus](https://prod.e-campus.cpe.fr/pluginfile.php/36437/mod_resource/content/0/TP1.pdf) pour obtenir le TP

## Exercice 1 - Installation du serveur

RAS

## Exercice 2 - Prise en main de l’interpréteur de commandes

**Manuel**

1. Rôle de la commande `which` : Cette commande **localise une commande**, elle observe dans tous les chemins et cherche la commande dans ce chemin
2. On peut **rechercher une chaîne de caractères dans un man** avec **/** : `man which` puis `/option` 
3. On quitte le terminal avec la touche `q` (pour quit)
4. Pour afficher la **première page d'une section** : `man 6 intro` Cette section traite des jeux installés sur le système
 
 **Navigation dans l'arborescence des fichiers**

1. `cd /var/log`
2.  `cd ../`
3.  `cd ~`
4.  `cd -`
5.  Pas les **droits** pour accéder à ce dossier
6.  Après demande du mot de passe, la commande cd n'est pas trouvée, car **cd est une commande interne du bash**, elle n'est donc pas trouvée par sudo
7.  `mkdir Dossier1 Dossier2` `touch Dossier1/Fichier1` `mkdir Dossier2/Dossier2.1 Dossier2/Dossier2.2` `touch Dossier2/Dossier2.2/Fichier2` `touch Dossier2/Dossier2.2/Fichier3`
8. La **suppression du fichier** est possible avec `rm`, pas celle du dossier
9. La commande `rmdir` permet de **supprimer un dossier**
10. Suppression impossible car le dossier n'est pas vide
11. La commande `rm -R Dossier2` permet de **supprimer récursivement tous les fichiers**  

**Commandes importantes**

1. La commande `date +"%H:%M:%S` permet d'**afficher l'heure**, la commande `time` permet de mesurer le temps d’exécution d'un processus
2. `ls` liste les fichiers classiques alors que `la` ajoute aussi les fichiers cachés
3. `which -a ls` : `ls` se trouve donc dans `/bin/ls`  (`/usr/bin/ls`)
4. `ll` = `ls -alF`
5. `ls /bin`
6. `ls ..` cite le contenu du répertoire parent 
7. `pwd` permet de **donner le chemin du dossier courant**
8. La commande `echo 'yo' > plop` redirige la sortie de la commande `echo` (yo) dans le fichier plop, exécutée 2 fois, elle écrase son contenu
9. La commande `echo 'yo' >> plop` n'écrase pas le contenu cette fois, elle écrit deux fois (yo) dans le fichier
10. `file` détermine le **type du fichier visé**
11. `echo 'Hello Toto' > Toto` `ln Toto Titi` `echo 'Titi' > Toto` Le fichier titi est lui aussi modifié, à la suppression par contre, Titi n'est pas supprimé
12. `ln -s Titi Tutu` `echo 'Tutu' > Titi` `cat tutu titi` Le contenu est identique, à la suppression le fichier tutu n'est pas supprimé mais le lien n'est plus présent et une erreur s'affiche
13. **CTRL+S arrête le défilement** et **CTRL+Q permet de reprendre le défilement**
14. `cat /var/log/syslog | head -n 10`, `cat /var/log/syslog | tail -n 10`, `cat /var/log/syslog | head -n 20 | tail -n 10`
15. `dmesg | less` `more` et `less` permettent à l'utilisateur de défiler librement dans une sortie de commande ou dans un fichier, `dsmg` donne des infos du noyau
16. `etc/passwd` contient tous les utilisateurs, groupes associés et permissions 
17. `cat /etc/passwd | cut -f1 -d ':' | sort -r`
18. Pour avoir le nombre d'utiliseurs, on compte les lignes du fichier avec `cat /etc/passwd | wc -l` : 31
19. `man -k conversion` : 4 pages
20. `find / -name 'passwd'`
21. `find -name passwd |wc -l 1> ~/list_passwd_files.txt 2> /dev/null` 
22. `grep "ll" -r`
23. `locate history.log` : Situé /var/log/apt/history.log
24. Le fichier n'est pas trouvé car on a pas mis à jour la database avec `updatedb`

## Exercice 3 - Découverte de l’éditeur de texte nano

RAS

## Exercice 4 - Personnalisation du shell

3. `sudo -s`, `source .bashrc`
4. `\e[35m[\A] - ${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;36m\]\w\[\033[00m\]\$`

## Exercice 5 - Pour les plus rapides

Manque de temps 

## TIPS

- Pour afficher au fur et à mesure un man (par exemple) : **man --help | more**
- Un **chemin absolu** commence par un **/**
