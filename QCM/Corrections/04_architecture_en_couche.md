### QCM sur les Architectures Logiciel

1. **Quelle est la caractéristique principale de l'architecture en couches par rapport au MVC ?**
   - [ ] Plus modulaire
     - **Feedback :** Incorrect. L'architecture en couches et le modèle MVC sont tous deux modulaires.
   - [ ] Moins modulable
     - **Feedback :** Incorrect. L'architecture en couches est également modulaire.
   - [ ] Plus facile à tester
     - **Feedback :** Incorrect. Les deux architectures peuvent être conçues pour être facilement testables.
   - [x] Plus rapide
     - **Feedback :** Correct. L'architecture en couches est généralement plus rapide en termes de développement et d'organisation, car elle sépare les préoccupations plus strictement.

2. **Dans une architecture en couches, quelle couche est responsable de l'interface utilisateur et de l'interaction avec l'utilisateur ?**
   - [x] Couche de présentation (Frontend)
     - **Feedback :** Correct. La couche de présentation gère l'interface utilisateur et les interactions avec l'utilisateur.
   - [ ] Couche métier (Backend)
     - **Feedback :** Incorrect. La couche métier gère la logique métier.
   - [ ] Couche d'accès aux données (Backend)
     - **Feedback :** Incorrect. La couche d'accès aux données gère l'interaction avec la base de données.
   - [ ] Couche d'infrastructure
     - **Feedback :** Incorrect. La couche d'infrastructure fournit des services sous-jacents.

3. **Quelle couche gère la logique métier de l'application ?**
   - [ ] Couche de présentation (Frontend)
     - **Feedback :** Incorrect. La couche de présentation gère l'interface utilisateur.
   - [x] Couche métier (Backend)
     - **Feedback :** Correct. La couche métier est responsable de la logique métier de l'application.
   - [ ] Couche d'accès aux données (Backend)
     - **Feedback :** Incorrect. La couche d'accès aux données gère les interactions avec la base de données.
   - [ ] Couche d'infrastructure
     - **Feedback :** Incorrect. La couche d'infrastructure fournit les services nécessaires au fonctionnement de l'application.

4. **Quelle couche est responsable de l'accès et de la manipulation des données dans une architecture en couches ?**
   - [ ] Couche de présentation (Frontend)
     - **Feedback :** Incorrect. La couche de présentation gère l'interface utilisateur.
   - [ ] Couche métier (Backend)
     - **Feedback :** Incorrect. La couche métier gère la logique métier.
   - [x] Couche d'accès aux données (Backend)
     - **Feedback :** Correct. La couche d'accès aux données est responsable de l'accès et de la manipulation des données.
   - [ ] Couche d'infrastructure
     - **Feedback :** Incorrect. La couche d'infrastructure fournit des services sous-jacents.

5. **Quelle est la fonction principale de la couche d'infrastructure dans une architecture en couches ?**
   - [ ] Gérer l'interface utilisateur
     - **Feedback :** Incorrect. Gérer l'interface utilisateur est le rôle de la couche de présentation.
   - [ ] Traiter les requêtes de l'utilisateur
     - **Feedback :** Incorrect. Traiter les requêtes de l'utilisateur est souvent le rôle de la couche de présentation et de la couche métier.
   - [x] Fournir les composants et services sous-jacents nécessaires au fonctionnement de l'application
     - **Feedback :** Correct. La couche d'infrastructure fournit les composants et services nécessaires au bon fonctionnement de l'application.
   - [ ] Assurer la persistance des données
     - **Feedback :** Incorrect. Assurer la persistance des données est généralement le rôle de la couche d'accès aux données.

6. **Quel est un exemple typique de technologie utilisée dans la couche de présentation (Frontend) ?**
   - [x] React
     - **Feedback :** Correct. React est une bibliothèque JavaScript utilisée pour construire des interfaces utilisateur.
   - [ ] Node.js
     - **Feedback :** Incorrect. Node.js est une plateforme de backend pour exécuter du JavaScript côté serveur.
   - [ ] SQL
     - **Feedback :** Incorrect. SQL est utilisé pour interagir avec les bases de données.
   - [ ] Spring
     - **Feedback :** Incorrect. Spring est un framework pour le développement d'applications backend en Java.

7. **Quelle technologie est souvent utilisée pour implémenter la couche métier (Backend) ?  (plusieurs choix possibles)**
   - [ ] HTML
     - **Feedback :** Incorrect. HTML est utilisé pour structurer le contenu des pages web dans la couche de présentation.
   - [x] Django
     - **Feedback :** Correct. Django est un framework web pour Python, souvent utilisé pour implémenter la couche métier.
   - [ ] CSS
     - **Feedback :** Incorrect. CSS est utilisé pour styliser les pages web dans la couche de présentation.
   - [x] Symfony
     - **Feedback :** Correct. Symfony est un framework web backend en PHP, souvent utilisé pour implémenter la couche métier.
   - [ ] Vue.js
     - **Feedback :** Incorrect. Vue.js est un framework JavaScript utilisé pour construire des interfaces utilisateur dans la couche de présentation.

8. **Quel est le principal avantage de l'architecture en couches ?**
   - [ ] Performances accrues
     - **Feedback :** Incorrect. L'architecture en couches n'augmente pas nécessairement les performances.
   - [x] Séparation des responsabilités
     - **Feedback :** Correct. L'architecture en couches permet une séparation claire des responsabilités, facilitant la maintenance et le développement.
   - [ ] Moins de code à écrire
     - **Feedback :** Incorrect. L'architecture en couches peut nécessiter plus de code pour maintenir la séparation des préoccupations.
   - [ ] Réduction des coûts de développement
     - **Feedback :** Incorrect. Bien que l'architecture en couches puisse réduire les coûts à long terme grâce à une meilleure maintenance, ce n'est pas toujours le cas au début du développement.

9. **Comment les couches sont-elles généralement organisées dans une architecture en couches ?**
   - [ ] En modules indépendants
     - **Feedback :** Incorrect. Les couches peuvent être organisées en modules, mais elles sont généralement définies par leurs responsabilités spécifiques.
   - [x] En couches fonctionnelles avec des responsabilités spécifiques
     - **Feedback :** Correct. Les couches sont organisées en fonction de leurs responsabilités spécifiques, comme la présentation, la logique métier, l'accès aux données, et l'infrastructure.
   - [ ] En services micro
     - **Feedback :** Incorrect. Les microservices sont une architecture différente où chaque service est indépendant et responsable d'une fonction spécifique.
   - [ ] En bases de données distribuées
     - **Feedback :** Incorrect. Les bases de données distribuées sont une technique de gestion des données, pas une organisation d'architecture en couches.

10. **Quel est le rôle des contrôleurs dans une architecture en couches ?**
    - [ ] Accéder aux données dans la base de données
      - **Feedback :** Incorrect. Accéder aux données est le rôle des services ou des référentiels dans la couche d'accès aux données.
    - [ ] Encapsuler la logique métier
      - **Feedback :** Incorrect. La logique métier est encapsulée dans la couche métier.
    - [x] Traiter les requêtes et renvoyer les réponses aux clients
      - **Feedback :** Correct. Les contrôleurs traitent les requêtes entrantes, appellent la logique métier et renvoient les réponses aux clients.
    - [ ] Fournir les composants et services sous-jacents
      - **Feedback :** Incorrect. Fournir les composants et services sous-jacents est le rôle de la couche d'infrastructure.

11. **Quel est le rôle des services dans une architecture en couches ?**
    - [ ] Accéder aux données dans la base de données
      - **Feedback :** Incorrect. Accéder aux données est le rôle des référentiels.
    - [x] Encapsuler la logique métier
      - **Feedback :** Correct. Les services encapsulent la logique métier et fournissent des fonctionnalités métier aux contrôleurs.
    - [ ] Traiter les requêtes et renvoyer les réponses aux clients
      - **Feedback :** Incorrect. Traiter les requêtes et renvoyer les réponses est le rôle des contrôleurs.
    - [ ] Fournir les composants et services sous-jacents
      - **Feedback :** Incorrect. Fournir les composants et services sous-jacents est le rôle de la couche d'infrastructure.

12. **Quel est le rôle des référentiels (repositories) dans une architecture en couches ?**
    - [x] Accéder aux données dans la base de données
      - **Feedback :** Correct. Les référentiels sont responsables de l'accès et de la manipulation des données dans la base de données.
    - [ ] Encapsuler la logique métier
      - **Feedback :** Incorrect. La logique métier est encapsulée dans les services de la couche métier.
    - [ ] Traiter les requêtes et renvoyer les réponses aux clients
      - **Feedback :** Incorrect. Traiter les requêtes et renvoyer les réponses est le rôle des contrôleurs.
    - [ ] Fournir les composants et services sous-jacents
      - **Feedback :** Incorrect. Fournir les composants et services sous-jacents est le rôle de la couche d'infrastructure.