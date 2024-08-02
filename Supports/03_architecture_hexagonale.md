# Architecture Hexagonale

**Définition :** L'architecture hexagonale, également connue sous le nom d'architecture en ports et adaptateurs, est une approche de conception logicielle où une application est organisée autour de son domaine métier, avec des interfaces (ports) permettant la communication avec le monde extérieur. L'idée principale est de rendre le cœur de l'application indépendant des détails techniques et des frameworks externes.

**Principaux Concepts :**

1. **Domaine Métier (Cœur de l'Application)**
   - **Rôle :** Contient la logique métier principale et les règles de traitement des données. C'est le centre de l'application, où se trouvent les fonctionnalités principales.
   - **Exemples :** Calculs de salaires, validation des données, règles de gestion.

2. **Ports**
   - **Rôle :** Définissent les points d'entrée (ports entrants) et de sortie (ports sortants) de l'application pour interagir avec le monde extérieur.
   - **Exemples :** API REST, interfaces utilisateur, services externes.

3. **Adaptateurs**
   - **Rôle :** Connectent les ports aux composants externes comme les bases de données, les interfaces utilisateur ou les services externes. Ils convertissent les données du format utilisé par le monde extérieur en un format compréhensible par le domaine métier et vice versa.
   - **Exemples :** Contrôleurs HTTP, connecteurs de base de données, clients d'API.

4. **Indépendance des Frameworks**
   - **Rôle :** Le domaine métier est indépendant des frameworks et des technologies spécifiques. Cela signifie que vous pouvez changer de framework ou de technologie sans modifier la logique métier.
   - **Exemples :** Le domaine métier peut rester inchangé si vous passez de Spring à Express.js.

**Avantages :**
- **Indépendance :** Le cœur de l'application n'est pas lié aux technologies spécifiques, ce qui facilite les changements et la portabilité.
- **Modularité :** Permet une séparation claire entre la logique métier et les détails techniques.
- **Testabilité :** Facilite les tests unitaires et d'intégration en isolant la logique métier des interfaces externes.

**Inconvénients :**
- **Complexité :** Peut ajouter de la complexité en introduisant des couches supplémentaires pour gérer les interactions.
- **Apprentissage :** Peut nécessiter un temps d'apprentissage pour comprendre et appliquer correctement les concepts.

**Exemple d'Organisation :**

- **Domaine Métier :**
  - Contient les entités, les services métier et les règles de gestion.

- **Ports :**
  - Définissent les interfaces pour la communication (API, services, etc.).

- **Adaptateurs :**
  - Implémentations concrètes pour interagir avec les ports (contrôleurs, repos, etc.).

- **Infrastructure :**
  - Détails techniques comme la gestion des bases de données, la configuration des serveurs, etc.

**Exemple Simplifié :**

```
src/
├── adapters/
│   ├── http/
│   └── database/
├── application/
├── domain/
│   ├── entities/
│   └── services/
└── infrastructure/
    ├── database/
    └── logging/
```

- **Domaine :** Contient les règles métier.
- **Adaptateurs :** Gestion des interfaces externes.
- **Application :** Utilise le domaine pour fournir des fonctionnalités.
- **Infrastructure :** Services techniques de bas niveau.

---

Cette architecture permet de créer des systèmes modulaires où le cœur de l'application est séparé des technologies et des détails externes, facilitant ainsi les modifications et la maintenance.