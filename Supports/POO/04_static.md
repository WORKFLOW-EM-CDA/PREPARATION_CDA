# Introduction à la notion de "statique" en PHP

En PHP, le mot-clé `static` est utilisé pour définir des propriétés et des méthodes qui appartiennent à la classe elle-même, plutôt qu'aux instances de cette classe. 

Cela signifie que vous pouvez accéder à une propriété ou une méthode statique sans avoir à créer une instance de la classe.

## Raisons conceptuelles

L'utilisation des propriétés et méthodes statiques en programmation orientée objet (OOP) en PHP (et dans d'autres langages) a plusieurs raisons conceptuelles. Voici les principales :

1. **Partage de données au niveau de la classe** : Les membres statiques appartiennent à la classe elle-même et non à une instance particulière. Cela permet de partager des données ou des états communs à toutes les instances d'une classe sans dupliquer ces informations.

2. **Utilisation sans instanciation** : Les méthodes statiques peuvent être appelées sans créer une instance de la classe. Cela est utile pour les fonctions utilitaires ou les constantes qui n'ont pas besoin de l'état d'une instance pour fonctionner.

3. **Gestion des ressources** : Les membres statiques peuvent être utilisés pour gérer des ressources partagées comme des connexions à une base de données, des configurations globales, ou des caches, permettant ainsi de réduire la consommation de ressources.

4. **Accès global** : Les membres statiques peuvent être facilement accessibles de n'importe où dans le code, ce qui est pratique pour les fonctions globales ou les données qui doivent être partagées entre différents composants du système.

5. **Modèles de conception** : Certains modèles de conception, comme le Singleton, dépendent fortement de l'utilisation de membres statiques pour s'assurer qu'il n'existe qu'une seule instance d'une classe dans toute l'application.

## Propriétés Statiques

Les propriétés statiques sont définies en utilisant le mot-clé `static`. Elles sont partagées entre toutes les instances de la classe.

```php
class Compteur {
    public static $compte = 0;

    public function __construct() {
        self::$compte++;
    }

    public static function getCompte() {
        return self::$compte;
    }
}

$objet1 = new Compteur();
$objet2 = new Compteur();

echo Compteur::getCompte(); // Affiche 2
```

## Méthodes Statiques

Les méthodes statiques sont également définies en utilisant le mot-clé `static`. Elles peuvent être appelées sans créer une instance de la classe.

```php
class Utilitaire {
    public static function saluer() {
        echo "Salut!";
    }
}

Utilitaire::saluer(); // Appelle la méthode statique sans instance
```

## Utilisation de `self`, `parent`, et `static`

- **self** : Réfère à la classe actuelle. Utilisé pour accéder aux membres statiques de la classe actuelle.
- **parent** : Utilisé pour accéder aux membres statiques de la classe parente.
- **static** : Tardive statique, utile en cas d'héritage pour se référer à la classe appelée.

### Exemple avec `self`

```php
class A {
    public static function direBonjour() {
        echo "Bonjour de A";
    }

    public static function saluer() {
        self::direBonjour();
    }
}

class B extends A {
    public static function direBonjour() {
        echo "Bonjour de B";
    }
}

B::saluer(); // Affiche "Bonjour de A"
```

### Exemple avec `static`

```php
class A {
    public static function direBonjour() {
        echo "Bonjour de A";
    }

    public static function saluer() {
        static::direBonjour();
    }
}

class B extends A {
    public static function direBonjour() {
        echo "Bonjour de B";
    }
}

B::saluer(); // Affiche "Bonjour de B"
```

## Points importants à retenir

- Les membres statiques ne peuvent pas accéder aux membres non statiques (instances) directement.
- Les membres statiques sont partagés entre toutes les instances de la classe, ce qui peut poser des problèmes de concurrence si plusieurs threads ou processus tentent de les modifier simultanément.
- Une utilisation excessive de membres statiques peut rendre le code moins flexible et plus difficile à tester, car les dépendances deviennent implicites et globales.

## Nouveautés en PHP 8.3

PHP 8.3 introduit plusieurs améliorations, mais concernant les propriétés et méthodes statiques, les concepts de base restent les mêmes. Voici quelques points d'amélioration et de clarification :

- **Propriétés statiques en lecture seule** : PHP 8.3 permet de déclarer des propriétés statiques en lecture seule, garantissant qu'elles ne peuvent être définies qu'une seule fois et ne peuvent pas être modifiées ensuite.
  ```php
  class Configuration {
      public static readonly string $config = "config_value";
  }
  ```

- **Static Analyzers** : Les améliorations dans les outils d'analyse statique de code en PHP 8.3 aident à mieux détecter les usages incorrects des membres statiques.

- **Améliorations de performance** : PHP 8.3 continue d'améliorer les performances, y compris celles des appels de méthodes et des accès aux propriétés statiques.

## 08 Exercice compte visiteur

Créer une classe `VisitorCounter` avec des méthodes statiques pour gérer un compteur global de visiteurs. La classe doit permettre d'incrémenter le compteur, de le réinitialiser et de récupérer le nombre actuel de visiteurs.

1. Créez une classe `VisitorCounter` avec une propriété statique `$count` pour stocker le nombre de visiteurs.
2. Ajoutez une méthode statique `increment()` pour incrémenter le compteur de visiteurs.
3. Ajoutez une méthode statique `reset()` pour réinitialiser le compteur de visiteurs à zéro.
4. Ajoutez une méthode statique `getCount()` pour obtenir le nombre actuel de visiteurs.

## Questions pour Aller Plus Loin

1. Comment pourrait-on rendre ce compteur persistant, par exemple, en utilisant une base de données ou des fichiers ?
1. Comment gérer la concurrence si plusieurs utilisateurs accèdent et modifient le compteur en même temps ?
1. Comment utiliser des tests unitaires pour vérifier que les méthodes statiques fonctionnent correctement ?
