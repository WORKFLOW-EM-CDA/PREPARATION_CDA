# Ressources & liens

### Repo github avec une préconfiguration du 2fa dans `app/config/packages/scheb-2fa.yaml`
- https://github.com/scheb/2fa

### symfonycasts activating-2fa
- https://symfonycasts.com/screencast/symfony-security/activating-2fa

### symfonycasts qr-code
- https://symfonycasts.com/screencast/symfony-security/qr-code

# Guide de mis en place

### Installation de la dépendance

```sh
composer require scheb/2fa-bundle
```

### configuration dans `config/packages/scheb-2fa.yaml`

Vous pourrez partir de l'exemple du repo GitHub comme base à votre configuration (Enlever, Ajouter ce que vous avez besoin).

<details>
<summary>Exemple du fichier de configuration `config/packages/scheb-2fa.yaml`</summary>

```yaml
# See the configuration reference at https://symfony.com/bundles/SchebTwoFactorBundle/6.x/configuration.html
scheb_two_factor:

   # Trusted device feature
    trusted_device:
        enabled: true                  # If the trusted device feature should be enabled
        lifetime: 5184000              # Lifetime of the trusted device cookie
        extend_lifetime: true
        key: cc21ed8d4b2a28a1f14028428fd3b5e5scheb
        cookie_name: trusted_device    # Name of the trusted device cookie
        cookie_secure: false           # Set the 'Secure' (HTTPS Only) flag on the trusted device cookie
        cookie_same_site: "lax"        # The same-site option of the cookie, can be "lax" or "strict"

    totp:
        enabled: true                  # If TOTP authentication should be enabled, default false
        server_name: Server Name       # Server name used in QR code
        issuer: Issuer Name            # Issuer name used in QR code
        leeway: 15                     # Acceptable time drift in seconds
        parameters:                    # Additional parameters added in the QR code
            image: 'https://my-service/img/logo.png'
        template: security/2fa.html.twig   # Template used to render the authentication form

    # The service which is used to persist data in the user object. By default Doctrine is used. If your entity is
    # managed by something else (e.g. an API), you have to implement a custom persister
    persister: scheb_two_factor.persister.doctrine

    # If your Doctrine user object is managed by a model manager, which is not the default one, you have to
    # set this option. Name of entity manager or null, which uses the default one.
    model_manager_name: ~

    # The security token classes, which trigger two-factor authentication.
    # By default the bundle only reacts to Symfony's username+password authentication. If you want to enable
    # two-factor authentication for other authentication methods, add their security token classes.
    security_tokens:
        - Symfony\Component\Security\Core\Authentication\Token\UsernamePasswordToken

    # A list of IP addresses, which will not trigger two-factor authentication
    ip_whitelist:
       - 127.0.0.2 # Used for testing
```
</details>

### Implémentation des interfaces dans l'entité `User`

<details>
<summary>Exemple de l'entité User</summary>

```php
<?php

declare(strict_types=1);

namespace App\Entity;

use Doctrine\ORM\Mapping as ORM;
use Scheb\TwoFactorBundle\Model\BackupCodeInterface;
use Scheb\TwoFactorBundle\Model\Email\TwoFactorInterface as EmailTwoFactorInterface;
use Scheb\TwoFactorBundle\Model\Google\TwoFactorInterface as GoogleTwoFactorInterface;
use Scheb\TwoFactorBundle\Model\Totp\TotpConfiguration;
use Scheb\TwoFactorBundle\Model\Totp\TotpConfigurationInterface;
use Scheb\TwoFactorBundle\Model\Totp\TwoFactorInterface as TotpTwoFactorInterface;
use Scheb\TwoFactorBundle\Model\TrustedDeviceInterface;
use Symfony\Component\Security\Core\User\PasswordAuthenticatedUserInterface;
use Symfony\Component\Security\Core\User\UserInterface;
use function in_array;

#[ORM\Entity]
#[ORM\Table(name: 'user')]
class User implements UserInterface, PasswordAuthenticatedUserInterface, EmailTwoFactorInterface, GoogleTwoFactorInterface, TotpTwoFactorInterface, TrustedDeviceInterface, BackupCodeInterface
{
    private const BACKUP_CODES = [111, 222];
    public const TRUSTED_TOKEN_VERSION = 1;

    #[ORM\Column(type: 'integer')]
    #[ORM\Id]
    #[ORM\GeneratedValue(strategy: 'AUTO')]
    private int $id;

    #[ORM\Column(type: 'string', length: 25, unique: true)]
    private string $username;

    #[ORM\Column(type: 'string', length: 64)]
    private string $password;

    #[ORM\Column(type: 'string', length: 60, unique: true)]
    private string $email;

    #[ORM\Column(type: 'boolean')]
    private bool $emailAuthenticationEnabled = true;

    #[ORM\Column(type: 'integer')]
    private string|null $emailAuthenticationCode = null;

    #[ORM\Column(type: 'boolean')]
    private bool $googleAuthenticatorEnabled = true;

    #[ORM\Column(type: 'string')]
    private string|null $googleAuthenticatorSecret = null;

    #[ORM\Column(type: 'boolean')]
    private bool $totpAuthenticationEnabled = true;

    public function getId(): int
    {
        return $this->id;
    }

    public function getUsername(): string
    {
        return $this->username;
    }

    public function getUserIdentifier(): string
    {
        return $this->username;
    }

    public function getEmail(): string
    {
        return $this->email;
    }

    public function getSalt(): string|null
    {
        return null;
    }

    public function getPassword(): string|null
    {
        return $this->password;
    }

    /**
     * @return string[]
     */
    public function getRoles(): array
    {
        return ['ROLE_USER'];
    }

    public function eraseCredentials(): void
    {
    }

    /**
     * @return mixed[]
     */
    public function __serialize(): array
    {
        return [
            $this->id,
            $this->username,
            $this->password,
        ];
    }

    /**
     * @param mixed[] $unserialized
     */
    public function __unserialize(array $unserialized): void
    {
        [
            $this->id,
            $this->username,
            $this->password,
        ] = $unserialized;
    }

    public function getEmailAuthRecipient(): string
    {
        return $this->email;
    }

    public function setEmailAuthEnabled(bool $emailAuthEnabled): void
    {
        $this->emailAuthenticationEnabled = $emailAuthEnabled;
    }

    public function isEmailAuthEnabled(): bool
    {
        return $this->emailAuthenticationEnabled;
    }

    public function getEmailAuthCode(): string
    {
        return (string) $this->emailAuthenticationCode;
    }

    public function setEmailAuthCode(string $authCode): void
    {
        $this->emailAuthenticationCode = $authCode;
    }

    public function setGoogleAuthenticatorEnabled(bool $googleAuthenticatorEnabled): void
    {
        $this->googleAuthenticatorEnabled = $googleAuthenticatorEnabled;
    }

    public function isGoogleAuthenticatorEnabled(): bool
    {
        return $this->googleAuthenticatorEnabled && $this->googleAuthenticatorSecret;
    }

    public function getGoogleAuthenticatorUsername(): string
    {
        return $this->username;
    }

    public function getGoogleAuthenticatorSecret(): string
    {
        return $this->googleAuthenticatorSecret;
    }

    public function setGoogleAuthenticatorSecret(string|null $googleAuthenticatorSecret): void
    {
        $this->googleAuthenticatorSecret = $googleAuthenticatorSecret;
    }

    public function setTotpAuthenticationEnabled(bool $totpAuthenticationEnabled): void
    {
        $this->totpAuthenticationEnabled = $totpAuthenticationEnabled;
    }

    public function isTotpAuthenticationEnabled(): bool
    {
        return $this->totpAuthenticationEnabled && $this->googleAuthenticatorSecret;
    }

    public function getTotpAuthenticationUsername(): string
    {
        return $this->username;
    }

    public function getTotpAuthenticationConfiguration(): TotpConfigurationInterface|null
    {
        return new TotpConfiguration($this->googleAuthenticatorSecret, TotpConfiguration::ALGORITHM_SHA1, 30, 6);
    }

    public function isBackupCode(string $code): bool
    {
        return in_array($code, self::BACKUP_CODES);
    }

    public function invalidateBackupCode(string $code): void
    {
    }

    public function getTrustedTokenVersion(): int
    {
        return self::TRUSTED_TOKEN_VERSION;
    }
}
```
</details>

### Créer le controller qui génére le qr-code et le fichier twig qui le met en place

<details>
<summary>Exemple de controller qui génére le qr-code</summary>

```php
namespace App\Controller;

use Endroid\QrCode\Builder\Builder;
use Scheb\TwoFactorBundle\Security\TwoFactor\Provider\Totp\TotpAuthenticatorInterface;
use Sensio\Bundle\FrameworkExtraBundle\Configuration\IsGranted;
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

class SecurityController extends BaseController
{
    // ...

    /**
     * @Route("/authentication/2fa/qr-code", name="app_qr_code")
     * @IsGranted("ROLE_USER")
     */
    public function displayGoogleAuthenticatorQrCode(TotpAuthenticatorInterface $totpAuthenticator)
    {
        $qrCodeContent = $totpAuthenticator->getQRContent($this->getUser());
        $result = Builder::create()
            ->data($qrCodeContent)
            ->build();

        return new Response($result->getString(), 200, ['Content-Type' => 'image/png']);
    }
}
```
</details>

<details>
<summary>Exemple du fichier twig qui appel le controller</summary>

```twig
{% extends 'base.html.twig' %}
{% block title %}2fa Activation{% endblock %}
{% block body %}
<div class="container">
    <div class="row">
        <div class="login-form bg-light mt-4 p-4">
            <h1 class="h3 mb-3 font-weight-normal">Use Authy or Google Authenticator to Scan the QR Code</h1>
            <img src="{{ render(controller('App\\Controller\\SecurityController::displayGoogleAuthenticatorQrCode'))}}" alt="2fa QR Code">
        </div>
    </div>
</div>
{% endblock %}
```
</details>

Deux controllers sont imbriqués; l'un rend la vue, l'autre le qrcode via les fonctions Twig render(controller('')).

### Les trois type d'authentication 2fa

- email
- compte google
- totp (Time-based One-time Password)
