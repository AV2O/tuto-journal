
---

# TP Pratique : Maîtriser Git en 4 Missions

**Prérequis :** Avoir un terminal ouvert (Git Bash ou Terminal) et un éditeur de texte (VS Code) prêt.

---

## Mission 1 : L'Initialisation (Local)
**Objectif :** Créer un projet de zéro et faire sa première "sauvegarde" (commit).

**Le Scénario :** Vous commencez un journal de bord de votre apprentissage.

**Vos tâches :**

1.  Créez un dossier nommé `journal-git` sur votre ordinateur.
2.  Ouvrez ce dossier dans votre terminal.
3.  Transformez ce dossier en dépôt Git.
4.  Créez un fichier `jour1.txt` et écrivez "J'ai appris les bases" dedans.
5.  Ajoutez le fichier à la zone de transit (Staging).
6.  Validez le fichier avec le message : "Premier jour".


---

## Mission 2 : L'Évolution et le Contrôle
**Objectif :** Comprendre comment Git gère les modifications et l'importance de `git status`.

**Le Scénario :** Le jour 2 arrive. Vous devez mettre à jour votre journal.

**Vos tâches :**

1.  Modifiez le fichier `jour1.txt` (ajoutez une ligne "Git est puissant").
2.  **Important :** Demandez à Git quel est le statut des fichiers. Regardez bien la couleur rouge.
3.  Ajoutez la modification à l'index.
4.  Refaites un `git status`. Regardez la couleur verte.
5.  Faites le commit avec le message "Mise à jour du jour 1".


---

## Mission 3 : Le Multivers (Les Branches)
**Objectif :** Apprendre à travailler sans casser le code principal. C'est le concept le plus puissant de Git.

**Le Scénario :** Vous voulez écrire un poème sur Git, mais vous avez honte, vous ne voulez pas le mettre dans le journal principal tout de suite.

**Vos tâches :**

1.  Créez une nouvelle branche nommée `poeme` et allez dessus immédiatement.
2.  Créez un fichier `poeme.txt` avec le contenu de votre choix.
3.  Faites un `add` et un `commit` de ce fichier.
4.  Revenez sur la branche `main` (ou `master`).
5.  Regardez dans votre dossier (explorateur de fichiers) : **Le fichier `poeme.txt` a disparu !** (C'est normal, magie !).
6.  Fusionnez (Merge) la branche `poeme` dans le `main` pour faire réapparaître le fichier définitivement.


---

## Mission 4 : L'envol vers GitHub
**Objectif :** Pousser votre travail local vers le cloud.

**Le Scénario :** Vous voulez sauvegarder ce journal précieux sur Internet.

**Vos tâches :**

1.  Allez sur le site GitHub et créez un **nouveau repository** vide nommé `tuto-journal` (ne cochez rien, pas de README).
2.  Copiez les 3 lignes de commandes proposées par GitHub sous le titre *"…or push an existing repository from the command line"*.
3.  Collez-les dans votre terminal (dans votre dossier `journal-git`).
4.  Rafraîchissez la page GitHub : vos fichiers `jour1.txt` et `poeme.txt` doivent être là !

---

## Mission Bonus : Le Nettoyage (.gitignore)
**Objectif :** Apprendre à ignorer des fichiers.

**Le Scénario :** Vous avez un fichier avec vos mots de passe `passwords.txt` dans le dossier. Vous ne voulez **surtout pas** l'envoyer sur GitHub.

**Vos tâches :**

1.  Créez un fichier `passwords.txt`.
2.  Faites un `git status` (il apparaît en rouge, c'est dangereux).
3.  Créez un fichier spécial nommé `.gitignore` (le point est important).
4.  Dans ce fichier, écrivez simplement `passwords.txt`.
5.  Refaites un `git status`.
6.  Que remarquez-vous ?


---

### 🎉 Bravo !
Si vous avez terminé ces exercices, vous maîtrisez les 20% de Git qui servent dans 80% des cas au quotidien. Vous êtes prêt pour votre premier vrai projet.