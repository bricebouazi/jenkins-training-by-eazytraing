####  Déploiement du Eazylabs
Eazylabs est un petit outil dévellopé par l'équipe **Eazytraining** afin de permettre le pilotage d'un démon docker via une API. Dans ce TP, il est question de déployer eazylabs sur votre serveur de déploiement.
[Voici](https://github.com/eazytraining/eazylabs) l'api eazylabs
Son déploiement consiste juste à lancer la commande suivante : 
```bash
docker run -d --name eazylabs --privileged -v /var/run/docker.sock:/var/run/docker.sock -p 1993:1993 eazytraining/eazylabs:latest
```

D'après la commande précédente, eazylabs sera disponible sur le port **1993** de votre machine docker
Si vous n'avez pas de machine avec docker installé, alors vous pouvez ***éventuellement*** la déployer sur la plateforme https://docker.labs.eazytraining.fr/ 
