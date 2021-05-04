# Commandes git
**git restore** Pour restaurer un fichier dans sa dernière version\
**git add** Ajouter au staging, possible d'ajouter qu'une partie du fichier\
**git add -p** Permet de faire le staging que d'une partie des modification d'un fichier\
**git add --update** Ajoute les modifications des fichiers déjà trackés par git, mais n'ajoute pas les modifs des fichiers jamais trackés\
**git log -p** Affiche le détail des modifications de chaque commit\
**git checkout -- files** équivalent de **git restore --staged** Supprime les modifications de fichiers du stagging\
**git commit --amend** Modifie le dernier commit\
**git rebase -i <idCommit>** Permet de faire de la réécriture d'historique. Attention car pose prb si déjà push, car on change tous les id des commits fils! Permet par exemple de fusionner plusieurs commits en un seul avant de push, ou de modifier les messages.\
**git reset** Réécriture d'historique mais sans modification. On "annule" les commits ultérieurs. **NB: git branch permet éventuellement de récupérer et merger les commits orphelins en créant une branche à partir de la chaine de commit courant**\
**git reset --soft** Le soft conserve les modif annulées dans le stagging, alors que le **git reset --hard** supprime les modifications du staging/working directory\
**git checkout <idCommit>** Positionne le HEAD sur le commit idCommit. Remet le répertoire de travail dans l'état du commit idCommit. N'impacte pas les commits ultérieurs.\
**git log --all** permet de voir les logs fils si on est en Detached par exemple\
**git diff COMMIT~ COMMIT** Affiche le diff entre le commit et son père, c'est à dire les modifications du commit en lui même. Le "~" permet de remonter vers le parent, tout comme "^". Exemple HEAD~ remonte au commit précédent.\
**git bisect** Permet d'investiguer pour détecter l'origine d'un bug en passant un commit OK et un KO. On fait un "git bisect start". Ensuite on indique si c'est OK ou KO par "git bisect good/bad"\
**git checkout -b <branche>** Crée la branche et fait un checkout pour se placer dessus\
**git merge** Si la branche est alignée avec la branche à merger, git fait un "fast forward", il n'y a pas besoin de merge. Sinon, un merge et éventuellement une gestion de conflit.\
**git rebase master (maBranche)** Sur la branche maBranche, intègre les commits de master puis réapplique les commits ajoutés uniquement sur maBranche\
**git checkout --track origin/coins** Pour récupérer en local une branche distante et la lier. A priori option par défaut.

# Principes de git
Un commit contient un hash, dépendant notamment de l'heure de commit, des parents du commit, etc.\
Les commandes git permettent de se déplacer dans l'arbre

# Messages de commit
On peut mettre plus de description sur les lignes suivantes, seule la taille de la première ligne est limitée.\
On peut mettre des "hook" en utilisant des crochets.

# Travail collaboratif
**remote** Est l'adresse du serveur distant. Par défaut elle s'appelle "origin".\
**git remote -v** permet de connaitre l'origine\
**git fetch** Met à jour le origin/master\
**git push** Pousse "master" local sur le "origin/master"\
**BONNE PRATIQUE : Faire un pull --rebase avant de faire un git gerrit ou push**

# Autres
https://git-school.github.io/visualizing-git permet de simuler les opérations git