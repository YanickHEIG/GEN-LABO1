# GEN - Labo 1 - GIT

Yanick Thomann - 27.02.2021

## 1. Introduction

Ce premier laboratoire du cours GEN nous permet de nous familiariser avec la ligne de commande Git.

L'adresse du repository GitHub est le suivant: https://github.com/YanickHEIG/GEN-LABO1.git

## 2. Laboratoire - partie 1

On commence par initialiser le repository local avec les commandes suivantes:

`git init`
`git add .`
`git commit`

On créé ensuite le repo sur GitHub.

_New repo_ -> Name repo

On obtient maintenant un lien vers lequel on peut synchroniser notre repo local

`git remote add origin https://github.com/YanickHEIG/GEN-LABO1.git`
`git push -u origin master`

![](firstCommitToOnlineRepo.png)



On a ajouté une image au git, on peut donc refaire un commit/push

`git add "firstCommitToOnlineRepo.png"`
`git commit -m "Second commit"`
`git push`

On créé ensuite une nouvelle branche _essai_

`git checkout -b essai`
`git add FirstEssaiCommit.txt`
`git commit -m "First commit on fork 'essai'"
git push --set-upstream origin essai`

On ajoute ensuite un fichier pour faire un nouveau commit sur la branche _essai_. On le synchronise avec le repository en ligne avec les commandes suivantes:

`git add SecondEssaiCommit.txt`
`git commit -m "Second commit on Essai"`
`git push`

On créé à présent la branche dev:

`git checkout -b dev`

Celle-ci est maintenant créée mais ne sera utilisée que plus tard.

A présent, nous refaisons un nouveau commit sur essai. Après l'ajout manuel d'un fichier, on refait un commit.

`git checkout essai`
``git add ThirdEssaiCommit.txt`
`git commit -m "Third commit on Essai"`
`git push`

On revient ensuite sur master pour faire un nouveau commit

`git checkout master`
`git add SecondMasterCommit.txt`
`git commit -m "Third commit to master"`
`git push`

On merge l'avant-dernier commit de la branche essai avec master

`git merge essai~1`
`git push`

On revient ensuite sur essai pour faire le commit suivant:

`git checkout essai`
`git add FourthEssaiCommit.txt`
`git commit -m "Fourth commit on essai"`
`git push`

On revient sur master pour créer un nouveau fork

`git checkout master`
`git checkout -b f2`
`git add CommitOnF2.txt`
`git commit -m "First and only commit on f2"`
`git push --set-upstream origin f2`

On remerge à nouveau essai sur master

`git checkout master`
`git merge essai`
`git push`

On vient à présent sur la branche dev

`git checkout dev`
`git add CommitOnDev.txt`
`git commit -m "First and only commit on dev"`
`git push --set-upstream origin dev`

On revient finalement sur master pour merger f2

`git checkout master`
`git merge f2`
`git push`

Le résultat final nous donne ceci:

![](finalNetworkGraph.png)

