### QCM : Gestion de Projet avec Git

#### 1. Quelle est la commande pour créer un dépôt Git et initialiser la branche principale ?

- [x] a) `git init && git checkout -b main && git remote add origin [url_du_dépôt] && git push -u origin main`
  - **Feedback :** Correct. Cette commande initialise un dépôt Git, crée et se positionne sur la branche `main`, ajoute l'origine du dépôt distant et pousse la branche `main` vers le dépôt distant.
- [ ] b) `git create repo && git branch main && git remote set-url origin [url_du_dépôt] && git push origin main`
  - **Feedback :** Incorrect. La commande `git create repo` n'existe pas et `git branch main` ne crée pas et ne bascule pas automatiquement sur la branche `main`.
- [ ] c) `git init && git branch main && git remote add origin [url_du_dépôt] && git push origin main`
  - **Feedback :** Incorrect. `git branch main` crée la branche `main` mais ne bascule pas automatiquement sur elle.
- [ ] d) `git init && git checkout -b master && git remote add origin [url_du_dépôt] && git push -u origin master`
  - **Feedback :** Incorrect. Cette commande utilise `master` au lieu de `main`, qui est souvent la branche par défaut de nos jours.

---

#### 2. Comment un développeur clone-t-il un dépôt Git ?

- [x] a) `git clone [url_du_dépôt]`
  - **Feedback :** Correct. La commande `git clone` est utilisée pour cloner un dépôt Git distant.
- [ ] b) `git pull [url_du_dépôt]`
  - **Feedback :** Incorrect. La commande `git pull` est utilisée pour récupérer les modifications d'un dépôt distant vers le dépôt local.
- [ ] c) `git fork [url_du_dépôt]`
  - **Feedback :** Incorrect. Il n'existe pas de commande `git fork`. Le forking est généralement effectué via les plateformes comme GitHub.
- [ ] d) `git checkout [url_du_dépôt]`
  - **Feedback :** Incorrect. La commande `git checkout` est utilisée pour basculer entre les branches ou réinitialiser les fichiers dans le dépôt de travail.

---

#### 3. Quel est le but de la commande `git checkout -b feature_authentification` ?

- [x] a) Créer une nouvelle branche nommée `feature_authentification` et se positionner dessus.
  - **Feedback :** Correct. `git checkout -b` crée une nouvelle branche et se positionne sur celle-ci.
- [ ] b) Supprimer la branche `feature_authentification` localement.
  - **Feedback :** Incorrect. Pour supprimer une branche localement, on utilise `git branch -d` ou `git branch -D`.
- [ ] c) Fusionner la branche `feature_authentification` dans la branche courante.
  - **Feedback :** Incorrect. Pour fusionner une branche, on utilise `git merge`.
- [ ] d) Rebaser la branche `feature_authentification` sur la branche principale.
  - **Feedback :** Incorrect. Pour rebaser une branche, on utilise `git rebase`.

---

#### 4. Quelle est la bonne commande pour pousser les changements d'une branche de fonctionnalité vers le dépôt distant ?

- [x] a) `git push -u origin feature_authentification`
  - **Feedback :** Correct. Cette commande pousse les changements et définit la branche distante comme upstream.
- [ ] b) `git push origin feature_authentification`
  - **Feedback :** Correct, mais ne définit pas la branche comme upstream pour les futurs pulls et pushes.
- [ ] c) `git push feature_authentification`
  - **Feedback :** Incorrect. Il manque l'indication du dépôt distant (`origin`).
- [x] d) `git push --set-upstream origin feature_authentification`
  - **Feedback :** Correct. Cette commande pousse les changements et définit la branche distante comme upstream.

---

#### 5. Quelle commande est utilisée pour fusionner une branche de fonctionnalité dans `main` après révision des Pull Requests ?

- [x] a) `git checkout main && git pull origin main && git merge feature_authentification && git push origin main`
  - **Feedback :** Correct. Cette série de commandes permet de basculer sur `main`, de la mettre à jour, de fusionner la branche de fonctionnalité et de pousser les changements.
- [ ] b) `git merge feature_authentification`
  - **Feedback :** Incorrect. Il manque les étapes de basculement sur `main` et de mise à jour avant la fusion.
- [ ] c) `git pull origin feature_authentification && git push origin main`
  - **Feedback :** Incorrect. Cette commande tire les changements de `feature_authentification`, mais ne fusionne pas et ne met pas à jour `main`.
- [ ] d) `git checkout feature_authentification && git push origin main`
  - **Feedback :** Incorrect. Cette commande bascule sur `feature_authentification` et pousse `main`, ce qui n'a pas de sens dans ce contexte.

---

#### 6. Comment un développeur supprime-t-il une branche de fonctionnalité localement et sur le dépôt distant ?

- [x] a) `git branch -d feature_authentification && git push origin --delete feature_authentification`
  - **Feedback :** Correct. Cette commande supprime la branche localement et sur le dépôt distant.
- [ ] b) `git branch -d feature_authentification && git push origin feature_authentification`
  - **Feedback :** Incorrect. La deuxième commande pousse les changements, elle ne supprime pas la branche sur le dépôt distant.
- [ ] c) `git branch -D feature_authentification && git push origin feature_authentification`
  - **Feedback :** Incorrect. La deuxième commande pousse les changements, elle ne supprime pas la branche sur le dépôt distant.
- [x] d) `git branch --delete feature_authentification && git push --delete feature_authentification`
  - **Feedback :** Correct. Cette commande supprime la branche localement et sur le dépôt distant, mais `--delete` est une forme équivalente à `-d` et `-D` pour la suppression locale.

---

#### 7. Quelle est la bonne manière de configurer une branche pour suivre une branche distante ?

- [ ] a) `git branch --set-upstream-to=origin/feature_authentification`
  - **Feedback :** Correct. Cette commande configure la branche actuelle pour suivre une branche distante.
- [x] b) `git branch -u origin/feature_authentification`
  - **Feedback :** Correct. Cette commande configure la branche actuelle pour suivre une branche distante.
- [ ] c) `git push -u origin feature_authentification`
  - **Feedback :** Incorrect. Cette commande configure la branche locale pour suivre une branche distante au moment du push.
- [ ] d) `git fetch origin feature_authentification`
  - **Feedback :** Incorrect. Cette commande récupère les modifications de la branche distante, mais ne configure pas le suivi.

**Remarque :** La réponse (a) est correcte également, mais généralement, la commande la plus utilisée pour cette configuration est (b).