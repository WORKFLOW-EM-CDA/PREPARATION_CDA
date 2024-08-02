# Introduction à la Programmation Orientée Objet (POO) en PHP

#### 1. Qu'est-ce que la Programmation Orientée Objet (POO) ? (Cochez toutes les réponses correctes)

- [ ] a) Un paradigme de programmation utilisant des objets et des classes
- [ ] b) Un paradigme de programmation basé sur des procédures
- [ ] c) Un modèle de gestion de bases de données
- [ ] d) Une technique pour améliorer la réutilisabilité du code
- [ ] e) Une méthode pour structurer le code de manière modulaire

---

#### 2. Quels sont les avantages de la Programmation Orientée Objet (POO) ? (Cochez toutes les réponses correctes)

- [ ] a) Modularité
- [ ] b) Réutilisabilité
- [ ] c) Maintenabilité
- [ ] d) Encapsulation
- [ ] e) Polymorphisme

---

#### 3. Quelle est la définition d'une classe en POO ? (Cochez toutes les réponses correctes)

- [ ] a) Un modèle définissant les propriétés et les comportements des objets
- [ ] b) Une instance d'un modèle
- [ ] c) Une méthode pour manipuler les données
- [ ] d) Un type de structure de données
- [ ] e) Un attribut spécifique d'un objet

---

#### 4. Quel est le rôle de l'encapsulation en POO ? (Cochez toutes les réponses correctes)

- [ ] a) Regrouper les données et les méthodes au sein d'une même classe
- [ ] b) Protéger les données contre les accès non contrôlés
- [ ] c) Permettre l'héritage de classes
- [ ] d) Faciliter la manipulation directe des attributs
- [ ] e) Contrôler l'accès aux données via des mots-clés de visibilité

---

#### 5. En quoi consiste l'héritage en POO ? (Cochez toutes les réponses correctes)

- [ ] a) Créer une nouvelle classe basée sur une classe existante
- [ ] b) Étendre ou modifier les fonctionnalités d'une classe existante
- [ ] c) Protéger les données des objets
- [ ] d) Définir des méthodes communes à plusieurs classes
- [ ] e) Modéliser des relations "est-un" entre les classes

---

#### 6. Que fait la méthode `__toString()` en PHP ? (Cochez toutes les réponses correctes)

- [ ] a) Elle permet de convertir un objet en chaîne de caractères
- [ ] b) Elle est utilisée pour définir un format d'affichage pour un objet
- [ ] c) Elle est appelée automatiquement lors de la conversion d'un objet en chaîne
- [ ] d) Elle est utilisée pour manipuler directement les attributs de l'objet
- [ ] e) Elle peut être utilisée pour implémenter des comportements polymorphiques

---

#### 7. Quelle est la définition d'une classe abstraite en POO ? (Cochez toutes les réponses correctes)

- [ ] a) Une classe qui ne peut pas être instanciée directement
- [ ] b) Une classe qui peut contenir des méthodes abstraites à implémenter
- [ ] c) Une classe qui définit un contrat pour les classes dérivées
- [ ] d) Une classe qui peut être instanciée directement si toutes les méthodes sont implémentées
- [ ] e) Une classe qui encapsule des comportements communs entre plusieurs classes

---

#### 8. Que permet le polymorphisme en POO ? (Cochez toutes les réponses correctes)

- [ ] a) Utiliser des objets de différentes classes de manière interchangeable
- [ ] b) Traiter des objets via une interface ou une classe de base commune
- [ ] c) Modifier le comportement des méthodes dans les classes dérivées
- [ ] d) Définir des attributs spécifiques pour chaque type d'objet
- [ ] e) Appliquer des modifications directes aux attributs d'objets

---

#### 9. Comment les interfaces sont-elles utilisées en PHP ? (Cochez toutes les réponses correctes)

- [ ] a) Pour définir des méthodes que les classes doivent implémenter
- [ ] b) Pour créer des classes abstraites avec des méthodes non implémentées
- [ ] c) Pour créer des contrats que les classes doivent suivre
- [ ] d) Pour encapsuler des méthodes communes entre plusieurs classes
- [ ] e) Pour permettre l'instanciation directe de classes

---

#### 10. Quel est le rôle des méthodes `getters` et `setters` en POO ? (Cochez toutes les réponses correctes)

- [ ] a) Accéder aux valeurs des attributs privés d'une classe
- [ ] b) Modifier les valeurs des attributs privés d'une classe
- [ ] c) Permettre un contrôle sur les données avant leur enregistrement
- [ ] d) Accéder directement aux attributs protégés d'une classe
- [ ] e) Appliquer des modifications directes aux méthodes d'une classe

---

#### 11. Que permet de visualiser un diagramme UML en Programmation Orientée Objet (POO) ? (Cochez toutes les réponses correctes)

- [ ] a) La structure et les relations entre les classes
- [ ] b) Les méthodes d'une classe
- [ ] c) Les attributs privés d'une classe
- [ ] d) Les relations d'héritage et d'implémentation
- [ ] e) Les algorithmes utilisés dans les méthodes

---

### Exercice : Gestion d'une Bibliothèque

#### 12. Quelle est la responsabilité principale d'une classe abstraite `Book` dans un système de gestion de bibliothèque ? (Cochez toutes les réponses correctes)

- [ ] a) Définir les attributs et méthodes communs à tous les types de livres
- [ ] b) Définir des méthodes spécifiques pour chaque type de livre
- [ ] c) Contenir des attributs privés pour stocker les informations des livres
- [ ] d) Définir des méthodes qui doivent être implémentées par les classes dérivées
- [ ] e) Fournir une implémentation complète des méthodes pour tous les types de livres

---

#### 13. Quel est l'intérêt de créer des classes dérivées `PhysicalBook` et `DigitalBook` à partir de la classe abstraite `Book` ? (Cochez toutes les réponses correctes)

- [ ] a) Partager les attributs et méthodes communs définis dans la classe abstraite
- [ ] b) Ajouter des fonctionnalités spécifiques pour chaque type de livre
- [ ] c) Protéger les données spécifiques aux types de livres des modifications non autorisées
- [ ] d) Définir des méthodes qui ne sont pas nécessaires pour chaque type de livre
- [ ] e) Étendre les fonctionnalités de la classe abstraite en ajoutant des méthodes spécifiques
