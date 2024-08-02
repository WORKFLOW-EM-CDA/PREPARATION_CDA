
# Révisions sur l'objet 

```php

// Déclaration de la classe abstraite Product
abstract class Product {
    // Propriétés protégées
    protected $name;
    protected $price;

    // Constructeur
    public function __construct($name, $price) {
        $this->name = $name;
        $this->price = $price;
    }

    // Méthode abstraite (doit être implémentée par les classes enfants)
    abstract public function getDescription();

    // Méthode concrète
    public function getName() {
        return $this->name;
    }

    public function getPrice() {
        return $this->price;
    }
}

// Classe concrète pour les produits électroniques
class Electronics extends Product {
    private $warrantyPeriod;

    // Constructeur
    public function __construct($name, $price, $warrantyPeriod) {
        parent::__construct($name, $price);
        $this->warrantyPeriod = $warrantyPeriod;
    }

    // Implémentation de la méthode abstraite
    public function getDescription() {
        return "Electronics: " . $this->name . " costs $" . $this->price . " with a warranty period of " . $this->warrantyPeriod . " months.";
    }
}

// Classe concrète pour les vêtements
class Clothing extends Product {
    private $size;

    // Constructeur
    public function __construct($name, $price, $size) {
        parent::__construct($name, $price);
        $this->size = $size;
    }

    // Implémentation de la méthode abstraite
    public function getDescription() {
        return "Clothing: " . $this->name . " costs $" . $this->price . " and is size " . $this->size . ".";
    }
}

// Utilisation des classes concrètes
$tv = new Electronics("4K TV", 499.99, 24);
$shirt = new Clothing("T-Shirt", 19.99, "M");

echo $tv->getDescription() . "\n"; // Affiche: Electronics: 4K TV costs $499.99 with a warranty period of 24 months.
echo $shirt->getDescription() . "\n"; // Affiche: Clothing: T-Shirt costs $19.99 and is size M.


# 

abstract class A {
    abstract public function getName():string ;
} 

class B extends A {
    public function getName():string {

        return "B extends A " ;
    }
}


```

## Interfaces 


```php 

// définit un comportement pour toutes les classes qui l'implémente // contrat
interface UserInterface{

    public function setAge( float $age):void ;
    public function formatAge():string ;
}

class User implements UserInterface{

    // ... d'autres méthodes 
    private float $age; 

    public function setAge( float $age):void {
        $this->age = $age;
    }
    public function formatAge():string {

        return "Age format : {$this->age} " ;
    }
} 

class SuperUser implements UserInterface{

    private int $score = 100 ;

    // ... d'autres méthodes 
    private float $age; 

    public function setAge( float $age):void {
        $this->age = $age;
    }
    public function formatAge():string {

        return "Age format : {$this->age} " ;
    }
} 


// container 
class School{

    private array $students = [];

    public function setUser( UserInterface $user) :void {
        $this->students[] = $user ;
    }

    public function allUsers():array{

        return $this->users;
    }
}

```