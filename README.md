# Test-Markdown


# Tutoriel Gogs

## Dépôt local

### Cloner un dépôt distant

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/1.png)


La commande :
> ls

affiche les fichiers clonés du répertoire.

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/2.png)

On créer un nouveau dossier avec 
>mkdir "nom du dossier"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/3.png)

Pour initialiser Git dans un dossier on utilise la commande :
>git init

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/4.png)

Après cette commande un dossier caché .git est créé dans le dossier.

Pour ajouter un fichier au git il faut utiliser la commande :
>git add "nom du fichier"

ou 
>git add -A

qui 

On verifie ensuite que le fichier a bien été ajouté avec la commande status : 
> git status

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/5.png)

Après avoir ajouté un fichier il faut effectuer un commit à l'aide de la commande :

> git commit -am "Message du commit"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/6.png)

La commande commit permet de mettre a jour le répertoire git il faut donc l'utiliser pour toute modification effectué dans le dossier du répertoire. Par exemple s'il on modifie un fichier et on effectue un git status on peut voir que la modification n'est pas prise on compte.
![git logo](https://github.com/adrienED/Test-Markdown/blob/master/7.png)

On effectue donc un nouveau commit :

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/8.png)

On peut voir la totalité des commit effectuer avec la commande :
>git log 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/9.png)

Avec la commande : 
>git reset "clé du commit"

on efface un commit en revenant a un commit antérieur. 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/10.png)

les éléments contenus dans le dossier git reviendront a l'état antérieur au commit. 


Pour plus de lisibilité on peut taguer un commit avec la commande :

>git tag "nom étiquette" "clé du commit"


![git logo](https://github.com/adrienED/Test-Markdown/blob/master/11.png)

On se déplace ensuite sur un commit voulu avec la commande :

>git checkout "clé du commit"

ou

>git checkout "étiquette du commit"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/12.png)



## Dépôt distant

Dans cette partie nous allons voir comment on peut synchroniser un dépôt local avec un dépôt distant.

Pour pouvoir envoyer des fichiers locaux sur un dépôt distant il faut d'abord créer un répertoire sur le dépôt distant. On récupère les information du dépôt distant à l'aide de la commande git clone. On ajoute ou modifie des fichiers localement dans le dossier ou a eu lieu le clonage. On effectue ensuite la commande :

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/13.png)


>git push

Pour envoyer les fichiers sur le dépôt distant 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/14.png)


On peut voir les fichiers ajoutés sur l'interface graphique du dépôt distant : 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/15.png)

On peut répéter l’opération pour rajouter des fichiers :


![git logo](https://github.com/adrienED/Test-Markdown/blob/master/16.png)

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/17.png)



## Collaboration sur un dépôt distant

Un dépôt git peut-être utiliser en collaboration pour cela un des membres doit inviter les autres membres ou un membre peut demander à être inclue dans un dépôt via l’interface graphique du dépôt distant. Une fois les demandes acceptées il suffit d'utiliser la commande ;

> git push "url du repertoire" 

pour envoyer des fichiers sur le dépôt distant 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/18.png)


![git logo](https://github.com/adrienED/Test-Markdown/blob/master/19.png)


Il peut se produire un conflit si un des membres du répertoire n'est pas à jour localement avec la version distante du dépôt, il faut donc utiliser la commande 
> git pull "url du dépôt"

ou

> git clone "url du dépôt"


avant d'utiliser la commande push.

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/20.png)



## Branches 


Les branches sont des éléments très importants dans l'utilisation de git, elle permette de testé des version de codes sont avoir d'impact sur les versions stables intérieur. 

On crée une branche à l'aide de la commande :

>git branch "nom de la branche"

Pour voir toutes les branches d'un repertoire on utlise la commande ;

>git branch

Et l'on peut se déplacer d'une branche à l'autre comme on se deplace d'un commit à un autre avec la commande 

> git checkout "nom de la branche"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/21.png)


 On peut comme sur la branche master ajouter ou modifier des fichiers et faire des commit 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/22.png)

Ensuite avec la commande push on peut l'envoyer sur le dépôt distant avec à l'aide de la commande :
>git push --set-upstream origin b1


![git logo](https://github.com/adrienED/Test-Markdown/blob/master/23.png)

On créer une seconde branche appelée b2 a partir du commit précédent le master courant.
Pour cela il faut revenir sur le master avec la commande 
>git checkout master,

faire un

> git log 

puis se positionner sur le commit précédent à l'aide de la commande

> git checkout "clé commit"


On effectue quelque commit sur cette branche 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/24.png)


La commande :

>git merge "nom de la branch"

permet de fusionner les modification de la branche avec la branch dans le master, si l'on est positionner sur le master.

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/25.png)


On peut également fusionner un master dans une branche, pour cela il faut se positionner sur une branche est saisir la commande :

>git merge master 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/26.png)


Avec le client graphique git GUI on peut observer le graphique des commit :

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/27.png)

On envoie la branche b2 sur le dépôt distant :

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/28.png)

Pour supprimer une branche localement il faut saisir :
>git branch -d "nom de la branche"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/29.png)

Puis du dépôt distant avec 
>git push --delete origin "nom de la branche"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/30.png)


## Forks

Un fork est une copie d'un dépôt, elle permet à un utilisateur de copier le dépôt d'une personne, effectué des modifications et les soumettre (appelé "pull request") au propriétaire du dépôt afin qu'elle soit incluse dans le dépôt distant.

### Exercice 1 collaboration

Je crée un dépôt nommé fork et attend qu'un collègue face un pull request. on peut voir qu'il y a "1" a côté de pull request.

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/31.png)

Je clique sur l'onglet pull request.

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/32.png)

Je peux voir le message de la personne demandant le pull request ainsi que les commit qu'il a effectué 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/33.png)

Pour accepté la pull request j'appuie sur "fusionner la pull request".

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/34.png)


 les modification sont donc maintenant inclus dans mon dépôt.

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/35.png)

### Exercice 2

On va maintenant créer deux dépôts disant, un public appelé ForksPublique et un privé ForksPrive.

On clone le dépôt privé 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/36.png)

On effectue quelque modification localement, on commit et on push le tout sur le depot distant :

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/37.png)

On crée ensuite une branche appelé "public" dans le depot privé local. On y fusionne le master avec la commande 
>git merge master

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/38.png)

On souhaite ensuite cette branche sur le dépôt privé ForksPrive, on utilise la commande 

>git push "url du dépôt"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/39.png)

Puis sur le dépôt publique ForksPublique, pour cela il faut d'abord ajouter une remote.

>git remote 

Permet de voir toute les remotes du dépôt. 

Pour ajouter une remote il faut utiliser la commande :

>git remote add "nom de la remote "  "url du dépôt" disant"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/40.png)

Avant d'utiliser push on utilise la commande 

>git fetch "url du depot distant"

afin de mettre a jour le dépôt local avec le dépôt distant puis on push :

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/41.png)

On effectue quelque commit dans la branche master, on souhaite fusionner ces commit dans la branche public. 
Pour cela on se place sur la branche publique avec 

>git checkout public

Puis on fusionne avec la commande :

>git merge master 

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/42.png)


Et l'on push avec 

>git push --set-upstream origin public

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/43.png)

On clone ensuite le dépôt public distant public

>git clone "url dépôt public"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/44.png)


On met a jour le dépôt public local avec la branche "public" de dépôt privé 

>git fetch "url du dépôt privé"

![git logo](https://github.com/adrienED/Test-Markdown/blob/master/45.png)



