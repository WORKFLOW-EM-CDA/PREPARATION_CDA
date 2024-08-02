# Support de Cours : Gestion de Projet avec Git

## Introduction à Git

Git est un système de contrôle de version décentralisé qui permet aux développeurs de suivre les modifications de leur code source, de collaborer efficacement et de gérer les différentes versions de leur projet.

## Configuration Initiale du Dépôt

### 1. Création et Initialisation du Dépôt

**Objectif :** Créer un nouveau dépôt Git et initialiser la branche principale.

- **Commandes :**
  ```sh
  git init
  git checkout -b main
  git remote add origin [url_du_dépôt]
  git push -u origin main
  ```

- **Explications :**
  - `git init` : Initialise un nouveau dépôt Git dans le répertoire courant.
  - `git checkout -b main` : Crée une nouvelle branche appelée `main` et bascule dessus.
  - `git remote add origin [url_du_dépôt]` : Ajoute un dépôt distant avec l'URL spécifiée.
  - `git push -u origin main` : Pousse la branche `main` vers le dépôt distant et établit `origin/main` comme branche de suivi par défaut. L'option `-u` (ou `--set-upstream`) configure cette branche pour suivre `origin/main`, ce qui simplifie les futures opérations de push et pull.

### 2. Clonage du Dépôt

**Objectif :** Cloner un dépôt Git existant.

- **Commande :**
  ```sh
  git clone [url_du_dépôt]
  ```

- **Explication :**
  - `git clone [url_du_dépôt]` : Crée une copie locale complète du dépôt distant, y compris tout l'historique des versions.

## Flux de Travail pour les Fonctionnalités

### 1. Création d'une Branche de Fonctionnalité

**Objectif :** Créer une nouvelle branche pour le développement d'une fonctionnalité spécifique.

- **Commande :**
  ```sh
  git checkout -b feature_authentification
  ```

- **Explication :**
  - `git checkout -b feature_authentification` : Crée une nouvelle branche nommée `feature_authentification` et vous bascule immédiatement dessus pour commencer le développement.

### 2. Commits et Poussée des Changements

**Objectif :** Enregistrer les changements locaux et les pousser vers le dépôt distant.

- **Commandes pour ajouter et commettre les changements :**
  ```sh
  git add .
  git commit -m "Message de commit"
  ```

- **Commande pour pousser les changements :**
  ```sh
  git push -u origin feature_authentification
  ```

- **Explications :**
  - `git add .` : Ajoute tous les fichiers modifiés dans le répertoire courant à l'index pour le prochain commit.
  - `git commit -m "Message de commit"` : Crée un commit avec un message décrivant les modifications.
  - `git push -u origin feature_authentification` : Pousse les changements de la branche locale `feature_authentification` vers le dépôt distant et établit `origin/feature_authentification` comme branche de suivi par défaut.

### 3. Fusion des Pull Requests (PR)

**Objectif :** Fusionner les changements des branches de fonctionnalités dans la branche principale après révision.

- **Commandes pour fusionner les PR :**
  ```sh
  git checkout main
  git pull origin main
  git merge feature_authentification
  git push origin main
  ```

- **Explications :**
  - `git checkout main` : Bascule sur la branche principale `main`.
  - `git pull origin main` : Récupère les dernières modifications de la branche `main` depuis le dépôt distant.
  - `git merge feature_authentification` : Fusionne les changements de la branche `feature_authentification` dans `main`.
  - `git push origin main` : Pousse les changements fusionnés dans la branche `main` vers le dépôt distant.

### 4. Suppression des Branches de Fonctionnalité

**Objectif :** Nettoyer les branches de fonctionnalités après fusion.

- **Commandes pour supprimer les branches localement et à distance :**
  ```sh
  git branch -d feature_authentification
  git push origin --delete feature_authentification
  ```

- **Explications :**
  - `git branch -d feature_authentification` : Supprime la branche locale `feature_authentification`. L'option `-d` est utilisée pour supprimer la branche seulement si elle a été fusionnée.
  - `git push origin --delete feature_authentification` : Supprime la branche `feature_authentification` du dépôt distant.

## Schéma du Flux de Travail

Voici un aperçu visuel du flux de travail pour le projet :

```plaintext
main
  |
  |-- feature_authentification (Antoine)  -- PR 
  |       \
  |        `--- (développement) dev_login 
  |
  |-- feature_commentaires (Mathieu) -- PR 
  |       \
  |        `--- (développement) dev_forme
  |
  |-- feature_tableau-de-bord (Mathieu) -- PR  
  |       \
  |        `--- (développement) ... 
  |
```

**Explications :**
- Chaque branche de fonctionnalité (`feature_authentification`, `feature_commentaires`, `feature_tableau-de-bord`) est développée indépendamment.
- Les Pull Requests (PR) sont utilisées pour réviser et fusionner les changements dans la branche principale `main`.
- Les branches sont supprimées après fusion pour garder le dépôt propre.

## Commandes de Référence

- **Créer une branche et basculer dessus :** `git checkout -b <nom_de_branche>`
- **Ajouter des fichiers au commit :** `git add .`
- **Créer un commit :** `git commit -m "<message_de_commit>"`
- **Pousser les changements :** `git push -u origin <nom_de_branche>`
- **Fusionner une branche dans `main` :** `git merge <nom_de_branche>`
- **Supprimer une branche localement :** `git branch -d <nom_de_branche>`
- **Supprimer une branche à distance :** `git push origin --delete <nom_de_branche>`

