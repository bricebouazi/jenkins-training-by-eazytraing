##### Partie 1 : Création du job pipeline dans jenkins
1. Créer un job 
    - type:  pipeline
    - nom: deployment
    - Paramètres: Toute variable débutant par PARAM_* est à déclarer comme paramètre
    - Cocher la case projet github et donner l'url du projet git
    - Dans les triggers, cocher la case "github hook trigger ..."
    - Dans Pipeline, choisir from SCM
        - donner l'url du repos git sur la branche master/main
    - Script path : Jenkinsfile
    - On save et on lance l'exécution du job

##### Partie 2 : Synchronisation jenkins/github
1. :warning: **Hors scope, à lire uniquement si votre serveur jenkins n'est pas accessible depuis une ip publique**.
   - Vous pouvez monter un tunnel à l'aide de l'outil [ngrok](https://dashboard.ngrok.com/get-started/setup)
   
      → Un compte gratuit devra être créé sur leur site
      
      → L'installation consiste simplement à télécharger le binaire
      ```bash
      wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz
      tar -xvf ngrok-v3-stable-linux-amd64.tgz
      sudo cp ngrok /bin
      ```
   - Une fois installé, récupérer votre token sur https://dashboard.ngrok.com/get-started/your-authtoken 
   - Configurer le token sur la machine votre serveur jenkins:
        ```bash
        ngrok config add-authtoken <VOTRE TOKEN>
        ```      
   - Lancer le tunnel sur le port 8080: 
      ```bash
      ngrok http 8080
      ```
   - Une URL publique vous est fournie, jenkins sera disponible à cette url        

2. Installer le plugin **github integration**
3. Configurez le **webhook** dans votre repos github 
Aller sur votre repository **alpinehelloworld** → **setting** → **webhooks**
    - **Payload URL**:  ${url de votre jenkins}:8080/github-webhook/
    - **Content type**: application/json
    - On laisse le reste
        - **Secret**: vide
        - **case Juste the push event** coché
        - **case Active** cochée
    - Cliquer sur **Add webhook** et attendre de voir que la synchro se passe bien


