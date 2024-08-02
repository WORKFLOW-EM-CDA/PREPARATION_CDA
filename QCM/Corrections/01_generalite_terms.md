# QCM - termes généraux

1. **Qu'est-ce que la logique métier ?**
   - [ ] La conception des interfaces utilisateur.
     - **Feedback :** Incorrect. La conception des interfaces utilisateur concerne l'apparence et l'expérience utilisateur, pas les règles métier.
   - [x] Les règles, processus et algorithmes définissant le comportement et les opérations métier d'une application.
     - **Feedback :** Correct. La logique métier concerne les règles et processus qui définissent comment les opérations de l'application sont exécutées et comment les données sont manipulées en fonction des besoins métier.
   - [ ] La gestion des requêtes HTTP.
     - **Feedback :** Incorrect. La gestion des requêtes HTTP est une partie de la couche de communication entre le client et le serveur, et non de la logique métier.
   - [ ] La mise en place des bases de données relationnelles.
     - **Feedback :** Incorrect. La mise en place des bases de données relationnelles est liée à la persistance des données et à la gestion des données, pas directement à la logique métier.

2. **Quel est le rôle principal de l'algorithmique ?**
   - [ ] Concevoir des interfaces utilisateur.
     - **Feedback :** Incorrect. La conception des interfaces utilisateur est une tâche distincte qui concerne l'UI/UX.
   - [x] Étudier et concevoir des algorithmes pour résoudre des problèmes spécifiques.
     - **Feedback :** Correct. L'algorithmique se concentre sur la conception, l'analyse et l'optimisation des algorithmes pour résoudre des problèmes de manière efficace.
   - [ ] Gérer les requêtes HTTP et les réponses.
     - **Feedback :** Incorrect. La gestion des requêtes HTTP relève des responsabilités des serveurs web et des contrôleurs d'application, pas directement de l'algorithmique.
   - [ ] Utiliser des opérations telles que la recherche, le tri, la manipulation de données, etc.
     - **Feedback :** Incorrect. Bien que l'algorithmique implique des opérations telles que la recherche et le tri, le rôle principal est la conception d'algorithmes pour résoudre des problèmes.

3. **Quel est le but principal des services dans une application Symfony ? (plusieurs choix possibles)**
   - [ ] Gérer les requêtes HTTP.
     - **Feedback :** Incorrect. La gestion des requêtes HTTP est généralement le rôle des contrôleurs.
   - [x] Effectuer des tâches spécifiques et encapsuler la logique métier.
     - **Feedback :** Correct. Les services dans Symfony sont utilisés pour encapsuler des tâches spécifiques et la logique métier, rendant le code plus modulaire et réutilisable.
   - [ ] Définir les routes de l'application.
     - **Feedback :** Incorrect. La définition des routes est gérée par le système de routage de Symfony.
   - [x] Être accessibles à partir des contrôleurs pour effectuer des opérations métier.
     - **Feedback :** Correct, mais moins précis. Les services sont effectivement accessibles à partir des contrôleurs, mais leur rôle principal est d'encapsuler la logique métier et les tâches spécifiques.

4. **Quel est le rôle des middlewares dans le traitement des requêtes HTTP ? (plusieurs choix possibles)**
   - [x] Agir comme un intermédiaire pour traiter une requête avant qu'elle n'atteigne la logique principale de l'application.
     - **Feedback :** Correct. Les middlewares sont des composants intermédiaires qui traitent les requêtes et les réponses, effectuant des tâches comme l'authentification, la validation, etc.
   - [x] Effectuer des opérations telles que l'authentification, la validation et la journalisation.
     - **Feedback :** Correct. Les middlewares sont souvent utilisés pour des tâches comme l'authentification, la validation des données et la journalisation.
   - [ ] Gérer uniquement les réponses HTTP sans intervenir sur les requêtes.
     - **Feedback :** Incorrect. Les middlewares interviennent à la fois sur les requêtes et les réponses, pas uniquement sur les réponses.
   - [ ] Manipuler la réponse avant qu'elle ne soit renvoyée au client.
     - **Feedback :** Correct, mais moins précis. Les middlewares peuvent aussi manipuler la réponse avant qu'elle ne soit renvoyée au client, mais leur rôle est plus général.

5. **Qu'est-ce que l'ORM (Object-Relational Mapping) ? (plusieurs choix possibles)**
   - [x] Une technique de programmation qui permet de mapper les objets d'une application à des tables dans une base de données relationnelle.
     - **Feedback :** Correct. L'ORM est une technique qui facilite la conversion des données entre des systèmes orientés objets et des bases de données relationnelles.
   - [ ] Un type de base de données relationnelle.
     - **Feedback :** Incorrect. L'ORM n'est pas une base de données, mais une technique pour interagir avec les bases de données relationnelles.
   - [x] Une technologie qui facilite la manipulation et la persistance des données dans une application logicielle.
     - **Feedback :** Correct, mais moins précis. L'ORM facilite la manipulation des données, mais il est spécifiquement une technique pour mapper des objets à des tables relationnelles.
   - [ ] Un framework pour gérer les requêtes HTTP.
     - **Feedback :** Incorrect. L'ORM ne concerne pas la gestion des requêtes HTTP, mais la gestion des interactions avec la base de données.

6. **Dans quel cas peut-on inclure de la logique métier directement dans un contrôleur ?**
   - [ ] Lorsqu'il s'agit de tâches complexes et volumineuses.
     - **Feedback :** Incorrect. Les tâches complexes et volumineuses doivent être gérées par des services pour maintenir une séparation des préoccupations.
   - [x] Lorsqu'il s'agit d'opérations simples qui ne justifient pas la création d'un service dédié.
     - **Feedback :** Correct. Les opérations simples peuvent être gérées directement dans les contrôleurs, mais les tâches plus complexes doivent être encapsulées dans des services.
   - [ ] Lorsqu'on souhaite définir des routes dynamiques.
     - **Feedback :** Incorrect. La définition des routes est séparée de la logique métier et est généralement gérée par le système de routage.
   - [ ] Lorsqu'on gère des sessions utilisateur.
     - **Feedback :** Incorrect. La gestion des sessions utilisateur peut impliquer une logique métier, mais cela se fait souvent dans des services ou des gestionnaires dédiés.

7. **Qu'est-ce qu'un boilerplate ?**
   - [ ] Un design pattern pour les applications web.
     - **Feedback :** Incorrect. Un boilerplate n'est pas un design pattern mais un code générique.
   - [x] Du code ou des sections de code répétées dans plusieurs endroits ou projets, souvent sans modification significative.
     - **Feedback :** Correct. Un boilerplate est du code répétitif utilisé comme base pour démarrer des projets ou sections de code.
   - [ ] Une bibliothèque pour la gestion des requêtes HTTP.
     - **Feedback :** Incorrect. Un boilerplate n'est pas spécifique à la gestion des requêtes HTTP.
   - [ ] Un outil de déploiement d'applications.
     - **Feedback :** Incorrect. Un boilerplate n'est pas un outil de déploiement mais du code pré-écrit utilisé pour initialiser des projets.

