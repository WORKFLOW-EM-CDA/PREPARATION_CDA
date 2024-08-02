# Gestion du Compteur de Visiteurs

Créer une classe `VisitorCounter` avec des méthodes statiques pour gérer un compteur global de visiteurs. La classe doit permettre d'incrémenter le compteur, de le réinitialiser et de récupérer le nombre actuel de visiteurs.

1. Créez une classe `VisitorCounter` avec une propriété statique `$count` pour stocker le nombre de visiteurs.
2. Ajoutez une méthode statique `increment()` pour incrémenter le compteur de visiteurs.
3. Ajoutez une méthode statique `reset()` pour réinitialiser le compteur de visiteurs à zéro.
4. Ajoutez une méthode statique `getCount()` pour obtenir le nombre actuel de visiteurs.

## Questions pour Aller Plus Loin

1. Comment pourrait-on rendre ce compteur persistant, par exemple, en utilisant une base de données ou des fichiers ?
1. Comment gérer la concurrence si plusieurs utilisateurs accèdent et modifient le compteur en même temps ?
1. Comment utiliser des tests unitaires pour vérifier que les méthodes statiques fonctionnent correctement ?
