/

---

# TP Pratique : Niveau Intermédiaire (Collaborer et Réparer)

**Prérequis :** Avoir terminé le TP précédent (vous avez le dossier `journal-git` relié à GitHub).

---

## Mission 5 : La Simulation du "Collègue" (Clone & Pull)
**Objectif :** Comprendre comment récupérer le travail des autres (ou le vôtre depuis un autre PC).

**Le Scénario :** Imaginez que vous changez d'ordinateur ou qu'un collègue a travaillé sur le projet. Vous devez récupérer la dernière version. Pour simuler cela, nous allons "cloner" votre projet dans un autre dossier.

**Vos tâches :**

1.  Sortez de votre dossier actuel (`cd ..`).
2.  Créez un dossier "simulation-collegue" et allez dedans.
3.  **Clonez** votre dépôt GitHub (trouvez le bouton vert "Code" sur GitHub pour avoir le lien HTTPS).
4.  Entrez dans le dossier téléchargé, modifiez `jour1.txt` en ajoutant : "Modif du collègue".
5.  Faites le `add`, `commit` et `push`.
6.  **Retournez dans votre dossier original** (`journal-git`).
7.  Ouvrez `jour1.txt` : la ligne du collègue n'est pas là !
8.  Utilisez la commande magique pour rapatrier les changements du serveur.


---

## Mission 6 : Le Cauchemar du Conflit
**Objectif :** Survivre à un "Merge Conflict". C'est LA peur du débutant, on va la dédramatiser.

**Le Scénario :** Vous et votre collègue (toujours vous, simulé) modifiez **la même ligne** du **même fichier** en même temps. Git ne saura pas lequel choisir.

**Vos tâches :**

1.  Dans votre dossier (`journal-git`), créez une branche `conflit-test`.
2.  Dans `jour1.txt`, remplacez tout le texte de la première ligne par : "JE VEUX DU BLEU".
3.  Validez (`add` + `commit`).
4.  Revenez sur la branche `main`.
5.  Dans `jour1.txt`, remplacez tout le texte de la première ligne par : "JE VEUX DU ROUGE".
6.  Validez (`add` + `commit`).
7.  Tentez de fusionner `conflit-test` dans `main`. Git va paniquer.
8.  Ouvrez VS Code. Vous verrez les zones en conflit. Choisissez une des deux versions (ou gardez les deux), supprimez les symboles bizarres (`<<<<`, `====`, `>>>>`).
9.  Terminez la fusion en faisant un `add` et un `commit`.


---

## Mission 7 : Le "Ctrl+Z" de Git (Revert)
**Objectif :** Apprendre à annuler une bêtise proprement.

**Le Scénario :** Vous avez fait un commit qui casse tout le projet. Vous ne voulez pas effacer l'historique (c'est dangereux), mais créer un nouveau commit qui fait l'inverse du mauvais commit.

**Vos tâches :**

1.  Modifiez un fichier pour écrire une bêtise (ex: "J'aime le Comic Sans MS").
2.  Faites le `commit`.
3.  Tapez `git log` et copiez les 7 premiers caractères du hash (l'identifiant) de ce mauvais commit.
4.  Utilisez la commande `git revert <hash>` pour créer un "anti-commit".


---

## Mission 8 : Le Workflow Pro (La Pull Request)
**Objectif :** Ne plus jamais travailler directement sur `main`. C'est comme ça qu'on travaille en entreprise.

**Le Scénario :** Vous voulez ajouter une fonctionnalité "Météo" au journal. Au lieu de fusionner vous-même, vous allez passer par GitHub pour "demander" la fusion.

**Vos tâches :**

1.  Créez une branche `feature-meteo`.
2.  Créez un fichier `meteo.txt` ("Il fait beau").
3.  Faites le `add`, `commit`.
4.  **Important :** Ne fusionnez pas ! Faites un `git push origin feature-meteo` (on envoie la branche, pas le main).
5.  Allez sur GitHub.com. Vous devriez voir un bandeau jaune "Compare & pull request". Cliquez dessus.
6.  Créez la Pull Request (PR).
7.  Observez l'interface : GitHub vérifie qu'il n'y a pas de conflits.
8.  Cliquez sur "Merge pull request" (bouton vert) sur le site web.
9.  Revenez sur votre terminal : mettez à jour votre `main` local (`checkout main` puis `pull`).


---

### Bilan des courses 🏆

Si vous avez réussi ces 8 missions (4 du TP précédent + 4 ici), vous savez :

1.  Versionner votre code.
2.  Utiliser les branches.
3.  Synchroniser avec GitHub.
4.  Gérer les conflits.
5.  Travailler en équipe via des Pull Requests.

Vous êtes officiellement opérationnel pour rejoindre un projet de développement junior !