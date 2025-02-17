# Démarche de configuration d'une GPO pour restreindre l'accès au Panneau de configuration pour le groupe Rank_Students

## 1. Création de la GPO "Rank"

- Ouvrir "Gestion de stratégie de groupe" (GPMC) sur un serveur ou un poste avec des outils d'administration Active Directory.
    - Appuyez sur Win + R pour ouvrir la fenêtre Exécuter.
    - Tapez gpmc.msc et appuyez sur Entrée pour ouvrir la Gestion des stratégies de groupe.
- Dans la fenêtre GPMC, cliquer avec le bouton droit sur l'unité d'organisation (OU) ou le domaine où la GPO doit être créée.

    - Créer et lier une GPO à votre domaine
Créer la GPO :
Faites un clic droit sur le domaine Rank.fr (ou sur l’OU spécifique, si vous souhaitez appliquer la GPO uniquement à une OU particulière).
Sélectionnez "Créer un objet GPO dans ce domaine et le lier ici".
Nommer la GPO :
- Choisir "Créer un objet GPO dans ce domaine et le lier ici".
- Donner un nom à la GPO, par exemple "Rank".
- Cliquer sur OK pour créer la GPO.

## 2. Modifier la GPO pour restreindre l'accès au Panneau de configuration

- Dans GPMC, sous la GPO Rank, faire un clic droit et sélectionner "Modifier".
- Dans l'éditeur de GPO qui s'ouvre, naviguer vers Configuration utilisateur > Stratégies > Modèles d'administration > Panneau de configuration.
- Double-cliquer sur "Interdire l'accès au Panneau de configuration".
- Dans la fenêtre qui s'ouvre, sélectionner Activé.
- Cliquer sur OK.

## 3. Restreindre la GPO aux utilisateurs du groupe "Students"

- Dans la GPMC, sous la GPO Rank, faire un clic droit et sélectionner "Filtrage de la sécurité".
- Cliquer sur Ajouter, puis entrer le nom du groupe Students.
- Cliquer sur délégation puis avancé 
- Sélectionner "Refuser" pour l'option "Lecture" et "Appliquer la stratégie de groupe" pour le groupe Students.
- Cliquer sur OK.

## 4. Forcer l'application de la GPO

- Ouvrir une fenêtre de commande (CMD) et exécuter la commande suivante pour forcer l’application de la GPO :
    ```bash
    gpupdate /force

## Tests effectués pour vérifier l'efficacité de la GPO

## 1. Test 1 : Vérification de l'accès au Panneau de configuration pour un utilisateur du groupe Students

    - Se connecter à un poste avec un compte d'utilisateur appartenant au groupe Students.
    - Essayer d'accéder au Panneau de configuration en cherchant dans le menu Démarrer ou via Exécuter (control).
    - Si la stratégie est appliquée correctement, l'accès au Panneau de configuration sera bloqué avec un message d'erreur disant que l'accès est restreint.

## 2. Test 2 : Vérification de l'accès au Panneau de configuration pour un utilisateur non membre du groupe Rank_Students

    - Se connecter à un poste avec un compte d'utilisateur qui n'appartient pas au groupe Students.
    - Essayer d'accéder au Panneau de configuration. L'accès devrait être autorisé, prouvant que la GPO n'affecte pas les autres utilisateurs.

