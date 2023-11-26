# **Contexte**
GIT un est outil très utilisé dans le monde professionnel, il est généralement utilisé pour stocker un projet sur un dépôt distant (Gitlab, Github,etc). Pour travailler, on peut utiliser le Git GUI (Graphical User Interface) mais je pense que la version Bash (console) est mieux pour travailler une fois qu'on connait les commandes. Avant de voir les commandes, voici comment GIT fonctionne : <br>

• Il y a trois "stage" dans le GIT (**unstaged** → **stage** → **unmodified**)

**1.** Un nouveau fichier / un fichier modifié va être mis dans le "stage" **UNSTAGED**. <br>
**2.** Une fois ajouté il passe au "stage" **STAGE**. <br>
**3.** Une fois qu'on fait un **commit** (on met un message à toutes les modifications effectué) il passe au "stage" **UNMODIFIED**.<br>
**4.** Maintenant on est prêt de le mettre sur le dépôt distant.

# **Push Gitea / Gitlab projet sur Github**
```
$git remote add github <repository_github>
$git fetch --all
$git push --mirror github
```

# **Commandes**

Voici quelques commandes qui sont utiliser pour travailler avec GIT :<br>

# Git Status
```
$git status
```
**état de votre dépôt**

# Git Log
```
$git log
```
**liste des commit** (code **sha1**, **auteur**, **date**, **nom**)
```
$git log --oneline
```
**liste des commit** (affiche que le **nom**) 
```
$git log --all
```
**liste des commit** (affiche tous les commit n'importe l'endroid où on est situer)
```
$git log --graph
```
**liste des commit** (affiche les commit sous forme d'un simple graphe voir bien visualer les branches)

# Git Init
```
$git init
```
**initialisation du dépôt en local**

# Git Add
```
$git add nomFichier
```
**ajoute le fichier nomFichier au contrôle de git**
```
$git add .
```
**ajoute toutes les fichiers au contrôle de git**

# Git Commit
```
$git commit -m "message"
```
**validation des modifications + un message pour décrire les modifications effectué**
```
$git commit -am "message"
```
**ajout des fichiers et validations des modifications + message**
```
$git commit -ammend"
```
**modifier le dernier message du commit**


# Git Branch
```
git branch
```
**liste des branche existantes**
```
$git branch nomBranch
```
**création d'une nouvelle branche appeller nomBranch**
```
$git branch -D nomBranch
```
**supprimer la branche nomBranch**

# Git Checkout
```
$git checkout nomBranch
```
**changement de branche sur nomBranch**
```
$git checkout -b nomBranch
```
**création de la branche nomBranch + changement de branche sur nomBranch**
```
$git checkout head^
```
**on révient en arrière d'une branche**
```
$git checkout head~1 (~2 ~3 ~4 etc)
```
**on révient en arrière d'une branche (ou 2, 3 , 4 etc)**

# Git Rm
```
$git rm nomFichier.txt / nomDossier
```
**supprimer un fichier / dossier**

# Git Mv
```
$git mv nomfichier.txt nouveauNomFichier.txt
```
**rénommer un fichier**

# Git Push
```
$git push
```
**les modifications qui ont été validé vont être transmis sur le dépôt distant**
```
$git push https://gitlab.com/portfolio-mihuta-mihail/gitmemento.git
```
**si votre remote n'est pas défini ou vous voulez le transmettre sur un autre dépôt il faut mettre le lien du dépôt**

# Git Pull
```
$git pull
```
**dans le cas où on travaille dans un groupe et quelqu'un a fait des modifications qui ont été PUSH, il faut faire un PULL pour récupérer ces modifications**
```
$git pull https://gitlab.com/portfolio-mihuta-mihail/gitmemento.git
```
**si votre remote n'est pas défini ou vous voulez récupérer les fichiers d'un autre dépôt il faut mettre le lien du dépôt**

# Git Merge
```
$git merge nomBranch
```
**On fusionne la branche actuelle et la branche nomBranch (pour récupérer son code). Généralement, un merge va crée un commit supplémentaire**

# Git Rebase
```
$git rebase nomBranch
```
**Presque la même chose que $git merge mais utiliser dans d'autres situations (ex : on veut fusionner deux branches mais il y a commit de plus sur l'une des branches. Un merge va crée un commit supplémentaire alors qu'un rebase va prendre ce commit et il va le mettre à la fin de la branche qu'on veut fusionner)**
```
$git rebase -i nomBranch
```
**c'est un rebase interactif (on peut modifier un commit, utiliser un commit ou pas, mettre un libellé,etc)**

# Git Stash
```
$git stash
```
**toutes les modifications en cours sont mises de côté et stockés dans un espace dédié**
```
$git stash list
```
**afficher la liste du stash**
```
$git stash pop
```
**récupérer le code du stash (le code est supprimer)**
```
$git stash apply
```
**récupérer le code du stash (le code n'est pas supprimer)**

# Git Tag
```
$git tag V1.0
```
**Un libellé pour un commit**

# Git Cherry-Pick 
```
$git cherry-pick n° commit
```
**déplacer le commit à l'endroit où je me trouve**

# Git Remote 
```
$git remote add origin https://gitlab.com/portfolio-mihuta-mihail/gitmemento.git
```
**on ajoute le lien suivant comment remote pour dire que ce dépôt local correspond au dépôt distant ...(lien)**

# Git Reset (annuler un commit avant un PUSH)
```
$git reset --soft head^ 
```
**Add → X → Commit**
```
$git reset --mixed head^
```
**X → Add → Commit**
```
$git reset --hard head^
```
**X → Edit → Add → Commit (tout ligne de code est perdu)**

# Git Revert (annuler un commit après un PUSH)
```
$git revert head
```
**On crée un commit avec l'inverse du commit (si le commit a une certaine ligne de code, l'inverse sera que cette ligne n'est plus la). On fait cela puisque le commit a été déjà PUSH et c'est plus facile pour les autres de faire un PULL ensuite**

















