# Installe et configure Active Directory server 

- Installer le rôle AD DS sur Windows Serveur 2012 R2
- Créer un domaine wilders.lan
- Explique la procédure que tu as utilisée dans une documentation qui permet de reproduire ton installation et que tu postera comme solution à cette quête

## Étapes d’Installation et de Configuration

### 1. Installation du rôle AD DS  

1. Ouvrir le Gestionnaire de serveur  
2. Cliquer sur "Ajouter des rôles et fonctionnalités"  
3. Sélectionner "Installation basée sur un rôle ou une fonctionnalité" puis "Suivant"  
4. Sélectionner le serveur concerné et cliquer sur "Suivant"  
5. Choisir "Services AD DS" et valider l’ajout des fonctionnalités requises  

### 2. Promotion du serveur en contrôleur de domaine

1. Une fois l’installation terminée, cliquer sur "Promouvoir ce serveur en contrôleur de domaine"

2. Choisir "Ajouter une nouvelle forêt" et entrer le nom du domaine : rank.fr

3. Configurer le niveau fonctionnel
    - Niveau fonctionnel de la forêt : Windows Server 2016 
    - Niveau fonctionnel du domaine : Windows Server 2016 
    - Cocher "Serveur DNS" et "Catalogue global (GC)"
    - Définir un mot de passe de restauration DSRM

4. Valider les options DNS et ignorer l’avertissement sur la délégation DNS

5. il faut maintenant indiquer l’équivalent NetBIOS pour les anciens appareils qui ne gèrent pas les noms de domaines qualifiés. Par exemple, pour « rank.fr» on pourra choisir le NetBIOS « RANK » .

6. Définir les chemins des bases de données AD
    - C:\Windows\NTDS pour la base de données
    - C:\Windows\SYSVOL pour les fichiers de réplication

7. Vérifier le résumé et cliquer sur "Installer"

8. Redémarrer le serveur après l’installation