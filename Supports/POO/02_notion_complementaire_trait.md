# Concepts Avancés de la POO en PHP

## 1 Traits

Les traits sont un mécanisme de réutilisation de code dans des langages à héritage simple comme PHP. 

Un trait est semblable à une classe mais est destiné à regrouper des fonctionnalités spécifiques et à être inclus dans plusieurs classes.

### Définition et Utilisation des Traits

Les traits permettent de définir des méthodes qui peuvent être utilisées dans plusieurs classes, même si ces classes ne partagent pas de relation d'héritage. Cela favorise la réutilisabilité du code et réduit la duplication.

**Exemple en PHP :**

```php
<?php

trait Logger {
    public function log($message) {
        echo "[LOG]: " . $message . "\n";
    }
}

class User {
    use Logger;

    private $name;

    public function __construct($name) {
        $this->name = $name;
        $this->log("User '$name' created.");
    }
}

class Product {
    use Logger;

    private $name;

    public function __construct($name) {
        $this->name = $name;
        $this->log("Product '$name' created.");
    }
}

$user = new User("Alice");
$product = new Product("Laptop");
```

Dans cet exemple, le trait `Logger` est utilisé par les classes `User` et `Product` pour fournir une fonctionnalité de journalisation commune.

## 2 Surcharge et Redéfinition des Méthodes

Les traits permettent également de surcharger les méthodes et de définir des méthodes abstraites que les classes utilisant le trait doivent implémenter.

**Exemple en PHP :**

```php
<?php

trait ExampleTrait {
    public function hello() {
        return "Hello from Trait";
    }
}

class BaseClass {
    public function hello() {
        return "Hello from BaseClass";
    }
}

class ChildClass extends BaseClass {
    use ExampleTrait;

    public function hello() {
        return "Hello from ChildClass";
    }

    public function parentHello() {
        return parent::hello();
    }

    public function traitHello() {
        return ExampleTrait::hello();
    }
}

$child = new ChildClass();
echo $child->hello(); // Hello from ChildClass
echo $child->parentHello(); // Hello from BaseClass
echo $child->traitHello(); // Hello from Trait
```

## Nouveautés de PHP 8.3

### 1 Intersection Types

PHP 8.3 introduit les types d'intersection, permettant de restreindre une valeur à appartenir à plusieurs types en même temps. Cela peut être utilisé pour des vérifications de type plus strictes.

**Exemple en PHP :**

```php
<?php

interface Logger {
    public function log(string $message);
}

interface JsonSerializable {
    public function jsonSerialize();
}

class JsonLogger implements Logger, JsonSerializable {
    public function log(string $message) {
        echo json_encode(["log" => $message]);
    }

    public function jsonSerialize() {
        return [];
    }
}

function acceptsLoggerAndJsonSerializable(Logger&JsonSerializable $obj) {
    echo "Object is both Logger and JsonSerializable";
}

$jsonLogger = new JsonLogger();
acceptsLoggerAndJsonSerializable($jsonLogger); // Valid
```
