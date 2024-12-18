##### Mise en place du serveur jenkins
L'objectif de ce TP est de mettre en place un serveur jenkins s'exécutant dans un conteneur **docker**. Pour celà, nous devons disposer d'une machine sur laquelle est installé **docker** et **docker-compose**. Le système d'exploitation sur lequel nous allons travailler est **Centos 7**

1. Installation de **Docker** sur **Centos 7**
	```bash
	curl -fsSL https://get.docker.com -o get-docker.sh
	sh get-docker.sh
	sudo usermod -aG docker centos
	sudo systemctl start docker
	systemctl enable docker
	```
	
2. Installation de [docker compose](https://docs.docker.com/compose/install/)

	```bash
	sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
	sudo chmod +x /usr/local/bin/docker-compose
	docker-compose -v
	```

3. Créer un répertoire de travail ```jenkins``` et déplacez vous dans ce répertoire
	```bash
	mkdir jenkins
	cd jenkins
	```

4. Télécharger [le fichier](https://github.com/eazytraining/jenkins-training/blob/master/TP1%20-%20Installation_de_%20jenkins/docker-compose.yml) ```docker-compose.yml```, contenu dans [ce dépot github](https://github.com/eazytraining/jenkins-training.git)
	```bash 
	wget https://github.com/eazytraining/jenkins-training/blob/master/TP1%20-%20Installation_de_%20jenkins/docker-compose.yml
	```

3. Lancer le docker-compose
	```bash
	docker-compose up -d
	```
4. vérifer que le conteneur jenkins a bien démaré: 
	```bash
	docker-compose ps
	docker ps -a
	```
5. Finaliser l'installatation via l'interface web de jenkins
	:warning: Pour recupererer le mot de passe, taper la commande suivante:
	```bash
	docker exec -it jenkins-training-jenkins-1 cat /var/jenkins_home/secrets/initialAdminPassword
	```
