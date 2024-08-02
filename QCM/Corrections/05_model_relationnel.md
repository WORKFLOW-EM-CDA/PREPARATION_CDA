### QCM sur le Modèle Relationnel et SQL

1. **Quels sont les quatre principaux groupes de commandes en SQL ? (Cochez toutes les réponses correctes)**
   - [x] a) DDL (Data Definition Language)
     - **Feedback :** Correct. DDL est utilisé pour définir et modifier les structures des bases de données.
   - [x] b) DML (Data Manipulation Language)
     - **Feedback :** Correct. DML est utilisé pour manipuler les données dans les bases de données.
   - [x] c) DCL (Data Control Language)
     - **Feedback :** Correct. DCL est utilisé pour contrôler l'accès aux données.
   - [x] d) TCL (Transaction Control Language)
     - **Feedback :** Correct. TCL est utilisé pour gérer les transactions dans les bases de données.
   - [ ] e) DML (Data Manipulation Language) (répété)
     - **Feedback :** Incorrect. Cette option est une répétition et n'apporte pas d'information supplémentaire.

2. **Quels groupes de commandes SQL sont utilisés pour manipuler les données ? (Cochez toutes les réponses correctes)**
   - [ ] a) DDL
     - **Feedback :** Incorrect. DDL est utilisé pour définir les structures des bases de données, pas pour manipuler les données.
   - [x] b) DML
     - **Feedback :** Correct. DML (Data Manipulation Language) est utilisé pour insérer, mettre à jour, supprimer et interroger des données.
   - [ ] c) DCL
     - **Feedback :** Incorrect. DCL est utilisé pour contrôler les droits d'accès et les permissions des utilisateurs.
   - [ ] d) TCL
     - **Feedback :** Incorrect. TCL est utilisé pour contrôler les transactions, pas pour manipuler directement les données.

3. **Quelles sont les contraintes d'intégrité en SQL ? (Cochez toutes les réponses correctes)**
   - [x] a) Contrainte NOT NULL
     - **Feedback :** Correct. NOT NULL assure qu'une colonne ne peut pas avoir de valeur NULL.
   - [x] b) Contrainte UNIQUE
     - **Feedback :** Correct. UNIQUE garantit que toutes les valeurs dans une colonne ou un groupe de colonnes sont uniques.
   - [x] c) Contrainte CHECK
     - **Feedback :** Correct. CHECK impose une condition que chaque valeur dans une colonne doit satisfaire.
   - [x] d) Contrainte de clé étrangère
     - **Feedback :** Correct. La contrainte de clé étrangère assure que les valeurs d'une colonne correspondent aux valeurs de la clé primaire d'une autre table.
   - [x] e) Contrainte de clé primaire
     - **Feedback :** Correct. La contrainte de clé primaire identifie de manière unique chaque enregistrement dans une table.

4. **Quel est le rôle des index en SQL ? (Cochez toutes les réponses correctes)**
   - [x] a) Améliorer les performances de recherche
     - **Feedback :** Correct. Les index permettent d'accélérer les opérations de recherche dans les tables.
   - [ ] b) Manipuler les données
     - **Feedback :** Incorrect. Les index ne manipulent pas les données, ils facilitent l'accès aux données.
   - [ ] c) Gérer les transactions
     - **Feedback :** Incorrect. La gestion des transactions relève du TCL.
   - [ ] d) Définir des structures de données
     - **Feedback :** Incorrect. Les structures de données sont définies par DDL, pas par les index.

5. **Quel est le rôle de la cardinalité dans les bases de données relationnelles ? (Cochez toutes les réponses correctes)**
   - [x] a) Définir les relations entre les tables
     - **Feedback :** Correct. La cardinalité définit le nombre de relations possibles entre les entités.
   - [ ] b) Déterminer les types de données des colonnes
     - **Feedback :** Incorrect. Les types de données des colonnes sont définis par DDL.
   - [ ] c) Identifier les clés primaires
     - **Feedback :** Incorrect. La clé primaire est identifiée par la définition des contraintes dans DDL.
   - [ ] d) Spécifier les règles d'intégrité des données
     - **Feedback :** Incorrect. Les règles d'intégrité des données sont définies par les contraintes comme NOT NULL, UNIQUE, etc.

6. **Quelle est la troisième forme normale (3NF) dans la normalisation des bases de données ? (Cochez toutes les réponses correctes)**
   - [x] a) Aucun attribut non clé ne doit dépendre transitivement d'une autre colonne non clé
     - **Feedback :** Correct. La 3NF exige que tous les attributs non clés dépendent uniquement de la clé primaire.
   - [x] b) Toutes les colonnes non clés doivent dépendre de la totalité de la clé primaire
     - **Feedback :** Correct. Pour qu'une table soit en 3NF, elle doit d'abord être en 2NF, ce qui signifie que toutes les colonnes non clés doivent dépendre de la totalité de la clé primaire.
   - [ ] c) Chaque attribut doit contenir une seule valeur
     - **Feedback :** Incorrect. Cette règle est associée à la première forme normale (1NF), pas la troisième.
   - [x] d) Aucun attribut non clé ne doit dépendre d'une autre colonne non clé
     - **Feedback :** Correct. En 3NF, aucun attribut non clé ne doit dépendre transitivement d'un autre attribut non clé.