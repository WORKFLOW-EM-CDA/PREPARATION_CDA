
# Utilisation des Attributs en PHP

Les attributs en PHP sont définis à l'aide de la syntaxe `#[...]`. Voici comment ils peuvent être utilisés et leur importance :

1. **Ajout de métadonnées** : Les attributs permettent d'ajouter des informations supplémentaires aux éléments de code sans affecter leur comportement direct.

2. **Découplage du code** : Les attributs permettent d'ajouter des fonctionnalités supplémentaires (comme la validation ou la documentation) sans modifier le code métier.

3. **Interopérabilité** : Les attributs peuvent être utilisés par des frameworks et des bibliothèques pour configurer des comportements spécifiques, ce qui rend le code plus modulaire et flexible.

## Les attributs peuvent être appliqués à différentes cibles dans le code :

- **Déclaration des Attributs** : Les attributs sont définis à l'aide de la syntaxe `#[...]` et peuvent être appliqués aux classes, méthodes, propriétés, et constantes.
  
- **Classe Attribute** : Pour qu'une classe puisse être utilisée comme attribut, elle doit être marquée avec `#[Attribute]`.
  
- **Réflexion** : Les attributs peuvent être récupérés et utilisés via les classes de réflexion (`ReflectionClass`, `ReflectionMethod`, `ReflectionProperty`, etc.).

## Classe Validate exemple

Voici un exemple illustrant l'utilisation des attributs en PHP :

```php
#[Attribute]
class Validate {
    public string $type;

    public function __construct(string $type) {
        $this->type = $type;
    }
}

class User {
    #[Validate('email')]
    private string $email;

    public function __construct(string $email) {
        $this->email = $email;
    }

    public function getEmail(): string {
        return $this->email;
    }
}

// Récupérer les attributs via la réflexion
$reflectionProperty = new ReflectionProperty(User::class, 'email');
$attributes = $reflectionProperty->getAttributes(Validate::class);

foreach ($attributes as $attribute) {
    $instance = $attribute->newInstance();
    echo "Property 'email' should be validated as: " . $instance->type;
    // Affiche: Property 'email' should be validated as: email
}
```

### Validation plus technique

Supposons que nous voulons utiliser des attributs pour valider les données d'un formulaire :

1. **Définir les Attributs de Validation** :

    ```php
    #[Attribute]
    class NotBlank {
        public function __construct() {}
    }

    #[Attribute]
    class Length {
        public int $min;
        public int $max;

        public function __construct(int $min, int $max) {
            $this->min = $min;
            $this->max = $max;
        }
    }

    #[Attribute]
    class Email {
        public function __construct() {}
    }
    ```

2. **Utiliser les Attributs sur une Classe** :

    ```php
    class User {
        #[NotBlank]
        #[Length(3, 50)]
        public string $username;

        #[NotBlank]
        #[Email]
        public string $email;

        #[NotBlank]
        #[Length(8, 20)]
        public string $password;

        public function __construct(string $username, string $email, string $password) {
            $this->username = $username;
            $this->email = $email;
            $this->password = $password;
        }
    }
    ```

3. **Valider les Données en Utilisant les Attributs** :

    ```php
    function validate(object $object): array {
        $errors = [];
        $reflectionClass = new ReflectionClass($object);

        foreach ($reflectionClass->getProperties() as $property) {
            $property->setAccessible(true);
            $value = $property->getValue($object);

            foreach ($property->getAttributes() as $attribute) {
                $instance = $attribute->newInstance();

                if ($instance instanceof NotBlank && empty($value)) {
                    $errors[] = $property->getName() . ' should not be blank';
                }

                if ($instance instanceof Length) {
                    $length = strlen($value);
                    if ($length < $instance->min || $length > $instance->max) {
                        $errors[] = $property->getName() . " should be between {$instance->min} and {$instance->max} characters";
                    }
                }

                if ($instance instanceof Email && !filter_var($value, FILTER_VALIDATE_EMAIL)) {
                    $errors[] = $property->getName() . ' should be a valid email address';
                }
            }
        }

        return $errors;
    }

    $user = new User('', 'invalid-email', 'short');
    $errors = validate($user);

    foreach ($errors as $error) {
        echo $error . PHP_EOL;
    }
    ```

    ### Résultat

    En exécutant ce code avec l'instance `User` fournie, la sortie sera :

    ```
    username should not be blank
    email should be a valid email address
    password should be between 8 and 20 characters
    ```



