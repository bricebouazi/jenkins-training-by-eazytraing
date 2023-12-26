
##### Installation d'une VM Jenkins via vagrant

1. Sur votre poste de travail, vous devez installer les outils ```git```, ```vagrant``` et ```virtualbox```.
2. Une fois installés, ouvrez un terminal et faites un clone du [dépôt github suivant](https://github.com/diranetafen/cursus-devops.git) et déplacez vous dans le répertoire ```cursus-devops/vagrant/jenkins```
    ```bash
    git clone  https://github.com/diranetafen/cursus-devops.git 
    cd cursus-devops/vagrant/jenkins
    ```
3. Déployer la VM jenkins dans virtualbox à l'aide de  la commande suivante
    ```bash
    vagrant up jenkins --provision
    ```
4. Une fois le processus terminé et la VM opérationnelle, connectez vous à cette dernière avec la commande suivante:
    ```bash
    vagrant ssh jenkins 
    #ou encore 
    # ssh vagrant@<IP>
        user = vagrant, 
        password = vagrant
    ```
    
5. Vous êtes connectés à la VM ? Alors vous pouvez récupérer le token initial: 
    ```bash
    docker exec -it jenkins-jenkins-1 cat /var/jenkins_home/secrets/initialAdminPassword
    ```    
6. Une fois le token obtenu, continuer l'installation depuis l'interface web de Jenkins, le port par défaut est le ```8080```
   - Si vous avez des erreurs vagrant, pensez à la commande suivante
        ```bash
        vagrant global-status --prune
        ```
   -  Si l'installation des plugins tombe en erreur, vérifier à toute fin utile si  [la page de statut](https://status.jenkins.io/) de jenkins pour savoir si les serveurs de jenkins ne sont pas en erreur indisponibles