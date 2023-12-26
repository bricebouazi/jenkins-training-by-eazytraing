L'objectif de ce TP est de mettre en place des restrictions d'accès sur un utilisateur.
1. Vérifiez que le plugin  **Role-based Authorization Strategy** est installé
2. Créez un utilisateur **eazytraining**
        **Manage Jenkins** → **Security** → **Manage user** → **Add** 
3. Configurez Jenkins afin que les autorisations soient gérées par le nouveau plugin
        **Manage Jenkins** → **Security** → **Configure Global security** → **Autorisation** -→ **Role based strategy**
4. Créez un rôle avec uniquement le droit de consulter le projet **test acceptance**
   - **Manage Jenkins** → **Security** → **Manage and assign role** → **Manage role** → **Item roles** ***(rôles de projet)***
        - nom : **viewer**
        - Pattern : **test.\***
        - Permissions à cocher: **View**, **Read** et **Discover**
5. Assignez ensuite ce rôle à l’utilisateur **eazytraining**
   - **Manage Jenkins** → **Security** → **Manage and assign role** → **Assign role** → **Item roles** ***(rôles de projets)***
Rajouter votre utilisateur dans la liste et cocher le rôle en question
6. Enfin, connectez vous à jenkins avec l’utilisateur **eazytraining** pour vérifier qu’il n’a que les droits qui lui ont été conféré et qu’il ne voit que le projet **test acceptance**
:warning: Si à la connexion, vous n'avez pas les droits, il faudrait rajouter **les rôles globaux overall**
   - **Manage Jenkins** → **Security** → **Manage and assign role** → **Manage role** → **Global roles** → Rajouter votre rôle dans la liste et cocher la permission **Read**