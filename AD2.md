# Documentation pour la création de l'OU, du Groupe et de l'Utilisateur dans Active Directory

## Objectif

Cette procédure permet de créer une Unité d'Organisation (OU) `rank_students`, un groupe `Students` et un utilisateur dans ce groupe dans Active Directory pour le domaine `rank.fr`.

---

## Prérequis

- Active Directory installé et configuré pour le domaine `rank.fr`.
- Accès administratif à Active Directory.

---

## Étapes

### 1. Créer l'Unité d'Organisation (OU)

1. Ouvrir **Utilisateurs et ordinateurs Active Directory**.
2. Faire un clic droit sur le domaine `rank.fr`.
3. Sélectionner **Nouveau** puis **Unité d'organisation**.
4. Nommer l'OU `rank_students`.
5. Cocher l'option **"Protéger cet objet contre la suppression accidentelle"** (facultatif mais recommandé).
6. Cliquer sur **OK** pour créer l'OU.

---

### 2. Créer le Groupe d'Utilisateurs

1. Naviguer vers l'OU `rank_students`.
2. Faire un clic droit sur l'OU et sélectionner **Nouveau** puis **Groupe**.
3. Nommer le groupe `Students`.
4. Sélectionner le type **Sécurisé** et la portée **Global**.
5. Cliquer sur **OK** pour créer le groupe.

---

### 3. Créer un Utilisateur dans le Groupe

1. Faire un clic droit sur l'OU `rank_students` et sélectionner **Nouveau** puis **Utilisateur**.
2. Compléter les informations pour l'utilisateur, par exemple :
   - Prénom : Jean
   - Nom de famille : Dupont
   - Nom d'utilisateur : jdupont
3. Saisir un mot de passe et confirmer.
4. Cliquer sur **Suivant** puis **Terminer**.
5. Ajouter l'utilisateur au groupe `Students` :
   - Faire un clic droit sur l'utilisateur, puis sélectionner **Ajouter au groupe**.
   - Tapez `Students` et ajouter l'utilisateur.

