#####  Shared library
###### --- A faire sur Github ---
1. Créer un nouveau repos github
    - Vous pourrez le nommer **shared-library** par exemple
    - Dans ce repos, créer un répertoire ```vars``` qui contiendra un un fichier nommé ```slackNotifier.groovy``` et y rajouter à l'intérieur, le contenu du fichier ```sharable.groovy``` donné avec l'énoncé. Votre nouveau dépot git devrait ressembler à [celui ci](https://github.com/AnselmeG300/shared-library)

###### --- A faire sur Le serveur Jenkins ---        
2. Aller dans **configure system**. Chercher **sharable** dans la section **Global Pipeline Libraries** (en Anglais) et cliquer sur **add**
     - name: **shared-library**
     - version: **main**
     - source Code management: sélectionner **github** et renseigner l'URL github de la shared Library
     - Sauvegarder
3. A présent, il faut adapter le Jenkinsfile pour utiliser la librairie partagée
    Aller dans le ```Jenkinsfile``` et rajouter l'import de la shared library → fichier **import.groovy** donné avec l'enonce
Cette ligne devra être la toute première  dans le Jenkinsfile, juste avant le bloc pipeline. 
Remplacer ensuite la primitive post en fin de pipeline par le contenu du fichier **post.groovy** fourni avec l'énonce