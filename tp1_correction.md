
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

<details>
<summary>🔻 <b>Cliquez ici pour voir la CORRECTION</b></summary>

```bash
# 1. & 2. Création et déplacement (ou faites-le à la souris)
mkdir journal-git
cd journal-git

# 3. Initialisation
git init

# 4. Création du fichier (via VS Code ou commande simple)
echo "J'ai appris les bases" > jour1.txt

# 5. Mise en carton (Staging)
git add jour1.txt

# 6. Validation (Commit)
git commit -m "Premier jour"
```
*Vérification : Tapez `git log`, vous devez voir votre commit avec votre nom.*
</details>

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

<details>
<summary>🔻 <b>Cliquez ici pour voir la CORRECTION</b></summary>

```bash
# 1. Modification (via votre éditeur)

# 2. Vérification (Le réflexe vital !)
git status
# -> Git vous dit : "modified: jour1.txt" (en rouge)

# 3. Ajout
git add jour1.txt

# 4. Vérification
git status
# -> Git vous dit : "modified: jour1.txt" (en vert, prêt à être commité)

# 5. Commit
git commit -m "Mise à jour du jour 1"
```
</details>

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

<details>
<summary>🔻 <b>Cliquez ici pour voir la CORRECTION</b></summary>

```bash
# 1. Créer et bouger sur la branche
git checkout -b poeme
# (Note : sur les versions très récentes de Git, on peut utiliser "git switch -c poeme")

# 2. & 3. Création et Commit sur la branche parallèle
echo "Git c'est fantastique" > poeme.txt
git add poeme.txt
git commit -m "Ajout d'un poeme"

# 4. Retour vers le futur (Main)
git checkout main
# (ou "git switch main")

# 5. Constat
ls
# (Le fichier poeme.txt n'est pas là, c'est la preuve que les branches sont isolées)

# 6. Fusion
git merge poeme
# -> Le fichier apparaît maintenant dans le main !
```

**Schéma de ce qu'il s'est passé :**

```text
Main:   O ----- O ------------------------- O (Fusion : Le poème arrive ici)
                 \                         /
Poeme:            \ -- (Création poeme) --/
```
</details>

---

## Mission 4 : L'envol vers GitHub
**Objectif :** Pousser votre travail local vers le cloud.

**Le Scénario :** Vous voulez sauvegarder ce journal précieux sur Internet.

**Vos tâches :**

1.  Allez sur le site GitHub et créez un **nouveau repository** vide nommé `tuto-journal` (ne cochez rien, pas de README).
2.  Copiez les 3 lignes de commandes proposées par GitHub sous le titre *"…or push an existing repository from the command line"*.
3.  Collez-les dans votre terminal (dans votre dossier `journal-git`).
4.  Rafraîchissez la page GitHub : vos fichiers `jour1.txt` et `poeme.txt` doivent être là !

<details>
<summary>🔻 <b>Cliquez ici pour voir la CORRECTION</b></summary>

Les commandes ressembleront à ceci (avec votre pseudo) :

```bash
# 1. Lier le local au distant
git remote add origin https://github.com/VOTRE-PSEUDO/tuto-journal.git

# 2. Renommer la branche en main (sécurité si vous étiez en master)
git branch -M main

# 3. Envoyer
git push -u origin main
```
</details>

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

<details>
<summary>🔻 <b>Cliquez ici pour voir la CORRECTION</b></summary>

```bash
# Création du fichier sensible
touch passwords.txt

# Création du fichier de règles
echo "passwords.txt" > .gitignore

# Vérification
git status
```
**Résultat :** Git ne vous propose plus jamais d'ajouter `passwords.txt`. Il ne voit plus que le fichier `.gitignore`. Vous pouvez commiter le `.gitignore` sans crainte, vos mots de passe resteront secrets sur votre ordinateur.
</details>

---

### 🎉 Bravo !
Si vous avez terminé ces exercices, vous maîtrisez les 20% de Git qui servent dans 80% des cas au quotidien. Vous êtes prêt pour votre premier vrai projet.