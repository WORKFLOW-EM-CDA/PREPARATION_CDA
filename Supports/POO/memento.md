# Glossaire de la Programmation Orientée Objet (POO) en PHP

## Notions fondamentales

### 1. Classe
**Définition :** Un modèle définissant les propriétés (attributs) et les comportements (méthodes) des objets.
```php
class Car {
    public string $brand;
    public string $color;
}
```

### 2. Objet
**Définition :** Instance d'une classe contenant des valeurs spécifiques pour les attributs et des implémentations des méthodes.
```php
$myCar = new Car();
```

### 3. Attribut
**Définition :** Variable définie dans une classe pour stocker des données spécifiques à un objet.
```php
public string $brand;
```

### 4. Méthode
**Définition :** Fonction définie dans une classe pour effectuer des actions ou des calculs sur les données de l'objet.
```php
public function start() {
    return "The car starts";
}
```

### 5. Constructeur
**Définition :** Méthode spéciale appelée lors de la création d'un objet pour initialiser ses attributs.
```php
public function __construct(string $brand, string $color) {
    $this->brand = $brand;
    $this->color = $color;
}
```

### 6. Encapsulation
**Définition :** Principe consistant à regrouper les données et les méthodes qui les manipulent et à protéger l'accès aux données internes de l'objet.
```php
private float $balance;
```

### 7. Héritage
**Définition :** Mécanisme permettant à une classe de dériver d'une autre classe en héritant de ses attributs et méthodes.
```php
class SavingsAccount extends BankAccount {
    // Additional properties and methods
}
```

### 8. Abstraction
**Définition :** Concept de créer des classes abstraites qui ne peuvent pas être instanciées directement et qui contiennent des méthodes abstraites devant être implémentées par les classes dérivées.
```php
abstract class Shape {
    abstract public function calculateArea(): float;
}
```

### 9. Polymorphisme
**Définition :** Capacité de traiter des objets de différentes classes de manière uniforme grâce à une interface ou une classe de base commune.
```php
interface Animal {
    public function makeSound(): string;
}

class Dog implements Animal {
    public function makeSound(): string {
        return "Bark";
    }
}
```

### 10. Interface
**Définition :** Déclaration d'un ensemble de méthodes que toute classe implémentant l'interface doit définir.
```php
interface Logger {
    public function log(string $message);
}
```

### 11. Méthode Statique
**Définition :** Méthode appartenant à la classe elle-même plutôt qu'à une instance spécifique, accessible sans instanciation.
```php
class Math {
    public static function add($a, $b) {
        return $a + $b;
    }
}
```

### 12. Attribut Statique
**Définition :** Attribut appartenant à la classe elle-même plutôt qu'à une instance spécifique, partagé entre toutes les instances.
```php
class Counter {
    public static int $count = 0;
}
```

### 13. Visibilité (Public, Protected, Private)
**Définition :** Niveau d'accès aux attributs et méthodes d'une classe.
- **Public :** Accessible depuis n'importe où.
- **Protected :** Accessible uniquement depuis la classe elle-même et les classes héritées.
- **Private :** Accessible uniquement depuis la classe elle-même.

```php
public string $name;
protected string $address;
private float $salary;
```

### 14. Héritage Multiple
**Définition :** Non supporté en PHP ; cependant, les interfaces peuvent être utilisées pour obtenir un effet similaire en permettant à une classe d'implémenter plusieurs interfaces.

```php
interface Drivable {
    public function drive();
}

interface Flyable {
    public function fly();
}

class FlyingCar implements Drivable, Flyable {
    public function drive() {
        // Implementation
    }

    public function fly() {
        // Implementation
    }
}
```

### 15. Surcharge de Méthode (Overloading)
**Définition :** En PHP, cela se réfère principalement à l'utilisation des méthodes magiques comme `__get`, `__set`, `__call` pour gérer dynamiquement les propriétés et méthodes.
```php
class Magic {
    public function __get($name) {
        // Dynamic getter
    }

    public function __set($name, $value) {
        // Dynamic setter
    }
}
```

### 16. Redéfinition de Méthode (Overriding)
**Définition :** Capacité de redéfinir une méthode héritée d'une classe parent dans une classe dérivée.
```php
class ParentClass {
    public function display() {
        echo "Parent display";
    }
}

class ChildClass extends ParentClass {
    public function display() {
        echo "Child display";
    }
}
```

## Glossaire des Concepts traits types

### 1. Trait
**Définition :** Un mécanisme de réutilisation de code dans des langages à héritage simple, permettant d'inclure des méthodes dans plusieurs classes sans utiliser l'héritage.
```php
trait Logger {
    public function log($message) {
        echo "[LOG]: " . $message . "\n";
    }
}
```

### 2. Utilisation des Traits
**Définition :** Inclusion d'un trait dans une classe pour utiliser les méthodes définies dans le trait.
```php
class User {
    use Logger;
}
```

### 3. Surcharge des Méthodes
**Définition :** Capacité de redéfinir une méthode dans une classe dérivée pour changer ou étendre son comportement.
```php
class BaseClass {
    public function hello() {
        return "Hello from BaseClass";
    }
}

class ChildClass extends BaseClass {
    public function hello() {
        return "Hello from ChildClass";
    }
}
```

### 4. Redéfinition des Méthodes
**Définition :** Utilisation d'une méthode définie dans un trait et modification de son comportement dans la classe qui l'utilise.
```php
trait ExampleTrait {
    public function hello() {
        return "Hello from Trait";
    }
}

class ChildClass {
    use ExampleTrait;

    public function hello() {
        return "Hello from ChildClass";
    }
}
```

### 5. Intersection Types
**Définition :** Types introduits en PHP 8.3 qui permettent de restreindre une valeur à appartenir à plusieurs types en même temps.
```php
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
```

### 6. Méthode Abstraite dans un Trait
**Définition :** Déclaration d'une méthode sans implémentation dans un trait, obligeant les classes utilisant le trait à implémenter cette méthode.
```php
trait ExampleTrait {
    abstract public function exampleMethod();
}

class ExampleClass {
    use ExampleTrait;

    public function exampleMethod() {
        echo "Implemented method";
    }
}
```

### 7. Méthode Magique
**Définition :** Méthode spéciale définie dans une classe qui permet de modifier le comportement par défaut de certaines actions, comme l'accès aux propriétés et méthodes dynamiques.
```php
class Magic {
    public function __get($name) {
        return "Getting " . $name;
    }

    public function __set($name, $value) {
        echo "Setting " . $name . " to " . $value;
    }
}
```
