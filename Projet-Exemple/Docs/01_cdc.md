# Cahier des Charges

## 1. Présentation d’ensemble du projet

### 1.1. Présentation de l’entreprise / du client
L’entreprise développe une plateforme de cours en ligne. Les cours sont hébergés sur GitHub, et l'application sera développée en Symfony 7 pour le back-end et React pour le front-end. La base de données utilisera MongoDB pour les recherches et PostgreSQL pour le stockage relationnel. Les utilisateurs incluront des formateurs, des élèves, et des administrateurs. Certains cours seront disponibles à l'achat.

### 1.2. Description de l’existant
Actuellement, les cours sont hébergés sur GitHub sans une plateforme centralisée pour la gestion des cours, des utilisateurs, et des transactions d'achat.

### 1.3. Objectifs du projet
- Créer une plateforme de gestion de cours en ligne
- Intégrer des fonctionnalités d'achat de cours
- Permettre aux formateurs et aux administrateurs de créer et gérer des cours sur GitHub et la plateforme
- Intégrer une IA pour l'analyse de la pertinence des cours

### 1.4. Intervenants sur le projet
- **Antoine** : Product Owner
- **Mathieu** : Développeur Principal
- **Paul** : Graphiste pour la proposition graphique
- **Michel** : Responsable de l'intégration de l'IA

### 1.5. Cible adressée par le projet
- Élèves
- Formateurs
- Administrateurs

### 1.6. Exigences de performances et de volumétrie
- La plateforme doit pouvoir gérer des milliers d'utilisateurs simultanément.
- Le temps de réponse pour les recherches de cours doit être inférieur à 2 secondes.

### 1.7. Multilinguisme & adaptations pour un public spécifique
- La plateforme doit être disponible en plusieurs langues.
- Doit être accessible pour les utilisateurs avec des besoins spécifiques.

## 2. Description graphique et ergonomique

### 2.1. Composants de la charte graphique
- Logo de l'entreprise
- Palette de couleurs
- Typographie

### 2.2. Design, Responsive design et autres exigences liées au design
- La plateforme doit être responsive, adaptée à tous les types d'appareils (desktop, tablette, mobile).

### 2.3. Maquettes
- Réalisées par Paul, incluant les principales pages de la plateforme (page d'accueil, page de cours, page de profil, etc.).

## 3. Besoins fonctionnels « métier »

### 3.1. Utilisateurs du projet
- Élèves
- Formateurs
- Administrateurs

### 3.2. Processus utilisateur impacté
- Inscription et gestion des profils
- Consultation et achat de cours
- Création et gestion de cours par les formateurs et administrateurs

### 3.3. Informations relatives aux contenus
- Cours hébergés sur GitHub
- Métadonnées des cours (titre, description, durée, etc.)
- Évaluations et retours des élèves

### 3.4. Inventaire des besoins fonctionnels
- Authentification et gestion des utilisateurs
- Système de paiement pour l'achat de cours
- Système de notation et de commentaires
- Moteur de recherche performant pour les cours
- Tableau de bord pour les formateurs et administrateurs

## 4. Prestations attendues

### 4.1. Livrables et prestations
- Code source de la plateforme
- Documentation technique et utilisateur
- Maquettes graphiques
- Tests unitaires et d'intégration
- Rapport sur les performances et la sécurité

## 5. Budget temps

### Phases et Estimation du Temps

1. **Conception et Planification**
   - **Estimé** : 10 jours (2 semaines)

2. **Développement Front-end**
   - **Proposition graphique par Paul** : 5 jours (1 semaine)
   - **Développement par Mathieu (Développeur Principal)** : 30 jours (6 semaines)

3. **Développement Back-end**
   - **Estimé** : 50 jours (10 semaines)

4. **Intégration de l'IA**
   - **Réalisée par Michel** : 5 jours (1 semaine)

5. **Tests et Assurance Qualité**
   - **Estimé** : 20 jours (4 semaines)

6. **Déploiement et Maintenance**
   - **Estimé** : 10 jours (2 semaines)

### Total des Jours Estimés

Additionnons les jours estimés pour chaque phase :

- Conception et Planification : 10 jours
- Proposition graphique par Paul : 5 jours
- Développement Front-end : 30 jours
- Développement Back-end : 50 jours
- Intégration de l'IA : 5 jours
- Tests et Assurance Qualité : 20 jours
- Déploiement et Maintenance : 10 jours

Total : 130 jours

### Détail du Budget Temps par Personne

1. **Antoine (Product Owner)**
   - **Conception et Planification** : 10 jours (2 semaines)

2. **Mathieu (Développeur Principal)**
   - **Conception et Planification** : 10 jours (2 semaines)
   - **Développement Front-end** : 30 jours (6 semaines)
   - **Développement Back-end** : 50 jours (10 semaines)
   - **Tests et Assurance Qualité** : 20 jours (4 semaines)
   - **Déploiement et Maintenance** : 10 jours (2 semaines)
   - **Total** : 120 jours (24 semaines)

3. **Paul**
   - **Proposition graphique** : 5 jours (1 semaine)

4. **Michel**
   - **Intégration de l'IA** : 5 jours (1 semaine)

### Répartition des Jours en Semaines

Pour chaque personne travaillant 5 jours par semaine, nous convertissons les jours en semaines :

- **Antoine (Conception et Planification)** : 10 jours
  - 10 jours / 5 jours par semaine = 2 semaines

- **Mathieu (Développeur Principal)** : 120 jours
  - 120 jours / 5 jours par semaine = 24 semaines

- **Paul (Proposition graphique)** : 5 jours
  - 5 jours / 5 jours par semaine = 1 semaine

- **Michel (Intégration de l'IA)** : 5 jours
  - 5 jours / 5 jours par semaine = 1 semaine

### Répartition des Semaines en Mois

Pour chaque personne travaillant 3 semaines par mois, nous convertissons les semaines en mois :

- **Antoine (Conception et Planification)** : 2 semaines
  - 2 semaines / 3 semaines par mois = 0,7 mois

- **Mathieu (Développeur Principal)** : 24 semaines
  - 24 semaines / 3 semaines par mois = 8 mois

- **Paul (Proposition graphique)** : 1 semaine
  - 1 semaine / 3 semaines par mois = 0,3 mois

- **Michel (Intégration de l'IA)** : 1 semaine
  - 1 semaine / 3 semaines par mois = 0,3 mois
