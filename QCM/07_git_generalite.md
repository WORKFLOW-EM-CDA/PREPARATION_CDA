# QCM : Gestion de Projet avec Git

## 1. Quelle est la commande pour créer un dépôt Git et initialiser la branche principale ?

- [ ] a) `git init && git checkout -b main && git remote add origin [url_du_dépôt] && git push -u origin main`
- [ ] b) `git create repo && git branch main && git remote set-url origin [url_du_dépôt] && git push origin main`
- [ ] c) `git init && git branch main && git remote add origin [url_du_dépôt] && git push origin main`
- [ ] d) `git init && git checkout -b master && git remote add origin [url_du_dépôt] && git push -u origin master`

## 2. Comment un développeur clone-t-il un dépôt Git ?

- [ ] a) `git clone [url_du_dépôt]`
- [ ] b) `git pull [url_du_dépôt]`
- [ ] c) `git fork [url_du_dépôt]`
- [ ] d) `git checkout [url_du_dépôt]`

## 3. Quel est le but de la commande `git checkout -b feature_authentification` ?

- [ ] a) Créer une nouvelle branche nommée `feature_authentification` et se positionner dessus.
- [ ] b) Supprimer la branche `feature_authentification` localement.
- [ ] c) Fusionner la branche `feature_authentification` dans la branche courante.
- [ ] d) Rebaser la branche `feature_authentification` sur la branche principale.

## 4. Quelle est la bonne commande pour pousser les changements d'une branche de fonctionnalité vers le dépôt distant ?

- [ ] a) `git push -u origin feature_authentification`
- [ ] b) `git push origin feature_authentification`
- [ ] c) `git push feature_authentification`
- [ ] d) `git push --set-upstream origin feature_authentification`

## 5. Quelle commande est utilisée pour fusionner une branche de fonctionnalité dans `main` après révision des Pull Requests ?

- [ ] a) `git checkout main && git pull origin main && git merge feature_authentification && git push origin main`
- [ ] b) `git merge feature_authentification`
- [ ] c) `git pull origin feature_authentification && git push origin main`
- [ ] d) `git checkout feature_authentification && git push origin main`

## 6. Comment un développeur supprime-t-il une branche de fonctionnalité localement et sur le dépôt distant ?

- [ ] a) `git branch -d feature_authentification && git push origin --delete feature_authentification`
- [ ] b) `git branch -d feature_authentification && git push origin feature_authentification`
- [ ] c) `git branch -D feature_authentification && git push origin feature_authentification`
- [ ] d) `git branch --delete feature_authentification && git push --delete feature_authentification`

## 7. Quelle est la bonne manière de configurer une branche pour suivre une branche distante ?

- [ ] a) `git branch --set-upstream-to=origin/feature_authentification`
- [ ] b) `git branch -u origin/feature_authentification`
- [ ] c) `git push -u origin feature_authentification`
- [ ] d) `git fetch origin feature_authentification`
