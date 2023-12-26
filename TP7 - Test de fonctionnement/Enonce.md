##### Partie 1:  Notification dans slack
###### --- A faire sur le serveur Slack ---
1. Créer un channel privé slack
   

2. Dans les ***applications de slack***, installer l'application **jenkins-ci*, ensuite:
    a. Aller dans les setting de cette application
    b. Rajouter le channel nouvellement créé
    c. Dans la section **Paramètres d'intégration**, copier le jeton (Token)


###### --- A faire sur le serveur Jenkins --- 
1. créer un nouveau crédential pour l'accès à slack
    a. ***type***:  secret text
    b. ***valeur***: valeur credential

2. Installer le plugin **slack notification**
3. Configurez jenkins pour publier dans slack des messages dans slack:
    Aller dans **Manage jenkins** → **configure system** → **slack** 
    renseigner les informations suivantes:  
    - **workspace slack**: nom de votre channel privé slack
    - **credential**: valeur credential
    - **channel**: *#test_notif_jenkins*
    - **tester la connexion**

4. Modifier le Pipeline dans Github pour rajouter la section liée aux notifications post:

    → confer fichier **post_initial.groovy** fournit avec l'énonce.
5. Committer et le build se lancera autmatiquement
6. Vérifier que le message arrive bien dans slack


#####Partie 2 : badge de statut
###### --- A faire sur Le serveur Jenkins ---
1. Installer le plugin de gestion des badges **Embeddable Build Status**
2. Dans **Administrer Jenkins** → **Configurer la sécurité globale** → Dans la section **Autorisations**, cocher la case **Allow anonymous read access**
3. On retourne dans le job, et tout à gauche on vera apparaitre **Embeddable Build Status** .
    - On copie la balise souhaité **(Readme unprotected)**
    - On la rajoute dans le Readme du projet
    :warning: Si github a du mal à lire le badge, vérifier les autorisations d'accès dans les paramètres du serveur jenkins: **Tableau de bord** → **Configurer la sécurité globale** → **Autorisation** → Vérifier que **Allow anonymous read access** est activé

           

